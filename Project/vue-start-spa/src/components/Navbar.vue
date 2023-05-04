<template>
    <nav
        :class="[`navbar-${theme}`, `bg-${theme}`, 'navbar', 'navbar-expand-lg']">
         <div class="container-fluid">
            <a class="navbar-brand" href="#">My Vue</a>
            <ul class="navbar-nav me-auto mb-2 mb-lg-0">
                <li v-for="(page, index) in pages" class="nav-item" :key="index">
                    <a class="nav-link" 
                    :class="{active: activepage==index}" aria-current="page" 
                    :href="page.link.url"
                    :title="`This link goes to ${page.link.text} page`" 
                    @click.prevent="navLinkClick(index)">{{page.link.text}}</a>
                </li>
            </ul>
            <form class="d-flex">
                <button
                    class="btn btn-primary" 
                    @click.prevent="changeTheme()">ToggleNavBar
                </button>
            </form>
        </div>
    </nav>  <!-- End of Navigation Bar -->
</template>

<script>
export default{
            props: ['pages', 'activepage', 'navLinkClick'],
            data(){
                return{
                    theme: 'dark'
                }
            },
            methods:{
                changeTheme(){
                    let theme='light';
                    if(this.theme == 'light'){
                        theme='dark'
                    }
                    this.theme = theme;
                }
            }
        }

</script>