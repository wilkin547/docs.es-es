---
title: Novedades de C# 7.0 | Guía de C#
description: Obtenga información general de las nuevas características de la versión 7.0 del lenguaje C#.
ms.date: 10/02/2020
ms.assetid: fd41596d-d0c2-4816-b94d-c4d00a5d0243
ms.openlocfilehash: 973491044808d7abc58920381ffed57549ee58d3
ms.sourcegitcommit: c7f0beaa2bd66ebca86362ca17d673f7e8256ca6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104876063"
---
# <a name="whats-new-in-c-70-through-c-73"></a>Novedades de C# 7.0 hasta C# 7.3

Entre C# 7.0 y C# 7.3 se han incorporado varias características y mejoras incrementales en la experiencia de desarrollo con C#. En este artículo se proporciona información general sobre las nuevas características y opciones del compilador del lenguaje. Se describe el comportamiento para C# 7.3, que es la versión más reciente compatible con las aplicaciones basadas en .NET Framework.

El elemento de configuración de [selección de versión del lenguaje](../language-reference/configure-language-version.md) se agregó con C# 7.1, lo que permite especificar la versión de lenguaje del compilador en el archivo del proyecto.

En C# 7.0-7.3 se agregan estas características y temas al lenguaje C#:

- [Tuplas y descartes](#tuples-and-discards)
  - Puede crear tipos ligeros sin nombre que contengan varios campos públicos. Los compiladores y las herramientas IDE comprenden la semántica de estos tipos.
  - Los descartes son variables temporales y de solo escritura que se usan en argumentos cuando el valor asignado es indiferente. Son especialmente útiles al deconstruir tuplas y tipos definidos por el usuario, así como al realizar llamadas a métodos con parámetros `out`.
- [Coincidencia de patrones](#pattern-matching)
  - Puede crear la lógica de bifurcación en función de tipos y valores arbitrarios de los miembros de esos tipos.
- [Método `async` `Main`](#async-main)
  - El punto de entrada de una aplicación puede tener el modificador `async`.
- [Funciones locales](#local-functions)
  - Puede anidar funciones en otras funciones para limitar su ámbito y visibilidad.
- [Más miembros con forma de expresión](#more-expression-bodied-members)
  - La lista de miembros que se pueden crear con expresiones ha crecido.
- [Expresiones `throw`](#throw-expressions)
  - Puede iniciar excepciones en construcciones de código que antes no se permitían porque `throw` era una instrucción.
- [Expresiones literales `default`](#default-literal-expressions)
  - Se pueden usar expresiones literales predeterminadas en expresiones de valor predeterminadas cuando el tipo de destino se pueda inferir.
- [Mejoras en la sintaxis de literales numéricos](#numeric-literal-syntax-improvements)
  - Nuevos tokens mejoran la legibilidad de las constantes numéricas.
- [Variables de `out`](#out-variables)
  - Puede declarar valores `out` insertados como argumentos en el método cuando se usen.
- [Argumentos con nombre no finales](#non-trailing-named-arguments)
  - Los argumentos con nombre pueden ir seguidos de argumentos posicionales.
- [Modificador de acceso `private protected`](#private-protected-access-modifier)
  - El modificador de acceso `private protected` permite el acceso de clases derivadas en el mismo ensamblado.
- [Mejoras en la resolución de sobrecarga](#improved-overload-candidates)
  - Nuevas reglas para resolver la ambigüedad de la resolución de sobrecarga.
- [Técnicas para escribir código eficiente seguro](#enabling-more-efficient-safe-code)
  - Una combinación de mejoras en la sintaxis que permiten trabajar con tipos de valor mediante la semántica de referencia.

Por último, el compilador tiene nuevas opciones:

- `-refout` y `-refonly` para controlar la [generación de ensamblados de referencia](#reference-assembly-generation).
- `-publicsign` para habilitar la firma de ensamblados de software de código abierto (OSS).
- `-pathmap` para proporcionar una asignación para los directorios de origen.

En el resto de este artículo se proporciona información general sobre cada característica. Para cada característica, obtendrá información sobre el razonamiento subyacente y la sintaxis. Puede explorar estas características en su entorno mediante la herramienta global `dotnet try`:

1. Instale la herramienta global [dotnet-try](https://github.com/dotnet/try/blob/main/DotNetTryLocal.md).
1. Clone el repositorio [dotnet/try-samples](https://github.com/dotnet/try-samples).
1. Establezca el directorio actual en el subdirectorio *csharp7* para el repositorio *try-samples*.
1. Ejecute `dotnet try`.

## <a name="tuples-and-discards"></a>Tuplas y descartes

C# ofrece una sintaxis enriquecida para clases y estructuras que se usa para explicar la intención del diseño. Pero a veces esa sintaxis enriquecida requiere trabajo adicional con apenas beneficio. Puede que a menudo escriba métodos que requieren una estructura simple que contenga más de un elemento de datos. Para admitir estos escenarios, se han agregado *tuplas* a C#. Las tuplas son estructuras de datos ligeros que contienen varios campos para representar los miembros de datos. Los campos no se validan y no se pueden definir métodos propios. Los tipos de tupla de C# admiten `==` y `!=`. Para obtener más información,

> [!NOTE]
> Las tuplas estaban disponibles antes de C# 7.0, pero no eran eficientes ni compatibles con ningún lenguaje. Esto significaba que solo se podía hacer referencia a los elementos tupla como `Item1`, `Item2`, por ejemplo. C# 7.0 presenta la compatibilidad de lenguaje con las tuplas, que permite usar nombres semánticos en los campos de una tupla mediante tipos de tupla nuevos y más eficientes.

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

Muchas veces, cuando se inicializa una tupla, las variables usadas en el lado derecho de la asignación son las mismas que los nombres que querríamos dar a los elementos de tupla: Los nombres de los elementos de tupla se pueden deducir de las variables usadas para inicializar la tupla:

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count, label); // element names are "count" and "label"
```

Encontrará más información sobre esta característica en el artículo sobre [tipos de tuplas](../language-reference/builtin-types/value-tuples.md).

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

La *coincidencia de patrones* es un conjunto de características que permiten nuevas formas de expresar el flujo de control en el código. En las variables, puede probar su tipo, sus valores o los valores de sus propiedades. Estas técnicas crean un flujo de código más legible.

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

A partir de C# 7.1, la expresión de patrón para `is` y el patrón de tipo `switch` pueden tener el tipo de un parámetro de tipo genérico. Esto puede ser especialmente útil al comprobar los tipos que pueden ser tipos `struct` o `class` y si quiere evitar la conversión boxing.

Puede obtener más información sobre la coincidencia de patrones en [Coincidencia de patrones en C#](../pattern-matching.md).

## <a name="async-main"></a>Async main

Un método *async main* permite usar `await` en el método `Main`. Anteriormente, hubiera sido necesario escribir lo siguiente:

```csharp
static int Main()
{
    return DoAsyncWork().GetAwaiter().GetResult();
}
```

Ahora se puede escribir esto:

```csharp
static async Task<int> Main()
{
    // This could also be replaced with the body
    // DoAsyncWork, including its await expressions:
    return await DoAsyncWork();
}
```

Si el programa no devuelve un código de salida, puede declarar un método `Main` que devuelva una <xref:System.Threading.Tasks.Task>:

```csharp
static async Task Main()
{
    await SomeAsyncMethod();
}
```

En el artículo sobre [async main](../programming-guide/main-and-command-args/index.md) de la guía de programación puede leer más detalles al respecto.

## <a name="local-functions"></a>Funciones locales

Muchos diseños de clases incluyen métodos que se llaman desde una sola ubicación. Estos métodos privados adicionales mantienen cada método pequeño y centrado. Las *funciones locales* permiten declarar métodos en el contexto de otro método. Las funciones locales facilitan que los lectores de la clase vean que el método local solo se llama desde el contexto en el que se declara.

Hay dos casos de uso comunes para las funciones locales: métodos de iterador públicos y métodos asincrónicos públicos. Ambos tipos de métodos generan código que informa de errores más tarde de lo que los programadores podrían esperar. En los métodos de iterador, las excepciones solo se observan al llamar a código que enumera la secuencia devuelta. En los métodos asincrónicos, las excepciones solo se observan cuando se espera al elemento `Task` devuelto. En el ejemplo siguiente se muestra la separación de la validación de parámetros de la implementación de iteradores mediante una función local:

[!code-csharp[22_IteratorMethodLocal](~/samples/snippets/csharp/new-in-7/Iterator.cs#IteratorMethodLocal "Iterator method with local function")]

La misma técnica se puede emplear con métodos `async` para asegurarse de que las excepciones derivadas de la validación de argumentos se inician antes de comenzar el trabajo asincrónico:

[!code-csharp[TaskExample](~/samples/snippets/csharp/new-in-7/AsyncWork.cs#TaskExample "Task returning method with local function")]

Esta sintaxis ahora se admite:

```csharp
[field: SomeThingAboutFieldAttribute]
public int SomeProperty { get; set; }
```

El atributo `SomeThingAboutFieldAttribute` se aplica al campo de respaldo generado por el compilador para `SomeProperty`. Para obtener más información, vea [atributos](../programming-guide/concepts/attributes/index.md) en la guía de programación de C#.

> [!NOTE]
> Algunos de los diseños que se admiten con funciones locales también se pueden realizar con *expresiones lambda*. Para más información, consulte [Funciones locales frente a expresiones lambda](../programming-guide/classes-and-structs/local-functions.md#local-functions-vs-lambda-expressions).

## <a name="more-expression-bodied-members"></a>Más miembros con forma de expresión

En C# 6 se presentaron los miembros con forma de expresión para funciones de miembros y propiedades de solo lectura. C# 7.0 amplía los miembros permitidos que pueden implementarse como expresiones. En C# 7.0, se pueden implementar *constructores*, *finalizadores* y descriptores de acceso `get` y `set` en *propiedades* e *indizadores*. En el código siguiente se muestran ejemplos de cada uno:

[!code-csharp[ExpressionBodiedMembers](~/samples/snippets/csharp/new-in-7/expressionmembers.cs#ExpressionBodiedEverything "new expression-bodied members")]

> [!NOTE]
> En este ejemplo no se requiere un finalizador, pero se muestra para demostrar la sintaxis. No debe implementar un finalizador en la clase salvo que sea necesario para liberar recursos no administrados. También debe plantearse el uso de la clase <xref:System.Runtime.InteropServices.SafeHandle> en lugar de administrar directamente los recursos no administrados.

Estas nuevas ubicaciones para los miembros con forma de expresión representan un hito importante para el lenguaje C#: miembros de la comunidad que trabajan en el proyecto [Roslyn](https://github.com/dotnet/Roslyn) de código abierto implementaron estas características.

Cambiar un método a un miembro con cuerpo de expresión es un [cambio compatible con un elemento binario](version-update-considerations.md#binary-compatible-changes).

## <a name="throw-expressions"></a>Expresiones throw

En C#, `throw` siempre ha sido una instrucción. Como `throw` es una instrucción, no una expresión, había construcciones de C# en las que no se podía usar. Incluyen expresiones condicionales, expresiones de fusión nulas y algunas expresiones lambda. La incorporación de miembros con forma de expresión agrega más ubicaciones donde las expresiones `throw` resultarían útiles. Para que pueda escribir cualquiera de estas construcciones, C# 7.0 presenta las [*expresiones throw*](../language-reference/keywords/throw.md#the-throw-expression).

Esta adición facilita la escritura de código más basado en expresiones. No se necesitan instrucciones adicionales para la comprobación de errores.

## <a name="default-literal-expressions"></a>Expresiones literales predeterminadas

Las expresiones literales predeterminadas constituyen una mejora con respecto a las expresiones de valor predeterminadas. Estas expresiones inicializan una variable en el valor predeterminado. Donde anteriormente habría que escribir:

```csharp
Func<string, bool> whereClause = default(Func<string, bool>);
```

Ahora, se puede pasar por alto el tipo del lado derecho de la inicialización:

```csharp
Func<string, bool> whereClause = default;
```

Para más información, consulte la sección [Literal default](../language-reference/operators/default.md#default-literal) del artículo [Operador default](../language-reference/operators/default.md).

## <a name="numeric-literal-syntax-improvements"></a>Mejoras en la sintaxis de literales numéricos

La lectura incorrecta de constantes numéricas puede complicar la comprensión del código cuando se lee por primera vez. Las máscaras de bits u otros valores simbólicos son propensos a malentendidos. En C# 7.0 se incluyen dos nuevas características para escribir números de la manera más legible para el uso previsto: *literales binarios* y *separadores de dígitos*.

En aquellos casos en que cree máscaras de bits, o siempre que una representación binaria de un número aumente la legibilidad del código, escriba el número en formato binario:

[!code-csharp[ThousandSeparators](~/samples/snippets/csharp/new-in-7/Program.cs#ThousandSeparators "Thousands separators")]

El `0b` al principio de la constante indica que el número está escrito como número binario. Los números binarios pueden ser muy largos, por lo que a menudo resulta más fácil ver los patrones de bits si se introduce `_` como separador de dígitos, como se ha mostrado en la constante binaria del ejemplo anterior. El separador de dígitos puede aparecer en cualquier parte de la constante. En números de base 10, es habitual usarlo como separador de miles. Los literales numéricos hexadecimales y binarios pueden empezar con `_`:

[!code-csharp[LargeIntegers](~/samples/snippets/csharp/new-in-7/Program.cs#LargeIntegers "Large integer")]

El separador de dígitos también se puede usar con tipos `decimal`, `float` y `double`:

[!code-csharp[OtherConstants](~/samples/snippets/csharp/new-in-7/Program.cs#OtherConstants "non-integral constants")]

En conjunto, se pueden declarar constantes numéricas con mucha más legibilidad.

## <a name="out-variables"></a>Variables `out`

La sintaxis existente que admite parámetros `out` se ha mejorado en C# 7. Ahora puede declarar variables `out` en la lista de argumentos de una llamada a método, en lugar de escribir una instrucción de declaración distinta:

[!code-csharp[OutVariableDeclarations](~/samples/snippets/csharp/new-in-7/program.cs#OutVariableDeclarations "Out variable declarations")]

Para mayor claridad, es posible que quiera especificar el tipo de la variable `out`, como se ha mostrado en el ejemplo anterior. Pero el lenguaje admite el uso de una variable local con tipo implícito:

[!code-csharp[OutVarVariableDeclarations](~/samples/snippets/csharp/new-in-7/program.cs#OutVarVariableDeclarations "Implicitly typed Out variable")]

- El código es más fácil de leer.
  - Declare la variable out donde la use, no en una línea de código anterior.
- No es preciso asignar ningún valor inicial.
  - Al declarar la variable `out` cuando se usa en una llamada de método, no podrá usarla accidentalmente antes de que se asigne.

La sintaxis que se agregó en C# 7.0 para permitir declaraciones de variable `out` se ha ampliado para incluir inicializadores de campo, inicializadores de propiedad, inicializadores de constructor y cláusulas de consulta. Permite código como el siguiente ejemplo:

```csharp
public class B
{
   public B(int i, out int j)
   {
      j = i;
   }
}

public class D : B
{
   public D(int i) : base(i, out var j)
   {
      Console.WriteLine($"The value of 'j' is {j}");
   }
}
```

## <a name="non-trailing-named-arguments"></a>Argumentos con nombre no finales

Las llamadas de método ya pueden usar argumentos con nombre que precedan a argumentos posicionales si están en la posición adecuada. Para obtener más información, vea [Argumentos opcionales y con nombre](../programming-guide/classes-and-structs/named-and-optional-arguments.md).

## <a name="private-protected-access-modifier"></a>Modificador de acceso *private protected*

Presentamos un nuevo modificador de acceso compuesto: `private protected` indica que se puede tener acceso a un miembro mediante una clase o clases derivadas declaradas en un mismo ensamblado. Mientras que `protected internal` permite el acceso a las clases derivadas o clases que se encuentran en un mismo ensamblado, `private protected` limita el acceso a los tipos derivados que se declaran en un mismo ensamblado.

Para obtener más información, vea los [modificadores de acceso](../language-reference/keywords/access-modifiers.md) en la referencia del lenguaje.

## <a name="improved-overload-candidates"></a>Mejoras en los candidatos de sobrecarga

En cada versión, las reglas de resolución de sobrecarga se actualizan para abordar situaciones en las que las invocaciones de métodos ambiguos tienen una opción "obvia". Esta versión agrega tres nuevas reglas para ayudar a que el compilador elija la opción obvia:

1. Cuando un grupo de métodos contiene tanto miembros de instancia como estáticos, el compilador descarta los miembros de la instancia si el método fue invocado sin un receptor o contexto de instancia. El compilador descarta los miembros estáticos si el método se invocó con un receptor de instancia. Cuando no hay ningún receptor, el compilador incluye solo miembros estáticos en un contexto estático; de lo contrario, miembros estáticos y de instancia. Cuando el receptor es ambiguamente una instancia o un tipo, el compilador incluye ambos. Un contexto estático, donde no se puede usar un receptor de instancia `this` implícito, incluye el cuerpo de miembros donde no se define `this`, como miembros estáticos, así como lugares donde `this` no se puede usar, como inicializadores de campo e inicializadores-constructores.
1. Cuando un grupo de métodos contiene algunos métodos genéricos cuyos argumentos de tipo no cumplen con sus restricciones, estos miembros se eliminan del conjunto de candidatos.
1. En el caso de una conversión de grupo de métodos, los métodos candidatos cuyo tipo de valor devuelto no coincide con el tipo de valor devuelto del delegado se eliminan del conjunto.

Solo notará este cambio porque encontrará menos errores de compilación para sobrecargas ambiguas de métodos cuando esté seguro de qué método es mejor.

## <a name="enabling-more-efficient-safe-code"></a>Habilitación de código seguro más eficaz

Debería poder escribir código de C# de forma segura que tenga el mismo rendimiento que el código no seguro. El código seguro evita clases de errores, como desbordamientos de búfer, punteros perdidos y otros errores de acceso a la memoria. Estas nuevas características amplían las capacidades de código seguro comprobable. Procure escribir más código utilizando construcciones seguras. Estas características lo facilitan en gran medida.

Las siguientes características nuevas admiten el tema del mejor rendimiento para código seguro:

- Puede tener acceso a campos fijos sin anclar.
- Puede volver a asignar variables locales `ref`.
- Puede usar inicializadores en matrices `stackalloc`.
- Puede usar instrucciones `fixed` con cualquier tipo que admita un patrón.
- Puede usar restricciones genéricas adicionales.
- El modificador `in` en los parámetros para especificar que un argumento se pasa mediante una referencia sin que el método al que se realiza una llamada lo modifique. Agregar el modificador `in` a un argumento es un [cambio compatible con el origen](version-update-considerations.md#source-compatible-changes).
- El modificador `ref readonly` en las devoluciones de método para indicar que un método devuelve su valor mediante una referencia, pero que no permite operaciones de escritura en el objeto. Agregar el modificador `ref readonly` es un [cambio compatible con el origen](version-update-considerations.md#source-compatible-changes), si el resultado devuelto se asigna a un valor. Agregar el modificador `readonly` a una instrucción return `ref` existente es un [cambio incompatible](version-update-considerations.md#incompatible-changes). Requiere que los autores de las llamadas actualicen la declaración de las variables locales `ref` para incluir el modificador `readonly`.
- La declaración `readonly struct` para indicar que una estructura es fija y que debería pasarse como parámetro `in` a los métodos de su miembro. Agregar el modificador `readonly` a una declaración struct existente es un [cambio compatible con un elemento binario](version-update-considerations.md#binary-compatible-changes).
- La declaración `ref struct` para indicar que un tipo de estructura tiene acceso directo a la memoria administrada y que siempre debe estar asignada a la pila. Agregar el modificador `ref` a una declaración `struct` existente es un [cambio incompatible](version-update-considerations.md#incompatible-changes). Un elemento `ref struct` no puede ser un miembro de una clase o usarse en otras ubicaciones donde puede asignarse en el montón.

Puede leer más información sobre todos estos cambios en [Write safe efficient code](../write-safe-efficient-code.md) (Escribir código eficiente seguro).

### <a name="ref-locals-and-returns"></a>Devoluciones y variables locales ref

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

Ahora, las variables locales de `ref` pueden reasignarse para hacer referencia a instancias diferentes después de haberse inicializado. El código siguiente ahora compila:

```csharp
ref VeryLargeStruct refLocal = ref veryLargeStruct; // initialization
refLocal = ref anotherVeryLargeStruct; // reassigned, refLocal refers to different storage.
```

Para obtener más información, vea el artículo sobre valores devueltos de [`ref` y `ref`locales](../programming-guide/classes-and-structs/ref-returns.md), así como el artículo sobre [`foreach`](../language-reference/keywords/foreach-in.md).

Para más información, consulte el artículo sobre la [palabra clave ref](../language-reference/keywords/ref.md).

### <a name="conditional-ref-expressions"></a>Expresiones `ref` condicionales

Por último, la expresión condicional puede producir un resultado de referencia en lugar de un resultado de valor. Por ejemplo, podría escribir lo siguiente para recuperar una referencia al primer elemento en una de dos matrices:

```csharp
ref var r = ref (arr != null ? ref arr[0] : ref otherArr[0]);
```

La variable `r` es una referencia al primer valor de `arr` o `otherArr`.

Para más información, vea el [operador condicional (?:)](../language-reference/operators/conditional-operator.md) en la referencia del lenguaje.

### <a name="in-parameter-modifier"></a>`in` (modificador de parámetro)

La palabra clave `in` complementa las palabras clave ref y out existentes para pasar argumentos por referencia. La palabra clave `in` especifica que se pasa el argumento por referencia, pero el método llamado no modifica el valor.

Puede declarar sobrecargas que se pasen por valor o por referencia de solo lectura, como se muestra en el código siguiente:

```csharp
static void M(S arg);
static void M(in S arg);
```

La sobrecarga por valor (la primera del ejemplo anterior) es mejor que la de la versión de referencia de solo lectura. Para llamar a la versión con el argumento de referencia de solo lectura, debe incluir el modificador `in` cuando llame al método.

Para obtener más información, consulte el artículo sobre el [modificador de parámetros`in`](../language-reference/keywords/in-parameter-modifier.md).

### <a name="more-types-support-the-fixed-statement"></a>Hay más tipos compatibles con la instrucción `fixed`

La instrucción `fixed` admite un conjunto limitado de tipos. A partir de C# 7.3, cualquier tipo que contenga un método `GetPinnableReference()` que devuelve un `ref T` o `ref readonly T` puede ser `fixed`. La adición de esta característica significa que `fixed` puede utilizarse con <xref:System.Span%601?displayProperty=nameWithType> y tipos relacionados.

Para más información, vea el artículo sobre la [instrucción `fixed`](../language-reference/keywords/fixed-statement.md) en la referencia del lenguaje.

### <a name="indexing-fixed-fields-does-not-require-pinning"></a>Indexación de campos `fixed` sin requerir anclaje

Considere esta estructura:

```csharp
unsafe struct S
{
    public fixed int myFixedField[10];
}
```

En versiones anteriores de C#, era necesario anclar una variable para acceder a uno de los enteros que forman parte de `myFixedField`. Ahora, el código siguiente se compila sin anclar la variable `p` dentro de una instrucción `fixed` independiente:

```csharp
class C
{
    static S s = new S();

    unsafe public void M()
    {
        int p = s.myFixedField[5];
    }
}
```

La variable `p` tiene acceso a un elemento en `myFixedField`. No es necesario declarar otra variable `int*` independiente. Todavía necesita un contexto `unsafe`. En versiones anteriores de C#, es necesario declarar un segundo puntero fijo:

```csharp
class C
{
    static S s = new S();

    unsafe public void M()
    {
        fixed (int* ptr = s.myFixedField)
        {
            int p = ptr[5];
        }
    }
}
```

Para más información, consulte el artículo sobre la [instrucción `fixed`](../language-reference/keywords/fixed-statement.md).

### <a name="stackalloc-arrays-support-initializers"></a>Las matrices `stackalloc` admiten inicializadores

Ha podido especificar los valores para los elementos en una matriz cuando la inicializa:

```csharp
var arr = new int[3] {1, 2, 3};
var arr2 = new int[] {1, 2, 3};
```

Ahora, esa misma sintaxis se puede aplicar a las matrices que se declaran con `stackalloc`:

```csharp
int* pArr = stackalloc int[3] {1, 2, 3};
int* pArr2 = stackalloc int[] {1, 2, 3};
Span<int> arr = stackalloc [] {1, 2, 3};
```

Para obtener más información, vea el artículo [Operador `stackalloc`](../language-reference/operators/stackalloc.md).

### <a name="enhanced-generic-constraints"></a>Restricciones genéricas mejoradas

Ahora puede especificar el tipo <xref:System.Enum?displayProperty=nameWithType> o <xref:System.Delegate?displayProperty=nameWithType> como restricciones de clase base para un parámetro de tipo.

También puede usar la nueva restricción `unmanaged` para especificar que el parámetro de tipo debe ser un [tipo no administrado](../language-reference/builtin-types/unmanaged-types.md) que no acepta valores NULL.

Para obtener más información, vea los artículos sobre [restricciones genéricas de `where`](../language-reference/keywords/where-generic-type-constraint.md) y [restricciones sobre parámetros de tipo](../programming-guide/generics/constraints-on-type-parameters.md).

Agregar estas restricciones a tipos existentes es un [cambio incompatible](version-update-considerations.md#incompatible-changes). Los tipos genéricos cerrados puede que ya no cumplan estas nuevas restricciones.

### <a name="generalized-async-return-types"></a>Tipos de valor devueltos de async generalizados

La devolución de un objeto `Task` desde métodos asincrónicos puede presentar cuellos de botella de rendimiento en determinadas rutas de acceso. `Task` es un tipo de referencia, por lo que su uso implica la asignación de un objeto. En los casos en los que un método declarado con el modificador `async` devuelva un resultado en caché o se complete sincrónicamente, las asignaciones adicionales pueden suponer un costo considerable de tiempo en secciones críticas para el rendimiento del código. Esas asignaciones pueden resultar costosas si se producen en bucles ajustados.

La nueva característica de lenguaje implica que los tipos de valor devuelto de métodos asincrónicos no están limitados a `Task`, `Task<T>` y `void`. El tipo devuelto debe seguir cumpliendo con el patrón asincrónico, lo que significa que debe haber un método `GetAwaiter` accesible. Como ejemplo concreto, se ha agregado el tipo `ValueTask` a .NET para sacar partido de esta nueva característica del lenguaje:

[!code-csharp[UsingValueTask](~/samples/snippets/csharp/new-in-7/AsyncWork.cs#UsingValueTask "Using ValueTask")]

> [!NOTE]
> Para poder usar el tipo <xref:System.Threading.Tasks.ValueTask%601> tiene que agregar el paquete NuGet [`System.Threading.Tasks.Extensions`](https://www.nuget.org/packages/System.Threading.Tasks.Extensions/).

Esta mejora es especialmente útil para que los creadores de bibliotecas eviten la asignación de un elemento `Task` en código de rendimiento crítico.

## <a name="new-compiler-options"></a>Nuevas opciones del compilador

Las nuevas opciones del compilador admiten nuevos escenarios de DevOps y compilación de programas de C#.

### <a name="reference-assembly-generation"></a>Generación de ensamblados de referencia

Hay dos opciones del compilador nuevas que generan *ensamblados de solo referencia*: [**ProduceReferenceAssembly**](../language-reference/compiler-options/output.md#producereferenceassembly) y [**ProduceOnlyReferenceAssembly**](../language-reference/compiler-options/code-generation.md#produceonlyreferenceassembly).
En los artículos de los vínculos se explican estas opciones y los ensamblados de referencia de manera más pormenorizada.

### <a name="public-or-open-source-signing"></a>Firma pública o de código abierto

La opción del compilador **PublicSign** indica al compilador que firme el ensamblado con una clave pública. El ensamblado se marca como firmado, pero la firma se toma de la clave pública. Esta opción le permite crear ensamblados firmados a partir de proyectos de código abierto utilizando una clave pública.

Para obtener más información, vea el artículo [Opción del compilador **PublicSign**](../language-reference/compiler-options/security.md#publicsign).

### <a name="pathmap"></a>pathmap

La opción del compilador **PathMap** indica al compilador que reemplace las rutas de acceso de origen del entorno de compilación por rutas de acceso de origen asignadas. La opción **PathMap** controla la ruta de acceso de origen que el compilador escribe en los archivos PDB o para <xref:System.Runtime.CompilerServices.CallerFilePathAttribute>.

Para obtener más información, vea el artículo [Opción del compilador **PathMap**](../language-reference/compiler-options/advanced.md#pathmap).
