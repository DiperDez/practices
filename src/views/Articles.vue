<template>
  <div class="row m-0 py-5">
    <div class="col-12 p-0 dcenter">
      <div class="col-4 p-0">
        <input type="text" class="form-control" placeholder="Enter your search." v-model="searchString">
      </div>
      <div class="col-12 p-0 dcenter justify-content-around py-5">
        <div v-for="(article, index) in filteredArticles" :key="index">
          <div class="card my-4 card-img-top p-3" style="width: 270px;">
            <img :src="article.url" alt="Article" class="w-100">
            <hr>
            <div class="card-body p-0 pt-2">
              <h6>{{article.nombre}}</h6>
              <h6>${{article.precio}}</h6>
              <div class="form-group m-0 dcenter justify-content-between pt-2">
                <button class="btn btn-sm btn-primary">Agregar al carrito</button>
                <button class="btn btn-sm btn-success">Comprar</button>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data(){
    return{
      searchString: '',
      articles: [
        {
          nombre: 'Silla Gamer',
          precio: 4000,
          url: 'https://resources.claroshop.com/medios-plazavip/mkt/5b9c288659c9b_2jpg.jpg'
        },
        {
          nombre: 'Tarjeta de vídeo',
          precio: 7000,
          url: 'https://www.cyberpuerta.mx/img/product/XL/CP-GIGABYTE-GV-N710D5-2GL-1.jpg'
        },
        {
          nombre: 'Procesador AMD Ryzen 5 2600',
          precio: 3500,
          url: 'https://www.cyberpuerta.mx/img/product/L/CP-AMD-YD2600BBAFBOX-1.jpg'
        },
        {
          nombre: 'Memoria RAM 16GB',
          precio: 3500,
          url: 'https://http2.mlstatic.com/D_NQ_NP_663630-MLA32170094257_092019-O.jpg'
        },
        {
          nombre: 'Disco Duro Western Digital 1TB',
          precio: 3500,
          url: 'https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcRS07k4Vp8hYSHOKrit0c7KRCSJPWF7t4xtVQ&usqp=CAU'
        },
        {
          nombre: 'Gabinete Aerocool',
          precio: 1000,
          url: 'https://www.cyberpuerta.mx/img/product/L/CP-AEROCOOL-A4718009156326-1.jpg'
        },
        {
          nombre: 'Disco Duro Western Digital Purple 8TB',
          precio: 6500,
          url: 'https://cdn.shopify.com/s/files/1/1933/6201/products/01_e53a8512-2b27-4644-9911-fa94f0a501bb.png?v=1572573976'
        },
        {
          nombre: 'Silla Gamer Ergonomica',
          precio: 4000,
          url: 'https://resources.claroshop.com/medios-plazavip/s2/10579/849287/5c92cae105e78-ga-sil-11-1600x1600.jpg'
        },
        {
          nombre: 'Teclado Gamer Xtreme',
          precio: 1600,
          url: 'https://www.steren.com.mx/media/catalog/product/cache/532829604b379f478db69368d14615cd/c/o/com-6490_x1_1_1.jpg'
        }
      ]
    }
  },
  computed:{
    filteredArticles(){
      let articles_array = this.articles,
          searchString = this.searchString;
      
      if(!searchString){
        return articles_array;
      }

      searchString = searchString.trim().toLowerCase();

      articles_array = articles_array.filter(item =>{
        if(item.nombre.toLowerCase().indexOf(searchString) !== -1){
          return item;
        }
      });

      return articles_array;
    }
  }
}
</script>
