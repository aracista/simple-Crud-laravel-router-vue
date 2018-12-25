<template>
    <div class="container">

            
                <div class="card card-default">
                    <div class="card-header" style="text-align: center;"><h3>Create new post</h3></div>

                    <div class="card-body">
                        <form action="Create_submit" method="get" accept-charset="utf-8">
                        	<div class="form-group">
                        		<input type="text" name="" value="" placeholder="Title" class="form-control">
                        	</div>
                        	<div class="form-group">
                        		<textarea rows="5" type="text" name="" placeholder="description..." class="form-control"></textarea>
                        	</div>
                        	<div class="form-group">
                        		<router-link to="/" class="btn btn-warning">Cancel</router-link>
                        		<button type="" class="btn btn-success">Create</button>
                        	</div>

                        </form>
                    </div>
                </div>
            
        
    </div>
</template>

<script>
    export default {
        mounted() {
            console.log('Component mounted.')
        }
    }
</script>
