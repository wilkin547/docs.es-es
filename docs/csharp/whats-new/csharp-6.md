---
title: Novedades de C# 6 - Guía de C#
description: Obtenga información sobre las nuevas características de la versión 6 de C#
ms.date: 12/12/2018
ms.openlocfilehash: da40b4c9d4af0094fdd907c542e971ba55086e0f
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2020
ms.locfileid: "92224238"
---
# <a name="whats-new-in-c-6"></a>Novedades de C# 6

La versión 6.0 de C# incluye muchas características que mejoran la productividad para los desarrolladores. El efecto general de estas características es que se escribe código más conciso y legible. La sintaxis contiene menos complejidad para muchas de las prácticas habituales. Es más fácil ver la intención del diseño con menos complejidad. Si conoce bien estas características, podrá mejorar la productividad y escribir código más legible. Puede concentrarse más en las características que en las construcciones del lenguaje.

El resto de este artículo proporciona información general de cada una de estas características, con un vínculo para examinar cada una. También puede examinar las características en una [exploración interactiva sobre C# 6](../tutorials/exploration/csharp-6.yml) en la sección de tutoriales.

## <a name="read-only-auto-properties"></a>Propiedades automáticas de solo lectura

*Las propiedades automáticas de solo lectura* proporcionan una sintaxis más concisa para crear tipos inmutables. La propiedad automática se declara solo con un descriptor de acceso get:

[!code-csharp[ReadOnlyAutoProperty](../../../samples/snippets/csharp/new-in-6/newcode.cs#ReadOnlyAutoProperty)]

Las propiedades `FirstName` y `LastName` solo se pueden establecer en el cuerpo del constructor de la misma clase:

[!code-csharp[ReadOnlyAutoPropertyConstructor](../../../samples/snippets/csharp/new-in-6/newcode.cs#ReadOnlyAutoPropertyConstructor)]

Intentar establecer `LastName` en otro método genera un error de compilación `CS0200`:

```csharp
public class Student
{
    public string LastName { get;  }

    public void ChangeName(string newLastName)
    {
        // Generates CS0200: Property or indexer cannot be assigned to -- it is read only
        LastName = newLastName;
    }
}
```

Esta característica habilita la compatibilidad de lenguaje real para crear tipos inmutables y usa la sintaxis de propiedades automáticas más concisa y cómoda.

Si al agregar esta sintaxis no se quita un método accesible, se trata de un [cambio compatible con los elementos binarios](version-update-considerations.md#binary-compatible-changes).

## <a name="auto-property-initializers"></a>Inicializadores de propiedades automáticas

Los *inicializadores de propiedades automáticas* permiten declarar el valor inicial de una propiedad automática como parte de la declaración de la propiedad.

[!code-csharp[Initialization](../../../samples/snippets/csharp/new-in-6/newcode.cs#Initialization)]

El miembro `Grades` se inicializa cuando se declara. Eso hace que sea más fácil realizar la inicialización exactamente una sola vez. La inicialización es parte de la declaración de la propiedad, lo que facilita igualar la asignación de almacenamiento con la interfaz pública para objetos `Student`.

## <a name="expression-bodied-function-members"></a>Miembros de función con cuerpos de expresión

Muchos de los miembros que se escriben son instrucciones únicas que podrían ser expresiones únicas. Escriba un miembro con forma de expresión en su lugar. Funciona para métodos y propiedades de solo lectura. Por ejemplo, un reemplazo de `ToString()` suele ser un excelente candidato:

[!code-csharp[ToStringExpressionMember](../../../samples/snippets/csharp/new-in-6/newcode.cs#ToStringExpressionMember)]

También puede usar esta sintaxis para propiedades de solo lectura:

[!code-csharp[FullNameExpressionMember](../../../samples/snippets/csharp/new-in-6/newcode.cs#FullNameExpressionMember)]

Cambiar un miembro existente por un miembro con cuerpo de expresión es un [cambio compatible con un elemento binario](version-update-considerations.md#binary-compatible-changes).

## <a name="using-static"></a>uso de versión estática

La mejora *using static* permite importar los métodos estáticos de una sola clase. Se especifica la clase que se está usando:

[!code-csharp[UsingStaticMath](../../../samples/snippets/csharp/new-in-6/newcode.cs#UsingStaticMath)]

<xref:System.Math> no contiene ningún método de instancia. También se puede usar `using static` para importar los métodos estáticos de una clase para una clase que tiene métodos estáticos y de instancia. Uno de los ejemplos más útiles es <xref:System.String>:

[!code-csharp[UsingStatic](../../../samples/snippets/csharp/new-in-6/newcode.cs#UsingStatic)]

> [!NOTE]
> Se debe usar el nombre de clase completo, `System.String`, en una instrucción using estática.  No se puede usar la palabra clave `string` en su lugar.

Al importar desde una instrucción `static using`, los métodos de extensión solo están en ámbito cuando se llaman mediante la sintaxis de invocación de métodos de extensión. No están en ámbito cuando se llaman como métodos estáticos. A menudo verá esto en las consultas LINQ. Puede importar el modelo LINQ mediante la importación de <xref:System.Linq.Enumerable> o <xref:System.Linq.Queryable>.

[!code-csharp[UsingStaticLinq](../../../samples/snippets/csharp/new-in-6/newcode.cs#usingStaticLinq)]

Normalmente se llama a los métodos de extensión mediante expresiones de invocación de método de extensión. La ambigüedad se resuelve al agregar el nombre de clase en el caso excepcional en que se llaman mediante una llamada de método estático.

La directiva `static using` también importa cualquier tipo anidado. Es posible hacer referencia a los tipos anidados sin calificación.

## <a name="null-conditional-operators"></a>Operadores condicionales NULL

El *operador condicional NULL* realiza comprobaciones NULL de una forma mucho más sencilla y fluida. Reemplace el acceso a miembros `.` por `?.`:

[!code-csharp[NullConditional](../../../samples/snippets/csharp/new-in-6/program.cs#NullConditional)]

En el ejemplo anterior, se asigna `null` a la variable `first` si el objeto person es `null`. De lo contrario, se le asigna el valor de la propiedad `FirstName`. Y lo más importante es que `?.` significa que esta línea de código no genera una excepción `NullReferenceException` si la variable `person` es `null`. En su lugar, se cortocircuita y devuelve `null`. También puede usar un operador condicional NULL para el acceso de matriz o indizador. Reemplace `[]` por `?[]` en la expresión de índice.

La siguiente expresión devuelve `string`, independientemente del valor de `person`. A menudo se usa esta construcción con el operador de *fusión nula* para asignar valores predeterminados cuando una de las propiedades es `null`. Si la expresión se cortocircuita, se asigna tipo al valor `null` devuelto para que coincida con la expresión completa.

[!code-csharp[NullCoalescing](../../../samples/snippets/csharp/new-in-6/program.cs#NullCoalescing)]

También se puede usar `?.` para invocar métodos de forma condicional. El uso más común de las funciones miembro con el operador condicional NULL es invocar de forma segura delegados (o controladores de eventos) que puedan ser `null`.  Se llama al método `Invoke` del delegado con el operador `?.` para acceder al miembro. Puede ver un ejemplo en el artículo sobre [patrones de delegado](../delegates-patterns.md#handling-null-delegates).

Las reglas del operador `?.` garantizan que el lado izquierdo del operador solo se evalúa una vez. Esto habilita muchos giros, incluido el ejemplo siguiente con controladores de eventos:

```csharp
// preferred in C# 6:
this.SomethingHappened?.Invoke(this, eventArgs);
```

La garantía de que el lado izquierdo se evalúa solo una vez también permite usar cualquier expresión, incluidas llamadas a métodos, en el lado izquierdo de `?.`

## <a name="string-interpolation"></a>Interpolación de cadenas

Con C# 6, la nueva característica de [interpolación de cadenas](../language-reference/tokens/interpolated.md) permite insertar expresiones en una cadena. Solo hay que anteponer `$` a la cadena y usar expresiones entre `{` y `}` en lugar de ordinales:

[!code-csharp[stringInterpolation](../../../samples/snippets/csharp/new-in-6/newcode.cs#FullNameExpressionMember)]

Este ejemplo usa propiedades para las expresiones sustituidas. Se puede usar cualquier expresión. Por ejemplo, se podría calcular la puntuación media de un alumno como parte de la interpolación:

[!code-csharp[stringInterpolationFormat](../../../samples/snippets/csharp/new-in-6/newcode.cs#stringInterpolationFormat)]

La línea de código anterior dará formato al valor de `Grades.Average()` como un número de punto flotante con dos posiciones decimales.

A menudo puede ser necesario dar formato a la cadena generada con una referencia cultural concreta. Se aprovecha el hecho de que el objeto generado por una interpolación de cadena puede convertirse implícitamente a <xref:System.FormattableString?displayProperty=nameWithType>. La instancia <xref:System.FormattableString> contiene la cadena de formato compuesta y los resultados de la evaluación de las expresiones antes de convertirlas en cadenas. Use el método <xref:System.FormattableString.ToString(System.IFormatProvider)?displayProperty=nameWithType> para especificar la referencia cultural cuando de formato a una cadena. En el ejemplo siguiente se genera una cadena con la referencia cultural de alemán (de-DE). (De forma predeterminada, la referencia cultural de alemán usa el carácter "," como separador de decimales y el carácter "." como separador de miles).

```csharp
FormattableString str = $"Average grade is {s.Grades.Average()}";
var gradeStr = str.ToString(new System.Globalization.CultureInfo("de-DE"));
```

Para empezar a trabajar con la interpolación de cadenas, vea el tutorial interactivo [Interpolación de cadenas en C#](../tutorials/exploration/interpolated-strings.yml), el artículo [Interpolación de cadenas](../language-reference/tokens/interpolated.md) y el tutorial [Interpolación de cadenas en C#](../tutorials/string-interpolation.md).

## <a name="exception-filters"></a>Filtros de excepciones

Los *filtros de excepciones* son cláusulas que determinan cuándo se debe aplicar una cláusula catch determinada. Si la expresión usada para un filtro de excepciones se evalúa como `true`, la cláusula catch realiza su procesamiento normal en una excepción. Si la expresión se evalúa como `false`, entonces se omite la cláusula `catch`. Un uso consiste en examinar la información sobre una excepción para determinar si una cláusula `catch` puede procesar la excepción:

[!code-csharp[ExceptionFilter](../../../samples/snippets/csharp/new-in-6/NetworkClient.cs#ExceptionFilter)]

## <a name="the-nameof-expression"></a>La expresión `nameof`

La expresión [nameof](../language-reference/operators/nameof.md) se evalúa como el nombre de un símbolo. Es una excelente manera de hacer que las herramientas funcionen siempre que se necesita el nombre de una variable, una propiedad o un campo de miembro. Uno de los usos más comunes de `nameof` es para proporcionar el nombre de un símbolo que produjo una excepción:

[!code-csharp[nameof](../../../samples/snippets/csharp/new-in-6/NewCode.cs#UsingStaticString)]

Otro uso es con aplicaciones basadas en XAML que implementan la interfaz `INotifyPropertyChanged`:

[!code-csharp[nameofNotify](../../../samples/snippets/csharp/new-in-6/viewmodel.cs#nameofNotify)]

## <a name="await-in-catch-and-finally-blocks"></a>Await en bloques Catch y Finally

C# 5 tenía varias limitaciones en cuanto a dónde se podían colocar las expresiones `await`. Con C# 6, ahora se puede usar `await` en expresiones `catch` o `finally`. Se suele usar principalmente con escenarios de registro:

[!code-csharp[AwaitFinally](../../../samples/snippets/csharp/new-in-6/NetworkClient.cs#AwaitFinally)]

Los detalles de implementación para agregar compatibilidad con `await` dentro de cláusulas `catch` y `finally` garantizan que el comportamiento sea coherente con el comportamiento del código sincrónico. Cuando el código que se ejecuta en una cláusula `catch` o `finally` produce una excepción, la ejecución busca una cláusula `catch` adecuada en el siguiente bloque adyacente. Si había una excepción actual, esa excepción se pierde. Lo mismo sucede con las expresiones de await en cláusulas `catch` y `finally`: se busca una cláusula `catch` adecuada y se pierde la excepción actual, si existe.  

> [!NOTE]
> Este comportamiento es el motivo por el que se recomienda escribir cláusulas `catch` y `finally` con cuidado, para evitar la introducción de nuevas excepciones.

## <a name="initialize-associative-collections-using-indexers"></a>Inicialización de colecciones asociativas mediante indexadores

Los *inicializadores de índice* son una de las dos características que hacen que los inicializadores de colección sean más coherentes con el uso del índice. En versiones anteriores de C#, se podían usar *inicializadores de colección* con colecciones de estilos de secuencia, incluido <xref:System.Collections.Generic.Dictionary%602>, al agregar llaves alrededor de los pares de clave y valor:

[!code-csharp[ListInitializer](../../../samples/snippets/csharp/new-in-6/initializers.cs#CollectionInitializer)]

Puede usarlos con colecciones <xref:System.Collections.Generic.Dictionary%602> y otros tipos donde el método `Add` accesible acepte más de un argumento. La nueva sintaxis admite la asignación con un índice en la colección:

[!code-csharp[DictionaryInitializer](../../../samples/snippets/csharp/new-in-6/initializers.cs#DictionaryInitializer)]

Esta característica significa que los contenedores asociativos se pueden inicializar mediante una sintaxis similar a la que se lleva usando en varias versiones para los contenedores de secuencia.

## <a name="extension-add-methods-in-collection-initializers"></a>Métodos `Add` de extensión para inicializadores de colección

Otra característica que facilita la inicialización de colecciones es la capacidad de usar un *método de extensión* para el método `Add`. Esta característica se agregó por motivos de paridad con Visual Basic. La característica es más útil cuando se tiene una clase de colección personalizada que tiene un método con un nombre diferente para agregar nuevos elementos de forma semántica.

## <a name="improved-overload-resolution"></a>Mejoras en la resolución de sobrecarga

Es probable que esta última característica no se aprecie. Había construcciones en las que la versión anterior del compilador de C# podía considerar ambiguas algunas llamadas a métodos con expresiones lambda. Considere este método:

[!code-csharp[AsyncMethod](../../../samples/snippets/csharp/new-in-6/overloads.cs#AsyncMethod)]

En versiones anteriores de C#, la llamada a este método con la sintaxis de grupo de método produciría un error:

[!code-csharp[MethodGroup](../../../samples/snippets/csharp/new-in-6/overloads.cs#MethodGroup)]

El compilador anterior no podía distinguir correctamente entre `Task.Run(Action)` y `Task.Run(Func<Task>())`. En las versiones anteriores, era necesario usar una expresión lambda como argumento:

[!code-csharp[Lambda](../../../samples/snippets/csharp/new-in-6/overloads.cs#Lambda)]

El compilador de C# 6 determina correctamente que `Task.Run(Func<Task>())` es una opción mejor.

### <a name="deterministic-compiler-output"></a>Resultado del compilador determinista

La opción `-deterministic` indica al compilador que cree un ensamblado de salida idéntico byte a byte para las compilaciones sucesivas de los mismos archivos de código fuente.

De forma predeterminada, todas las compilaciones generan una salida única en cada compilación. El compilador agrega una marca de tiempo y genera un GUID a partir de números aleatorios. Use esta opción si quiere comparar la salida byte a byte para garantizar la coherencia entre las compilaciones.

Para obtener más información, vea el artículo [-deterministic (opción del compilador)](../language-reference/compiler-options/deterministic-compiler-option.md).
