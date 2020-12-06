<template>
    <div>
        <div v-if="count===1">
            {{greet}}
        </div>
        <div>
            <input v-model="greet" type="text"/>
        </div>
    </div>
</template>

<script>
export default {
    name: 'directives',
    data(){
        return {
            count: 1,
            greet: 'Hello vue'
        }
    }
}
</script>