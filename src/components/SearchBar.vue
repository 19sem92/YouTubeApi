<template>
 <div>
     <input @input.lazy="onInput" type="text">
 </div>
</template>

<script>
    export default {
        name: 'SearchBar',
        methods: {
            onInput(e){
                this.$emit('termChange', e.target.value)
            }
        }
    }

</script>

<style></style>
