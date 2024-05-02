# Laravel_blog
Ejemplo de blog utilizando Laravel

Pasos realizados para crear la web:

1. se creo DB en mysql.
2. se asigno los datos de conexion en archivo .env
3. crear un modelo llamado Post, una tabla llamada posts, un archivo de migración y un controlador conel comando:  php artisan make:model Post -mc
4. se modifica archivo de migracion con nuevos atributos y luego se migra: php artisan migrate
5. se acrean carpetas en resources/views: layouts y posts.
6. se crean las rutas dentro del archivo routes/web.php, por ejmplo: Route::resource('posts', PostController::class)
7. en el archivo  app/Http/Controllers/PostController.php se crean los metodos : index ,  create y store.
8. se registras nuevas rutas en archivo web.php:
   
Route::resource('/', PostController::class)->names([
  'index' => 'posts.index',
  'create' => 'posts.create',
  'store' => 'posts.store',
  'show' => 'posts.show',
]);

9. se hereda contenidos en las vistas creadas con el archivo app.blade.php que esta en el directorio layouts utilizando @extends('layouts.app')
