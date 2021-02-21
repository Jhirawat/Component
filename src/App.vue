<template>
  <div id="app">
    <nav class="navbar navbar-dark bg-dark">
      <div id="nav">
        <router-link to="/User">
          <b-icon
            icon="book"
            style="width: 30px; height: 30px"
          ></b-icon>
        </router-link>
        
        <router-link to="/"> Total-Manga Shop</router-link>
      </div>
      <div>
        <router-link to="/User">
          <button
            type="button "
            class="btn btn-outline-success mr-1"
            @click="submit()"
          >
            ยืนยัน
          </button>
          <button
            type="button"
            class="btn btn-outline-danger"
            @click="cleardata()"
          >
            ยกเลิก
          </button>
        </router-link>
      </div>
    </nav>
    <router-view
      :Total="Total"
      :User="User"
      :Menuitem="Menuitem"
      :Data="Data"
      @Order="menuorder"
      @OrderAdmin="AddMenu"
    />
  </div>
</template>
<script>
export default {
  data() {
    return {
      Total: 0,
      Menuitem: [
        {
          NameProduct: "Doctor stone",
          img: 
            "https://cdn-local.mebmarket.com/meb/server1/103590/Thumbnail/book_detail_large.gif?6",
          Price: 120
        },
        {
          NameProduct: "One piece",
          img:
            "https://2.bp.blogspot.com/-2YN25cQ-7DQ/WAzIjE2K8eI/AAAAAAAAOYA/CmBAotZ5HZQ3ZfJxtPpcum00S5rgO0FdQCLcB/s1600/One%252BPiece01_001.jpg",
          Price: 90
        },
        {
          NameProduct: "Attack on titan",
          img:
            "https://images-na.ssl-images-amazon.com/images/I/81qPzeEO5IL.jpg",
          Price: 95
        },
        {
          NameProduct: "My hero academia",
          img:
            "https://images-na.ssl-images-amazon.com/images/I/51PyGPC5fXL._SX331_BO1,204,203,200_.jpg",
          Price: 89
        },
        {
          NameProduct: "มหาศึกคนชนเทพพระพุทธเจ้า",
          img:
            "https://asset.mebmarket.com/meb/server1/112386/Thumbnail/book_detail_large.gif?2",
          Price: 200
        },
        {
          NameProduct: "เกิดชาตินี้พี่ต้องเทพ",
          img:
            "https://www.phanpha.com/sites/default/files/imagecache/product_full/images01/9786163636003.JPG",
          Price: 99
        },
        {
          NameProduct: "Black Cover",
          img: 
            "https://images-na.ssl-images-amazon.com/images/I/81Qfy0poVPL.jpg",
          Price: 101
        },
        {
          NameProduct: "ดาบพิฆาตอสูร",
          img:
            "https://cdn-local.mebmarket.com/meb/server1/102020/Thumbnail/book_detail_large.gif?4",
          Price: 85
        },
         {
          NameProduct: "Darwin's game",
          img:
            "https://www.animefagos.com/wp-content/uploads/2018/10/darwingame01.jpg",
          Price: 129
        },
         {
          NameProduct: "Danganronpa the animation ",
          img:
            "https://m.media-amazon.com/images/I/517IqW2JKVL.jpg",
          Price: 44
        },
         {
          NameProduct: "Shokugeki no Soma",
          img:
            "https://www.d-ook.com/wp-content/uploads/2012/10/Shokugeki-no-Soma.jpg",
          Price: 100
        },
         {
          NameProduct: "Gleipnir",
          img:
            "https://2.bp.blogspot.com/-rDzg5z_8MLo/XwN_Ah-R_uI/AAAAAAAADCk/Pu_a5ddQhdo4dkZf8VkA3onFr36b1yZqACLcBGAsYHQ/s0/Oremanga2.jpg",
          Price: 112
        },
         {
          NameProduct: "มหาเวทย์ผนึกมาร",
          img:
            "https://images-na.ssl-images-amazon.com/images/I/71+HW7-kq2L.jpg",
          Price: 149
        },
         {
          NameProduct: "Tokyo ghoul ",
          img:
            "https://images-na.ssl-images-amazon.com/images/I/81gv-D-LqhL.jpg",
          Price: 111
        },
         {
          NameProduct: "นารูโตะ นิจาจอมคาถา",
          img:
            "http://1.bp.blogspot.com/-oH2CboRoIw0/UBRPJQiObOI/AAAAAAAAXdg/nZd2XiF6mfw/s1600/0001.jpg",
          Price: 65
        },
         {
          NameProduct: "Baki",
          img:
            "https://i0.wp.com/akibatan.com/wp-content/uploads/2016/11/donald-trump-Appearance-in-manga-baki-01.jpg?ssl=1",
          Price: 70
        },
      ],
      select: [],
      Data: []
    };
  },
  methods: {
    //คิดยอดรวมทั้งหมด
    submit() {
      this.Data = this.select;
      this.Total = 0;
      for (var i = 0; i < this.Data.length; i++) {
        this.Total = this.Total + this.Data[i].Total;
      }
    },
    cleardata() {
      this.Total = 0;
      this.Data = [{}];
      this.select = [{}];
    },
    menuorder(value) {
      this.select = value;
    },
    AddMenu(value) {
      this.Menuitem.push(value);
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #000000;
}

#nav {
  padding: 10px;
}

#nav a {
  font-weight: bold;
  color: #e98f29;
}

#nav a.router-link-exact-active {
  color: #e98f29;
}
</style>
