<template>
  <div class="container my-5">
    <b-card>
      <b-card-body>
        <div class="row mt-2">
          <div class="col-5">
            <div style="width: 30rem">
              <b-carousel
                id="carousel-1"
                v-model="slide"
                :interval="4000"
                indicators
                background="#fff"
                img-width="1024"
                img-height="480"
                style="text-shadow: 1px 1px 2px #333;"

              >
                <!-- Text slides with image -->

                <b-carousel-slide v-for="img in product.image"
                                  :img-src="img"
                ></b-carousel-slide>
              </b-carousel>
              <!--        <b-img :src="product.image" fluid alt="Responsive image"></b-img>-->
            </div>

          </div>
          <div class="col-7">
            <div class="row">
              <div class="card-content__title">
                <h2 class="title is-3 ">{{ product.title }}
                  <button class="button is-small" :title="removeFromFavouriteLabel" v-show="product.isFavourite"
                          @click="removeFromFavourite(product.id)">
                <span class="icon is-small">
                  <i class="fa fa-heart"></i>
                </span>
                  </button>
                  <button class="button is-small" :title="addToFavouriteLabel" v-show="!product.isFavourite"
                          @click="saveToFavorite(product.id)">
                <span class="icon is-small">
                  <i class="fa fa-heart-o"></i>
                </span>
                  </button>
                </h2>
              </div>
            </div>
            <div class="row my-4" style="color: #00BB13;font-weight: 700">

              <p>
                <b-icon-check2></b-icon-check2>
                В наличии

              </p>
            </div>

            <div class="row">
              <div class="card-content__text">
                <p>
                  <span class="muted">Диагональ дисплея</span> : 14 дюйм <br>
                  <span class="muted">Серия процессора</span> : Intel Core i7 <br>
                  <span class="muted">Модель процессора</span> : 10710U <br>
                  <span class="muted">Объём оперативной памяти</span> : 16 гб <br>
                  <span class="muted">Объём SSD накопителя</span> : 1000<br>
                  <span class="muted">Операционная система</span> : Windows 10<br>
                </p>
              </div>
            </div>

            <div class="row my-3">
              <div class="card-content__price is-pulled-left">
                <span class="title is-3"><strong>{{ product.price }} ₸</strong></span>
              </div>
            </div>
            <div class="row my-4">
              <div class="card-content__btn is-pulled-right">
                <b-button variant="primary" class="buy-btn" v-if="!isAddedBtn" @click="addToCart(product.id)">{{
                    addToCartLabel
                  }}
                </b-button>
                <button class="button is-text" v-if="isAddedBtn" @click="removeFromCart(product.id)">{{
                    removeFromCartLabel
                  }}
                </button>
              </div>
            </div>


          </div>
        </div>

      </b-card-body>

    </b-card>


  </div>
</template>

<script>
export default {
  name: 'product_detail-id',

  validate({params}) {
    return /^\d+$/.test(params.id)
  },

  data() {
    return {
      addToCartLabel: 'Купить',
      removeFromCartLabel: 'Убрать из корзины',
      addToFavouriteLabel: 'Add to favourite',
      removeFromFavouriteLabel: 'Remove from favourite',
      product: {},
      selected: 1,
      quantityArray: []
    };
  },

  mounted() {
    this.product = this.$store.getters.getProductById(this.$route.params.id);
    this.selected = this.product.quantity;

    for (let i = 1; i <= 20; i++) {
      this.quantityArray.push(i);
    }
  },

  computed: {
    isAddedBtn() {
      return this.product.isAddedBtn;
    }
  },

  methods: {
    addToCart(id) {
      let data = {
        id: id,
        status: true
      }
      this.$store.commit('addToCart', id);
      this.$store.commit('setAddedBtn', data);
    },
    removeFromCart(id) {
      let data = {
        id: id,
        status: false
      }
      this.$store.commit('removeFromCart', id);
      this.$store.commit('setAddedBtn', data);
    },
    onSelectQuantity(id) {
      let data = {
        id: id,
        quantity: this.selected
      }
      this.$store.commit('quantity', data);
    },
    saveToFavorite(id) {
      let isUserLogged = this.$store.state.userInfo.isLoggedIn;

      if (isUserLogged) {
        this.$store.commit('addToFavourite', id);
      } else {
        this.$store.commit('showLoginModal', true);
      }
    },
    removeFromFavourite(id) {
      this.$store.commit('removeFromFavourite', id);
    }
  }
};
</script>

<style lang="scss" >

@import url('https://fonts.googleapis.com/css2?family=Open+Sans:wght@400;600;700&display=swap');

.container {
  font-family: 'Open Sans', sans-serif;
}

.card-content {
  padding: 15px 10px 15px 0;

  &__text {
    margin: 15px 0;
  }

  &__reviews {
    display: inline-block;
    width: 100%;
    margin-bottom: 10px;
  }
}

.card {
  border-radius: 0;
}

.carousel-control-prev {
  color: #000;
}

.title {
  font-weight: 700;
}

.muted {
  color: #A8A8A8;
}

.buy-btn {
  width:20rem;
  font-size: 25px;
  font-weight: 700;
}
.btn-primary{
  border-color: #0077C8;
  background-color: #0077C8;
}
</style>

