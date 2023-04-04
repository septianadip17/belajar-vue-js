<template>
    <div class="container">
        <h1 class="title">To-Do</h1>
        <form class="form">
            <input type="text" v-model="input">
            <button type="button" @click="addList">Submit</button>
        </form>
        <ul class="list">
            <li v-for="(item, index) in list" :key="index">
            {{ item.title }} <span class="delete" @click="deleteList(index)">Hapus </span>
            </li>
        </ul>
    </div>
</template>

<script>
export  default{
    data:function() {
        return{
            list: [
                {
                    title: "menyapu"
},
                {
                    title: "cuci piring"
                },
                {
                    title: "pel"
                },
            ],
            input : " "
        }
    },
    mounted() {
        console.log( 'Component mounted.' )
    },
    methods: {
        addList(){
            let newList = {
                title : this.input
            }
            this.list.push(newList)
            this.input = null;
        },
        deleteList(index){
            this.list.splice(index, 1)
        }
    },

}
</script>