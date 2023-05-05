<template>
    <div id='content' class="container">
        <h1 class="emphasize">{{page.pageTitle}}</h1>
    </div>

</template>

<script>
export default{
    props: {
        page:{
            type: Object,
            default(rawProps){
                return{
                    pageTitle:''
                }
            }
        }
    }
}
</script>
<style scoped>
.emphasize{
    color: rgb(255, 94, 0) !important;    
}
</style>