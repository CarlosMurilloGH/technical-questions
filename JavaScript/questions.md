# javascript-questions
## diferencia entre arrow function y regular functions?
arrow function no tienen this, las funciones regulares tiene el keyword new
## que es this?
hace referencia a un objeto https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this

```
const test = {
  prop: 42,
  func: function() {
    return this.prop;
  },
};

console.log(test.func());
// expected output: 42
```

## que es un spread operator?
copia todas las partes de un array u objecto en otro array u objeto.

## que es un callback?
es una funcion que se llama asi misma y se ejecuta cuando sucede cierta operacion, por ejemplo cuando hacemos click en un boton.

## que es un closure?
Es una función dentro de otra función, esto se hace porque la función de adentro puede acceder a las propiedades de la funcion que la contiene.

## que es call?
con call llamamos a una function, en donde podemos selecciona un objeto y los parametros de la funcion https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/call 

```
const user = {
  name:"Marcos"
};

const busienss = {
  name:"Headbook"
};

function showInfo(likes,friends){
  return `${this.name} tiene ${likes} likes y ${friends}`
}

console.log(showInfo(10,5)); 
si lo ponemos así, JS va a correr showInfo, pero no va a saber a this estamos haciendo referencia.
tenemos que hacerlo de la siguiente manera:
console.log(showInfo.call(user, 4,8)); 
el primer parametro es para especificar a que objeto tenemos que hacerle referencia, para que tenga un this.

```
## que es apply?
Es lo mismo que call, llamamos a una funcion, en donde seleccionamos un objeto, pero los parametros los pasamos como un array

```
console.log(showInfo.apply(user,[6,9]))
```

## que es bind?
Nos permite crear una función, utilizando otra función, pero con el objeto ya en contexto y cuando lo ejecutemos la nueva funcion tenemos que pasar los parametros de la funcion contenida. 

```
const newFunction = showInfo.bind(user);
console.log(newFunction(10,15))
```

## diferencia entre null y undefined?
undefined se muestra cuando una variable ha sido declarada, pero no se le ha asignado un valor.
```
var test
console.log(test)
```
null es una asignación que le damos a una variable, para que tenga un valor vacio. Ya que siempre le tenemos que dar un valor a una variable, null nos sirve para que tenga un valor vacio.

## diferencia entre let,var y const
let y const tienen un scope local y var tiene un scope global, let y var se pueden re declarar y const no se puede volver a declarar,solo  var hace hoisting

## que es el call stack?
es el orden en el que se ejecuta el codigo, como hace el drilling de resolver las funciones.

## que es una funcion recursiva?
es una función que se ejecuta asi misma hasta que se cumpla una condición

## que es mutabilidad?
primitive type es inmutable, al hacer "cambios" en su valor, solo se le hace una referencia.
primitive type : numeros,strings,booleans,null y undefined.

```
function add5(num){
  num +=5
  console.log(num)
}

var x =5
add5(x)
console.log(x)

#10
#5, porque el valor de x no ha cambiado en realidad
```

```
function append5(arr){
  arr.push(5)
  console.log(arr)
}

var x = [1,2,3,4]
append5(x)
console.log(x)

# [1,2,3,4,5]
# [1,2,3,4,5]
El valor de x va a cambiar porque los objetos sí son mutables, es decir que su valor cambia directamente, a diferencia de los primite types, en donde solo se hace una referencia, así que su valor no cambia.
```
