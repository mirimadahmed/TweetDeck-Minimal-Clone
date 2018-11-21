<template>
    <b-row>
        <b-col>
            <h1><b-btn v-b-modal.myModal>Config</b-btn></h1>
            <b-modal id="myModal">
                Hello From My Modal!
            </b-modal>
        </b-col>
        
    </b-row>
</template>
<script>
export default {
    name: 'ConfigCard'
}
</script>