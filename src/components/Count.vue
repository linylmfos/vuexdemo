<template>
    <div>
        <h2>{{msg}}</h2> <hr/>
        <h3>{{count}}</h3>
        <p>
            <button @click="$store.commit('add',10)">+</button>
            <button @click="reduce">-</button>
        </p>
        <p>
            <button @click="addAction">+</button>
            <button @click="reduceAction">-</button>
        </p>
    </div>    
</template>
<script>
    import store from '@/vuex/store'
    import { mapState, mapMutations, mapGetters, mapActions } from 'vuex'
    export default {
        data () {
            return {
                msg: 'Hello Vuex'
            }
        },
        computed: {
            ...mapState(['count'])
    
            // count(){
            //     this.$store.getters.count
            // }
            //...mapGetters(['count'])
        },
        // mapState({
        //     count: state => state.count
        // }),
        methods:{
            ...mapMutations([  
                'add','reduce'
            ]),
            ...mapActions(['addAction','reduceAction'])
        },
        store
    }
</script>
<style scoped>
    button{width: 50px;height:40px;background: red;}
</style>

