<template>
    <div class="mt-5">
        <b-container>
            <b-row>
                <b-col md="3">
                    <b-form-input v-model="texto" placeholder="Enter your name" :state="validar" type="text"></b-form-input>
                    <small>Minimo 3 caracteres</small>
                    <p>Texto: {{ texto }}</p>
                </b-col>
                <b-col md="3">
                    <b-form-select v-model="selected" :options="animales" :select-size="1"></b-form-select>
                    <div class="mt-3">Selected: <strong>{{ selected }}</strong></div>
                </b-col>
                <b-col md="3">
                    <b-form-radio-group v-model="radio" name="some-radios" :options="animalesRadio"></b-form-radio-group>
                    <div class="mt-3">Radio: <strong>{{ radio }}</strong></div>
                </b-col>
                <b-col md="3">
                    <b-form-checkbox-group id="checkbox-group-2" v-model="checkbox" name="flavour-2">
                        <b-form-checkbox value="orange">Orange</b-form-checkbox>
                        <b-form-checkbox value="apple">Apple</b-form-checkbox>
                        <b-form-checkbox value="pineapple">Pineapple</b-form-checkbox>
                        <b-form-checkbox value="grape">Grape</b-form-checkbox>
                    </b-form-checkbox-group>
                    <div class="mt-3">Radio: <strong>{{ checkbox }}</strong></div>
                </b-col>
            </b-row>
        </b-container>
    </div>
</template>

<script>
export default {
    name: 'Forms',
    data: function(){
        return {
            texto: '',
            selected: null,
            radio: null,
            checkbox: null,
            animales: [
                {value: null, text: 'Seleccione un animal'},
                {value: 'perro', text: 'perro'},
                {value: 'gato', text: 'gato'},
                {value: 'conejo', text: 'conejo'}
            ],
            animalesRadio: [
                {value: 'perro', text: 'perro'},
                {value: 'gato', text: 'gato'},
                {value: 'conejo', text: 'conejo'}
            ]
        }
    },
    computed: {
        validar: function(){
            return this.texto.length > 2 ? true : false
        }
    },
}
</script>