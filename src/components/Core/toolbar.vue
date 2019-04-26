<template>
    <div>
        <v-toolbar><v-toolbar-side-icon @click="nav=!nav"></v-toolbar-side-icon>
        <v-toolbar-title><router-link to="/" tag="span" style="cursor:pointer">Mercedes AMG</router-link></v-toolbar-title></v-toolbar>
        <v-navigation-drawer v-model="nav" clipped>
            <v-list>
                <v-list-tile v-for="item in items" :key="item.name" @click="">
                    <v-list-tile-action>
                        
                        <v-icon>{{item.icon}}</v-icon>
                    </v-list-tile-action>
                    <v-list-tile-content>
                        <router-link tag="span" :to="item.route">{{item.name}}</router-link>
                    </v-list-tile-content>
                </v-list-tile>
            </v-list>
        </v-navigation-drawer>
    </div>
</template>
<script>
export default {
    data(){
        return{
            items:[{name:'Dashboard',icon:'show_chart',route:'/dashboard'},{name:'Monitoring',icon:'personal_video',route:'/monitoring'}],
            nav:false
        }
    }
    
}
</script>
