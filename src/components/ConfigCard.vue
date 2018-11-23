<template>
    <b-row id='ConfigBar'>
        <b-col>
            <div id='ConfigLogo'>
                <b-img src="http://www.transparentpng.com/download/twitter/twitter-pictures-image-17.png" height='50px' />
            </div>
            <h5>Edit Layout</h5>
            <b-form-group horizontal v-for='(col, i) in cols' :key="i" :label='col' :label-cols="6">
                <b-form-input id="input_sm" size="sm" v-model="lengths[i]"></b-form-input>
            </b-form-group>
            
        </b-col>
    </b-row>
</template>
<script>
export default {
    name: 'ConfigCard',
    props: {
        cols: {
            type: Array,
        }
    },
    data () {
        return {
            lengths: ['30', '30', '30']
        }
    },
    mounted () {
        if (localStorage.getItem('lengths')){
            this.lengths = JSON.parse(localStorage.getItem('lengths'));
        }
    },
    watch: {
        lengths () {
            this.$emit('lengths', this.lengths);
            const parsed = JSON.stringify(this.lengths);
            localStorage.setItem('lengths', parsed);
        }
    }
}
</script>

<style scoped>
#ConfigBar {
    margin-top:10px;
    color: #1da1f2;
}

#ConfigLogo{
    margin-bottom: 10px;
    text-align: center;
}
</style>
