<template>
  <div
    class="bg-image d-flex justify-content-center align-items-center"
    style="background-color:white"
  >
    <v-container>
      <br>
      <center><h1 style="color:#212121" class="font-weight-black" >F I L A</h1></center>
      <br>
      <v-container class="d-flex flex-wrap">
        <v-card
          class="mx-auto mb-5"
          max-width="400"
          v-for="(i, index) in productlist"
          :key="index"
        >
          <v-img class="text-black align-end" height="400px" :src="i.imageurl">
            <v-card-title>{{ i.name }}</v-card-title>
          </v-img>

          <v-card-subtitle class="pb-0">{{ i.rightText }}</v-card-subtitle>

          <v-card-text class="text--primary">
            <div style="font-size: large">{{ i.leftText }}</div>
          </v-card-text>

          <v-card-actions>
            <v-btn color="#F50057" text :to="'/detail/' + i.rightText"
              >detail</v-btn
            >
            <v-btn color="#FFCA28" @click="selected(i)"> Add </v-btn>
          </v-card-actions>
        </v-card>
      </v-container>

      <table class="table table-striped table-hover"></table>
      <v-container>
        <h2 class="font-weight-black">TOTAL {{ total() }} BAHT.</h2></v-container
      >
      <v-container grid-list-xs class="grey lighten-5">
        <router-view :key="$route.path"></router-view>
      </v-container>
    </v-container>
  </div>
</template>

<script>
export default {
  data() {
    return {
      productlist: [
        {
          name: "Fila Korea Disruptor 2 Premium",
          imageurl:
            "https://th-test-11.slatic.net/p/903471f10e8c3717774cdd9fc57e2267.jpg",
          rightText:
            "90s shoes are back! FILA Disruptor is the original Dad shoe suitable for everyday life. As they tend to have a very narrow fit for women, it is best to order one size larger. The upper material is made of high-quality leatherette, while the inside of the shoe is textile fabric. The sole is made of synthetic TPR. The tongue and heel are equipped with pull loops, and the inside of the shoe is perforated. This sneaker will look best with tight jeans but can be worn with almost any outfit.",
          leftText: "Price : 2,690฿",
          active: false,
          price: 2690,
        },

        {
          name: "Fila Disruptor 2A Chrome",
          imageurl:
            "https://cf.shopee.co.th/file/d77c6c35b0c44ee5ea72116550adeca0",
          rightText:
            "Switch up your look in the Disruptor 2A Chrome Women's Trainers featuring lace-up fastening, cushioned sole, reflective eye row detailing, and moulded metallic heal wrap for a bold look.",
          leftText: "Price : 1,495฿",
          active: false,
          price: 1495,
        },

        {
          name: "Fila NUOVO Sandal",
          imageurl:
            "https://d1a2ggqmhsoom.cloudfront.net/XjdGUDd2HeTN3Uw3aZE1y3R49Pw=/fit-in/346x500/filters:quality(90):fill(ffffff)/http://static-catalog.supersports.co.th/p/fila-4953-01978-2.jpg",
          rightText:
            "FILA Nuovo Women's Slide Slip-on Style Sandals Distinctive with a two-line upper made of synthetic materials. Embellished with FILA brand logo graphics for outstanding design. It comes with a super soft sole that provides flexible support for your feet and provides a soft, comfortable ride with every step.",
          leftText: "Price : 619฿",
          active: false,
          price: 619,
        },

        {
          name: "FILA Disruptor II Sun Reactive",
          imageurl:
            "https://d1a2ggqmhsoom.cloudfront.net/iP4vHpBUjKXTKpTRGpol_iI7aQM=/fit-in/346x500/filters:quality(90):fill(ffffff)/http://static-catalog.supersports.co.th/p/fila-8883-559901-9.jpg",
          rightText:
            "The all-time favorite FILA Disruptor II Sun Reactive Women's Casual Shoe has been refreshed to make it colorful and unique once again. The special feature of this model is that the leather upper of the shoe can change color according to the sunlight and ultraviolet rays, which is why the model name Disrupter II Sun Reactive is another item that you can enjoy. Fashion fun both indoors and outdoors.",
          leftText: "Price : 3,590฿",
          active: false,
          price: 3590,
        },
        {
          name: "FILA 2 Flag",
          imageurl:
            "https://d1a2ggqmhsoom.cloudfront.net/ZEMOk2YtN2enmtP3tilYgzF7M9w=/fit-in/346x500/filters:quality(90):fill(ffffff)/http://static-catalog.supersports.co.th/p/fila-2532-842111-1.jpg",
          rightText:
            "	FILA 2 Flag Women's Sandals Slip-on style Synthetic upper Embossed FILA branding logo on the upper. outstanding design The outsole provides traction on wet and dry surfaces. The insole is made of highly resilient EVA foam to support the foot and provide a soft, comfortable fit.",
          leftText: "Price : 690฿",
          active: false,
          price: 690,
        },
        {
          name: "FILA Disruptor II EXP",
          imageurl:
            "https://d1a2ggqmhsoom.cloudfront.net/NImNIuMiOjjlWgAjL6Y5NQrabV8=/fit-in/346x500/filters:quality(90):fill(ffffff)/http://static-catalog.supersports.co.th/p/fila-4969-159901-1.jpg",
          rightText:
            "FILA's all-time favorite FILA Disruptor II EXP Women's Casual Shoe returns with a new color scheme and layered side-overlay F FLAG logo print. Suede upper combines materials and patterns to add more cool details. The EVA sole is lightweight and provides soft cushioning.",
          leftText: "Price : 2,990฿",
          active: false,
          price: 2990,
        },
      ],
    };
  },
  methods: {
    selected: function (i) {
      i.active = !i.active;
    },
    total: function () {
      var sum = 0;
      this.productlist.forEach(function (i) {
        if (i.active) {
          sum += i.price;
        }
      });
      return sum;
    },
  },
};
</script>
