<template>
    <div>
        <template v-if="persona">
            <h1 v-text="datosPersona.nombre"></h1>
            <h2 v-text="datosPersona.email"></h2>
            <img v-bind:src="datosPersona.foto"></h2>
        </template>
    </div>
</template>
<script>
import axios from 'axios';

export default {
    data() {
        return {
            persona: null,
        }
    },
    mounted() {
        axios.get('https://randomuser.me/api/')
            .then((response) => {
                this.persona = response.data.results[0];
            })
            .catch();
    },
    computed: {
        datosPersona() {
            return {
                nombre: `${this.persona.name.first} ${this.persona.name.last}`,
                foto: this.persona.picture.large,
                email: this.persona.email
            }
        }
    }
}
</script>
<style lang="scss" scoped>

</style>



