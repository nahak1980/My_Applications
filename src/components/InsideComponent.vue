<template>
    <div>
        <cat-list></cat-list>
    </div>
</template>
<script>

Vue.component('cat-list',{
    props: ['cats'],
    template:
    <ul>
        <li>cat</li>
    </ul>
})

export default {
    components: [
        'cat-list'
    ],
    data(){
        return{
            cat: [
                'LULU',
                'MEW'
            ]
        }
    }
}
</script>