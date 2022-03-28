## Spread operator

Normalmente tenemos situaciones en las que necesitamos acceder a todos los elementos de un array para unirlos/concatenarlos a otro array, o a varios simultáneamente.

Un ejemplo de concatenación:

```js
const terrestres = ['Perro', 'Vaca', 'Águila'];
const marinos = ['Tiburón', 'Salmón'];

const animalesCompletos = [...terrestres, ...marinos];
// ['Perro', 'Vaca', 'Águila', 'Tiburón', 'Salmón']
```

Dato a tener en cuenta es que el orden en que hagamos el `spread` importa.

***

Otro uso importante y muy común es en objetos, por lo que podemos cambiar las propiedades de un objeto sin tener que repetir los datos que no nos interesan cambiar, o incluso anexar propiedades nuevas a un objeto existente:

```js
const persona = {
    nombre: 'Carlos',
    edad: 25
}

const profesion = {
    oficio: 'Carpintero',
    antiguedad: '20 años'
}

const datosCompletos = {...persona, ...profesion}
```

Otro ejemplo sería anexar manualmente una nueva propiedad:

```js
const datosCompletos = {...persona, telefono: 34111000}
```

Por último, podemos actualizar alguna propiedad:

```js
const datosCompletos = {...persona, nombre: 'Alberto'}
```

***

Dato a tener en cuenta es que solo se puede usar con objetos iterables, como un array.

***

Por otro lado, podemos usar el mismo tipo de sintaxis para capturar parámetros extra que posiblemente podamos enviar en una función. Estos parámetros van a ser agrupados en un array para que podamos acceder a ellos:

```js
function imprimirNumeros(num1, num2, ...otrosNumeros) {
    console.log(num1)
    console.log(num2)
    console.log(otrosNumeros)
}

imprimirNumeros(1, 2, 33, 44)

// 1
// 2
// [33, 44]
```