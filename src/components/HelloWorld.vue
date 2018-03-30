<template>
	<div>
		<table>
			<tr>
				<td>id</td>
				<td>标题</td>
				<td>内容</td>
			</tr>
			<tr v-for="i in arr">
				<td>{{i.id}}</td>
				<td>{{i.tit}}</td>
				<td>{{i.con}}</td>
        
        <button>删除</button>
			</tr>
			<!-- <button @click="add">增加</button> -->
		</table>
	</div>

</template>
<script>
	export default {
		// filters:{
		// 	return i.con.splict(9)+"..."
		// }
		created() {
				this.$http.get("http://localhost:8000/").then(e=>this.arr=e.body)
			},
			data() {
				return {
					arr:[]
				}
      }
      // methods:{
      //   add(){
      //     alert('增加了')
      //   },
      //   del(){
			// 		alert('删除了')
			// 		this.$http.post("http://localhost:8000/del",{id:e},{emulateJSON:true})
      //   }
      // }

	}
</script>

<style>

</style>