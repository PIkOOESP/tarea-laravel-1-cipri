# Despliegue de laravel en Vercel

Creamos un nuevo projecto de laravel o en mi caso descargo el [example_app](https://github.com/CGARCHER/example-app) de cipriano

Para el despliegue necesitaremos:

- Carpeta api: En la que tendremos un index.php que redirige al index.php de la carpeta public.

- vercel.json: Donde añadiremos las configuracion del entorno, las rutas y el runtime.

- .vercelignore: Solo se añade la carpeta vendor a este

- Carpeta vacia dist.

## Vercel

Iniciamos sesion en vercel con github e importamos nuestro repositorio. Teoricamente esto seria válido para desplegar la aplicacion.

## Problemas en el despliegue

### Primer problema

El primer problema que se me ha presentado era que al subir a github los archivos no conseguia subir la carpeta dist vacia.

#### Solucion

Cambiar la carpeta donde se guarda el proyecto. Segun el tutorial, la carpeta public es la indicada para hacerlo asi que vamos a settings, a build and development y cambiamos la carpeta de output a public

### Segundo problema

El segundo problema ha sido el runtime. Al instalar las depencencias decia que el runtime: vercel-php@0.6.0 estaba anticuado y que tenia que cambiarlo.

#### Solucion

Busque runtime vercel php y encontre este [github](https://github.com/vercel-community/php). En el readme.md ponia runtime : vercel-php@0.9.0. Hice pinta e inventa suponiendo que era la ultima version y resulta que funciona.

### Tercer problema

No tengo base de datos.

#### Solucion

Primero empecé creando una base de datos en neon (el propio vercel te da esa opcion). Por alguna razon daba error al poner los email de usuarios unico y por no cambiarlo he preferido hacer la base de datos con render, la que use para el ultimo trabajo de subir a render la misma app. Poniendo los credenciales en el .env se despliega bien.

[Url de la aplicacion desplegada](https://tarea-laravel-1-cipri-3okzdvqz4-pikooesps-projects.vercel.app)