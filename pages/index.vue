<template>
  <div >
  	<h1>This is app nuxt XXX</h1>
	<no-ssr>
    <v-select v-model="selected" placeholder="Seleccione una ciudad" :options="['foo','bar', 'clips']"></v-select>
	</no-ssr>
  </div>
</template>

<script >
	export default {
		data() {
			return {
				selected:''
			}
		}
	};
</script>
