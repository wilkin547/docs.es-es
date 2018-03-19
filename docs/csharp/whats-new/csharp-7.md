---
title: "Novedades de C# 7: guía de C#"
description: "Obtenga información general sobre las nuevas características que entran en la próxima versión 7 del lenguaje C#."
keywords: "C#, .NET, .NET Core, Características más recientes, Novedades"
author: BillWagner
ms.author: wiwagn
ms.date: 12/21/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: fd41596d-d0c2-4816-b94d-c4d00a5d0243
ms.openlocfilehash: 374ac9917464a7e83566440abab10eda8a9c8683
ms.sourcegitcommit: 83dd5ec003e788ccb3e33f3412a7af39ae347646
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2018
---
# <a name="whats-new-in-c-7"></a>Novedades de C# 7

C# 7 incorpora varias características nuevas al lenguaje C#:
* [Variables de `out`](#out-variables)
    - Puede declarar valores `out` que se inserten como argumentos en el método en que se usen.
* [Tuplas](#tuples)
    - Puede crear tipos ligeros sin nombre que contengan varios campos públicos. Los compiladores y las herramientas IDE comprenden la semántica de estos tipos.
* [Descartes](#discards)
    - Los descartes son variables temporales y de solo escritura que se usan en argumentos cuando el valor asignado es indiferente. Son especialmente útiles al deconstruir tuplas y tipos definidos por el usuario, así como al realizar llamadas a métodos mediante parámetros de `out`.
* [Coincidencia de patrones](#pattern-matching)
    - Puede crear la lógica de bifurcación en función de tipos y valores arbitrarios de los miembros de esos tipos.
* [Devoluciones y variables locales `ref`](#ref-locals-and-returns)
    - Los argumentos de método y las variables locales pueden ser referencias a otro dispositivo de almacenamiento.
* [Funciones locales](#local-functions)
    - Puede anidar funciones en otras funciones para limitar su ámbito y visibilidad.
* [Más miembros con forma de expresión](#more-expression-bodied-members)
    - La lista de miembros que se pueden crear con expresiones ha crecido.
* [Expresiones `throw`](#throw-expressions)
    - Puede iniciar excepciones en construcciones de código que antes no se permitían porque `throw` era una instrucción. 
* [Tipos de valor devueltos de async generalizados](#generalized-async-return-types)
    - Los métodos declarados con el modificador `async` pueden devolver otros tipos además de `Task` y `Task<T>`.
* [Mejoras en la sintaxis de literales numéricos](#numeric-literal-syntax-improvements)
    - Nuevos tokens mejoran la legibilidad de las constantes numéricas.

En el resto de este tema se tratan cada una de las características. Para cada característica, conocerá el razonamiento subyacente. Aprenderá la sintaxis. Verá algunos escenarios de ejemplo en que, al usar la nueva característica, será más productivo como desarrollador. 

## <a name="out-variables"></a>Variables `out`

En esta versión se ha mejorado la sintaxis existente que admite parámetros `out`.  

Anteriormente, tendría que separar la declaración de la variable out y su inicialización en dos instrucciones diferentes:

[!code-csharp[OutVariableOldStyle](../../../samples/snippets/csharp/new-in-7/program.cs#03_OutVariableOldStyle "classic out variable declaration")]

Ahora puede declarar variables `out` en la lista de argumentos de una llamada a método, en lugar de escribir una instrucción de declaración distinta:

[!code-csharp[OutVariableDeclarations](../../../samples/snippets/csharp/new-in-7/program.cs#01_OutVariableDeclarations "Out variable declarations")]

Para mayor claridad, puede que prefiera especificar el tipo de la variable `out`, tal y como se muestra anteriormente. Pero el lenguaje admite el uso de una variable local con tipo implícito:

[!code-csharp[OutVarVariableDeclarations](../../../samples/snippets/csharp/new-in-7/program.cs#02_OutVarVariableDeclarations "Implicitly typed Out variable")]

* El código es más fácil de leer. 
    - Declare la variable out donde la use, no en otra línea anterior.
* No es preciso asignar ningún valor inicial.
    - Al declarar la variable `out` donde se usa en una llamada a método, no podrá usarla accidentalmente antes de que se asigne.

El uso más común de esta característica será el patrón `Try`. En este patrón, un método devuelve un `bool` que indica éxito o error y una variable `out` que proporciona el resultado si el método tiene éxito.

Cuando se usa la declaración de variable `out`, la variable declarada "se pierde" en el ámbito externo de la instrucción if. Esto permite usar la variable después:

```csharp
if (!int.TryParse(input, out int result))
{    
    return null;
}

return result;
```

## <a name="tuples"></a>Tuplas

> [!NOTE]
> Las nuevas características de tupla requieren los tipos <xref:System.ValueTuple>.
> Debe agregar el paquete NuGet [`System.ValueTuple`](https://www.nuget.org/packages/System.ValueTuple/) para usarlo en plataformas que no incluyen los tipos.
>
> Esto es similar a otras características del lenguaje que se basan en tipos que se han proporcionado en el marco. El ejemplo incluye `async` y `await`, que se basan en la interfaz `INotifyCompletion`. LINQ se basa en `IEnumerable<T>`. En cambio, el mecanismo de entrega está cambiando a medida que .NET está pasando a ser más independiente de las plataformas. Puede que .NET Framework no proporcione siempre la misma cadencia que el compilador de lenguaje. Cuando las nuevas características del lenguaje se basan en tipos nuevos, esos tipos estarán disponibles como paquetes NuGet cuando se proporcionen las características del lenguaje. Como estos tipos nuevos se agregan a la API de .NET Standard y se proporcionan como parte del marco, el requisito del paquete NuGet se quitará.

C# ofrece una sintaxis enriquecida para clases y estructuras que se usa para explicar la intención del diseño. Pero a veces esa sintaxis enriquecida requiere trabajo adicional con apenas beneficio. Puede que a menudo escriba métodos que requieren una estructura simple que contenga más de un elemento de datos. Para admitir estos escenarios, se han agregado *tuplas* a C#. Las tuplas son estructuras de datos ligeros que contienen varios campos para representar los miembros de datos.
Los campos no se validan y no se pueden definir métodos propios

> [!NOTE]
> Las tuplas estaban disponibles antes de C# 7, pero no eran eficientes y no eran compatibles con ningún lenguaje.
> Esto significaba que solo se podía hacer referencia a los elementos tupla como `Item1`, `Item2`, por ejemplo. C# 7 presenta la compatibilidad con lenguajes para las tuplas, lo que permite usar nombres de semántica en los campos de una tupla mediante tipos de tupla nuevos y más eficientes.

Puede crear una tupla asignando cada miembro a un valor:

[!code-csharp[UnnamedTuple](../../../samples/snippets/csharp/new-in-7/program.cs#04_UnnamedTuple "Unnamed tuple")]

Esta asignación crea una tupla con los miembros `Item1` y `Item2`. Se puede usar del mismo modo que <xref:System.Tuple>. Además, puede cambiar la sintaxis para crear una tupla que proporciona nombres de semántica a cada uno de sus miembros:

[!code-csharp[NamedTuple](../../../samples/snippets/csharp/new-in-7/program.cs#05_NamedTuple "Named tuple")]

La tupla `namedLetters` contiene campos denominados `Alpha` y `Beta`. Esos nombres solo existen en el tiempo de compilación y no se conservan, por ejemplo, al inspeccionar la tupla mediante una reflexión en tiempo de ejecución.

En la asignación de una tupla, también pueden especificarse los nombres de los campos a la derecha de la asignación:

[!code-csharp[ImplicitNamedTuple](../../../samples/snippets/csharp/new-in-7/program.cs#06_ImplicitNamedTuple "Implicitly named tuple")]

Puede especificar nombres para los campos a la izquierda y la derecha de la asignación:

[!code-csharp[NamedTupleConflict](../../../samples/snippets/csharp/new-in-7/program.cs#07_NamedTupleConflict "Named tuple conflict")]

La línea anterior genera una advertencia, `CS8123`, que indica que los nombres a la derecha de la asignación, `Alpha` y `Beta`, se omiten porque entran en conflicto con los nombres a la izquierda, `First` y `Second`.

Los ejemplos anteriores muestran la sintaxis básica para declarar tuplas. Las tuplas resultan más útiles como tipos de valor devuelto para los métodos `private` y `internal`. Las tuplas ofrecen una sintaxis sencilla para que dichos métodos devuelvan varios valores discretos: Se ahorra el trabajo de crear un `class` o un `struct` que defina el tipo devuelto. No hay necesidad de crear otra tupla.

La creación de tuplas resulta más eficiente y productiva.
Se trata de una sintaxis ligera y más sencilla para definir una estructura de datos que incluya más de un valor. El siguiente método de ejemplo devuelve los valores mínimos y máximos de una secuencia de enteros:

[!code-csharp[TupleReturningMethod](../../../samples/snippets/csharp/new-in-7/program.cs#08_TupleReturningMethod "Tuple returning method")]

El uso de tuplas de esta manera supone varias ventajas:

* Se ahorra el trabajo de crear un `class` o un `struct` que defina el tipo devuelto. 
* No tiene que crear otro tipo.
* Las mejoras del lenguaje hacen innecesario llamar al método <xref:System.Tuple.Create``1(``0)>.

La declaración del método proporciona los nombres de los campos de la tupla que se devuelve. Cuando se llama al método, el valor devuelto es una tupla cuyos campos son `Max` y `Min`:

[!code-csharp[CallingTupleMethod](../../../samples/snippets/csharp/new-in-7/program.cs#09_CallingTupleMethod "Calling a tuple returning method")]

Puede que a veces quiera desempaquetar los miembros de una tupla devueltos de un método.  Para ello, declare distintas variables para cada uno de los valores de la tupla. Esto se denomina *deconstruir* la tupla:

[!code-csharp[CallingWithDeconstructor](../../../samples/snippets/csharp/new-in-7/program.cs#10_CallingWithDeconstructor "Deconstructing a tuple")]

<!-- Add wildcards here, if they are in C# 7
-->

También puede proporcionar una deconstrucción similar para cualquier tipo de .NET. Para ello, escriba un método `Deconstruct` como miembro de la clase. Ese método `Deconstruct` proporciona un conjunto de argumentos `out` para cada una de las propiedades que quiere extraer. Tenga en cuenta que esta clase `Point` proporciona un método deconstructor que extrae las coordenadas `X` e `Y`:

[!code-csharp[PointWithDeconstruction](../../../samples/snippets/csharp/new-in-7/point.cs#11_PointWithDeconstruction "Point with deconstruction method")]
 
Puede extraer los campos individuales asignando una tupla a un `Point`:

[!code-csharp[DeconstructPoint](../../../samples/snippets/csharp/new-in-7/program.cs#12_DeconstructPoint "Deconstruct a point")]

No está obligado por los nombres definidos en el método `Deconstruct`. Puede cambiar el nombre de las variables de extracción como parte de la asignación:  

[!code-csharp[DeconstructNames](../../../samples/snippets/csharp/new-in-7/program.cs#13_DeconstructNames "Deconstruct with new names")]

Puede aprender más sobre tuplas en el [tema sobre tuplas](../tuples.md).

## <a name="discards"></a>Descartes

Habitualmente, al deconstruir una tupla o realizar una llamada a un método mediante parámetros `out`, debe definir una variable con un valor indiferente y que no vaya a usar. C# agrega la compatibilidad con *descartes* para gestionar este tipo de escenarios. Un descarte es una variable de solo escritura con el nombre `_` (el carácter de guion bajo). Puede asignar todos los valores que quiera descartar a una única variable. Un descarte se parece a una variable no asignada, aunque no puede usarse en el código (excepto la instrucción de asignación).

Los descartes se admiten en los escenarios siguientes:

* Al deconstruir tuplas o tipos definidos por el usuario.

* Al realizar llamadas a métodos mediante parámetros [out](../language-reference/keywords/out-parameter-modifier.md).

* En una operación de coincidencia de patrones con las instrucciones [is](../language-reference/keywords/is.md) y [switch](../language-reference/keywords/switch.md).

* Como un identificador independiente cuando quiera identificar explícitamente el valor de una asignación como descarte.

En el ejemplo siguiente se define un método `QueryCityDataForYears` que devuelve una tupla de tipo 6 con datos de una ciudad correspondientes a dos años diferentes. La llamada de método del ejemplo se refiere únicamente a los dos valores de rellenado que devuelve el método, por lo que trata los valores restantes de la tupla como descartes al deconstruirla.

[!code-csharp[Tuple-discard](../../../samples/snippets/csharp/programming-guide/deconstructing-tuples/discard-tuple1.cs)]

Para obtener más información, vea [Descartes](../discards.md).
 
## <a name="pattern-matching"></a>Detección de patrones

La *coincidencia de patrones* es una característica que permite implementar la distribución de métodos en propiedades distintas al tipo de un objeto. Probablemente ya esté familiarizado con la distribución de métodos en función del tipo de un objeto. En la programación orientada a objetos, los métodos virtuales y de invalidación proporcionan la sintaxis del lenguaje para implementar la distribución de métodos en función del tipo de un objeto. Las clases base y derivadas proporcionan distintas implementaciones. Las expresiones de coincidencia de patrones extienden este concepto para que se puedan implementar fácilmente patrones de distribución similares para tipos y elementos de datos que no se relacionan mediante una jerarquía de herencia. 

La coincidencia de patrones admite expresiones `is` y `switch`. Cada una de ellas habilita la inspección de un objeto y sus propiedades para determinar si el objeto cumple el patrón buscado. Use la palabra clave `when` para especificar reglas adicionales para el patrón.

### <a name="is-expression"></a>Expresión `is`

Las expresiones de patrón `is` extienden el conocido operador `is` para consultar un objeto más allá de su tipo.

Comencemos por un escenario sencillo. Agregaremos funciones a este escenario que muestren cómo las expresiones de coincidencia de patrones crean algoritmos que funcionan fácilmente con tipos no relacionados. Empezaremos por un método que calcule la suma de varias tiradas de dados:

[!code-csharp[SumDieRolls](../../../samples/snippets/csharp/new-in-7/patternmatch.cs#14_SumDieRolls "Sum die rolls")]

Es posible que descubra rápidamente que tiene que encontrar la suma de tiradas de dados en las que algunas de las tiradas se realizan con más de un dado. Puede que parte de la secuencia de entrada tenga varios resultados en lugar de un solo número:

[!code-csharp[SumDieRollsWithGroups](../../../samples/snippets/csharp/new-in-7/patternmatch.cs#15_SumDieRollsWithGroups "Sum die rolls with groups")]

La expresión de patrón `is` funciona bastante bien en este escenario. Como parte de la comprobación del tipo, escriba una variable de inicialización. Esta crea otra variable del tipo de tiempo de ejecución validado.

Mientras siga extendiendo estos escenarios, puede que vea que crea más instrucciones `if` y `else if`. Cuando esto resulte poco manejable, probablemente prefiera cambiar a expresiones de patrón `switch`.

### <a name="switch-statement-updates"></a>Actualizaciones de instrucciones `switch`

La *expresión de coincidencia* tiene una sintaxis conocida, que se basa en la instrucción `switch` que ya forma parte del lenguaje C#. Vamos a traducir el código existente para usar una expresión de coincidencia antes de agregar nuevos casos: 

[!code-csharp[SumUsingSwitch](../../../samples/snippets/csharp/new-in-7/patternmatch.cs#16_SumUsingSwitch "Sum using switch")]

Las expresiones de coincidencia tienen una sintaxis ligeramente distinta que las expresiones `is`, donde el tipo y la variable se declaran al principio de la expresión `case`.

Las expresiones de coincidencia también admiten constantes. Esto puede ahorrar tiempo al no tener en cuenta casos sencillos:

[!code-csharp[SwitchWithConstants](../../../samples/snippets/csharp/new-in-7/patternmatch.cs#17_SwitchWithConstants "Switch with constants")]

El código anterior agrega casos de `0` como un caso especial de `int` y `null` como un caso especial cuando no hay ninguna entrada. Muestra una nueva característica importante en expresiones de patrón de modificador: el orden de las expresiones `case` ahora cuenta. El caso `0` debe aparecer antes del caso general `int`. De lo contrario, el primer patrón que coincida sería el caso `int`, aunque el valor sea `0`. Si accidentalmente ordena expresiones de coincidencia como estas una vez controlado el último caso, el compilador las marcará y generará un error.

Este mismo comportamiento habilita el caso especial en una secuencia de entrada vacía.
Puede ver que el caso de un elemento `IEnumerable` que tiene elementos debe aparecer antes que el caso general `IEnumerable`.

En esta versión se ha agregado también un caso `default`. El caso `default` siempre se evalúa en último lugar, independientemente del orden en que aparezca en el origen. Por ese motivo, la convención es poner el caso `default` al final.

Por último, agregaremos un último `case` para un nuevo estilo de dado. Algunos juegos usan dados de percentil para representar intervalos mayores de números. 

> [!NOTE]
> Dos dados de percentil de 10 caras pueden representar todos los números del 0 al 99. Un dado tiene caras etiquetadas con `00`, `10`, `20`, ...`90`. El otro tiene caras etiquetadas con `0`, `1`, `2`, ...`9`. Sume los valores de los dos dados y podrá obtener todos los números del 0 al 99.

Para agregar este tipo de dado a la colección, defina primero un tipo que represente el dado de percentil. La propiedad `TensDigit` almacena hasta `90` valores `0`, `10` y `20`:

[!code-csharp[18_PercentileDice](../../../samples/snippets/csharp/new-in-7/patternmatch.cs#18_PercentileDice "Percentile Die type")]

Después agregue una expresión de coincidencia `case` para el nuevo tipo:

[!code-csharp[SwitchWithNewTypes](../../../samples/snippets/csharp/new-in-7/patternmatch.cs#19_SwitchWithNewTypes "Include Percentile Die type")]

La nueva sintaxis de expresiones de coincidencia de patrones facilita la creación de algoritmos de distribución basados en un tipo del objeto o en otras propiedades, mediante una sintaxis clara y concisa. Las expresiones de coincidencia de patrones habilitan estas construcciones en tipos de datos que no se relacionan por herencia.

Puede obtener más información sobre la coincidencia de patrones en el tema dedicado a [coincidencia de patrones en C#](../pattern-matching.md).

## <a name="ref-locals-and-returns"></a>Devoluciones y variables locales ref

Esta característica habilita algoritmos que usan y devuelven referencias a variables definidas en otro lugar. Por ejemplo, trabajar con matrices de gran tamaño y buscar una sola ubicación con determinadas características. Un método devolvería los dos índices para una sola ubicación en la matriz:

[!code-csharp[FindReturningIndices](../../../samples/snippets/csharp/new-in-7/MatrixSearch.cs#20_FindReturningIndices "Find returning indices")]

Existen varios problemas con este código. En primer lugar, se trata de un método público que devuelve una tupla. El lenguaje admite esto, pero se recomienda usar tipos definidos por el usuario (clases o structs) para las API públicas.

En segundo lugar, este método devuelve los índices al elemento de la matriz.
Esto lleva a los autores de llamadas a escribir código que use esos índices para desreferenciar la matriz y modificar un solo elemento:

[!code-csharp[UpdateItemFromIndices](../../../samples/snippets/csharp/new-in-7/program.cs#21_UpdateItemFromIndices "Update Item From Indices")]

Es preferible escribir un método que devuelva una *referencia* al elemento de la matriz que quiere cambiar. Esto solo podría llevarse a cabo si usa un código no seguro y devuelve un puntero a un `int` en versiones anteriores.

Repasaremos una serie de cambios que muestran la característica local ref y cómo crear un método que devuelva una referencia al almacenamiento interno.
Por el camino, conocerá las reglas de devolución de ref y la característica de la variable local ref que impide que accidentalmente se haga un uso incorrecto de ella.

Empiece por modificar la declaración de método `Find` para que devuelva un `ref int` en lugar de una tupla. Luego modifique la instrucción return para que devuelva el valor almacenado en la matriz y no en los dos índices:

```csharp
// Note that this won't compile. 
// Method declaration indicates ref return,
// but return statement specifies a value return.
public static ref int Find2(int[,] matrix, Func<int, bool> predicate)
{
    for (int i = 0; i < matrix.GetLength(0); i++)
        for (int j = 0; j < matrix.GetLength(1); j++)
            if (predicate(matrix[i, j]))
                return matrix[i, j];
    throw new InvalidOperationException("Not found");
}
```

Cuando se declara que un método devuelva una variable `ref`, debe agregarse también la palabra clave `ref` a cada instrucción return. Esto indica una devolución por referencia y ayuda a que los desarrolladores que lean el código después recuerden que el método devuelve por referencia:

[!code-csharp[FindReturningRef](../../../samples/snippets/csharp/new-in-7/MatrixSearch.cs#22_FindReturningRef "Find returning by reference")]

Ahora que el método devuelve una referencia al valor entero de la matriz, hay que modificar dónde se llama.  La declaración `var` indica que `valItem` es ahora un `int` en lugar de una tupla:

[!code-csharp[AssignRefReturnToValue](../../../samples/snippets/csharp/new-in-7/program.cs#23_AssignRefReturnToValue "Assign ref return to value")]

La segunda instrucción `WriteLine` del ejemplo anterior imprime el valor `42`, no `24`. La variable `valItem` es un `int`, no un `ref int`. La palabra clave `var` permite que el compilador especifique el tipo, pero no agregará implícitamente el modificador `ref`. En su lugar, el valor al que hace referencia el `ref return` se *copia* en la variable a la izquierda de la asignación. La variable no es una variable local `ref`.

Para obtener el resultado que quiere, debe agregar el modificador `ref` a la declaración de variable local para convertir la variable en una referencia cuando el valor devuelto sea una referencia:

[!code-csharp[AssignRefReturn](../../../samples/snippets/csharp/new-in-7/program.cs#24_AssignRefReturn "Assign ref return")]

Ahora, la segunda instrucción `WriteLine` del ejemplo anterior imprimirá el valor `24`, que indica que se ha modificado el almacenamiento en la matriz. La variable local se ha declarado con el modificador `ref` y tomará un valor devuelto `ref`. Debe inicializar una variable `ref` cuando se declara, no puede separar la declaración de la inicialización.

El lenguaje C# tiene otras tres reglas que protegen del uso incorrecto de las variables locales y devoluciones de `ref`:

* No se puede asignar un valor devuelto del método estándar para una variable local `ref`.
    - No permite instrucciones como `ref int i = sequence.Count();`
* No puede devolver un `ref` a una variable cuya duración se extiende más allá de la ejecución del método.
    - Esto significa que no puede devolver una referencia a una variable local o a una variable con un ámbito similar.
* Las `ref` locales y las devoluciones no se pueden usar con métodos asíncronos.
    - El compilador no puede identificar si una variable a la que se hace referencia se ha establecido en su valor final en la devolución del método asíncrono.

La incorporación de variables locales ref y devoluciones de ref permite usar algoritmos que resultan más eficientes si se evita copiar los valores o se realizan operaciones de desreferencia varias veces. 

## <a name="local-functions"></a>Funciones locales

Muchos diseños de clases incluyen métodos que se llaman desde una sola ubicación. Estos métodos privados adicionales mantienen cada método pequeño y centrado. Pero pueden complicar la comprensión de una clase cuando se lee por primera vez. Estos métodos deben entenderse fuera del contexto de la ubicación de llamada única.

En esos diseños, las *funciones locales* permiten declarar métodos en el contexto de otro método. Esto facilita que los lectores de la clase vean que el método local solo se llama desde el contexto en el que se declara.

Hay dos casos de uso muy común para funciones locales: métodos de iterador públicos y métodos asincrónicos públicos. Ambos tipos de métodos generan código que informa de errores más tarde de lo que los programadores podrían esperar. En el caso de los métodos de iterador, las excepciones solo se observan al llamar a código que enumera la secuencia devuelta. En el caso de los métodos asincrónicos, las excepciones solo se observan cuando se espera al `Task` devuelto.

Empecemos por un método de iterador:

[!code-csharp[IteratorMethod](../../../samples/snippets/csharp/new-in-7/Iterator.cs#25_IteratorMethod "Iterator method")]

Examine el código siguiente que llama al método de iterador incorrectamente:

[!code-csharp[CallIteratorMethod](../../../samples/snippets/csharp/new-in-7/program.cs#26_CallIteratorMethod "Call iterator method")]

La excepción se inicia cuando se itera `resultSet`, no cuando se crea `resultSet`.
En este ejemplo independiente, la mayoría de los desarrolladores diagnosticarían en seguida el problema. Pero, en bases de datos de mayor tamaño, el código que crea un iterador no suele estar tan cerca del código que enumerar el resultado. Puede refactorizar el código para que el método público valide todos los argumentos y un método privado genere la enumeración:

[!code-csharp[IteratorMethodRefactored](../../../samples/snippets/csharp/new-in-7/Iterator.cs#27_IteratorMethodRefactored "Iterator method refactored")]

Esta versión refactorizada iniciará excepciones inmediatamente porque el método público no es un método de iterador; solo el método privado usa la sintaxis `yield return`. Pero hay posibles problemas con esta refactorización. El método privado solo debe llamarse desde el método de interfaz público, ya que de lo contrario se omiten todas las validaciones de argumento.
Los lectores de la clase deben detectar este hecho al leer toda la clase y buscar cualquier otra referencia al método `alphabetSubsetImplementation`.

Puede dejar más clara la intención del diseño declarando la `alphabetSubsetImplementation` como función local dentro del método API público:

[!code-csharp[22_IteratorMethodLocal](../../../samples/snippets/csharp/new-in-7/Iterator.cs#28_IteratorMethodLocal "Iterator method with local function")]

La versión anterior deja claro que hace referencia al método local solo en el contexto del método externo. Las reglas para las funciones locales también garantizan que un desarrollador no pueda llamar accidentalmente a la función local desde otra ubicación de la clase y omitir la validación del argumento.

La misma técnica se puede emplear con métodos `async` para asegurarse de que las excepciones derivadas de la validación de argumentos se inician antes de comenzar el trabajo asincrónico:

[!code-csharp[TaskExample](../../../samples/snippets/csharp/new-in-7/AsyncWork.cs#29_TaskExample "Task returning method with local function")]

> [!NOTE]
> Algunos de los diseños que se admiten con funciones locales también se podrían realizar con *expresiones lambda*. Aquellos que estén interesados pueden [obtener más información sobre las diferencias](../local-functions-vs-lambdas.md)

## <a name="more-expression-bodied-members"></a>Más miembros con forma de expresión

En C# 6 se presentaron los [miembros con forma de expresión](csharp-6.md#expression-bodied-function-members) para funciones de miembros y propiedades de solo lectura. C# 7 amplía los miembros permitidos que pueden implementarse como expresiones. En C# 7, se pueden implementar *constructores*, *finalizadores* y descriptores de acceso `get` y `set` en *propiedades* e *indexadores*. En el código siguiente se muestran ejemplos de cada uno:

[!code-csharp[ExpressionBodiedMembers](../../../samples/snippets/csharp/new-in-7/expressionmembers.cs#36_ExpressionBodiedEverything "new expression-bodied members")]

> [!NOTE]
> En este ejemplo no se requiere un finalizador, pero se muestra para demostrar la sintaxis. No debe implementar un finalizador en la clase salvo que sea necesario para liberar recursos no administrados. También debe plantearse el uso de la clase <xref:System.Runtime.InteropServices.SafeHandle> en lugar de administrar directamente los recursos no administrados.

Estas nuevas ubicaciones de miembros con forma de expresión representan un hito importante en el lenguaje C#: estas características las han implementado miembros de la comunidad que trabajan en el proyecto de código abierto [Roslyn](https://github.com/dotnet/Roslyn).

## <a name="throw-expressions"></a>Expresiones throw

En C#, `throw` siempre ha sido una instrucción. Dado que `throw` es una instrucción, no una expresión, había construcciones de C# en las que no se podía usar. Incluyen expresiones condicionales, expresiones de fusión nulas y algunas expresiones lambda. La incorporación de miembros con forma de expresión agrega más ubicaciones donde las expresiones `throw` resultarían útiles. Para que pueda escribir cualquiera de estas estructuras, C# 7 presenta las *expresiones throw*.

La sintaxis es la misma que siempre ha usado con instrucciones `throw`. La única diferencia es que ahora puede colocarlas en nuevas ubicaciones, como en una expresión condicional:

[!code-csharp[Throw_ExpressionExample](../../../samples/snippets/csharp/new-in-7/throwexpressions.cs#37_Throw_ExpressionExample "conditional throw expressions")]

Esta característica permite usar expresiones throw en expresiones de inicialización:

[!code-csharp[ThrowInInitialization](../../../samples/snippets/csharp/new-in-7/throwexpressions.cs#38_ThrowInInitialization "conditional throw expressions")]

Anteriormente, esas inicializaciones tendrían que estar en un constructor, con las instrucciones throw en el cuerpo del constructor:


[!code-csharp[ThrowInConstructor](../../../samples/snippets/csharp/new-in-7/throwexpressions.cs#39_ThrowInConstructor "throw statements")]

> [!NOTE]
> Dos de las construcciones anteriores iniciarán excepciones durante la construcción de un objeto. Suele ser difícil recuperarse de ellas.
> Por ese motivo, no se recomienda usar diseños que inicien excepciones durante la construcción.

## <a name="generalized-async-return-types"></a>Tipos de valor devueltos de async generalizados

La devolución de un objeto `Task` desde métodos asincrónicos puede presentar cuellos de botella de rendimiento en determinadas rutas de acceso. `Task` es un tipo de referencia, por lo que su uso implica la asignación de un objeto. En los casos en los que un método declarado con el modificador `async` devuelva un resultado en caché o se complete sincrónicamente, las asignaciones adicionales pueden suponer un costo considerable de tiempo en secciones críticas para el rendimiento del código. Esas asignaciones pueden resultar muy costosas si se producen en bucles ajustados.

La nueva característica de lenguaje significa que los métodos asincrónicos pueden devolver otros tipos además de `Task`, `Task<T>` y `void`. El tipo devuelto debe seguir cumpliendo con el patrón asincrónico, lo que significa que debe haber un método `GetAwaiter` accesible. Como ejemplo concreto, se ha agregado el tipo `ValueTask` a .NET Framework para sacar partido de esta nueva característica del lenguaje: 

[!code-csharp[UsingValueTask](../../../samples/snippets/csharp/new-in-7/AsyncWork.cs#30_UsingValueTask "Using ValueTask")]

> [!NOTE]
> Debe agregar el paquete de NuGet [`System.Threading.Tasks.Extensions`](https://www.nuget.org/packages/System.Threading.Tasks.Extensions/) para poder usar el tipo <xref:System.Threading.Tasks.ValueTask%601>.

Una optimización simple sería usar `ValueTask` en lugares donde antes se usaría `Task`. Pero si quiere realizar otras optimizaciones a mano, puede almacenar en caché los resultados del trabajo asincrónico y volver a usar el resultado en llamadas posteriores. La estructura `ValueTask` tiene un constructor con un parámetro `Task` para que se pueda diseñar un `ValueTask` a partir del valor devuelto de cualquier método asincrónico existente:

[!code-csharp[AsyncOptimizedValueTask](../../../samples/snippets/csharp/new-in-7/AsyncWork.cs#31_AsyncOptimizedValueTask "Return async result or cached value")]
 
Como con todas las recomendaciones de rendimiento, debe evaluar las dos versiones antes de realizar grandes cambios de escala en el código.

## <a name="numeric-literal-syntax-improvements"></a>Mejoras en la sintaxis de literales numéricos

La lectura incorrecta de constantes numéricas puede complicar la comprensión del código cuando se lee por primera vez. Esto suele ocurrir cuando estos números se usan como máscaras de bits u otros elementos simbólicos y no como valores numéricos. C# 7 incluye dos nuevas características que hacen que resulte más fácil escribir números de la manera más legible para el uso previsto: *literales binarios* y *separadores de dígitos*.

En aquellos casos en que cree máscaras de bits, o siempre que una representación binaria de un número aumente la legibilidad del código, escriba el número en formato binario:

[!code-csharp[BinaryConstants](../../../samples/snippets/csharp/new-in-7/Program.cs#32_BinaryConstants "Binary constants")]

El `0b` al principio de la constante indica que el número está escrito como número binario.

Los números binarios pueden ser muy largos, por lo que a menudo resulta más fácil ver los patrones de bits introduciendo el `_` como separador de dígitos:

[!code-csharp[ThousandSeparators](../../../samples/snippets/csharp/new-in-7/Program.cs#33_ThousandSeparators "Thousands separators")]

El separador de dígitos puede aparecer en cualquier parte de la constante. En números de base 10, sería habitual usarlo como separador de miles:

[!code-csharp[LargeIntegers](../../../samples/snippets/csharp/new-in-7/Program.cs#34_LargeIntegers "Large integer")]

El separador de dígitos también puede usarse con tipos `decimal`, `float` y `double`:

[!code-csharp[OtherConstants](../../../samples/snippets/csharp/new-in-7/Program.cs#35_OtherConstants "non-integral constants")]

En conjunto, se pueden declarar constantes numéricas con mucha más legibilidad.
