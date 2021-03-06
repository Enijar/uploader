# uploader
Front end image cropping and editing with Cropper JS and Plupload for Laravel.

#### Note

> This is still in testing. This will be published to a package once testing is complete.

#### Include the Uploader
For each uploader, you will need to include the `uploader.ui` partial:

```php
    @include('partials.uploader.ui', [
        'name' => 'cropper',
        'width' => 500,
        'height' => 500,
        'upload_url' => url('upload'),
        'max_file_size' => '5mb',
        'allowed_extensions' => 'jpg,gif,png',
        'flash_swf_url' => asset('js/vendor/plupload/Moxie.swf'),
        'silverlight_xap_url' => asset('js/vendor/plupload/Moxie.xap'),
        'onPostInit' => '',
        'onFileAdded' => '',
        'onBeforeUpload' => '',
        'onFileUploaded' => '',
        'onUploadProgress' => '',
        'onError' => '',
    ])
```

#### Adding the Uploader Route
This will point to the Uploader controller to handle uploading files:

```php
    Route::post('upload', 'UploaderController@store');
```

#### Options
***name*** will be the name of the hidden input which stores all uploaded file names as a JSON array.

***upload_url*** is the route URL to the route that will call `UploaderController@store`

***flash_swf_url*** Path to the fallback Flash file

***silverlight_xap_url*** Path to the fallback Silverlight file

***onPostInit*** Javascript function to call after the uploader is instantiated

***onFileAdded*** Javascript function to call after a file is added

***onBeforeUpload*** Javascript function to call before a file is uploaded

***onFileUploaded*** Javascript function to call after a file is uploaded

***onUploadProgress*** Javascript function to call when a file is being uploaded

***onError*** Javascript function to call when an error is encountered