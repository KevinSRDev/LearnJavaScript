# **Day One - Learn JS**

# *Bloque 1*
- ##  Variables en JavaScript
    ```JS
    let edad = 30; // let para variables que pueden cambiar
    const nombre = "Juan"; // const para variables que no cambian
    var ciudad = "Madrid"; // var es una forma antigua de declarar variables
    ```

- ## TIPOS DE DATOS

  + ### **`string`** = cadena de texto

    ```JS
    const saludo = "Hola mundo";
    const nombre = 'Carlos';  // comillas simples también funcionan
    const mensaje = `Hola ${nombre}`; // template literal (muy útil!)
    console.log(mensaje); // → Hola Carlos
    ```
  + ### **`number`** = numeros

    ```JS
    const entero = 42;
    const decimal = 3.14;
    const negativo = -10;
    console.log(entero + decimal); // → 45.14
    ```
  + ### **`boolean`** = true or false

    ```JS
    const esMayorDeEdad = true;
    const estaLloviendo = false;
    ```
  + ### **`null`** = ausencia de valor

    ```JS
    const respuesta = null; // "sé que esto no tiene valor aún"
    ```
  + ### **`undefined`** = se declara sin valor

    ```JS
    let telefono;
    console.log(telefono); // → undefined
    ```
  + ### **`array`** = lista de valores

    ```JS
    const frutas = ["manzana", "pera", "uva"];
    console.log(frutas[0]); // → manzana (los índices empiezan en 0)
    ```
  + ### **`object`** = coleccion de propiedades

    ```JS
    const persona = {
      nombre: "Carlos",
      edad: 25,
      ciudad: "Bogotá"
    };
    console.log(persona.nombre); // → Carlos
    ```
  + ### `typeof` = ¿Qué tipo es esto?
    ```JS
    console.log(typeof "hola");     // → string
    console.log(typeof 42);         // → number
    console.log(typeof true);       // → boolean
    console.log(typeof undefined);  // → undefined
    console.log(typeof null);       // → object (quirk histórico de JS!)
    ```
<hr>
<hr>
<hr>

## 💻 EJERCICIOS

- **Ejercicio 1 — Básico:**
Crea variables para almacenar tu nombre, tu edad, tu ciudad y si eres mayor de edad. Usa el tipo de dato correcto para cada una e imprímelas con `console.log`.

- **Ejercicio 2 — Intermedio:**
Crea un objeto llamado `perfil` con al menos 5 propiedades (nombre, edad, ciudad, profesión, hobby). Luego imprime cada propiedad individualmente.

- **Ejercicio 3 — Template literals:**
Usando las variables del ejercicio 1, crea un mensaje así:
    ```JS 
    "Hola, me llamo Carlos, tengo 25 años y vivo en Bogotá"
    ```
<hr>

## Answer
- **Ejecicio 1**
  ```JS
  const name = "KDev"; // Variable para nombre
  let age = 15; // Variavle para edad, let porque va a cambiar el valor
  const city = "Bogotá";

  // Imprimir valor
  console.log(name); // KDev
  console.log(age); // 15
  console.log(city); // Bogotá
  ```
- **Ejecicio 2**
    ```JS
    const perfil = {
        name: "Juan",
        age: 25,
        country: "Suiza",
        profesion: "Developer",
        hobby: "La Musica"
    };

    // Imprimir valor individualmente
    console.log(perfil.name); // Juan
    console.log(perfil.age); // 25
    console.log(perfil.country); // Suiza
    console.log(perfil.profecion); // Developer
    console.log(perfil.hobby); // La Musica
    ```
- **Ejecicio 3**
    ```JS
    // Variables ejecicio 1 
    const name = "KDev";
    let age = 15;
    const city = "Bogotá";

    // Imprimir Template literals
    console.log(`Hola, me llamo ${name}, tengo ${age} años y vivo en ${city}.`);
    // Salida  
    "Hola, me llamo KDev, tengo 15 años y vivo en Bogotá."
    ```

# *Bloque 2*
`console.log` a fondo + Conversión de tipos de datos (type casting).


