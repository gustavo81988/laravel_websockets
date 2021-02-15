<template>
    <div class="container">
        <h1>{{coordenadas}}</h1>
    </div>
</template>

<script>
    export default {
        data: function () {
            return {
                coordenadas: []
            }
        },
        mounted() {
            Echo.channel('test')
            .listen('Test', (e) => {
                this.coordenadas = e
                console.log(e)
                console.log('ok')
            })
            console.log('Component mounted.')
        }
    }
</script>
