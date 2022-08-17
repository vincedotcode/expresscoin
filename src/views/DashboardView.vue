<template>
    <div class="main p-60 flex justify-between">
        <div class="card rounded shadow bg-slate-500 ">
            <h3 class="text-indigo-400">{{cryptoCoins.name}}</h3>
            <p v-html="cryptoCoins.description" style="color: {cryptoCoins.color};"></p>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Dashboard',
    data() {
        return {
            cryptoCoins: [],
        }
    },
    methods: {
        doSearch: function () {
            const options = {
                method: 'GET',
                headers: {
                    'X-RapidAPI-Key': '2f2c40750bmshb883650768a7dcap195a4ajsn1969f6e68df8',
                    'X-RapidAPI-Host': 'coinranking1.p.rapidapi.com'
                }
            };

            fetch('https://coinranking1.p.rapidapi.com/coin/Qwsogvtv82FCd?referenceCurrencyUuid=yhjMzLPhuIDl&timePeriod=24h', options)
                .then(response => response.json())
                // .then(response => console.log(response))
                .then(response => this.cryptoCoins = response.data.coin)
                .then(response => console.log(this.cryptoCoins))
                .catch(err => console.error(err));
        }
    },

    mounted() {
        this.doSearch();
    }
}
</script>