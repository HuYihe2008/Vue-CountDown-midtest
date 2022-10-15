<template>
    <div class="news">
        <p>{{testdate}}</p>
    </div>
</template>

<script>

export default {
    data() {
        return{
            testdate: '',
            notise: ''
        }
    },
    mounted() {
        this.getList()
    },
    methods: {
        getList() {
          this.axios.get('http://api.jamyido.top/admin-version.json').then((response) => {
            console.log(response.data)
            this.testdate = response.data.cheek.version
          })
          // or
         /*this.$http.get(api).then((response) => {
           console.log(response.data)
          })*/
        }
  }

}
</script>

<style>
.news {
    position: relative;
    z-index: 9;
}
p {
    font-size: 200px;
}
</style>