    <template>
    <div>
        <ul>
            <!-- <list-item v-for="(beer, index) in beers" :beers="beers" :key="index"></list-item> -->
        </ul>
    </div>
    </template>

    <script>
    // import ListItem from './'
    export default {
    name: 'beer-list',
    data(){
        return {
            beers: {}
            
        }
    },
    props: ['beers'],
    components: {
        // "list-item": ListItem
    },
    methods: {

    }
    }
    </script>

    <style>
    </style>