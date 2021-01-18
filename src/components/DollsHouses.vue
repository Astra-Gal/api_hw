<template lang="html">
    <div>
        <span v-if="dollshouses">
        <h3>Doll's Houses</h3>

    </span>
    <div>
        <button v-on:click="testFilter"> Test filter </button>
    </div>
        <div>
        <button v-on:click="testTruthy"> Test Truthy </button>
    </div>
    <div>
        <button v-on:click="testDollHouseTitles"> Somethinuthy </button>
    </div>
    </div>
</template>

<script>
export default {
    name: 'dolls-houses',
    props: ['dollshouses'],
    data() {
        return {
            something: null
        }
    },
    computed: {
        getDollHouseTitles: function() {
            return this.dollshouses.filter( dollshouse => dollshouse.title.match(/Dolls/gi) != null)
            }
    },
    methods: {
        testFilter: function(){
            
            console.log(this.dollshouses[0].title.match(/Dolls/gi) !== null); // true
            console.log(this.dollshouses[4].title.match(/Dolls/gi) !== null); // false
        },
        testTruthy: function() {
            console.log(this.dollshouses.filter((dollshouse) => {
                typeof dollshouse.title.match(/Doll/gi) !== -1; 
            }))
        },
        testDollHouseTitles : function() {
            this.something = this.dollshouses.filter((dollshouse) => {
                dollshouse.title.match(/Dolls/gi) !== null;
            })
            }
    }
}
</script>

<style lang="css" scoped>
h2, h3 {
    font-family: 'Antic Didone', serif;
}

</style>