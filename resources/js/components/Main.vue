<template>
    <main>
        <ul>
            <li v-for="post in posts" :key="post.id">
                {{post.title}}
            </li>
        </ul>
    </main>
</template>

<script>
export default {

    name : 'Main',
    components : {},
    props : {
        posts : Array,
    }

}
</script>

<style>

</style>