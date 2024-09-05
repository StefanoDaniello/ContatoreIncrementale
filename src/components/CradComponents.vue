<template>
    <!-- La key aiuta Vue a identificare in modo univoco gli elementi in un ciclo v-for. 
    Ed usa la chiave per sapere quale elemento specifico cambiare-->
    <div v-for="(card, index) in props" :key="index">
      <h2>{{ card.name }}</h2>
      <p>{{ card.sottotitolo }}</p>
      <p>{{ index }}</p>
    </div>
</template>

<script>
// Array: Viene iterato nel componente figlio, consentendo di mostrare più dati (oggetti, stringhe, ecc.).
// Stringa: Viene trattata come un singolo valore e viene mostrata direttamente come testo, senza necessità di iterare su di essa.
// Oggetto come prop: Se preferisci passare un oggetto che contenga più proprietà, puoi farlo e accedere alle proprietà individuali dell'oggetto nel componente figlio.
    export default {
        props:{
            props: Array
        },
        name: 'CradComponents',
        data() {
            return {
                
            }
        }
    }
</script>

<style lang="scss" scoped>

</style>