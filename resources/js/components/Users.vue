<template>
    <div class="container">        
       <div class="row" mt-5>
        <div class="col-12">
          <div class="card">
            <div class="card-header">
              <h3 class="card-title">Users Table</h3>

              <div class="card-tools">
                <div class="input-group input-group-sm" style="width: 150px;">
                <button class="btn btn-success" data-toggle="modal" data-target="#addUser">Create User <i class="fa fa-user fa-fw"></i></button>
                  
                </div>
              </div>
            </div>
            <!-- /.box-header -->
            <div class="box-body table-responsive no-padding">
              <table class="table table-hover">
                <tbody><tr>
                  <th>ID</th>
                  <th>Name</th>
                  <th>Email</th>
                  <th>Type</th>
                  <th>Modify</th>
                </tr>
                <tr>
                  <td>183</td>
                  <td>John Doe</td>
                  <td>11-7-2014</td>
                  <td><span class="label label-success">Approved</span></td>
                  <td><a href="#"><i class="fa fa-edit text-blue"></i></a> <a href="#">/<i class="fa fa-trash text-red"></i></a></td>
                </tr>
                
              </tbody></table>
            </div>
            <!-- /.box-body -->
          </div>
          <!-- /.box -->
        </div>
      </div>

            <!-- Modal -->
        <div class="modal fade" id="addUser" tabindex="-1" role="dialog" aria-labelledby="addUserlLabel" aria-hidden="true">
        <div class="modal-dialog modal-dialog-centered" role="document">
            <div class="modal-content">
            <div class="modal-header">
                <h5 class="modal-title" id="exampleModalLabel">Add User</h5>
                <button type="button" class="close" data-dismiss="modal" aria-label="Close">
                <span aria-hidden="true">&times;</span>
                </button>
            </div>
            <div class="modal-body">
                <div class="form-group">
                    <label>Name</label>
                    <input v-model="form.name" type="text" name="name"
                      placeholder="Name"  class="form-control" :class="{ 'is-invalid': form.errors.has('name') }">
                    <has-error :form="form" field="name"></has-error>
                </div>
                <div class="form-group">
                    <label>Email</label>
                    <input v-model="form.email" type="text" name="email"
                       placeholder="Email" class="form-control" :class="{ 'is-invalid': form.errors.has('email') }">
                    <has-error :form="form" field="email"></has-error>
                </div>
                 <div class="form-group">
                    <label>Password</label>
                    <input v-model="form.password" type="text" name="password"
                      placeholder="Password"  class="form-control" :class="{ 'is-invalid': form.errors.has('password') }">
                    <has-error :form="form" field="password"></has-error>
                </div>
            </div>
            <div class="modal-footer">
                <button type="button" class="btn btn-danger" data-dismiss="modal">Close</button>
                <button type="button" class="btn btn-primary">Create User</button>
            </div>
            </div>
        </div>
        </div>
    </div>
</template>

<script>
    export default {
     data () {
            return {
            // Create a new form instance
            form: new Form({
                name: '',
                email: '',
                password: ''
            })
    }
  },
        mounted() {
            console.log('Component mounted.')
        }
    }
</script>
