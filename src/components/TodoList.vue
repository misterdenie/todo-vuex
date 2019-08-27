<template>
    <ul>
      <li v-for="item in items" :key="item.time">
        <button @click="done(item.time)">Done</button> {{item.text | caplitalize }}
      </li>
    </ul>
</template>

<script>
export default {
    name : 'TodoList',
    props: {
        items: {
            type : Array
        }
    },
    filters: {
    caplitalize (val){
        return val.toUpperCase()
        }
    },
    methods: {
        ItemDone(id) {
          this.$emit('onItemDone',id)
        }
    }
}
</script>

<style>

</style>