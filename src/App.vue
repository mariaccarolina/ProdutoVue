<script setup>
import Produtos from "./Components/Produtos.vue"
import { ref } from "vue";
import ProdutosVue from "./Components/Produtos.vue";
const carrinho = ref(0);

function adicionar() {
  carrinho.value++;
}

function remover() {
  if (carrinho.value > 0) {
    carrinho.value--;
  }
}
</script>

<template>
   <Produtos/>
  <main>
    <section class="card">
      <figure>
        <img src="./assets/ShoppingCart.png" alt="carrinho" />
        <figcaption>Adicione ao carrinho</figcaption>
      </figure>
      <div class="btn">
        <!-- pegar o evento de click v-on:click="adicionar" -->
        <button @click="adicionar">+</button>
        <h3>{{ carrinho }}</h3>
        <button @click="remover">-</button>
      </div>
    </section>
  </main>
</template>

<style lang="scss">
main{
  display: flex;
  justify-content: space-around;
}
@mixin flex{
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  align-items: center
}
  .card{
    @include flex();
    background-color: #F7E0CE;
    width: 40vw;
    height: 40vh;
    border-radius: 30px;

    figure{
      background-color: #D3C5BB;
      padding: 30px;
      border-radius: 20px;
      text-align: center
    }

    div{
      @include flex();
      flex-direction: row;
      width: 40%;
      border-radius: 20px;
      padding: 10px;
      background-color: #D3C5BB;

      button{
        border: solid 2px;
        padding: 2px 4px;
        border-radius: 50%;
      }
    }
  }

</style>