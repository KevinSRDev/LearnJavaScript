# **Day Three - Learn JS**

# *Bloque 1*

## Condicionales
1. `if / else`
2. `else if`
3. Operador ternario

## Condicionales en JS
- ### `if / else`
Se ejecuta un bloque de codigo su se cumple una condición, y otro si no:

```JS
let edad = 20;

if (edad >= 18) {
    console.log("Eres mayor de edad");
} else {
    console.log("Eres menor de edad");
}

// (Output)Imprime: "Eres mayor de edad"
```

- ### `else if`
Cuando se tiene más de dos posibilidades:

```JS
let nota = 75;

if (nota >= 90) {
    console.log("Excelente");
} else if (nota >= 70) {
    console.log("Aprobado");
} else if (nota >= 50) {
    console.log("Recuperacion");
} else {
    console.log("Reprobado");
}

// (Output) Imprime: Aprobado
```

> [!NOTE]
> **JavaScript** evalúa las condiciones de arriba hacia abajo y se detiene en la primera que sea `true`.

- ### Operador Ternario
Es un `if / else` resumido en una sola línea:

```JS
// Sintaxis:
// codicion ? "si es true" : "si es false"

let edad = 20;
let acceso = edad >= 18 ? "Permitido" : "Denegado";

console.log(acceso);
// (Output) Imprime: Permitido
```

> [!TIP]
> `condición ? valor_si_true : valor_si_false`
> 
> Se puede leer como: **¿Se cumple la condición? Si sí, esto. Si no, aquello**

> [!NOTE]
> El `ternario` es ideal para asignar un valor según una condición simple. Si la lógica es compleja, es mejor usar `if / else`.

+ #### Comparación directa con `if/else`

```JS
let saldo = 200;

// Con if/else
if (saldo >= 100) {
    console.log("Puedes comprar");
} else {
    console.log("Saldo insuficiente");
}

// Con ternario — exactamente lo mismo
console.log(saldo >= 100 ? "Puedes comprar" : "Saldo insuficiente");
```

+ #### Asignar a una variable
    Uso más frecuente:

```JS
let edad = 15;
let tipo = edad >= 18 ? "adulto" : "menor";
console.log(tipo); // "menor"
```

+ #### Ternarios anidados
Puedes encadenar ternarios para simular un `else if`, aunque hay que usarlo con cuidado porque puede volverse difícil de leer:

```JS
let nota = 85;

let resultado = nota >= 90 ? "Excelente"
              : nota >= 70 ? "Aprobado"
              : nota >= 50 ? "Recuperacion"
              : "Reprobado";

console.log(resultado); //Imprime: Aprobado
```

> [!IMPORTANT]
> Los **ternarios anidados** funcionan, pero si tienes más de 2 niveles, un `if / else if` es más legible. El ternario brilla en **condiciones simples**.

+ #### Ternario con funciones
También puedes ejecutar funciones dentro:

```JS
let activo = true;
activo ? console.log("Usuario activo") : console.log("Usuario inactivo");
```

## Ejecicios
Contexto:

```JS
const usuarios = [
    { nombre: "Juan", edad: 17, membresia: "free", saldo: 50 },
    { nombre: "Lisa", edad: 25, membresia: "premium", saldo: 200 },
    { nombre: "Jose", edad: 32, membresia: "premium", saldo: 80 }
];
```

Resuelve cada punto escribiendo el código, no solo el resultado:

1. Usando `if / else`, imprime si `Juan` es mayor o menor de edad.
2.  Usando `else if`, clasifica el saldo de `Lisa`:

    - Mayor o igual a 200 → `"Saldo alto"`
    - Mayor o igual a 100 → `"Saldo medio"`
    - Menor a 100 → `"Saldo bajo"`
3. Usando el **ternario**, imprime si `Jose` es `"premium"` o `"free"`.
4.  🔥 Usando el **ternario anidado**, clasifica a los tres usuarios según su saldo con la misma lógica del punto 2.

## Answer 

1. Usando `if / else`

```JS
if (usuarios[0].edad >= 18) {
    console.log(`${usuarios[0].nombre} es mayor de edad`);
} else {
    console.log(`${usuarios[0].nombre} es menor de edad`);
}

// (Output) Imprime: juan es menor de edad
```

2. Usando `else if`

```JS
if (usuarios[1].saldo >= 200) {
    console.log("Lisa: Saldo alto")
} else if (usuarios[1].saldo >= 100) {
    console.log("Lisa: Saldo medio");
} else if (usuarios[1].saldo < 100) {
    console.log("Lisa: Saldo bajo");
}

// (Output) Imprime: Lisa: Saldo alto
```

3. **Ternario**

```JS
usuarios[2].membresia === "premium" ? console.log(`${usuarios[2].nombre} es premium`) : console.log(`${usuarios[2].nombre} es free)`);

// (Output) Imprime: Jose es premium
```

4. **Ternario anidado**

```JS
let rankingJuan = usuarios[0].saldo >= 200 ? "Saldo alto"
                : usuarios[0].saldo >= 100 ? "Saldo medio"
                : "Saldo bajo";

let rankingLisa = usuarios[1].saldo >= 200 ? "Saldo alto"
                : usuarios[1].saldo >= 100 ? "Saldo medio"
                : "Saldo bajo";

let rankingJose = usuarios[2].saldo >= 200 ? "Saldo alto"
                : usuarios[2].saldo >= 100 ? "Saldo medio"
                : "Saldo bajo";

console.log(`Juan: ${rankingJuan}`);   // Juan: Saldo bajo
console.log(`Lisa: ${rankingLisa}`);   // Lisa: Saldo alto
console.log(`Jose: ${rankingJose}`);   // Jose: Saldo bajo
```