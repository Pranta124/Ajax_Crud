# Ajax_Crud
# index_blade
**
@extends('layouts.app')
@section('content')


  <!-- Modal -->
  <div class="modal fade" id="AddStudentModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
    <div class="modal-dialog">
      <div class="modal-content">
        <div class="modal-header">
          <h5 class="modal-title" id="exampleModalLabel">Add Student</h5>
          <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
        </div>
        <form id="add_student">
            <div class="modal-body">
                <ul id="saveform_erre"></ul>
            <div class="form-group mb-3">
                    <label for="">Name</label>
                    <input type="text" name="name" class="name form-control">
                    <span id="error_name" class="text-danger"></span>
            </div>
            <div class="form-group mb-3">
                    <label for="">Email</label>
                    <input type="text" name="email" class="email form-control">
                    <span id="error_email" class="text-danger"></span>
            </div>
            <div class="form-group mb-3">
                    <label for="">Phone</label>
                    <input type="text" name="phone"class="phone form-control">
                    <span id="error_phone" class="text-danger"></span>
            </div>
            <div class="form-group mb-3">
                    <label for="">Course</label>
                    <input type="text" name="course" class="course form-control">
                    <span id="error_course" class="text-danger"></span>
            </div>
            </div>
            <div class="modal-footer">
            <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
            <button type="submit"  class="btn btn-primary add_student">Save</button>
            </div>
        </form>
      </div>
    </div>
  </div>
  {{-- {{Edit modal}} --}}
  <div class="modal fade" id="EditStudentModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
    <div class="modal-dialog">
      <div class="modal-content">
        <div class="modal-header">
          <h5 class="modal-title" id="exampleModalLabel">Edit & Update Student</h5>
          <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
        </div>

            <div class="modal-body">
                <ul id="updateform_erre"></ul>


                <input type="hidden" id="edit_stud_id" class="id form-control">

            <div class="form-group mb-3">
                    <label for="">Name</label>
                    <input type="text" id="edit_name" name="name" class="name form-control">
                    <span id="error_name" class="text-danger"></span>
            </div>
            <div class="form-group mb-3">
                    <label for="">Email</label>
                    <input type="text" id="edit_email"  name="email" class="email form-control">
                    <span id="error_email" class="text-danger"></span>
            </div>
            <div class="form-group mb-3">
                    <label for="">Phone</label>
                    <input type="text" id="edit_phone"  name="phone"class="phone form-control">
                    <span id="error_phone" class="text-danger"></span>
            </div>
            <div class="form-group mb-3">
                    <label for="">Course</label>
                    <input type="text" id="edit_course"  name="course" class="course form-control">
                    <span id="error_course" class="text-danger"></span>
            </div>
            </div>
            <div class="modal-footer">
            <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
            <button type="submit"  class="btn btn-primary update_student">Update</button>
            </div>

      </div>
    </div>
  </div>
{{-- {{Delete Modal}} --}}
  <div class="modal fade" id="DeleteStudentModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
    <div class="modal-dialog">
      <div class="modal-content">
        <div class="modal-header">
          <h5 class="modal-title" id="exampleModalLabel">Delete Student</h5>
          <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
        </div>

            <div class="modal-body">
                <ul id="updateform_erre"></ul>


                <input type="hidden" id="delete_stud_id" class="id form-control">
                <h4>Are you sure? want to delete this data?</h4>

            </div>
            <div class="modal-footer">
            <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
            <button type="submit"  class="btn btn-primary delete_student_btn">Yes Delete</button>
            </div>

      </div>
    </div>
  </div>
  {{-- {{End_Modal}} --}}
    <div class="container py-5">
        <div class="row">
            <div class="col-md-12">
                <div id="success"></div>
                <div class="card">
                    <div class="card-header">
                        <h4> Students Data
                            <a href="#" data-bs-toggle="modal" data-bs-target="#AddStudentModal" class="btn btn-primary float-end btn-sm">ADD Student</a>
                        </h4>
                    </div>
                    <div class="card-body">
                        <table class="table">
                            <thead >
                              <tr>
                                <th scope="col">ID</th>
                                <th scope="col">Name</th>
                                <th scope="col">Email</th>
                                <th scope="col">Phone</th>
                                <th scope="col">Course</th>
                                <th scope="col">Edit</th>
                                <th scope="col">Delete</th>
                              </tr>
                            </thead>
                            <tbody id="scheduleShowData">

                            </tbody>
                          </table>
                    </div>
                </div>
            </div>
        </div>
    </div>

@endsection

