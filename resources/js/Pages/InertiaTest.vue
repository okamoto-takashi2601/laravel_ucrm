<script setup>
import { Link } from '@inertiajs/inertia-vue3';
import { ref } from 'vue'

const newTitle = ref('')
const newContent = ref('')

</script>

<template>
<a href="/"> a tag</a>
<br>
<Link href="/"> link 経由です</Link>
<br>
<Link :href="route('inertia.index')"> name route test</Link>
<br>
<Link :href="route('inertia.show',{id : 50})"> route parameter test</Link>
<div class="mb-8"></div>
<input type="text" name="newTitle" v-model="newTitle">{{ newTitle }}<br>
<input type="text" name="newContent" v-model="newContent">{{ newContent }}<br>
<Link as="button" method ="post" :href="route('inertia.store')" 
:data="{
    title : newTitle,
    content : newContent
}">DB保存テスト</Link>
</template>