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

   <create-page
        @page-created="pageCreated"
   ></create-page>
</template>

<script>

import Navbar from './components/Navbar.vue';
import PageViewer from './components/PageViewer.vue';
import CreatePage from './components/CreatePage.vue';

export default {
    components:{
        PageViewer, 
        Navbar,
        CreatePage
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
        },
        pageCreated(pageObj){
           this.pages.push(pageObj);
        }
    }
}
</script>