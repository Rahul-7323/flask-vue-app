<script>
export default {
    data() {
        return {
            count: 0,
            disabled: true
        }
    },

   methods: {
       increment() {
           this.count++;
       }
   },
}
</script>

<template>
    <div class="container">
        <h1>This is a button</h1>
        <slot></slot>
        <button @click="increment" :style="{disabled:disabled,}">Count is: {{ count }}</button>
    </div>
</template>

<style scoped>
    .container {
        border: 2px solid grey;
        display: flex;
        flex-flow: column nowrap;
        width: 250px;
        border-radius: 20px;
        transition: all 100ms ease-out;
        margin: 20px;
        padding: 20px;
        background: white;
    }

    .container:hover {
        box-shadow: 5px 8px 10px;
        transform: scale(1.02,1.02) translateY(-10px); 
    }

    button {
        margin: 20px 0;
        height: 50px;
        border-radius: 10px;
        background-color: rgb(157, 224, 255); 
        font-size: 20px;
        font-weight: 600;
        color: rgb(59, 59, 59);
    }
    button:hover {
        background-color: rgb(108, 208, 255);        
    }
</style>