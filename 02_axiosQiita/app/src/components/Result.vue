<template>
  <div>
    <ul class="list">
      <li class="item" v-for="item of sortedItemsByLikes" :key="item.title">
        <a v-bind:href="item.url">
          <div class="item-inner">
            <div class="photo">
              <img class="photo-img" src="https://pbs.twimg.com/profile_images/748042935124492288/knHIR7XC.jpg" alt="item.title" />
            </div>
            <div class="content">
              <p><a class="title" target="_blank">{{ item.title }}</a></p>
            </div>
            <span class="good">{{ item.likes_count }}</span>
          </div>
        </a>
      </li>
    </ul>
    <Loading class="loading" v-show="loadProgress"></Loading>
  </div>
</template>

<script>
import Loading from '@/components/Loading';

export default{
  props: ["items", "loadProgress"],
  components: {
    Loading
  },
  methods: {
    // getYear(dateStr) {
    //   const date = new Date(dateStr)
    //   return date.getFullYear()
    // },
  },

  computed:{
    // reverseItems() {
    //   return this.items.slice().reverse();
    // },
    sortedItemsByLikes(){
      return this.items.sort((a, b) => {
        return (a.likes_count < b.likes_count) ? 1 : (a.likes_count > b.likes_count) ? -1 : 0;
      })
    }
  }
}
</script>

<style scoped>
.item{
  padding: 20px 0;
  text-decoration: none;
  -webkit-transition: 0.2s ease-in-out;
  -moz-transition: 0.2s ease-in-out;
  -o-transition: 0.2s ease-in-out;
  transition: 0.2s ease-in-out;
}

.item:nth-of-type(even){
  background-color: #f5f5f5;
}

.item:hover{
  border: solid 5px #35495e;
}

.item-inner{
  display: flex;
  width: 90%;
  max-width: 800px;
  margin: auto;
}

.photo{
  flex: 0 0 150px;
}

.photo-img{
  width: 50%;
  display: block;
}

.content{
  flex: 1 1;
  padding-left: 20px;
}

.title {
  color: #42b883;
  font-size: 1.5rem;
  font-weight: 700;
  text-decoration: none;
}

.good{
  display: flex;
  color: #42b883;
  font-size: 4rem;
  font-weight: 900;
  justify-content: center;
  align-items: center;
  padding-left: 4rem;
}
</style>
