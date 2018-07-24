<template>
    <div>
        hi iam a component
        {{myTitle}}
        {{categories}}
    </div>
</template>

<script>
import axios from 'axios';
export default {
    props:['myTitle'],
    data(){
        return {
            categories:''
        }
    },
    created(){
        axios.get('http://api.ar5ss.com/category')
        .then(res => {
            console.log(res);
            this.categories=res.data;
        })
        .catch( e => console.log(e));
    }
}
</script>

<style>

</style>
