<template>
    <div class="azaz">
      <div class="name__and__input">
        <div class="nameOf">Find</div>
        <input type="search" class="search" placeholder="Поиск магазина..." v-model="search">
      </div>
      <div class="wrapper">
        <div class="result__of__search">
          <!-- <p>{{ search }}</p> -->
          <ul class="list">
            <li v-for="item in searchHandler" :key="item.id" class="name__info" style="display: flex; flex-direction: column; gap: 5px; border-bottom: 1px solid black;">
              <span>{{ item.name }}</span>
              <span style="padding-left: 10px;">{{ item.area }}</span>
            </li>
          </ul>
          <p v-if="searchHandler.length === 0">Ничего не найдено</p>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  import { dataB } from "../search.js";
  
  export default {
    data() {
      return {
        search: "",
        data: [],
      };
    },
    created() {
      this.data = dataB;
      console.log(this.data);
    },
    
    computed: {
      searchHandler() {
        return this.data.filter((item) =>
          item.name.toLowerCase().includes(this.search.toLowerCase()) ||
          item.area.toLowerCase().includes(this.search.toLowerCase())
        );
      },
    },
  };
  </script>
  
  <style>
  .list {
    display: flex;
    flex-direction: column;
    gap: 20px;
  }

  .search {
  padding: 8px;
  font-size: 16px;
  border: 1px solid #ccc;
  border-radius: 4px;
  width: 40%;
  box-sizing: border-box;
  margin-bottom: 10px;
  
}
.name__and__input{
    display: flex;
    justify-content: space-around;
    align-items: center;
    font-size: 24px;
    font-weight: 600;
}

.result__of__search{
    width: 40%;
    margin: 0 auto;
}
  </style>
  