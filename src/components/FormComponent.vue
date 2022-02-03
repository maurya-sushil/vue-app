<template>
    <form>
        <input type="text" v-model="itemData.itemName" placeholder="Add a new task">
        <button type="submit" v-on:click="addItem">Add</button>
    </form>
</template>

<script>

export default {
    name : 'FormComponent',
    data() {
        return {
            itemData : {
                'itemName' : "",
            },
            itemList: []
        }
    },
    methods: {
    addItem : function (e) {
            e.preventDefault();
            this.itemList.push(JSON.stringify({"itemName" : this.itemData.itemName }))
            console.log(typeof(localStorage.getItem('task')))
            localStorage.setItem("task", JSON.stringify(this.itemList));
        }
    },
}
</script>