<template>
    <div>
        <h1>TRELLO API</h1>
        <div>
            <label>Board Name</label>
             <input type="text" :value="trelloBoard.name">
             <label>Board description</label>
             <input type="text" :value="trelloBoard.description">
             <button  type='button'  v-on:click="storeCard()" value="send"> store</button>
            <!--<input type="text" :value="trelloList.name">
            <input type="text" :value="trelloCard.name"> -->
        </div>
    </div>
</template>
<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String,
    trelloBoard :{}
  },
  mounted(){
      this.trelloBoard = {}
     //this.storeCard()
  },
  methods: {
      storeCard(){
          console.log('sendig request')
          let description = this.trelloBoard.description || 'description defautl'
          let name = this.trelloBoard.name || 'name default'
        window.axios.post('http://127.0.0.1:8000/api/boards',{
                name: name,
                description: description
        }).then(response => {
          console.log('created')
          this.trelloBoard = response.data
          console.log(response)
      })
    }
  }
}
</script>