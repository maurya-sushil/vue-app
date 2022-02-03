<template>
    <div>
         <li class="list-item" v-for="item in items" v-bind:key="item.name">
            <p>{{item.itemName}}</p>
            <span>
                <button class="edit">Edit</button> 
                 <button class="edit">Delete</button> 
            </span>
        </li>
    </div>
</template>
<script>
export default {
    name: "ListComponent",
    data() {
        return {
            items : []
        }
    },
        methods : { 
        getData : function () {
            console.log( " list item Data", localStorage.getItem('task'))
            this.items.push(localStorage.getItem('task'))            
        }
    },
    mounted() {
        this.getData()
    },

}
</script>