# **Day Two - Learn JS**

# *Boque 1*
- ## Operadores en JavaScript
    1. ### Operadores Aritméticos = Son los que hacen cálculos matemáticos:
        ```JS
        let a = 10;
        let b = 3;

        console.log(a + b); // Suma: 13
        console.log(a - b); // Resta: 7
        console.log(a * b); // Multiplicacion: 30
        console.log(a / b); // Division: 3.3333333333333335
        console.log(a % b); // Residuo-Division: 1
        console.log(a ** b); // Potencia: (10³) = 1000
        ```
        > [!NOTE]
        >  **El módulo `%` es muy usado en programación — sirve para saber si un número es par o impar, entre otras cosas.**
    2. ### Operadores de Comparacion
        Comparan dos valores y siempre devuelven un Boolean = `true` o `false`;
        ```JS
        let x = 5;

        console.log(x > 3); // true porque x es mayor que 3
        console.log(x < 3); // flase porque x no es menor que 3
        console.log(x >= 5); // true porque x es mayor o igual a 5
        console.log(x <= 4); // false porque x no es menor o igual a 4
        console.log(x == 5); // true porque x es igual a 5 y no se compara el tipo de dato
        console.log(x != 5); // false porque x no es diferente a 5
        ```
    3. ### Operadores Lógicos
        Combinan condiciones
        ```JS
        let edad = 20;
        let tieneID = true;

        console.log(edad >= 18 && tieneID); // true porque (AND o &&) deben ser las dos condiciones verdaderas
        console.log(edad < 18 || tieneID); // true porque (OR o ||) solo necesita una de las condiciones sea verdadera
        console.log(!tieneID); // false porque (NOT o !) invierte el valor de la variable, en este caso true se convierte en false
        ```
        ```JS
        | Operador | Nombre |               Resultado              |
        |----------|--------|--------------------------------------|
        |    &&    |   AND  | `true` solo si /*ambos*/ son `true`  |
        |    ||    |   OR   | `true` si /*al menos uno*/ es `true` |
        |    !     |   NOT  | Invierte el valor                    |
        ```

## Ejecicio - Operadores
Resolver lo siguiente sin correr el codigo primero y intenta predecir el resultado de cada  `console.log`
```JS
let a = 8;
let b = 3;
let nombre = "Juan";
let activo = true;

// Bloque 1 — Aritméticos
console.log(a + b);
console.log(a % b);
console.log(a ** b);

// Bloque 2 — Comparación
console.log(a > b);
console.log(a === 8);
console.log(b === "3");

// Bloque 3 — Lógicos
console.log(a > 5 && activo);
console.log(b > 5 || activo);
console.log(!activo);
```
> [!IMPORTANT]
> # El módulo **%**
> 
> El módulo devuelve el residuo `(lo que sobra)` de una división entera.
> 
> Cuando divides dos números en programación:
> 
> La división común `(/)` te da el cociente `(cuántas veces cabe)`.
> 
> El módulo `(%)` te da el resto `(cuánto quedó sin poder repartirse)`.

### Answer
```JS
// Bloque 1 — Aritméticos
console.log(a + b); // Suma: 11
console.log(a % b); // Modulo: 2
console.log(a ** b); // Potencia: (8 elevado a 3) 512

// Bloque 2 — Comparación
console.log(a > b); // true 
console.log(a === 8); // true
console.log(b === "3"); // false, aunque el valor es 3, el tipo de dato es diferente (número vs texto)

// Bloque 3 — Lógicos
console.log(a > 5 && activo); // true: (&& o AND) ambas son verdaderas 
console.log(b > 5 || activo); // true, (|| o OR) aunque b no es mayor que 5, activo es true, y con que solo una sea verdadera el resultado es true
console.log(!activo); // false, el !(NOT) invierte el valor
```

## Ejercicio Avanzado — Operadores combinados
Tienes este contexto:
```JS
const usuarios = [
    { nombre: "Juan", edad: 17, membresia: "premium", saldo: 150 },
    { nombre: "Lisa", edad: 25, membresia: "free", saldo: 0 },
    { nombre: "Jose", edad: 32, membresia: "premium", saldo: 80 }
];
```
Responde cada console.log sin correr el código:
```JS
let u = usuarios[2]; // Jose

// 1
console.log(u.edad > 18 && u.membresia === "premium");

// 2
console.log(u.saldo >= 100 || u.membresia === "premium");

// 3
console.log(u.saldo >= 100 && u.membresia === "premium");

// 4
console.log(!(u.membresia === "free"));

// 5
console.log(u.edad >= 18 && u.saldo > 0 && u.membresia === "premium");

// 6 — Este es el más difícil 🔥
console.log((u.saldo + 20) ** 2 > 5000 && !(u.membresia === "free"));
```
### Answer
```JS
let u = usuarios[2]; // Jose

console.log(u.edad > 18 && u.membresia === "premium");
// 1 (&& o AND):
// true, porque Jose tiene más de 18 años y es premium

console.log(u.saldo >= 100 || u.membresia === "premium");
// 2 (|| o OR):
// true, porque Jose es premium, aunque su saldo no es mayor a 100

console.log(u.saldo >= 100 && u.membresia === "premium");
// 3 (&& o AND):
// false, porque Jose tiene un saldo de 80, aunque es premium

console.log(!(u.membresia === "free"));
// 4 (! o NOT, === o igualdad estricta):
// true, porque Jose no es free

console.log(u.edad >= 18 && u.saldo > 0 && u.membresia === "premium");
// 5 (&& o AND):
// Jose true, porque cumple las tres condiciones

console.log((u.saldo + 20) ** 2 > 5000 && !(u.membresia === "free"));
// 6 (Potencias, && o AND, ! o NOT):
// Jose true, porque (80 + 20) ** 2 es mayor a 5000 y no es free
```