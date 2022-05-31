# laravel_uploadfile_to_folder

> We are going to use postman as our front-end simulation to upload a picture.
> Create a laravel project and go to Route>>api file and add a route 

$ Route::post('upload',[UploadController::class, "upload"]);

> Now create the controller file using command line and make sure that you are the directory of your project in cmd.
>  $ php artisan make:controller UploadController
>  Then right in your controller, create a function to accept a file and either save in a folder or in a database as blob.
>  In this process we are going to save the file to a folder and also save the file name in the database.
>  The following is a function inside the controller to manipulate the incoming file.
>  public function upload(Request $request)
>  {
>  // check whether the request has the file.
>     if($request->hasFile('photo')
>     {
>     // get the image from the request
>     $image = $request->file('photo');
>     // give the image a unique name
>     $ImageNewName = date("Ymd").''.time().''.$image->getClientOriginalExtension();
>     //initialize the destination of the image
>     $Destination = public_path()."/storage/image_avatar";
>     //Now move the image to the destination
>     $image->move($Destination, $ImageNewName);
>     // Once the image has been save to the destination, pick the $ImageNewName and save it in your database table as a string.
>     }
>  }
>  Now open your postman and initiate a post request with your localhost url or if in production use the full url .
>  For input go to body>>form-data and add an input photo as a file. Choose the image file you want to upload.
>  Click send and check if the action has been executed.
#  Thank you.
