
<p align="center">
LARAVEL 6-7-8 Sweet Alert | ALSO FIXED LIVEWIRE INTEGRATION
</p>
<p align="center">
    <img src="https://raw.github.com/sweetalert2/sweetalert2/master/assets/sweetalert2.gif" width="562" height="388">
</p>



# Install

To get started with SweetAlert2, use Composer to add the package to your project's dependencies:

```
composer require uyanik13/sweet-alert

```
Add This Provider to app.php

```
DRO\SweetAlert\SweetAlertServiceProvider::class,

'providers' => [
    /*
    * Package Service Providers...
    */
    DRO\SweetAlert\SweetAlertServiceProvider::class,
],

```
Also, add the Alert facade to the aliases array in your app configuration file:

```
'Alert' => DRO\SweetAlert\Facades\Alert::class,
```

Include 'sweetalert::alert' in master layout

```
@include('sweetalert::alert')

```

and run the below command to publish the package assets.

````
php artisan sweetalert:publish
````

Using the Middleware

```
\DRO\SweetAlert\ToSweetAlert::class,

````
ENV file

```
SWEET_ALERT_MIDDLEWARE_AUTO_CLOSE=false
SWEET_ALERT_MIDDLEWARE_TOAST_POSITION='top-end'
SWEET_ALERT_MIDDLEWARE_TOAST_CLOSE_BUTTON=true
SWEET_ALERT_MIDDLEWARE_ALERT_CLOSE_TIME=5000
SWEET_ALERT_AUTO_DISPLAY_ERROR_MESSAGES=true
```


Examples

```
public function store(Request $request)
{
    //validation
    $request->validate([
        'title' => 'required|min:3',
        'body' => 'required|min:3'
    ]);
    $task = Task::create($request->all());
    return redirect('tasks')->with('success', 'Task Created Successfully!');
    // OR
    return redirect('tasks')->withSuccess('Task Created Successfully!');
}
```





SweetAlert2 is open-sourced software licensed under the MIT License (MIT). Please see [License File](LICENSE.md) for more information.

<p align="center"> <b>Made ❤️ with Laravel <b> </p>

