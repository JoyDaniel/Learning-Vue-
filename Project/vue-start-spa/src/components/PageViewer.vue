<template>
    <div id='content' class="container">
        <h1 class="emphasize">{{page.pageTitle}}</h1>
    </div>

</template>

<script>
export default{
    props: ['page']
}
</script>
<style scoped>
.emphasize{
    color: blue !important;    
}
</style>