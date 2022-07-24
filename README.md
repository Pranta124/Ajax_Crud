# Ajax_Crud
# app_blade

<!DOCTYPE html>
<html lang="{{ str_replace('_', '-', app()->getLocale()) }}">
    <head>
        <meta charset="utf-8">
        <meta name="viewport" content="width=device-width, initial-scale=1">
        <meta name="csrf-token" content="{{ csrf_token() }}">
        <title>Laravel</title>

        <!-- Fonts -->
        <link href="https://fonts.googleapis.com/css2?family=Nunito:wght@400;600;700&display=swap" rel="stylesheet">

        <!-- Styles -->
        <style>
            /*! normalize.css v8.0.1 | MIT License | github.com/necolas/normalize.css */html{line-height:1.15;-webkit-text-size-adjust:100%}body{margin:0}a{background-color:transparent}[hidden]{display:none}html{font-family:system-ui,-apple-system,BlinkMacSystemFont,Segoe UI,Roboto,Helvetica Neue,Arial,Noto Sans,sans-serif,Apple Color Emoji,Segoe UI Emoji,Segoe UI Symbol,Noto Color Emoji;line-height:1.5}*,:after,:before{box-sizing:border-box;border:0 solid #e2e8f0}a{color:inherit;text-decoration:inherit}svg,video{display:block;vertical-align:middle}video{max-width:100%;height:auto}.bg-white{--bg-opacity:1;background-color:#fff;background-color:rgba(255,255,255,var(--bg-opacity))}.bg-gray-100{--bg-opacity:1;background-color:#f7fafc;background-color:rgba(247,250,252,var(--bg-opacity))}.border-gray-200{--border-opacity:1;border-color:#edf2f7;border-color:rgba(237,242,247,var(--border-opacity))}.border-t{border-top-width:1px}.flex{display:flex}.grid{display:grid}.hidden{display:none}.items-center{align-items:center}.justify-center{justify-content:center}.font-semibold{font-weight:600}.h-5{height:1.25rem}.h-8{height:2rem}.h-16{height:4rem}.text-sm{font-size:.875rem}.text-lg{font-size:1.125rem}.leading-7{line-height:1.75rem}.mx-auto{margin-left:auto;margin-right:auto}.ml-1{margin-left:.25rem}.mt-2{margin-top:.5rem}.mr-2{margin-right:.5rem}.ml-2{margin-left:.5rem}.mt-4{margin-top:1rem}.ml-4{margin-left:1rem}.mt-8{margin-top:2rem}.ml-12{margin-left:3rem}.-mt-px{margin-top:-1px}.max-w-6xl{max-width:72rem}.min-h-screen{min-height:100vh}.overflow-hidden{overflow:hidden}.p-6{padding:1.5rem}.py-4{padding-top:1rem;padding-bottom:1rem}.px-6{padding-left:1.5rem;padding-right:1.5rem}.pt-8{padding-top:2rem}.fixed{position:fixed}.relative{position:relative}.top-0{top:0}.right-0{right:0}.shadow{box-shadow:0 1px 3px 0 rgba(0,0,0,.1),0 1px 2px 0 rgba(0,0,0,.06)}.text-center{text-align:center}.text-gray-200{--text-opacity:1;color:#edf2f7;color:rgba(237,242,247,var(--text-opacity))}.text-gray-300{--text-opacity:1;color:#e2e8f0;color:rgba(226,232,240,var(--text-opacity))}.text-gray-400{--text-opacity:1;color:#cbd5e0;color:rgba(203,213,224,var(--text-opacity))}.text-gray-500{--text-opacity:1;color:#a0aec0;color:rgba(160,174,192,var(--text-opacity))}.text-gray-600{--text-opacity:1;color:#718096;color:rgba(113,128,150,var(--text-opacity))}.text-gray-700{--text-opacity:1;color:#4a5568;color:rgba(74,85,104,var(--text-opacity))}.text-gray-900{--text-opacity:1;color:#1a202c;color:rgba(26,32,44,var(--text-opacity))}.underline{text-decoration:underline}.antialiased{-webkit-font-smoothing:antialiased;-moz-osx-font-smoothing:grayscale}.w-5{width:1.25rem}.w-8{width:2rem}.w-auto{width:auto}.grid-cols-1{grid-template-columns:repeat(1,minmax(0,1fr))}@media (min-width:640px){.sm\:rounded-lg{border-radius:.5rem}.sm\:block{display:block}.sm\:items-center{align-items:center}.sm\:justify-start{justify-content:flex-start}.sm\:justify-between{justify-content:space-between}.sm\:h-20{height:5rem}.sm\:ml-0{margin-left:0}.sm\:px-6{padding-left:1.5rem;padding-right:1.5rem}.sm\:pt-0{padding-top:0}.sm\:text-left{text-align:left}.sm\:text-right{text-align:right}}@media (min-width:768px){.md\:border-t-0{border-top-width:0}.md\:border-l{border-left-width:1px}.md\:grid-cols-2{grid-template-columns:repeat(2,minmax(0,1fr))}}@media (min-width:1024px){.lg\:px-8{padding-left:2rem;padding-right:2rem}}@media (prefers-color-scheme:dark){.dark\:bg-gray-800{--bg-opacity:1;background-color:#2d3748;background-color:rgba(45,55,72,var(--bg-opacity))}.dark\:bg-gray-900{--bg-opacity:1;background-color:#1a202c;background-color:rgba(26,32,44,var(--bg-opacity))}.dark\:border-gray-700{--border-opacity:1;border-color:#4a5568;border-color:rgba(74,85,104,var(--border-opacity))}.dark\:text-white{--text-opacity:1;color:#fff;color:rgba(255,255,255,var(--text-opacity))}.dark\:text-gray-400{--text-opacity:1;color:#cbd5e0;color:rgba(203,213,224,var(--text-opacity))}.dark\:text-gray-500{--tw-text-opacity:1;color:#6b7280;color:rgba(107,114,128,var(--tw-text-opacity))}}
        </style>

        <style>
            body {
                font-family: 'Nunito', sans-serif;
            }
        </style>
            <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-EVSTQN3/azprG1Anm3QDgpJLIm9Nao0Yz1ztcQTwFspd3yD65VohhpuuCOmLASjC" crossorigin="anonymous">
        <!-- JavaScript Bundle with Popper -->

    </head>
    <body>
        <div id="app">
            <main class="py-4">
                @yield('content');
            </main>
        </div>
        <script src="https://code.jquery.com/jquery-3.6.0.min.js" integrity="sha256-/xUj+3OJU5yExlq6GSYGSHk7tPXikynS7ogEvDej/m4=" crossorigin="anonymous"></script>
        <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/js/bootstrap.bundle.min.js" integrity="sha384-MrcW6ZMFYlzcLA8Nl+NtUVF0sA7MsXsP1UyJoMp4YLEuNSfAP+JcXn/tWtIaxVXM" crossorigin="anonymous"></script>
        @yield('scripts')
    </body>
</html>
# index_blade
**


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
