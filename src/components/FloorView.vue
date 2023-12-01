<template>
    <div>
      <div id="bimbimbambam" v-if="selectCard.id == ''" style="background: transparent;"></div>
        <div id="bimbimbambam" v-else style="position: absolute; width: 200px; height: auto; background: white; border-radius: 5px">
            <div class="wrapper">
                <img :src="selectCard.logo" alt="" style="padding: 15px;">
                <div class="info__about__shop">
                    <div id="name">{{ selectCard.name }}</div>
                    <div id="kategory">{{ selectCard.kategory }}</div>
                    <div id="works__time">{{ selectCard.works__time }}</div>
                    <a id="link" :href="selectCard.link">{{ selectCard.link }}</a>
                </div>
            </div> 
        </div>
        
      
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        elements: [
          {
            id: "#a15",
            textId: "#text497",
            logo:  require("../assets/25_50.png"),
            name: "Di Murano",
            kategory: "Подарки, сувениры, Товары для дома",
            works__time: "с 10:00 до 22:00",
            link: "Dimurano.org",
          },
          {
            id: "#a14",
            textId: "#text469",
            logo: require("../assets/25_103.png"),
            name: "RODIS",
            kategory: "Подарки, сувениры, ювелирные изделия, часы",
            works__time: "с 10:00 до 22:00",
            link: "Atrodis.ru",
          },
          {
            id: "#a13",
            textId: "#text493",
            logo: require("../assets/25_113.jpg"),
            name: "TARUTIN",
            kategory: "Для женщин, Для мужчин, Подарки, сувениры, Ювелирные изделия, часы",
            works__time: "с 10:00 до 22:00",
            link: "www.tarutin.ru",
          },
          {
            id: "#a11",
            textId: "#text485",
            logo:  require("../assets/25_89.jpg"),
            name: "Галерея Михайлов",
            kategory: "Ювелирные изделия, часы",
            works__time: "10:00 - 22:00",
            link: "Vmikhailov.com",
          },
          {
            id: "#a12",
            textId: "#text481",
            logo:  require("../assets/25_89.jpg"),
            name: "Gourji",
            kategory: "Для женщин, Для мужчин, Подарки, сувениры, Ювелирные изделия, часы",
            works__time: "с 10:00 до 22:00",
            link: "Gourji.ru",
          },
          {
            id: "#a10",
            textId: "#text489",
            logo:  require("../assets/25__111.jpg"),
            name: "Визион",
            kategory: "Красота и здоровье, Оптика, Услуги, сервисы",
            works__time: "10:00 - 22:00",
            link: "Vizion-optika.ru",
          },
        ],
        selectCard: {
          name: "",
          kategory: "",
          logo: "",
          works__time: "",
          link: "",
        },
      };
    },
    methods: {
      initID(item) {
        let tag = document.querySelector(item.id);
        tag.addEventListener("mousemove", (event) => {
          console.log(event);
          tag.style.opacity = "0.5";
  
          document.querySelector("#bimbimbambam").style.left = event.clientX + 10 + "px";
          document.querySelector("#bimbimbambam").style.top = event.clientY + 10 + "px";
          document.querySelector("#bimbimbambam").style.opacity = 1;
  
         
          this.selectCard = { ...item };
        });
  
        let tagText = document.querySelector(item.textId);
        tagText.addEventListener("mousemove", (event) => {
          console.log(event);
          tag.style.opacity = "0.5";
  
          document.querySelector("#bimbimbambam").style.left = event.clientX + 10 + "px";
          document.querySelector("#bimbimbambam").style.top = event.clientY + 10 + "px";
          document.querySelector("#bimbimbambam").style.opacity = 1;
          
          
          
  
         
          this.selectCard = { ...item };
        });
  
        tag.addEventListener("mouseout", (event) => {
          console.log(event);
          tag.style.opacity = "1";
          tag.style.zindex = "0"
  
          document.querySelector("#bimbimbambam").style.left = 0 + "px";
          document.querySelector("#bimbimbambam").style.top = 0 + "px";
          document.querySelector("#bimbimbambam").style.opacity = 0;
  
         
          this.selectCard = {
            name: "",
            kategory: "",
            works__time: "",
            link: "",
          };
        });
      },
    },
    mounted() {
      for (let i = 0; i < this.elements.length; i++) {
        this.initID(this.elements[i]);
      }
    },
  };
  </script>
  
  <style>
  #bimbimbambam {
  position: absolute;
  width: 200px;
  height: auto;
  background: white;
  border-radius: 5px;
  opacity: 0;
  
}
  .wrapper {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    
    
  }
  
  .info__about__shop {
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    margin-top: 15px;
    padding: 15px;
    gap: 13px;
  }

  #link{
    color: yellow;
    text-decoration: none;
  }
  </style>

  