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
				    <tr>
				      <td>Title disini...</td>
				      <td>deskripsi disini>>>></td>
				      <td><button type="" class="btn btn-info"><i class="fa fa-eye"></i> View</button></td>
				      <td><button type="" class="btn btn-success"><i class="fa fa-pencil-square-o"></i> Edit</button></td>
				      <td><button type="" class="btn btn-danger"><i class="fa fa-trash"></i>  Delete</button></td>
				    </tr>
				  </tbody>
			</table>
		</div>
	</div>
</template>