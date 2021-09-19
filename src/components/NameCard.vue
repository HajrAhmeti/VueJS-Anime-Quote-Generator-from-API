<template>
    <div class="container">
        <div class="card">
            <div class="name">
                {{ name }}
            </div>
            <div class="age">
                {{ age }}
            </div>
            <div class="count">
                {{ count }}
            </div>
        </div>
    </div>
</template>



<script>
import 'bootstrap/dist/css/bootstrap.css'

export default {
    props: ['name','age','count']

}
</script>

<style lang="scss">

</style>