---
title: Novedades de C# 7.0 | Guía de C#
description: Obtenga información general de las nuevas características de la versión 7.0 del lenguaje C#.
ms.date: 02/20/2019
ms.assetid: fd41596d-d0c2-4816-b94d-c4d00a5d0243
ms.openlocfilehash: 73563a04dea04c942a6326d6a04ddd54bb80b0ed
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75694587"
---
# <a name="whats-new-in-c-70"></a>Novedades de C# 7.0

C# 7.0 incorpora varias características nuevas al lenguaje C#:

- [Variables de `out`](#out-variables)
  - Puede declarar valores `out` insertados como argumentos en el método cuando se usen.
- [Tuplas](#tuples)
  - Puede crear tipos ligeros sin nombre que contengan varios campos públicos. Los compiladores y las herramientas IDE comprenden la semántica de estos tipos.
- [Descartes](#discards)
  - Los descartes son variables temporales y de solo escritura que se usan en argumentos cuando el valor asignado es indiferente. Son especialmente útiles al deconstruir tuplas y tipos definidos por el usuario, así como al realizar llamadas a métodos con parámetros `out`.
- [Coincidencia de patrones](#pattern-matching)
  - Puede crear la lógica de bifurcación en función de tipos y valores arbitrarios de los miembros de esos tipos.
- [Devoluciones y variables locales `ref`](#ref-locals-and-returns)
  - Las variables locales de método y los valores devueltos pueden ser referencias a otro almacenamiento.
- [Funciones locales](#local-functions)
  - Puede anidar funciones en otras funciones para limitar su ámbito y visibilidad.
- [Más miembros con forma de expresión](#more-expression-bodied-members)
  - La lista de miembros que se pueden crear con expresiones ha crecido.
- [Expresiones `throw`](#throw-expressions)
  - Puede iniciar excepciones en construcciones de código que antes no se permitían porque `throw` era una instrucción.
- [Tipos de valor devueltos de async generalizados](#generalized-async-return-types)
  - Los métodos declarados con el modificador `async` pueden devolver otros tipos además de `Task` y `Task<T>`.
- [Mejoras en la sintaxis de literales numéricos](#numeric-literal-syntax-improvements)
  - Nuevos tokens mejoran la legibilidad de las constantes numéricas.

En el resto de este artículo se proporciona información general sobre cada característica. Para cada característica, conocerá el razonamiento subyacente. Aprenderá la sintaxis. Puede explorar estas características en su entorno mediante la herramienta global `dotnet try`:

1. Instale la herramienta global [dotnet-try](https://github.com/dotnet/try/blob/master/README.md#setup).
1. Clone el repositorio [dotnet/try-samples](https://github.com/dotnet/try-samples).
1. Establezca el directorio actual en el subdirectorio *csharp7* para el repositorio *try-samples*.
1. Ejecute `dotnet try`.

## <a name="out-variables"></a>Variables `out`

En esta versión se ha mejorado la sintaxis existente que admite parámetros `out`. Ahora puede declarar variables `out` en la lista de argumentos de una llamada a método, en lugar de escribir una instrucción de declaración distinta:

[!code-csharp[OutVariableDeclarations](~/samples/snippets/csharp/new-in-7/program.cs#OutVariableDeclarations "Out variable declarations")]

Para mayor claridad, puede que prefiera especificar el tipo de la variable `out`, tal y como se muestra anteriormente. Pero el lenguaje admite el uso de una variable local con tipo implícito:

[!code-csharp[OutVarVariableDeclarations](~/samples/snippets/csharp/new-in-7/program.cs#OutVarVariableDeclarations "Implicitly typed Out variable")]

- El código es más fácil de leer.
  - Declare la variable out donde la use, no en otra línea anterior.
- No es preciso asignar ningún valor inicial.
  - Al declarar la variable `out` cuando se usa en una llamada de método, no podrá usarla accidentalmente antes de que se asigne.

## <a name="tuples"></a>Tuplas

C# ofrece una sintaxis enriquecida para clases y estructuras que se usa para explicar la intención del diseño. Pero a veces esa sintaxis enriquecida requiere trabajo adicional con apenas beneficio. Puede que a menudo escriba métodos que requieren una estructura simple que contenga más de un elemento de datos. Para admitir estos escenarios, se han agregado *tuplas* a C#. Las tuplas son estructuras de datos ligeros que contienen varios campos para representar los miembros de datos.
Los campos no se validan y no se pueden definir métodos propios

> [!NOTE]
> Las tuplas estaban disponibles antes de C# 7.0, pero no eran eficientes ni compatibles con ningún lenguaje.
> Esto significaba que solo se podía hacer referencia a los elementos tupla como `Item1`, `Item2`, por ejemplo. C# 7.0 presenta la compatibilidad de lenguaje con las tuplas, que permite usar nombres semánticos en los campos de una tupla mediante tipos de tupla nuevos y más eficientes.

Puede crear una tupla asignando un valor a cada miembro, y, opcionalmente, proporcionando nombres semánticos a cada uno de los miembros de la tupla:

[!code-csharp[NamedTuple](~/samples/snippets/csharp/new-in-7/program.cs#NamedTuple "Named tuple")]

La tupla `namedLetters` contiene campos denominados `Alpha` y `Beta`. Esos nombres solo existen en tiempo de compilación y no se conservan, por ejemplo, al inspeccionar la tupla mediante la reflexión en tiempo de ejecución.

En la asignación de una tupla, también pueden especificarse los nombres de los campos a la derecha de la asignación:

[!code-csharp[ImplicitNamedTuple](~/samples/snippets/csharp/new-in-7/program.cs#ImplicitNamedTuple "Implicitly named tuple")]

Puede que a veces quiera desempaquetar los miembros de una tupla devueltos de un método.  Para ello, declare distintas variables para cada uno de los valores de la tupla. Este desempaquetado se denomina *deconstrucción* de la tupla:

[!code-csharp[CallingWithDeconstructor](~/samples/snippets/csharp/new-in-7/program.cs#CallingWithDeconstructor "Deconstructing a tuple")]

También puede proporcionar una deconstrucción similar para cualquier tipo de .NET. Un método `Deconstruct` se escribe como un miembro de la clase. Ese método `Deconstruct` proporciona un conjunto de argumentos `out` para cada una de las propiedades que quiere extraer. Tenga en cuenta que esta clase `Point` proporciona un método deconstructor que extrae las coordenadas `X` e `Y`:

[!code-csharp[PointWithDeconstruction](~/samples/snippets/csharp/new-in-7/point.cs#PointWithDeconstruction "Point with deconstruction method")]

Puede extraer los campos individuales asignando un `Point` a una tupla:

[!code-csharp[DeconstructPoint](~/samples/snippets/csharp/new-in-7/program.cs#DeconstructPoint "Deconstruct a point")]

Puede obtener más información sobre las tuplas en el [artículo sobre tuplas](../tuples.md).

## <a name="discards"></a>Descartes

Habitualmente, al deconstruir una tupla o realizar una llamada a un método mediante parámetros `out`, debe definir una variable con un valor indiferente y que no vaya a usar. C# agrega la compatibilidad con *descartes* para gestionar este tipo de escenarios. Un descarte es una variable de solo escritura con el nombre `_` (el carácter de guion bajo). Puede asignar todos los valores que quiera descartar a una única variable. Un descarte se parece a una variable no asignada, aunque no puede usarse en el código (excepto la instrucción de asignación).

Los descartes se admiten en los escenarios siguientes:

- Al deconstruir tuplas o tipos definidos por el usuario.
- Al realizar llamadas a métodos mediante parámetros [out](../language-reference/keywords/out-parameter-modifier.md).
- En una operación de coincidencia de patrones con las instrucciones [is](../language-reference/keywords/is.md) y [switch](../language-reference/keywords/switch.md).
- Como un identificador independiente cuando quiera identificar explícitamente el valor de una asignación como descarte.

En el ejemplo siguiente se define un método `QueryCityDataForYears` que devuelve una tupla de tipo 6 con datos de una ciudad correspondientes a dos años diferentes. La llamada de método del ejemplo se refiere únicamente a los dos valores de rellenado que devuelve el método, por lo que trata los valores restantes de la tupla como descartes al deconstruirla.

[!code-csharp[Tuple-discard](~/samples/snippets/csharp/programming-guide/deconstructing-tuples/discard-tuple1.cs)]

Para obtener más información, vea [Descartes](../discards.md).

## <a name="pattern-matching"></a>Detección de patrones

La *coincidencia de patrones* es una característica que permite implementar la distribución de métodos en propiedades distintas al tipo de un objeto. Probablemente ya esté familiarizado con la distribución de métodos en función del tipo de un objeto. En la programación orientada a objetos, los métodos virtuales y de invalidación proporcionan la sintaxis del lenguaje para implementar la distribución de métodos en función del tipo de un objeto. Las clases base y derivadas proporcionan distintas implementaciones.
Las expresiones de coincidencia de patrones extienden este concepto para que se puedan implementar fácilmente patrones de distribución similares para tipos y elementos de datos que no se relacionan mediante una jerarquía de herencia.

La coincidencia de patrones admite expresiones `is` y `switch`. Cada una de ellas habilita la inspección de un objeto y sus propiedades para determinar si el objeto cumple el patrón buscado. Use la palabra clave `when` para especificar reglas adicionales para el patrón.

La expresión de patrón `is` extiende el conocido [operador `is`](../language-reference/keywords/is.md#pattern-matching-with-is) para consultar el tipo de un objeto y asignar el resultado en una instrucción. En el código siguiente se comprueba si una variable es de tipo `int` y, si lo es, se agrega a la suma actual:

```csharp
if (input is int count)
    sum += count;
```

En el pequeño ejemplo anterior se muestran las mejoras en la expresión `is`. Puede probar con tipos de valor y tipos de referencia, y asignar el resultado correcto a una nueva variable del tipo correcto.

La expresión de coincidencia switch tiene una sintaxis conocida, basada en la instrucción `switch` que ya forma parte del lenguaje C#. La instrucción switch actualizada tiene varias construcciones nuevas:

- El tipo de control de una expresión `switch` ya no se limita a tipos enteros, tipos `Enum`, `string` o a un tipo que acepta valores NULL correspondiente a uno de esos tipos. Se puede usar cualquier tipo.
- Puede probar el tipo de la expresión `switch` en todas las etiquetas `case`. Como sucede con la expresión `is`, puede asignar una variable nueva a ese tipo.
- Puede agregar una cláusula `when` para probar más condiciones en esa variable.
- Ahora el orden de las etiquetas `case` es importante. Se ejecuta la primera rama de la que se quiere obtener la coincidencia, mientras que el resto se omite.

En el código siguiente se muestran estas características:

```csharp
public static int SumPositiveNumbers(IEnumerable<object> sequence)
{
    int sum = 0;
    foreach (var i in sequence)
    {
        switch (i)
        {
            case 0:
                break;
            case IEnumerable<int> childSequence:
            {
                foreach(var item in childSequence)
                    sum += (item > 0) ? item : 0;
                break;
            }
            case int n when n > 0:
                sum += n;
                break;
            case null:
                throw new NullReferenceException("Null found in sequence");
            default:
                throw new InvalidOperationException("Unrecognized type");
        }
    }
    return sum;
}
```

- `case 0:` es el patrón de constante conocido.
- `case IEnumerable<int> childSequence:` es un patrón de tipo.
- `case int n when n > 0:` es un patrón de tipo con una condición `when` adicional.
- `case null:` es el patrón NULL.
- `default:` es el caso predeterminado conocido.

Puede obtener más información sobre la coincidencia de patrones en [Coincidencia de patrones en C#](../pattern-matching.md).

## <a name="ref-locals-and-returns"></a>Devoluciones y variables locales ref

Esta característica habilita algoritmos que usan y devuelven referencias a variables definidas en otro lugar. Por ejemplo, trabajar con matrices de gran tamaño y buscar una sola ubicación con determinadas características. El método siguiente devuelve una **referencia** a ese almacenamiento en la matriz:

[!code-csharp[FindReturningRef](~/samples/snippets/csharp/new-in-7/MatrixSearch.cs#FindReturningRef "Find returning by reference")]

Puede declarar el valor devuelto como un elemento `ref` y modificar ese valor en la matriz, como se muestra en el código siguiente:

[!code-csharp[AssignRefReturn](~/samples/snippets/csharp/new-in-7/Program.cs#AssignRefReturn "Assign ref return")]

El lenguaje C# tiene varias reglas que impiden el uso incorrecto de las variables locales y devoluciones de `ref`:

- Tendrá que agregar la palabra clave `ref` a la firma del método y a todas las instrucciones `return` de un método.
  - Esto evidencia que el método se devuelve por referencia a lo largo del método.
- Se puede asignar `ref return` a una variable de valor, o bien a una variable `ref`.
  - El autor de la llamada controla si se copia el valor devuelto o no. La omisión del modificador `ref` al asignar el valor devuelto indica que el autor de la llamada quiere una copia del valor, no una referencia al almacenamiento.
- No se puede asignar un valor devuelto de método estándar a una variable local `ref`.
  - No permite instrucciones como `ref int i = sequence.Count();`
- No se puede devolver un elemento `ref` a una variable cuya duración se extiende más allá de la ejecución del método.
  - Esto significa que no se puede devolver una referencia a una variable local o a una variable con un ámbito similar.
- Las `ref` locales y las devoluciones no se pueden usar con métodos asíncronos.
  - El compilador no puede identificar si una variable a la que se hace referencia se ha establecido en su valor final en la devolución del método asíncrono.

La incorporación de variables locales ref y devoluciones de ref permite usar algoritmos que resultan más eficientes si se evita copiar los valores o se realizan operaciones de desreferencia varias veces.

Agregar `ref` al valor devuelto es un [cambio compatible con el origen](version-update-considerations.md#source-compatible-changes). El código existente se compila, pero el valor devuelto de referencia se copia cuando se asigna. Los autores de las llamadas deben actualizar el almacenamiento para el valor devuelto en una variable local `ref` para almacenar el valor devuelto como referencia.

Para más información, consulte el artículo sobre la [palabra clave ref](../language-reference/keywords/ref.md).

## <a name="local-functions"></a>Funciones locales

Muchos diseños de clases incluyen métodos que se llaman desde una sola ubicación. Estos métodos privados adicionales mantienen cada método pequeño y centrado. Las *funciones locales* permiten declarar métodos en el contexto de otro método. Las funciones locales facilitan que los lectores de la clase vean que el método local solo se llama desde el contexto en el que se declara.

Hay dos casos de uso comunes para las funciones locales: métodos de iterador públicos y métodos asincrónicos públicos. Ambos tipos de métodos generan código que informa de errores más tarde de lo que los programadores podrían esperar. En los métodos de iterador, las excepciones solo se observan al llamar a código que enumera la secuencia devuelta. En los métodos asincrónicos, las excepciones solo se observan cuando se espera al elemento `Task` devuelto. En el ejemplo siguiente se muestra la separación de la validación de parámetros de la implementación de iteradores mediante una función local:

[!code-csharp[22_IteratorMethodLocal](~/samples/snippets/csharp/new-in-7/Iterator.cs#IteratorMethodLocal "Iterator method with local function")]

La misma técnica se puede emplear con métodos `async` para asegurarse de que las excepciones derivadas de la validación de argumentos se inician antes de comenzar el trabajo asincrónico:

[!code-csharp[TaskExample](~/samples/snippets/csharp/new-in-7/AsyncWork.cs#TaskExample "Task returning method with local function")]

> [!NOTE]
> Algunos de los diseños que se admiten con funciones locales también se podrían realizar con *expresiones lambda*. Para más información, consulte [Funciones locales frente a expresiones lambda](../local-functions-vs-lambdas.md).

## <a name="more-expression-bodied-members"></a>Más miembros con forma de expresión

En C# 6 se presentaron los [miembros con forma de expresión](csharp-6.md#expression-bodied-function-members) para funciones de miembros y propiedades de solo lectura. C# 7.0 amplía los miembros permitidos que pueden implementarse como expresiones. En C# 7.0, se pueden implementar *constructores*, *finalizadores* y descriptores de acceso `get` y `set` en *propiedades* e *indizadores*. En el código siguiente se muestran ejemplos de cada uno:

[!code-csharp[ExpressionBodiedMembers](~/samples/snippets/csharp/new-in-7/expressionmembers.cs#ExpressionBodiedEverything "new expression-bodied members")]

> [!NOTE]
> En este ejemplo no se requiere un finalizador, pero se muestra para demostrar la sintaxis. No debe implementar un finalizador en la clase salvo que sea necesario para liberar recursos no administrados. También debe plantearse el uso de la clase <xref:System.Runtime.InteropServices.SafeHandle> en lugar de administrar directamente los recursos no administrados.

Estas nuevas ubicaciones para los miembros con forma de expresión representan un hito importante para el lenguaje C#: miembros de la comunidad que trabajan en el proyecto [Roslyn](https://github.com/dotnet/Roslyn) de código abierto implementaron estas características.

Cambiar un método a un miembro con cuerpo de expresión es un [cambio compatible con un elemento binario](version-update-considerations.md#binary-compatible-changes).

## <a name="throw-expressions"></a>Expresiones throw

En C#, `throw` siempre ha sido una instrucción. Como `throw` es una instrucción, no una expresión, había construcciones de C# en las que no se podía usar. Incluyen expresiones condicionales, expresiones de fusión nulas y algunas expresiones lambda. La incorporación de miembros con forma de expresión agrega más ubicaciones donde las expresiones `throw` resultarían útiles. Para que pueda escribir cualquiera de estas construcciones, C# 7.0 presenta las [*expresiones throw*](../language-reference/keywords/throw.md#the-throw-expression).

Esta adición facilita la escritura de código más basado en expresiones. No se necesitan instrucciones adicionales para la comprobación de errores.

## <a name="generalized-async-return-types"></a>Tipos de valor devueltos de async generalizados

La devolución de un objeto `Task` desde métodos asincrónicos puede presentar cuellos de botella de rendimiento en determinadas rutas de acceso. `Task` es un tipo de referencia, por lo que su uso implica la asignación de un objeto. En los casos en los que un método declarado con el modificador `async` devuelva un resultado en caché o se complete sincrónicamente, las asignaciones adicionales pueden suponer un costo considerable de tiempo en secciones críticas para el rendimiento del código. Esas asignaciones pueden resultar costosas si se producen en bucles ajustados.

La nueva característica de lenguaje implica que los tipos de valor devuelto de métodos asincrónicos no están limitados a `Task`, `Task<T>` y `void`. El tipo devuelto debe seguir cumpliendo con el patrón asincrónico, lo que significa que debe haber un método `GetAwaiter` accesible. Como ejemplo concreto, se ha agregado el tipo `ValueTask` a .NET Framework para sacar partido de esta nueva característica del lenguaje:

[!code-csharp[UsingValueTask](~/samples/snippets/csharp/new-in-7/AsyncWork.cs#UsingValueTask "Using ValueTask")]

> [!NOTE]
> Debe agregar el paquete de NuGet [`System.Threading.Tasks.Extensions`](https://www.nuget.org/packages/System.Threading.Tasks.Extensions/) para poder usar el tipo <xref:System.Threading.Tasks.ValueTask%601>.

Esta mejora es especialmente útil para que los creadores de bibliotecas eviten la asignación de un elemento `Task` en código de rendimiento crítico.

## <a name="numeric-literal-syntax-improvements"></a>Mejoras en la sintaxis de literales numéricos

La lectura incorrecta de constantes numéricas puede complicar la comprensión del código cuando se lee por primera vez. Las máscaras de bits u otros valores simbólicos son propensos a malentendidos. En C# 7.0 se incluyen dos nuevas características para escribir números de la manera más legible para el uso previsto: *literales binarios* y *separadores de dígitos*.

En aquellos casos en que cree máscaras de bits, o siempre que una representación binaria de un número aumente la legibilidad del código, escriba el número en formato binario:

[!code-csharp[ThousandSeparators](~/samples/snippets/csharp/new-in-7/Program.cs#ThousandSeparators "Thousands separators")]

El `0b` al principio de la constante indica que el número está escrito como número binario. Los números binarios pueden ser muy largos, por lo que a menudo resulta más fácil ver los patrones de bits si se introduce `_` como separador de dígitos, como se ha mostrado antes en la constante binaria. El separador de dígitos puede aparecer en cualquier parte de la constante. En números de base 10, es habitual usarlo como separador de miles:

[!code-csharp[LargeIntegers](~/samples/snippets/csharp/new-in-7/Program.cs#LargeIntegers "Large integer")]

El separador de dígitos también se puede usar con tipos `decimal`, `float` y `double`:

[!code-csharp[OtherConstants](~/samples/snippets/csharp/new-in-7/Program.cs#OtherConstants "non-integral constants")]

En conjunto, se pueden declarar constantes numéricas con mucha más legibilidad.
