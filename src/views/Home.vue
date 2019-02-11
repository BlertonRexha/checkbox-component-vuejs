<template>
  <div class="home">
    <check-box :value="true"/>
  </div>
</template>

<script>
// @ is an alias to /src
import CheckBox from '@/components/CheckBox.vue'

export default {
  name: 'home',
  components: {
    CheckBox
  }
}
</script>
<style>
	.home{
		display: flex;
	}
</style>
