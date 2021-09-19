<template>
    <section class="name-list">
        <div class="name" v-for="(content,i) in saved.slice().reverse()" :key="i">
            <div class="name-content">
                {{ content.name }} - {{content.age}} vjeq
            </div>
        </div>
    </section>
</template>


<script>
export default({
    props: ['saved','name','age']
})
</script>



<style lang="scss" scoped>
    .name-list{
        padding:32px;
        max-width: 720px;
        margin: 0 auto;
    .name{
        background-color: var(--light);
        padding:16px;
        border-radius:16px;
        margin-bottom: 16px;
     &-content{
         overflow: hidden;
         text-overflow: ellipsis;
         white-space: nowrap;
         line-height: 18px;
         max-height: 18px;
     }
     &:hover{
         .name-content{
             white-space: unset;
             max-height: unset;
         }
     }
    }
    }
</style>