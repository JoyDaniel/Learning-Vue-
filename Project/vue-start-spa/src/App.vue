<template>
    <navbar 
        :pages="pages"
        :active-page="activepage"
        :nav-link-click="(index) => activepage=index"
   ></navbar>    
   <page-viewer :page="pages[activepage]"></page-viewer>
</template>

<script>

import Navbar from './components/Navbar.vue';
import PageViewer from './components/PageViewer.vue';


export default {
    components:{
        PageViewer, 
        Navbar
    },
    data(){
        return {
            activepage:0,
            pages:[    
                {
                    link: {text:'Home', url:'Home.html'}, 
                    pageTitle: 'Home Page'
                },
                {
                    link: {text:'About', url:'About.html'}, 
                    pageTitle: 'About page'
                },
                {
                    link: {text:'Contact', url:'Contact.html'}, 
                    pageTitle: 'Contact page'
                }
            ]
        };
    }
}
</script>