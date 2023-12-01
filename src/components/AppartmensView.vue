<template>
    <div class="text">
        <div v-for="(item, index) in items" :key="index" class="block" @mouseover="hover(item.ids)" @mouseleave="unhover(item.ids)">{{ item.name }}</div>
    </div>
  </template>
  
  <script>
  export default {
    data(){
        return {
            items: [
                {
                    name: 'Туалет',
                    ids: ['use651']
                },
                {
                    name: 'Лифт',
                    ids: ['use363','use278','use359']
                },
                {
                    name: 'Лестница',
                    ids: ['use373','use367','use369','use365']
                },
                {
                    name: 'Эскаватор',
                    ids: ['use663','use657']
                },
                {
                    name: 'Банкомат',
                    ids: ['text1150']
                },
                {
                    name: 'Информация',
                    ids: ['use351','use371']
                },
                {
                    name: 'Гардероб',
                    ids: ['use353',]
                },
                {
                    name: 'Материнская комната',
                    ids: ['use351',]
                },
                {
                    name: 'Инвалиды',
                    ids: ['use355',]
                },
                
            ]
            
        }
    },
    methods: {
      hover(ids) {
        // alert(id)
        // this.$emit('changeSvgColor', id);
        for (let i = 0; i < ids.length; i++) {
            document.querySelector(`#${ids[i]}`).style.opacity = "0.2";
            
            
        }
        
      },
      unhover(ids) {
        // alert(id)
        // this.$emit('changeSvgColor', id);
        for (let i = 0; i < ids.length; i++) {
            document.querySelector(`#${ids[i]}`).style.opacity = "1";
        }
        
      }
    }
  };
  </script>
  
  <style scoped>
 .text{
    display: flex;
    flex-direction: column;
    gap: 20px;
 }

 .block{
    font-size: 18px;
 }
 .block:hover{
    color: yellow;
    cursor: pointer;
 }
  

  
  </style>