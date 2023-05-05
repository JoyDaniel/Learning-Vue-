<template>
    <navbar 
        :pages="pages"
        :active-page="activepage"
        :nav-link-click="(index) => activepage=index"
   ></navbar>
   
   <div v-show="false">
        hide this...
   </div>
   
   <page-viewer 
   v-if="pages.length > 0"
   :page="pages[activepage]"></page-viewer>
</template>

<script>

import Navbar from './components/Navbar.vue';
import PageViewer from './components/PageViewer.vue';


export default {
    components:{
        PageViewer, 
        Navbar
    },
    created(){
        this.getPages();
    },
    data(){
        return {
            activepage:0,
            pages:[]
        };
    },
    methods:{
        async getPages(){
            let res =  await fetch('pages.json');
            let data= await res.json();

            this.pages = data;

        }
    }
}
</script>