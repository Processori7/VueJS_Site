<template>
  
  <div class="hello">
    <h1 class = 'change-text'>{{ msg }}</h1>
    <p class="change-text-text">
      Больше моих работ можно увидеть на
      <a href="https://igorportfolio.42web.io" target="_blank" rel="noopener">моём сайте.</a>.
    </p>

    <div class="card">
      <div class = 'box'>
  <img src="../assets/1.jpg" alt="Avatar" style="width:30%; height: 30%; border-radius: 50% 50% 50% 50%;">
  </div>
  <div class="container">
    <div class = 'box'></div>
    <h4><b class="change-text" @click="Redirect">{{name}}</b></h4>
    <p class="change-text-text">{{ text }}</p>
    <br>
    <h4 class = 'change-text' @click="show= !show">Список дел</h4>
    <ui v-if="show">
      <li v-for="work in works" :key="work" class="change-text-text"> {{ work }}</li>
    </ui>
  </div>
  </div>
</div>

</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data(){
    return{
      name: 'Игорь Усенко',
      text: 'Учиться всегда тяжело, но всегда приятно применять полученные знания.',
      bgcolor: '#1215f3',
      works: ['Учить Vue', 'Учить Express', 'Повторить CSS', 'Повторить HTML'],
      show: true
    }
  },
  methods: {
    Redirect(){
      confirm('Перейти на сайт?');
      if (confirm ==true){
        window.location.href = "https://it-mir.info";
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
  color: #f66d52;
}
a {
  color: #f01809;
}

.card {
    /* box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2); */
    max-width: 1000px;
    margin: auto;
    text-align: center;
}

/* On mouse-over, add a deeper shadow */
/* .card:hover {
    box-shadow: 0 8px 16px 0 rgba(0,0,0,0.2);
} */

/* Add some padding inside the card container */
.container {
    padding: 2px 16px;
}

.change-text{
  color: #f66d52; /* Цвет текста */
  font-size: 2em; /* Размер текста */
  font-weight: bold;
  padding: 20px 0px;
  text-transform: uppercase;
  line-height: 1;
  -webkit-transition: all 0.5s ease;
          transition: all 0.5s ease; 
}
.change-text:hover{
  color: #f1db0d; /* Меняем цвет текста */
}

.change-text-text{
  font-weight: bold;
  color: #f66d52; /* Цвет текста */
  text-transform: uppercase;
  line-height: 1;
  -webkit-transition: all 0.5s ease;
          transition: all 0.5s ease; 
}
.change-text-text:hover{
  color: #f1db0d; /* Меняем цвет текста */
}

.box {
  display: flex;
  align-items: center;
  justify-content: center;
}

.box div {
  width: 100px;
  height: 100px;
}

</style>
