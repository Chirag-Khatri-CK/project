<template lang="en">
    <div class="complete">
    <h1>List</h1> 
    <ul class="item" v-for="item in list" :key="item.id">
    <li>{{item.id}}</li>
    <li>{{item.title}}</li> 
    <li>{{item.body}}</li>
    </ul>
    </div>
</template>
<script>

import axios from 'axios';
export default {
    name: "List",
    data()
    {
            return {
                list:[]
            }
    },

    async mounted()

    {
        let result = await axios.get("https://jsonplaceholder.typicode.com/posts");
        console.warn(result.data)
        this.list=result.data
    }
    
};
</script>

<style>

.complete{
   background: linear-gradient(to right, #3399ff 0%, #00ffff 100%);
   font-family: "Times New Roman", Times, serif;
   font-size:20px;
   float:left;
}

.complete h1{
    border-bottom: 2px solid black; 
    margin-left: 15px;
    width: 70px;
}

.item u li{
  list-style-type: circle;
}

</style>
