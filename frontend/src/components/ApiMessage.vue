<script>
    export default{
        data() {
            return {
                message: null,
            }
        },
        mounted(){
            setInterval(() => {
                fetch("http://127.0.0.1:5000/")
                .then(resp => {
                    if(!resp.ok){
                        throw new Error("Some Error", resp.status)
                    }
                    return resp.json()
                })
                .then(data => {
                    console.log(data);
                    if(this.message != data.message)
                        this.message = data.message;
                })
                .catch(err => {
                    console.log(err);
                    this.message = "some error in the api...."
                })
            },1000)
        }
    }
</script>

<template>
<h1>Message from the api: {{ message }}</h1>
</template>