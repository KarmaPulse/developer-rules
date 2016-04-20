# Lineamientos de Desarrollo

A continuación te presento una serie de reglas que nos gusta seguir a la hora de estar desarrollando. Éstas pretenden ser de carácter general y aplicables a cualquier proyecto o lenguaje de programación, sin embargo, si el lenguaje de programación o el proyecto en el que vas a trabajar tiene establecidas sus propias reglas, apégate a ellas, no es necesario que sigas éstas pero échales un ojo, por si acaso.

## Tabla de Contenido

### Formato

* [Indentación a cuatro espacios](#indentación-a-cuatro-espacios)
* [Saltos de línea](#saltos-de-línea)
* [Sin espacios en blanco al final de la línea](#sin-espacios-en-blanco-al-final-de-la-línea)
* [80 caracteres por línea](#80-caracteres-por-línea)
* [La llave que abre ¡va en la misma línea!](#la-llave-que-abre-¡va-en-la-misma-línea!)
* [Una variable, una línea](#una-variable,-una-línea)
* [Todo el código en inglés](#todo-el-código-en-inglés)

### Convenciones de nombramiento

* [lowerCamelCase para variables, propiedades y nombres de funciones](#lowercamelcase-para-variables,-propiedades-y-nombres-de-funciones)
* [UpperCamelCase para nombres de clases](#uppercamelcase-para-nombres-de-clases)
* [Mayúsculas para constantes](#mayúsculas-para-constantes)
* [Nombres de carpetas y archivos](#nombres-de-carpetas-y-archivos)
* [Nombres de repositorios](#nombres-de-repositorios)

### Bases de Datos

* [Nombres de las Bases de Datos](#nombres-de-las-bases-de-datos)
* [Nombres de tablas y colecciones](#nombres-de-tablas-y-colecciones)
* [Nombres de columnas y llaves](#nombres-de-columnas-y-llaves)

### Misceláneo

* [URLs](#urls)

## Formato

### Indentación a cuatro espacios

Usa cuatro espacios para indentar tu código. Sí, sabemos que la mayoría de editores están configurados a dos espacios por defecto, sin embargo, con esa cantidad de espacios es algo difícil ubicar a simple vista dónde empieza y acaba una función, un if, una clase, etc., así que facilitemos el trabajo de nuestros ojos usando cuatro espacios. ¡Ah! ¡Y por el amor de Dios! No mezcles TABs con Espacios, existe un lugar especial en el infierno para los desarrolladores que hacen eso, evita terminar allí.

### Saltos de línea

Usa saltos de linea tipo UNIX (`\n`), y deja un salto de linea al final de cada archivo. Los saltos de linea tipo Windows (`\r\n`) están prohibidos dentro de cualquier repositorio.

### Sin espacios en blanco al final de la línea

Así como cepillas tus dientes después de cada comida, elimina los saltos de línea y espacios en blanco que estén de más en tu código antes de dar por terminada esa brillante función, script o clase. De lo contrario, con el tiempo, el olor producido por la imprudencia y el abandono ahuyentará a tus compañeros de trabajo.

### 80 caracteres por línea

Limita tus líneas a 80 caracteres. Sí, con el pasar de los años las pantallas se han vuelto más grandes, pero no así tu cerebro.

### La llave que abre ¡va en la misma línea!

La llave que abre va siempre en la misma línea que la sentencia condicional o bucle.

*Correcto:*

```
if ( true ) {
	console.log('Eres un campeón XD');
}
```

*Incorrecto:*

```
if ( true )
{
	console.log('Pero qué mal estás U_U');
}
```
Nótese también el uso de espacios antes y después de la sentencia, así como antes y después de la condicionante.

### Una variable, una línea

Ya sea que estés creando variables o asignándoles un valor, utiliza una linea por cada creación o asignación. Por otro lado, declara y asigna variables en donde haga más sentido.

*Correcto:*
```
var keys   = ['foo', 'bar'];
var values = [23, 42];

var object = {};
while ( keys.length ) {
	var key = keys.pop();
	object[key] = values.pop();
}
```
*Incorrecto:*
```
var keys = ['foo', 'bar'],
    values = [23, 42],
    object = {},
    key;

while ( keys.length ) {
	key = keys.pop();
	object[key] = values.pop();
}
```

### Todo el código en inglés

Amamos el idioma español, es uno de los idiomas mas completos y eficientes que existen, sin embargo, el idioma más común y con el cual están desarrollados casi todos (si no es que todos) los lenguajes de programación es el inglés. Por eso y por que no siempre vamos a estar ahí para darle mantenimiento a nuestro código —puede que le sea delegada esa tarea a un extranjero— todo el código debe de ir en inglés.


## Convenciones de nombramiento

### lowerCamelCase para variables, propiedades y nombres de funciones

Los nombres de variables, propiedades y funciones deben de ir en `lowerCamelCase`. Tienen que ser descriptivos; evita usar nombres de variables de un solo carácter o abreviaciones raras e indescifrables.

*Correcto:*
```
var adminUser = db.query( 'SELECT * FROM users ...' );
```
*Incorrecto:*
```
var admin_user = db.query( 'SELECT * FROM users ...' );
```

### UpperCamelCase para nombres de clases

Los nombres de las clases deben de comenzar con mayúscula `UpperCamelCase`.

*Correcto:*
```
public class FileMaker {
	...
}
```
*Incorrecto:*
```
public class file_Maker {
	...
}
```

### Mayúsculas para constantes

Todas las letras del nombre de una variable constante deben de ir en mayúsculas, haciendo uso de guiones bajos para aquellos nombres que estén compuestos por más de dos palabras.

*Correcto:*
```
var SECOND = 1 * 1000;

function File() {
}
File.FULL_PERMISSIONS = 0777;
```
*Incorrecto:*
```
const second = 1 * 1000;

function File() {
}
File.fullPermissions = 0777;
```

### Nombres de carpetas y archivos

Todas las letras del nombre de un directorio o archivo deben de ir en minúsculas y en inglés, haciendo uso de guiones bajos para aquellos nombres que estén compuestos por más de dos palabras. Esto es para facilitar el manejo de los mismos.

*Correcto:*
```
twitter_connector/
connector_replay.js
```
*Incorrecto:*
```
twitterConnector/
Connector_Replay.js
```

### Nombres de repositorios

Los nombres de repositorios tienen el siguiente formato:
```
<product>_<type>_<description>
```
Donde:

#### Product
Hace referencia al nombre del producto al que corresponde el repositorio: kpulse, kboard, kmetrics o kbrain

#### Type
Hace referencia al tipo de aplicación que se encuentra contenida en el repositorio: worker, client, api, product, etc.

#### Description
Hace referencia al nombre que identifica al repositorio: admin, site, hub_citizen etc.


## Bases de Datos

Reglas que aplican a bases de datos relacionales y no relacionales.

### Nombres de las Bases de Datos

Todas las letras del nombre de la base de datos deben de ser minúsculas. En caso de que el nombre contenga más de dos palabras, éstas deberán separarse por medio de guiones bajos. Finalmente, trata que el nombre a utilizar sea corto pero que, a la vez, exprese a que sistema o aplicación corresponde.

### Nombres de tablas y colecciones

El nombramiento de tablas y colecciones es muy parecido al nombramiento de la base de datos: todas las letras del nombre deben de ir en minúsculas y en caso de que el nombre contenga mas de dos palabras, estas deberán separarse por medio de guiones bajos. Pero además de esto, el nombre debe seguir la regla Módulo-Entidad, en la cual, la primer palabra del nombre ( Módulo ) nos indica a que sección de la aplicación corresponde y las palabras siguientes ( Entidad ) nos indican qué conjunto de datos contiene la tabla o colección. Finalmente, los nombres deben estar en inglés y expresados en singular.

*Correcto:*
```
auth_permission
auth_person
auth_person_permission
pulse_account
pulse_person_account
```
*Incorrecto:*
```
Permissions
Persons
PersonsPermissions
Accounts
PersonAccounts
```

### Nombres de columnas y llaves

Todas las letras del nombre de la columna o llave deben de ser minúsculas. En caso de que el nombre contenga más de dos palabras, éstas deberán estar separadas por medio de guiones bajos. Finalmente, todos los nombres deben de estar en inglés.


## Misceláneo

### URLs

Todas las letras de las urls deben de ir en minúsculas. Si una url está compuesta por dos o más palabras, éstas deben de ir separadas por un guión medio y todas las palabras que conformen la url deben de estar en inglés.
