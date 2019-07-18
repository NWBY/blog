# Resources

`php artisan make:resource Name` will generate a resource with the name of the model given. A resource only transforms an individual model to a JSON response. A resource collection will transform a collection of models: `php artisan make:resource Name --collection`.

Inside a resource file for an individual model, everything goes inside the toArray() method. Then to access model properties inside this method we define as `'name' => $this->name`. The resource can then be returned inside a controller method:

```
use App\Http\Resources\User as UserResource;

public function show(User $user) {
    // pass data to the resource that needs to be returned.
    return new UserResource($user);
}
```

Then in an API route can call that method:

```
Route::get('api/user', 'APIController@index');
```

# Resource Collections

Same as a resource but requires:

```
use App\Http\Resources\User as UserResource;

public function index() {
    // pass data to the resource collection that needs to be returned.
    return UserResource::collection(User::all());
}
```

This approach doesn't include any metadata.

Can then call this API in a Vue component or instance using axios and pass it down to child components.
