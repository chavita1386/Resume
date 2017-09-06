<template>
    <div>
        <template v-if="persona">
            <h1 v-text="datosPersona.nombre"></h1>
            <h2 v-text="datosPersona.email"></h2>
            <!-- <img v-bind:src="datosPersona.foto"></h2> -->
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
        var config = {
            xhrFields: {
                withCredentials: true
            }
        }
        axios.get('http://bossinovations.com.stem.arvixe.com/api/Usuario/')
            .then((response) => {
                console.log(response);
                this.persona = response.data[0];
            })
            .catch((response) => {
                console.error(response);
            });
    },
    computed: {
        datosPersona() {
            return {
                nombre: `${this.persona.name} ${this.persona.last}`,                
                email: this.persona.email
            }
        }
    }
}
</script>
<style lang="scss" scoped>

</style>



