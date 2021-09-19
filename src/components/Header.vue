<template>
    <header>
        <h1> <span class="red">{{ name }}</span> ngjan me moshën  <span class="red">{{ age }} </span></h1>
    </header>

</template>

<script>
export default {
    props: ['name','age']
}
</script>

<style lang="scss" scoped>
    .red{
        color:var(--primary);
    }
    header{
        padding: 24px 32px;
        display: flex;
        justify-content: center;
    }
    h1{
        font-size: 32px;
        color: var(--dark);
        font-weight: 700;
        text-align: center;
        text-transform: uppercase;
        padding-bottom: 8px;
        border-bottom: 5px solid var(--primary);
    }
</style>