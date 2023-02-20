# Introducción a Kotlin

## Objetivo

En este laboratorio exploraremos los principios básicos de Kotlin como lenguaje de programación antes de empezar a aplicarlo en los principios de desarrollo móvil en Android.

Si bien atenderemos las bases del lenguaje de programación para que estés más familiarizado con el mismo. **Este no es un curso sobre Kotlin, por lo que conceptos avanzados deberás ir buscándolos conforme avance el curso**.

## Instrucciones

Sigue los pasos descritos en la siguiente práctica, si tienes algún problema no olvides que tus profesores están para apoyarte.

## Laboratorio
### Paso 1 Herramienta de trabajo

Si bien en el curso utilizaremos Android Studio la mayor parte del tiempo, para aprender los fundamentos vamos a realizarlo de una manera más simple. Para ello utilizaremos la siguiente página [Kotlin Playgrounds](https://play.kotlinlang.org/#eyJ2ZXJzaW9uIjoiMS44LjEwIiwicGxhdGZvcm0iOiJqYXZhIiwiYXJncyI6IiIsIm5vbmVNYXJrZXJzIjp0cnVlLCJ0aGVtZSI6ImlkZWEiLCJjb2RlIjoiLyoqXG4gKiBZb3UgY2FuIGVkaXQsIHJ1biwgYW5kIHNoYXJlIHRoaXMgY29kZS5cbiAqIHBsYXkua290bGlubGFuZy5vcmdcbiAqL1xuZnVuIG1haW4oKSB7XG4gICAgcHJpbnRsbihcIkhlbGxvLCB3b3JsZCEhIVwiKVxufSJ9)

Dentro de esta página observarás que ya tenemos un entorno de compilación completo, la única recomendación es que el avance que vayas teniendo lo guardes en un archivo de texto aparte o un archivo con extensión **.kts** que es la extensión de un script de Kotlin mientras te familiarizas.

### Paso 2 Hello World en Kotlin

Una vez con nuestro entorno configurado vamos a empezar con el típico **Hello World**.

Como notarás ya tenemos una función main declarada en nuestro archivo actual, como cualquier programa compilado, esta función es necesaria para poder arrancar, dependiendo el entorno donde estemos trabajando podremos añadir algunos parámetros a esta función ya que la que tenemos actualmente es:

```
fun main(){}
```

Si quisiéramos, por ejemplo, recibir parámetros desde la terminal, necesitaríamos modificarla a lo siguiente:

```
fun main(args: Array<String>){}
```

De momento no vamos a ahondar mucho en la sintaxis, es solo para que sepas que si trabajas en algún otro entorno como terminal o IntelliJ, este es el formato que puede aparecerte. Si alguna vez has trabajado con Java verás la similitud en esta declaración:

```
public static void main(String[] args){}
```

Aquí es donde empezarás a notar que mucho del código de Kotlin es una traducción de Java, las funciones más avanzadas ya son propias de Kotlin pero un programador aprendiz puede notar las similitudes entre ambos lenguajes.

Para completar este paso, escribe la función main completa de la siguiente forma, en tu caso ya debería venir escrito:

```
fun main(){
	println("Hello World")
}
```

Como puedes ver **println** muestra lo que hay dentro del paréntesis siempre en formato de String para que se muestre en la terminal. En este caso **println** sería el equivalente de **System.out.println** de Java.

Algo importante a destacar es que Kotlin es sensible a mayúsculas y minúsculas. Para probar esto escribe en vez de **println** **Println**. Si ejecutas el programa te debería salir el siguiente error:

```
Unresolved reference: Println
```

### Paso 3 Variables en Kotlin

Como ya sabes una variable, no es más que un espacio de memoria en el que podemos guardar información.

Dependiendo del tipo de información disponemos de diferentes variables, esto nos evita el intentar sumar números con letras ya que al ser de diferente tipo no nos lo permitirá.

Algo fácil de perder es que Kotlin no es un lenguaje **Script**, ya que está construido sobre Java y por tanto encima de la Java Virtual Machine, por lo tanto es un lenguaje **Compilado**.

Ahora bien, por que es fácil confundirlo, por que Kotlin hace la inferencia de tipos en algunas ocasiones, pero esta inferencia se realiza por conocimiento de tipos desde el momento de la compilación más no por que se adapte una variable al tipo como sucede en los lenguajes Script.

Para comenzar vamos a eliminar el println de nuestra función main y vamos a declarar una función del siguiente modo:

```
var numeroFavorito = 1
```

**var** nos dice que es una variable, a continuación le asignamos un nombre, en este caso **numeroFavorito** y le asignamos un valor.

Este es un perfecto ejemplo de la inferencia que realiza Kotlin, si bien no le hemos dicho quetipo de variable es, Kotlin lo ha entendido, esto por que Kotlin busca el tipo de valos, y le asigna un tipo por detrás, pero como dije, esto no siempre será correcto o siempre podrá realizarse así que en esos casos necesitamos decirle el tipo.

```
var numeroFavorito:Int = 1
```
Observa que hemos colocado dos punto y acto seguido el tipo de variable, en este caso Int.

### Paso 4 Tipos de Variables

#### Variables Numéricas
Variables para asignación de números, calculo de tamaños y realizar operaciones matemáticas entre otras. Dentro de ellas se dividen dos grupos, enteros y reales.

- Integer: Dentro de las enteras encontramos las variables Int, las más básicas que usaremos, aquí tenemos números naturales pero con limitación. Con una variable tipo **Int** no se puede pasar de los rangos  **-2,147,483,647 a** **2,147,483,647**
```
var numeroFavorito: Int = -269
```

- Long: Básicamente igual que Int, a diferencia que soporta un rango mayor de números **-9,223,372,036,854,775,807 a 9,223,372,036,854,775,807**.
```
var numeroFavorito: Long = 23740564
```

- Float: Variables reales, a diferencia de las anteriores pueden almacenar decimales con un soporte de hasta máximo 6. Aunque también pueden trabajar con números enteros. Este tipo cambia un poco con respecto a las demás, puesto que deberemos añadir una **f** al final del valor.

```
var numeroFavorito: Float = 1.93f
```

- Double: Para terminar las variables más grandes que soportan hasta 14 decimales, pero ojo, ocupan más memoria así que para un código óptimo tenemos que pensar cual es la que se adapta mejor a nuestro proyecto. En estas no necesitamos agregar ningún tipo de letra al final del valor.
```
var numeroFavorito: Double= 7.478492375
```

#### Variables Alfanuméricas

Ya que aprendimos sobre números ahora veremos como usar texto o mezclas de caracteres.

- Char: Este tipo de varibles permite guardar un caracter de cualquier tipo, lo único a tomar en cuenta es que va entre comillas simples.
```
var numeroFavorito: Char = '5'
var letraFavorita: Char = ‘h’ 
var caracterFavorito: Char = ‘@’
```

- String: Como norma general será la que más utilicemos. Permite almacenar cualquier tipo de caracteres aunque a diferencia de Char, podemos añadir la cantidad que queramos. Entonces como ya debes sabes un String es una cadena de Char, e igualmente como ya debes saber las cadenas van entre comillas dobles.
```
var numeroFavorito: String = "Mi número favorito es el 44"
var test: String = "Test. 12345!·$%&/"
```

#### Variables Booleanas

- Boolean: Variables que solo pueden ser verdaderas o falsas {true o false}. 
```
var estoyTriste: Boolean = false
var estoyFeliz: Boolean = true
```

**Nota: A estas alturas de la carrera, espero no tengas problema con los tipos básicos para el lenguaje, empezamos desde 0 para que veas los pasos para poder aprender cualquier lenguaje de programación en general, lo primero es conocer los datos primitivos del lenguaje.**

### Paso 5 Operaciones aritméticas

A continuación te mostraré los tipos de operaciones básicas que podemos realizar.

```
fun main() {
    var a = 8
    var b = 3

    print("Suma: ")
    println(a + b)

    print("Resta: ")
    println(a - b)

    print("Multiplicación: ")
    println(a * b)

    print("División: ")
    println(a / b)

    print("El módulo (resto): ")
    println(a % b)
}
```

Estas operaciones son muy básicas por lo que no debería haber ninguna complicación, ahora veremos que pasa cuando tenemos un **Float** y un **Int**.

```
fun main() {
    var a: Float = 8.5f
    var b: Int = 3

    print("Suma: ")
    var resultado = a + b

   print(resultado)
}
```

Toma nota en esta parte, esto funcionará pero solo por que no le hemos asignado un tipo a la variable resultado, por lo que de inmediato se le asignará un Float. ¿Qué pasaría si generamos la variable resultado siendo Int? Tan simple como que no funcionará, puesto que no podemos operar con variables de tipos diferentes. Para ello necesitamos del uso de la función **toInt()** que permite convertir una variable a **Int**.

```
fun main() {
    var a: Float = 10.5f
    var b: Int = 5
    var resultado: Int

    //Esto no funciona
    print("Suma: ")
    resultado =  a + b
    
    //Esto sí
    print("Suma: ")
    resultado =  a.toInt() + b
    
   print(resultado)
}
```

Otra forma de resolver el problema es haber tenido la variable resultado en **Float** y pasar b con **toFloat()**, y aquí vamos a hacer un paréntesis, tanto en Android como en cualquier algoritmo podemos encontrar soluciones diferentes a un mismo problema. Busca la solución más óptima posible, que sea sencillo y más importante aún que entiendas.

**Nota: En Kotlin tenemos varios métodos toX() { toString, toInt, toDouble, toFloat, etc. } para cambiar los valores como mejor nos convenga. Debemos tener cuidado con ellos pues si por ejemplo intentamos convertir un String en un número nos dará una excepción y el código no funcionará.**

### Paso 5 Concatenación

Si tenemos dos String, obviamente no se pueden sumar para mostrarlas, así que para eso existe la concatenación. Que en forma simple es más que un atributo para poder poner más de una variable.

La forma más tradicional de concatenación que es heredada de Java es la siguiente:

```
fun main() {
    val greeting = "Hola, me llamo"
    val name = "Alex"
    println(greeting + " " + name)
}
```

Pero si usamos la forma más actual se vería de la siguiente manera:

```
fun main() {
    val greeting = "Hola, me llamo"
    val name = "Alex"

    println("$greeting $name")
}
```

Esta nueva forma tiene algunas capacidades adicionales, como poder llamar métodos de funciones desde la misma concatenación.

Para ejecutar la concatenación solo se debe añadir las variables entre comillas dobles y anteponer a cada una de ellas el símbolo **$**. También observa que en la concatenación se añade un espacio entre ambas variables, de lo contrario aparecerá el resultado sin ese espacio.

**Nota:  Observa que en las variables colocamos val en vez de var, esto se debe a que Kotlin prefiere variables inmutables, esto significa que si nunca vamos a cambiar el valor de una variable, debemos poner val en lugar de var.**

Como te mencionaba con la concatenación también podemos hacer operaciones. Debemos cuidar cualquier error ya que de lo contrario será difícil detectarlo, pero si lo controlamos no debería haber problema.

```
val introduction = "El resultado de"
val plus = "más"
val firstNumber = 2
val secondNumber = 5

println("$introduction $firstNumber $plus $secondNumber es: ${firstNumber + secondNumber}")
```

Para este ejemplo hicimos algo más completo, donde concatenamos una frase, después hemos vuelto a añadir un $ y entre ( **{}** ) hemos metido la operación. El resultado sería este:

```
El resultado de 2 más 5 es: 7
```


### Paso 6 Funciones en Kotlin

Empezaremos a hablar de las funciones en Kotlin, en otros lenguajes también son conocidos como métodos como en Java. Una función nos es más que un conjunto de instrucciones que realizan una determinada tarea y la podemos invocar mediante su nombre.

#### Declarando funciones

Las funciones se declaran usando la palabra clave **fun**, seguida del nombre del método, los paréntesis donde declararemos los valores de entrada y unas llaves que limitan la función.

```
fun main() {
    showMyName()
    showMyLastName()
    showMyAge()
}
fun showMyName(){
    println("Me llamo Alex")
}
fun showMyLastName(){
    println("Mi Apellido es Fernández")
}
fun showMyAge(){
    println("Tengo 31 años")
}
```

Como puedes ver tenemos 4 métodos. 3 de ellos están destinados para una sola función (mostrar nombre, edad y apellidos) pero no se ejecutarán a no ser que sean llamados. Por ello el cuarto método que es el que ejecuta el código, los llamará en el orden que le pongamos. Dándonos como resultado:

```
Me llamo Alex 
Mi Apellido es Fernández 
Tengo 31 años
```

#### Funciones con parámetros de entrada

Ahora vamos a ver las funciones con parámetros de entrada, que son iguales, pero al llamarlas habrá que mandarle las variables que necesite.

```
fun main() {
    showMyInformation("Alex", "Fernández", 31)
}
fun showMyInformation(name: String, lastName: String, age: Int){
    println("Me llamo $name $lastName y tengo $age años.")
}
```

Como podemos observar, tiene tres parámetros de entrada, la forma de declararlos es muy fácil: el **nombre** de la variable, seguida de **dos puntos** y el **tipo de variable**, **aquí si es obligatorio definir el tipo**.

#### Funciones con parámetros de salida

Para poder devolver un resultado siempre debemos tener en cuenta como en otros lenguajes que la única limitación es que solo se puede devolver un parámetro.

```
fun main() {
    var result = add(2, 8)
    println(result)
}
fun add(firstNumber: Int, secondNumber: Int) : Int{
    return firstNumber + secondNumber
}
```

Tal como en el ejemplo anterior, añadimos los parámetros de entrada pero esta vez, al cerrar los paréntesis pondremos el tipo de variable que debe devolver nuestra función. Luego la función hará todo lo que tenga que hacer y cuando tenga el resultado, lo devolveremos con la palabra clave **return**.

Una novedad en Kotlin que quizás lleguemos a utilizar en Android es que si el método es muy fácil, podemos evitar las llaves y simplificar la función un poco más.

```
fun add(firstNumber: Int, secondNumber: Int) : Int = firstNumber + secondNumber
```

### Paso 7 Instrucciones Condicionales

Estas instrucciones nos permiten realizar lógica en función del resultado de una variable o condición, en este primer apartado veremos las condiciones **if-else**.

#### La condición if

Como ya debes saber, es de las más habituales y realizará una función o varias si la condición que hemos generado es verdadera.

```
fun main() {
    var result = add(3, 7)

    if(result > 5){
        println("El resultado es mayor que 5")
    }
}

fun add(firstNumber: Int, secondNumber: Int) : Int = firstNumber + secondNumber
```

Simplemente añadimos la condición entre paréntesis. No solo podemos usar operadores como <,>, = sino que podemos comparar String a través del doble igual ==

```
var name = "Alex"

if(name == ("Alex")){
    println("Se llama Alex")
}
```

#### If-Else
Hay veces que necesitaremos más de un if, y por eso está la palabra clave **else** que actuará como segundo condicional.

```
var name = "Alex"

if(name == ("Alex")){
  println("Se llama Alex")
}else{
  println("No se llama Alex")
}
```

El funcionamiento es muy claro, si no pasa la condición, entonces entrará directo en el else, así por ejemplo no necesitamos realizar 2 if, sino solo uno comprobando si el nombre es igual y otro comprobando si es diferente.

#### Anidamiento
Aunque no es la mejor práctica y en lo general **no deberíamos abusar**, en determinadas ocasiones necesitamos más condiciones, y aunque podríamos recurrir a otras instrucciones, lo podemos hacer con if.

```
if(animal == "dog"){
	println("Es un perro")
}else if(animal == "cat"){
	println("Es un gato")
}else if(animal == "bird"){
	println("Es un pájaro")
}else{
	println("Es otro animal")
}
```

Aquí hemos realizado varios anidamientos y aunque funciones como ya dijimos no es la mejor práctica.

Para poder usar más de una condición a la vez gracias a los operadores **&&** **||**

```
//solo entrará si cumple ambas condiciones
    if(animal == "dog" && raza == "labrador"){
        println("Es un perro de raza labrador")
    }

//Entrará si es verdadera una de las condiciones
    if(animal == "dog" || animal == "gato"){
        println("Es un perro o un gato")
    }
```

### Paso 8 Expresión when en Kotlin

Para seguir trabajando con el control de flujo ahora veremos el **when**. Este nos permite realizar una o varias acciones dependiendo del resultado recibido. También es posible realizarlo en el paso anterior con if-else anidados, pero no sería lo correcto. Esta sería la forma más óptima. Para hacer una comparativa desde otros lenguajes de programación sería el equivalente al **switch**.

```
fun main(args: Array<String>) {
    getMonth(2)
}
fun getMonth(month : Int){
    when (month) {
        1 -> print("Enero")
        2 -> print("Febrero")
        3 -> print("Marzo")
        4 -> print("Abril")
        5 -> print("Mayo")
        6 -> print("Junio")
        7 -> print("Julio")
        8 -> print("Agosto")
        9 -> print("Septiembre")
        10 -> print("Octubre")
        11 -> print("Noviembre")
        12 -> print("Diciembre")
        else -> {
            print("No corresponde a ningún mes del año")
        }
    }
}
```

Este ejemplo es muy sencillo, la función **getMonth** recibe un **Int** al cual se lo mandamos al  **when**, una vez ahí se comprobará todos los casos disponibles, aquí tenemos del 1 a 12. Si concuerda con algún valor automáticamente entrará por ahí y realizará la función oportuna, en este caso imprimir el mes.

Si por el contrario no encuentra ningún caso igual, entrará por el else. Dicho else no es obligatorio, por lo que se puede quitar, y si no entra por ningún caso entonces no se mostrará nada.

La expresión **when** no solo soporta números, sino que puede trabajar con textos y expresiones.

```
fun getMonth(month : Int){
    when (month) {
        1,2,3 -> print("Primer trimestre del año")
        4,5,6 -> print("segundo trimestre del año")
        7,8,9 -> print("tercer trimestre del año")
        10,11,12 -> print("cuarto trimestre del año")
    }
}
```

En este siguiente ejemplo vemos como poder separar varios valores a través de comas.

Si son rangos más altos tenemos la posibilidad de usar **in** y **lin** para trabajar con **arrays** y **ranges** (lo veremos en los siguientes pasos).

```
fun getMonth(month : Int){
    when (month) {
        in 1..6 -> print("Primer semestre")
        in 7..12 -> print("segundo semestre")
    }
}
```

Con esto podemos comprobar si está entre una cantidad de números específicos (en este caso entre 1 y 6 y 7 y 12) o si por el contrario no está en un rango específico (de 1 a 12) poniendo una exclamación al principio de la expresión **in**.

```
fun getMonth(month : Int){
    when (month) {
        in 1..6 -> print("Primer semestre")
        in 7..12 -> print("segundo semestre")
        !in 1..12 -> print("no es un mes válido")
    }
}
```

También podemos usar la expresión **is** para comprobar el tipo de variable que es.

```
fun result(value: Any){
    when (value){
        is Int -> print(value + 1)
        is String -> print("El texto es $value")
        is Boolean -> if (value) print("es verdadero") else print("es falso")
    }
}
```

Si es **Int**, sumará 1 al valor, si es un **String** lo concatenará al texto que vemos arriba y si es un **Booleano** nos pintará un resultado dependiendo si es true o false.

Para finalizar veremos que podemos guardar el resultado de un **when** automáticamente.

```
fun result(month : Int){
    val response : String = when (month) {
        in 1..6 -> "Primer semestre"
        in 7..12 -> "segundo semestre"
        !in 1..12 -> "no es un mes válido"
        else ->  "error"
    }
}
```

Hemos declarado la variable de tipo **String**, pero podríamos hacerla de tipo **Any** si no tuviéramos claro el resultado de la expresión. Aquí si es obligatorio añadir un **else**, aunque como podéis apreciar, podemos quitar los paréntesis de dicha condición.

### Paso 9 Arrays en Kotlin

Los arrays o arreglos son secuencias de datos, del mismo tipo e identificados por un nombre común.  Para hacerlo más fácil de entender imaginemos que tenemos que almacenar los 7 días de la semana, podríamos crear 7 variables Strings o almacenarlas todas en un solo array.

```
fun main() {
    val weekDays = arrayOf("Lunes", "Martes", "Miércoles", "Jueves", "Viernes", "Sábado", "Domingo")
}
```

Ahora que en la variable **weekDays** tenemos los días de la semana podremos acceder a cada uno de los valores. Esto lo haremos a través de su posición. Como sabes la posición tiene una cuenta inicial desde 0 hasta n-1 posiciones en nuestro arreglo.

```
fun main(args: Array<String>) {
 val weekDays = arrayOf("Lunes", "Martes", "Miércoles", "Jueves", "Viernes", "Sábado", "Domingo") 

    println(weekDays.get(0))
    println(weekDays.get(1))
    println(weekDays.get(2))
    println(weekDays.get(3))
    println(weekDays.get(4))
    println(weekDays.get(5))
    println(weekDays.get(6))
}
```

Igualmente como ya sabes si nos excedemos a una posición que el arreglo no tiene, por ejemplo la 7, entonces nos daría una excepción al ejecutarse la aplicación, **ArrayIndexOutOfBoundsException**, y es por ello por lo que al trabajar con arrays debemos tener bien claro el tamaño.

Otra forma de evitar ese tipo de problemas es mediante el uso del método **size** que nos devolverá el tamaño de dicho array.

```
fun main() {
    val weekDays = arrayOf("Lunes", "Martes", "Miércoles", "Jueves", "Viernes", "Sábado", "Domingo")

    println(weekDays.get(0))
    println(weekDays.get(1))
    println(weekDays.get(2))
    println(weekDays.get(3))
    println(weekDays.get(4))
    println(weekDays.get(5))
    println(weekDays.get(6))

    if(weekDays.size >= 8){
        println(weekDays.get(7))
    }else{
        println("no tiene más parámetros la array")
    }
}
```

Kotlin se encuentra en constante cambio, entonces si bien el uso del método **get** es correcto, las nuevas versiones del compilador te dirán que puedes usar el acceso directo a la propiedad, y esto es que para cada valor en una posición dada puedes acceder de la forma:

```
fun main() {
    val weekDays = arrayOf("Lunes", "Martes", "Miércoles", "Jueves", "Viernes", "Sábado", "Domingo")

    println(weekDays[0])
    println(weekDays[1])
    println(weekDays[2])
    println(weekDays[3])
    println(weekDays[4])
    println(weekDays[5])
    println(weekDays[6])
}
```

Como mencionamos, una de las limitantes de los array es que deben tener un tamaño fijo y será el número de valores que le asignemos al instanciarla, por lo que para nuestro ejemplo el tamaño siempre va a ser de 7, pero si bien no podemos añadir más, no significa que no podamos modificarlos. Esto podemos realizarlo a través de la función **set()**.

```
weekDays.set(0, "Horrible lunes") //Contenía Lunes
weekDays.set(4, "Por fin viernes") //Contenía Viernes
```

Igualmente como el acceso usando propiedad para lectura, podemos usar el acceso mediante propiedades de la forma:

```
weekDays[1] = "Un martes" //Contenía Martes
weekDays[3] = "Viernes chiquito" //Contenía Jueves
```

En cualquier caso la función **set()** recibe la posición y el valor. 

**Nota: El valor que mandemos a la asignación debe ser del mismo tipo, por ejemplo este array es de Strings, por lo que no podremos pasar un Int.**

#### Recorriendo Arrays

Ya que sabemos interactuar con arrays ahora vamos a ver como podemos recorrerlas.

Para ello tenemos el bucle **for()**, pero ojo este for es diferente al de otros lenguajes de programación.

```
fun main() {
    val weekDays = arrayOf("Lunes", "Martes", "Miércoles", "Jueves", "Viernes", "Sábado", "Domingo")

    for (posicion in weekDays.indices){
        println(weekDays.get(posicion))
    }
}
```

A diferencia del primer código nos evitamos una línea por cada posición que es lo que buscamos.

El **for** necesita una variable, en este caso **posicion** que irá teniendo el valor de cada una de las posiciones del array. Su funcionamiento es muy simple, cuanod para por el for por primera vez tendrá el valor 0, entonces comprueba el tamaño de **weekDays** u en caso de ser mayor, entra a la función, hace lo que le pidamos y vuelve a iniciar, así hasta llegar a 6 que será la última posición del array.

Otra forma de explotar el **for** es obtener tanto el índice como el valor directamente, para ello se hace lo siguiente:

```
fun main() {
    val weekDays = arrayOf("Lunes", "Martes", "Miércoles", "Jueves", "Viernes", "Sábado", "Domingo")

    for ((posicion, valor) in weekDays.withIndex()) {
        println("La posición $posicion contiene el valor $valor")
    }
}
```

El resultado sería el siguiente:

```
La posición 0 contiene el valor Lunes 
La posición 1 contiene el valor Martes 
La posición 2 contiene el valor Miércoles 
La posición 3 contiene el valor Jueves 
La posición 4 contiene el valor Viernes 
La posición 5 contiene el valor Sábado 
La posición 6 contiene el valor Domingo
```

Si por el contrario solo nos interesa el contenido podríamos realizar el **for** sin acceder a la posición, solo al contenido.

```
for (weekDay in weekDays) {
  println(weekDay)
}
```

### Paso 10 Listas en Kotlin

En el paso anterior hablamos de los arreglos, pero como ya sabemos su principal inconveniente es la limitación al definirlos.

#### Tipos de listas

Las colecciones se pueden clasificar en dos grandes grupos, las mutables e inmutables. Es decir, las que se pueden editar **mutables** y las que son solo de lectura **inmutable**.

#### Listas inmutables

La declaración de una lista inmutable sería así:

```
val readOnly: List<String> = listOf("Lunes", "Martes", "Miércoles", "Jueves", "Viernes", "Sábado", "Domingo")
```

Para poder trabajar con estos tipos de lista existen varias funciones:

```
val readOnly: List<String> = listOf("Lunes", "Martes", "Miércoles", "Jueves", "Viernes", "Sábado", "Domingo")

readOnly.size //Muestra el tamaño de la lista
readOnly.get(3) //Devuelve el valor de la posición 3
readOnly.first() //Devuelve el primer valor
readOnly.last() //Devuelve el último valor
println(readOnly) //[Lunes, Martes, Miércoles, Jueves, Viernes, Sábado, Domingo]
```

Como ves podemos trabajar completamente con ellas con la excepción de poder añadir más elementos, tal y como en los arrays.

Si conoces conceptos de programación funcional, notarás el uso del **first()** y del **last()**, esto en Kotlin se va utilizando mediante el uso de funciones lamda que justamente añaden este paradigma de programación al lenguajes además del orientado a objetos.

Con eso dicho podríamos filtrar usando el patrón iterator, que es un mecanismo para acceder a los elementos de la lista, por ejemplo **first()** o **last()** usando una función lambda.

```
val a = readOnly.filter { it == "Lunes" || it == "Juernes" }
```

Para este ejemplo el **filter()** nos permite filtrar en la lista a través de una o varias condiciones que pongamos. Para ello lamamamos a it (iterator) y buscaremos en la lista, si contiene la palabra **Lunes** o **Juernes**. En este caso solo pintará **Lunes**.

#### Listas mutables

Ahora nos toca hablar de las más interesantes y dinámicas, las listas mutables, que poseen todo lo anterior, pero también nos dan la posibilidad de ir rellenando la lista a medida que lo necesitemos, **el único inconveniente es que es más ineficiente con la memoria**.

```
var mutableList: MutableList<String> = mutableListOf("Lunes", "Martes", "Miércoles", "Jueves", "Viernes", "Sábado")

    mutableList.add("domingo")
```

La definición es muy similar, a través de la función **mutableListOf**. Ahora si te das cuenta el ejemplo añade de Lunes a Sábado, luego usando el método **add** se añade el Domingo.

Por defecto los valores se irán añadiendo  en la última posición, pero podemos añadir el índice en el que queramos escribir el valor.

```
mutableList.add(0, "Semana: ")
```

Si imprimiéramos el valor actual de la lista aparecería lo siguiente.

```
[Semana: , Lunes, Martes, Miércoles, Jueves, Viernes, Sábado, domingo]
```

Aquí es donde empiezan las complicaciones, ya que una lista podría estar vacía o contener un null. El **null** en Kotlin es un valor nulo en cada una de sus posiciones, que, si accedemos a él e intentamos realizar alguna función, la aplicación fallará, nos soltará un **crash**. Para ello, tenemos algunas funciones que nos permitirán trabajar como una lista inmutable, pero con seguridad.

```
var mutableList: MutableList<String> = mutableListOf()

   mutableList.none() //Nos devuelve un true si está vacía la lista
   mutableList.firstOrNull() //Nos devolverá el primer campo, y si no hay, un null.
   mutableList.elementAtOrNull(2) //El elemento del índice 2, si no hay, devolverá un null
   mutableList.lastOrNull() //Último valor de la lista o null
```

En este ejemplo se crea la lista sin ningún valor, por lo que la lista está vacía. Con todos estos métodos recuperaremos un **null** (menos el primero que dará true) y la aplicación seguirá corriendo. Pero si por el contrario hubiéramos añadido un **first()** hubieramos obtenido:

```
Exception in thread "main" java.util.NoSuchElementException: List is empty.  
at kotlin.collections.CollectionsKt___CollectionsKt.first (_Collections.kt:214)  
at FileKt.main (File.kt:4)  
at FileKt.main (File.kt:-1)
```

Esto pasa no solo con las listas sino también con cualquier dato mutables, por lo que debemos tener mucho cuidado a la hora de trabajar con datos que puedan ser modificados.

#### Recorriendo listas

Igual que en el paso anterior de arrays, aquí hay formas muy similares para recorrerlas.

Esta sería la forma más sencilla, y nos devolvería el contenido de cada uno de los valores de la lista.

```
for (item in mutableList) {
      print(item)
  }
```

Si necesitamos saber la posición de cada uno de los valores podemos usar la función **withIndex** que nos permite generar 2 variables, la primera será la posición y la segunda el contenido.

```
for ((indice, item) in mutableList.withIndex()) {
      println("La posición $indice contiene $item")
  }
```

Para el último ejemplo, usaremos **forEach**, una función que hará que por cada posición haga una cosa, por ejemplo pintar el valor como el for anterior. A diferencia de ellos, no tenemos una variable con el contenido sino que accedemos a él con el iterator, ente caso simplemente habría que poner it.

En el siguiente ejemplo imaginemos que queremos añadir a los días de la semana dos puntos **:** así que vamos a crear una nueva lista **mutable** e iremos rellenando la lista a través del **forEach**.

```
val mutableList: MutableList<String> = mutableListOf("Lunes", "Martes", "Miércoles", "Jueves", "Viernes", "Sábado")
  val newListEmpty: MutableList<String> = mutableListOf()

  mutableList.forEach {
      newListEmpty.add(it+":")
  }

  print(newListEmpty)
```

### Ejercicios

Ya que hemos revisado los conceptos básicos de Kotlin paso a paso, es momento de que empieces con uno de los elementos fundamentales de este curso y es a **hacerte dueño de tu aprendizaje.**

A continuación te dejaré los [Kotlin Challenges](https://github.com/igorwojda/kotlin-coding-challenges) que nos son más que problemas para seguir reforzando el aprendizaje de Kotlin.

Esto te podrá llevar a trabajar más en tu lógica de programación o en su defecto buscar algunas librerías adicionales para trabajar el lenguaje y hacerte la vida más simple.

De acuerdo a tu experiencia actual implementa algunos de estos problemas para terminar de reforzar los conceptos vistos, si te es necesario práctica de tarea.

**Recuerda que este módulo no cuenta con tareas a entregar, pero en el examen final se espera que el alumno cumpla con los conocimientos básicos del lenguaje, así como las evidencias de los mismos para el desarrollo de competencias.**

**Nota: Entre más complejo sea el problema resuelto esto puede beneficiarte en las evidencias de tus competencias de desarrollo.**