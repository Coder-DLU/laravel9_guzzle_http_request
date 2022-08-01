# laravel9_guzzle_http_request
## 1. Install Laravel 9
```Dockerfile
composer create-project laravel/laravel laravel9_guzzle_http_request
```
## 2. Laravel 9 HTTP cURL GET Request
- Vào routes/web.php
```Dockerfile
<?php
  
use Illuminate\Support\Facades\Route;
  
use App\Http\Controllers\PostController;
  
/*
|--------------------------------------------------------------------------
| Web Routes
|--------------------------------------------------------------------------
|
| Here is where you can register web routes for your application. These
| routes are loaded by the RouteServiceProvider within a group which
| contains the "web" middleware group. Now create something great!
|
*/
  
Route::get('posts', [PostController::class, 'index']);
```
- Vào app/Http/Controllers/PostController.php
```Dockerfile
<?php
  
namespace App\Http\Controllers;
  
use Illuminate\Http\Request;
use Illuminate\Support\Facades\Http;
  
class PostController extends Controller
{
    /**
     * Write code on Method
     *
     * @return response()
     */
    public function index()
    {
        $response = Http::get('https://jsonplaceholder.typicode.com/posts');
    
        $jsonData = $response->json();
          
        dd($jsonData);
    }
}
```

![Container](a.png)

## 3. Laravel 9 HTTP cURL POST Request 
- Vào routes/web.php
```Dockerfile
<?php
  
use Illuminate\Support\Facades\Route;
  
use App\Http\Controllers\PostController;
  
/*
|--------------------------------------------------------------------------
| Web Routes
|--------------------------------------------------------------------------
|
| Here is where you can register web routes for your application. These
| routes are loaded by the RouteServiceProvider within a group which
| contains the "web" middleware group. Now create something great!
|
*/
  
Route::get('posts/store', [PostController::class, 'store']);
```
- Vào app/Http/Controllers/PostController.php
```Dockerfile
<?php
  
namespace App\Http\Controllers;
  
use Illuminate\Http\Request;
use Illuminate\Support\Facades\Http;
  
class PostController extends Controller
{
    /**
     * Write code on Method
     *
     * @return response()
     */
    public function store()
    {
        $response = Http::post('https://jsonplaceholder.typicode.com/posts', [
                    'title' => 'This is test from ItSolutionStuff.com',
                    'body' => 'This is test from ItSolutionStuff.com as body',
                ]);
  
        $jsonData = $response->json();
      
        dd($jsonData);
    }
}
```

![Container](a1.png)

## 4. Laravel 9 HTTP cURL PUT Request
- Vào routes/web.php
```Dockerfile
<?php
  
use Illuminate\Support\Facades\Route;
  
use App\Http\Controllers\PostController;
  
/*
|--------------------------------------------------------------------------
| Web Routes
|--------------------------------------------------------------------------
|
| Here is where you can register web routes for your application. These
| routes are loaded by the RouteServiceProvider within a group which
| contains the "web" middleware group. Now create something great!
|
*/
  
Route::get('posts/update', [PostController::class, 'update']);
```
- Vào app/Http/Controllers/PostController.php
```Dockerfile
<?php
  
namespace App\Http\Controllers;
  
use Illuminate\Http\Request;
use Illuminate\Support\Facades\Http;
  
class PostController extends Controller
{
    /**
     * Write code on Method
     *
     * @return response()
     */
    public function update()
    {
        $response = Http::put('https://jsonplaceholder.typicode.com/posts/1', [
                    'title' => 'This is test from ItSolutionStuff.com',
                    'body' => 'This is test from ItSolutionStuff.com as body',
                ]);
  
        $jsonData = $response->json();
      
        dd($jsonData);
    }
}
```

![Container](a2.png)