- ## `console.log` a fondo
    ```JS
    console.log("Mensaje normal");           // → Mensaje normal
    console.warn("Cuidado con esto!");       // → ⚠️ Advertencia (amarillo)
    console.error("Algo salió mal!");        // → ❌ Error (rojo)
    console.info("Información útil");        // → ℹ️ Info

    // Muy útil para ver objetos completos
    const persona = { nombre: "Carlos", edad: 25 };
    console.log(persona);                    // → { nombre: 'Carlos', edad: 25 }
    console.table(persona);                  // → Lo muestra como tabla 🔥

    // Para medir tiempo de ejecución
    console.time("mi-timer");
    // ...código...
    console.timeEnd("mi-timer");            // → mi-timer: 0.123ms
    ````
    > [!NOTE]
    > `console.table()` es especialmente útil con **arrays** de **objetos**.
- ##  Conversión de tipos de datos(Type Casting)
    > [!IMPORTANT]
    > **Conversión explícita — Tú lo haces a propósito**
    + **`String()` = Convierte a texto**
        ```JS
        const numero = 42;
        const texto = String(numero);
        console.log(texto);         // → "42"
        console.log(typeof texto);  // → string
        ```
    + **`Number()` = convierte a numero**
        ```JS
        const texto = "123";
        const numero = Number(texto);
        console.log(numero);         // → 123
        console.log(typeof numero);  // → number

        // Casos especiales importantes:
        console.log(Number("123abc")); // → NaN (Not a Number) ⚠️
        console.log(Number(""));       // → 0
        console.log(Number(true));     // → 1
        console.log(Number(false));    // → 0
        console.log(Number(null));     // → 0
        ```
    + **`Boolean()` = convierte a true / false**
        ```JS
        console.log(Boolean(1));        // → true
        console.log(Boolean(0));        // → false  ⚠️
        console.log(Boolean("hola"));   // → true
        console.log(Boolean(""));       // → false  ⚠️
        console.log(Boolean(null));     // → false  ⚠️
        console.log(Boolean(undefined));// → false  ⚠️
        ```
        > [!NOTE]
        > Los valores que se convierten a `false` se llaman **"falsy values"**: `0`, `""`, `null`, `undefined`, `NaN`, `false`. **!IMPORTANTE SABERLOS!**
    + **`parseInt` y `parseFloat` — Para strings con números**
        ```JS
        const precio = "42.99 USD";
        console.log(parseInt(precio));   // → 42   (solo entero)
        console.log(parseFloat(precio)); // → 42.99 (con decimales)

        // Diferencia con Number():
        console.log(Number("42.99 USD")); // → NaN ❌
        console.log(parseFloat("42.99 USD")); // → 42.99 ✅
        ```
    > [!IMPORTANT]
    > **Conversión implícita — JS lo hace solo (¡cuidado!)** 

    JavaScript a veces convierte tipos de datos automáticamente, lo que puede causar bugs:
    ```JS
    // Suma vs concatenación
    console.log(5 + 5);  // → 10  (número + número)
    console.log("5" + 5);  // → "55" ⚠️ JS convierte 5 a string!
    console.log("5" - 5);  // → 0   JS convierte "5" a número
    console.log("5" * "2");  // → 10  JS convierte ambos a número

    // La comparación débil (==) también hace conversión
    console.log(5 == "5"); // → true ⚠️ compara valor, ignora tipo de dato
    console.log(5 === "5"); // → false  ✅ compara valor Y tipo
    ```
    > [!TIP]
    > #### Usa siempre `===` (triple igual) para **comparar**. Nunca `==`. El `===` no hace conversión implícita.

    **`NaN` — Not a Number**
    ```JS
    const resultado = Number("abc");
    console.log(resultado); // → NaN
    console.log(typeof NaN); // → number (¡sí, es irónico!)

    // Para verificar si algo es NaN:
    console.log(isNaN("abc")); // → true
    console.log(isNaN(42));  // → false
    console.log(Number.isNaN("abc")); // → false ⚠️ (más estricto)
    console.log(Number.isNaN(NaN)); // → true  ✅
    ```
    ## 💻 EJERCICIOS
    **Ejercicio 1 — console:**
    Crea un array de objetos con 3 personas (nombre, edad, ciudad) y muéstralo con console.table().
    
    **Ejercicio 2 — Conversión:**
    Tienes estos valores. Conviértelos al tipo indicado e imprime el resultado:
    ```JS
    const a = "456";      // → convertir a Number
    const b = 0;          // → convertir a Boolean
    const c = null;       // → convertir a String
    const d = "3.75 kg";  // → extraer solo el número decimal
    const e = true;       // → convertir a Number
    ```
    **Ejercicio 3 — Trampa JS:**
    ¿Qué imprime cada línea? Primero intenta adivinarlo sin ejecutar el código, luego verifícalo:
    ```JS
    console.log("10" + 5);
    console.log("10" - 5);
    console.log(true + 1);
    console.log(null + 1);
    console.log("5" == 5);
    console.log("5" === 5);
    ```

    ## Answer
    + **`Ejecicio 1`**
        ```JS
         const personas = [
            {
                name: "Juan",
                age: 45,
                city: "Bogotá"
            },
            {
                name: "Lisa",
                age: 15,
                city: "Cali"
            },
            {
                name: "Jose",
                age: 50,
                city: "Saboyá"
            }
        ]

        // Imprimir objetos del array     
        console.table(personas); // Todos los objetos del array
        console.log(personas[0]); // Primer objeto del array
        console.log(personas[1]); // Segundo objeto del array
        console.log(personas[2]); // Tercer objeto del array
        ```
    + **`Ejecicio 2`**
        ```JS
        const a = "456";
        const numberA = Number(a); // → convertir a Number
        console.log(numberA); // 456

        const b = 0;          
        const booleanA = Boolean(b); // → convertir a Boolean
        console.log(booleanA); // false

        const c = null;       
        const stringA = String(c); // → convertir a String
        console.log(stringA); // "null"

        const d = "3.75 kg";  
        const numberB = parseFloat(d); // → extraer solo el número decimal
        console.log(numberB); // 3.75

        const e = true;       
        const numberC = Number(e); // → convertir a Number
        console.log(numberC); // 1
        ```
    + **`Ejecicio 3`**
        ```JS
        console.log("10" + 5); // Imprime "105", porque JS convierte 5 en un string
        console.log("10" - 5); // Imprime 5, porque JS convierte "10" en un numero
        console.log(true + 1); // Imprime 2 porque true == 1
        console.log(null + 1); // Imprime 1 porque null se convierte directamente a 0
        console.log("5" == 5); // Imprime true porque == no es estricto y solo compara el valor y no con el tipo de dato
        console.log("5" === 5); // Imprime false porque === es estricto y compara el valor y el tipo de dato
        ```