<template>
  <div>
<div class="container">
  <div class="row">
    <div class="col-sm">
      <h1>GOD</h1>
      <p>
        <img v-bind:style="{width: aHero.hp*2 + 'px'}" :src="HP1" alt height="50px">
      </p>
       <p style="font-size: 200%">HP :{{aHero.hp}}</p>
      <p>
        <img style="width:400px" :src="aHero.image"/>
      </p>
      <p style="font-size: 200%">{{aHero.name}}</p>
    </div>
    <div class="col-sm">
     <button v-bind:disabled="finisd" @click="start()"> Start</button>
     <button v-bind:disabled="finisd" @click="attack()"> Attack</button>
     <button v-bind:disabled="finisd" @click="specialattack()"> Special Attack</button>
     <button @click="restart()"> Restart</button>
     <br>
     <br>  
     <br>
     <br>  
     <br>
     <br>  
     <br>
     <br>  
     <br>
     <br>  
     <br>
     <br>  
     <br> <img src="https://imgur.com/fA3VuNP.png" width="100%">
     <br>
     <br>
     <br>  
     <br>
     <br>  
     <br>
 
     <div id="end">
     <div v-if="aHunter.hp <=0">GOD IS  WINNER</div>
     <div v-else-if="aHero.hp <=0">DEMON  IS  WINNER</div>
      <br>
     <br>
     <br>  
     <br>
     <br>  
     <br> <br>
     <br>
     <br>  
     <br>
     <br>  
     <br>
    </div>
    </div>
    <div class="col-sm">
     <h1>DEMON</h1>
     <p>
        <img v-bind:style="{width: aHunter.hp*2 + 'px'}" :src="HP2" alt height="50px">
      </p>
      <p style="font-size: 200%">HP :{{aHunter.hp}}</p>
       <p>
        <img style="width:400px" :src="aHunter.image"/>
      </p>
      <p style="font-size: 200%">{{aHunter.name}}</p>
    </div>
  </div>
</div>
    
    
  </div>
</template>

<script>
export default {
  data:function() {
    return {
     
     player:[
        {name:'Phapoom',hp:80,image:"https://siamganesh.com/all_gods/brahma/brahma-dollsofindia.jpg" },
        {name:'Phanarai',hp:90,image:"https://files.gqthailand.com/uploads/p7.jpg" },
        {name:'Phasiwa',hp:100,image:"https://www.siamganesh.com/all_gods/shiva/nandi_dollsofindia.jpg" },
        {name:'Phapikhanad',hp:120,image:"https://f.ptcdn.info/530/028/000/1424164950-GANESH6720-o.jpg" },
       {name:'Phamaekhali',hp:160,image:"https://lh3.googleusercontent.com/proxy/qXuXzxK9Y5zf4TWeE-sAZo4O-sdIoKG0P2R29stswkbEkmTZnVxEFnoI1RlCgPYgvPwkNPbEPh5VKsnNyLO-vsZY4RlmDiWkXnvmvc5p6Zk1dg" },
       {name:'Phamaethoranee',hp:199,image:"https://lh3.googleusercontent.com/-qSNeiWjHT4k/XDV-B6latjI/AAAAAAAAgLQ/7Q6-RLyVpS0_ZZ5dMpgl1vmNube6bS9DwCMQCGAYYCw/s400/6qk23.gif" },
      
      ],
    Hunter:[
        {name:'Thodsakan',hp:80 ,image:"https://static.freelancebay.com/portfolios/image/2019/6/1000x1000xinside/1561693636841-123.0751953125-ea347m81xd16hylqmck5.jpg" },
        {name:'Nonthok',hp:90,image:"https://i.pinimg.com/originals/c8/e9/2a/c8e92ae37342fe8cd3e6adc82a6f898b.jpg" },
        {name:'Pipake',hp:100,image:"https://f.ptcdn.info/804/040/000/o3ta1e4bx1WeZp2P8j0-o.jpg" },
        {name:'KumPhan',hp:120,image:"https://ramakeans.files.wordpress.com/2012/03/easd8201.jpg" },
        {name:'Sammanakkha',hp:160,image:"https://fbi.dek-d.com/27/0350/0867/125345072" },
        {name:'Benyakai',hp:199,image:"https://upload.wikimedia.org/wikipedia/th/thumb/9/94/Benyakaya.jpg/250px-Benyakaya.jpg" },
        ],
         
       aHero:{name:"",HP:0,image:""},
       aHunter:{name:"",HP:0,image:""},
      A:"",
      D:"",
      HP1:"https://i.ppy.sh/bca61e3c2183a86ddb4c1d75914fab845e2b128f/687474703a2f2f692e696d6775722e636f6d2f6953766c5662432e706e67?fbclid=IwAR3HXqqNPWD_6W3OHaA9vpYY7LInoHK9GNylOSg7XHVQTzPbQYsyMINnYmY",
      HP2:"https://i.ppy.sh/bca61e3c2183a86ddb4c1d75914fab845e2b128f/687474703a2f2f692e696d6775722e636f6d2f6953766c5662432e706e67?fbclid=IwAR3HXqqNPWD_6W3OHaA9vpYY7LInoHK9GNylOSg7XHVQTzPbQYsyMINnYmY",
      finisd: false,   
    }




  },

    methods: {randomno: function (min,max) {
      return Math.max(Math.floor(Math.random()*max)+1,min);
    },
     start : function (){
       this.aHero= this.player[this.randomno(0,6)-1];
       this.aHunter= this.Hunter[this.randomno(0,6)-1];
     },
     attack : function(){
       this.A=this.randomno(2,10);
       this.aHero.hp =this.aHero.hp-this.A;
       this.D=this.randomno(2,10);
       this.aHunter.hp =this.aHunter.hp-this.D;
       if (this.aHero.hp <=0){
         this.aHero.hp =0;
         this.finisd =true;
      }else if (this.aHunter.hp <=0){
         this.aHunter.hp =0;
          this.finisd =true;
      }
     
     },
      specialattack : function(){
       this.A=this.randomno(10,15);
       this.aHero.hp =this.aHero.hp-this.A;
       this.D=this.randomno(10,15);
       this.aHunter.hp =this.aHunter.hp-this.D;
       if (this.aHero.hp <=0){
         this.aHero.hp =0;
         this.finisd =true;
      }else if (this.aHunter.hp <=0){
         this.aHunter.hp =0;
          this.finisd =true;
      }
     
     },
    restart: function () {
      window.location.reload();
    },
  },
}

</script>

<style>
#end {
  font-size: 200%;
  color: darkred;
}
</style>