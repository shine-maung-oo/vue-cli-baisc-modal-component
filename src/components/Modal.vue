<template>
    <div class="backdrop" @click="closemModal">
        <div class="modal" :class="{ success:theme==='success',danger:theme2==='delete' }">
            <!-- <h1>{{ header }}</h1>
            <p>{{ content }}</p> -->
            <slot/>
        </div>
    </div>
</template>

<script>
export default {
    name: 'App',
    props: 
        [
            'header','content','theme','theme2'
        ],
    methods:{
        closemModal(){
            this.$emit('close');
        }
    }    
}
</script>

<style>
    .backdrop {
        position: fixed;
        top: 0;
        background-color: rgba(0, 0, 0,0.5);
        width: 100%;
        height: 100%;
    }
    .modal{
        width: 400px;
        padding: 20px;
        margin: 100px auto;
        background-color: #fff;
        border-radius:10px;
    }
    .success{
        background-color: green;
        color: white;
    }
    .danger{
        background-color: crimson;
        color: white;
    }
</style>