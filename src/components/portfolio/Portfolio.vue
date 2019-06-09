<template>
    <div>
        <app-stock v-for="stock in stocks" :key="stock.id" :stock="stock"></app-stock>
        <div class="panel-body alert alert-warning"  role="alert" v-if="stocks.length == 0">
            No Stock Bought!      
        </div>
    </div>
</template>

<script>

import {mapGetters} from 'vuex';
import Stock from './Stock.vue'
export default {
    computed: {
        ...mapGetters({
            stocks: 'stockPortfolio'
        })
    },
    components: {
        appStock: Stock
    }
}
</script>

