<script setup lang="ts">
import {useDataStore} from "~/stores/data";

const route = useRoute()
const dataStore = useDataStore();
const user = dataStore.items[0]
const router = useRouter()
</script>

<template>
<h1>tem</h1>
</template>