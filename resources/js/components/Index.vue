<template>
	<div class="card">
		<div class="card-header">
    		<router-link to="/create" class="btn btn-info float-right">Create New Post</router-link>
			
		</div>
		<div class="card-body">
			<table class="table table-striped">
				  <thead>
				    <tr>
				      <th scope="col">Title</th>
				      <th scope="col">Description</th>
				      <th width="110"></th>
				      <th width="110"></th>
				      <th width="110"></th>
				    </tr>
				  </thead>
				  <tbody>
				    <tr v-for="post, index in posts">
				      <td>{{post.title}}</td>
				      <td>{{post.description}}</td>
				      <td>
				      	<router-link :to="{name:'readPost', params:{id:post.id}}" class="btn btn-info"><i class="fa fa-eye"></i> Show</router-link>
				      </td>
				      <td>
				      	<router-link :to="{name:'editPost', params:{id:post.id}}" class="btn btn-success"><i class="fa fa-pencil-square-o"></i> Edit</router-link>
				      </td>
				  
				      <td><button class="btn btn-danger" v-on:click="submitPostDelete(post.id,index)"><i class="fa fa-trash"></i>  Delete</button></td>
				    </tr>
				  </tbody>
			</table>
		</div>
	</div>
</template>

<script>

export default {
  data() {
    return {
      posts: [],
      errors: []
    }
  },

  // Fetches posts when the component is created.
  created() {
    axios.get(`/posts`)
    .then(response => {
      // JSON responses are automatically parsed.
      this.posts = response.data
    })
    .catch(e => {
      this.errors.push(e)
    })

    // async / await version (created() becomes async created())
    //
    // try {
    //   const response = await axios.get(`http://jsonplaceholder.typicode.com/posts`)
    //   this.posts = response.data
    // } catch (e) {
    //   this.errors.push(e)
    // }
  },
    methods:{
  submitPostDelete(id, index) {
  	if (confirm("Clock 'Ok' to Delete.")){
    axios.delete(`/posts/` + id)
    .then(response => {
      // JSON responses are automatically parsed.
      console.log(response)
      this.posts.splice(index, 1);
    })
    .catch(e => {
      this.errors.push(e)
    })

    // async / await version (created() becomes async created())
    //
    // try {
    //   const response = await axios.get(`http://jsonplaceholder.typicode.com/posts`)
    //   this.posts = response.data
    // } catch (e) {
    //   this.errors.push(e)
    // }
    }
    }
  }
}
</script>