@section('scripts')
    <script>
        $(document).ready(function(e)
        {
            fetchstudent();

            function fetchstudent()
            {
                $.ajax({
                    type: "GET",
                    url:"/fetch_student",
                    dataType:"json",
                    success: function(response) {
                    console.log(response);
                     $('#scheduleShowData').html("");
                    var data = '';
                    $.each(response.students, function(key, value) {
                        data += ` <tr>
                                    <td>${value.id}</td>
                                    <td>${value.name}</td>
                                    <td>${value.email}</td>
                                    <td>${value.phone}</td>
                                    <td>${value.course}</td>
                                    <td><button type="button" value="${value.id}" class="edit_student btn btn-primary btn-sm">Edit<button></td>
                                    <td><button type="button" value="${value.id}" class="delete_student btn btn-danger btn-sm">Delete<button></td>
                                </tr>`;
                    });
                    $('#scheduleShowData').append(data);
                },


                });
            }

            $(document).on('click','.delete_student',function(e){
                e.preventDefault();
                var studnt_id = $(this).val();
                 $('#delete_stud_id').val(studnt_id);
                 $('#DeleteStudentModal').modal('show');
            });
            $(document).on('click','.delete_student_btn',function(e)
            {
                e.preventDefault();
                var studnt_id = $('#delete_stud_id').val();
                $.ajaxSetup({
                                headers: {
                                    'X-CSRF-TOKEN': $('meta[name="csrf-token"]').attr('content')
                                }
                            });
                $.ajax({
                    type: "DELETE",
                    url:"/delete_student/"+studnt_id,
                    success: function(response)
                    {
                        console.log(response);
                        $('#success').addClass('alert alert-success')
                        $('#success').text(response.message);
                        $('#DeleteStudentModal').modal('hide');
                        fetchstudent();
                    }

                });
            });
            $(document).on('click','.edit_student',function(e)
            {
                e.preventDefault;
                var student_id = $(this).val();
                // console.log(student_id);
                $('#EditStudentModal').modal('show')
                $.ajax({
                    type: "GET",
                    url:"/edit_student/"+student_id,
                    success: function(response)
                    {
                        // console.log(response);
                        if (response.status == 400) {
                        $('#error_name').text(response.errors.name);
                        $('#error_email').text(response.errors.email);
                        $('#error_phone').text(response.errors.phone);
                        $('#error_course').text(response.errors.course);

                        }
                        else
                        {
                            $('#edit_name').val(response.student.name);
                            $('#edit_email').val(response.student.email);
                            $('#edit_phone').val(response.student.phone);
                            $('#edit_course').val(response.student.course);
                            $('#edit_stud_id').val(student_id);
                        }
                    }
                });
            });
            $(document).on('click','.update_student',function(e)
            {
                e.preventDefault();
                var stud_id = $('#edit_stud_id').val();
                var data = {
                    'name':$('#edit_name').val(),
                    'email':$('#edit_email').val(),
                    'phone':$('#edit_phone').val(),
                    'course':$('#edit_course').val(),
                }
                $.ajaxSetup({
                                headers: {
                                    'X-CSRF-TOKEN': $('meta[name="csrf-token"]').attr('content')
                                }
                            });
                $.ajax({
                    type: "PUT",
                    url:"/update_student/"+stud_id,
                    data: data,
                    dataType: "json",
                    success: function(response)
                    {
                        // console.log(response);

                        if(response.status==400)
                        {
                            $('#error_name').text(response.errors.name);
                            $('#error_email').text(response.errors.email);
                            $('#error_phone').text(response.errors.phone);
                            $('#error_course').text(response.errors.course);
                        }
                        else if(response.status==404)
                        {
                            $('#success').addClass('alert alert-success')
                            $('#success').text(response.message)
                            $('#AddStudentModal').modal('hide')
                            $('#AddStudentModal').find('input').val(" ");
                        }
                        else
                        {
                            $('#success').addClass('alert alert-success')
                            $('#success').text(response.message)
                            $('#EditStudentModal').modal('hide')
                            $('#EditStudentModal').find('input').val(" ");
                        }
                        fetchstudent();
                    }
                });


            });
            $(document).on('click','.add_student',function(e)
            {
                e.preventDefault();
                // console.dir($('#add_student'));
                 let imagesData = new FormData($('#add_student')[0]);
                $.ajaxSetup({
                                headers: {
                                    'X-CSRF-TOKEN': $('meta[name="csrf-token"]').attr('content')
                                }
                            });
                $.ajax({
                    type: "POST",
                    url:"students",
                    data:imagesData,
                    dataType:"json",
                    processData: false,
                    contentType: false,
                    success: function(response)
                    {
                        if (response.status == 400) {
                        $('#error_name').text(response.errors.name);
                        $('#error_email').text(response.errors.email);
                        $('#error_phone').text(response.errors.phone);
                        $('#error_course').text(response.errors.course);

                        }
                        else
                        {
                            $('#success').addClass('alert alert-success')
                            $('#success').text(response.message)
                            $('#AddStudentModal').modal('hide')
                            $('#AddStudentModal').find('input').val(" ");
                        }
                        fetchstudent();

                    }

                });
            });
        });
    </script>
@endsection

**
