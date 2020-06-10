---
title: 'Tipos de tupla: Guía de C#'
description: Más información sobre tipos de tupla con nombre y sin nombre en C#
ms.date: 05/15/2018
ms.technology: csharp-fundamentals
ms.assetid: ee8bf7c3-aa3e-4c9e-a5c6-e05cc6138baa
ms.openlocfilehash: 497f95811677c300e1fadad65eb495dced7f2da3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84374621"
---
# <a name="c-tuple-types"></a>Tipos de tupla de C#

Las tuplas de C# son tipos que se definen mediante una sintaxis ligera. Entre otras ventajas, incluyen una sintaxis más sencilla, reglas para conversiones en función de un número (denominadas cardinalidad) y tipos de elementos y reglas coherentes para copias, pruebas de igualdad y asignaciones. Como contrapartida, las tuplas no admiten algunas de las expresiones orientadas a objetos que se asocian a la herencia. Puede obtener información general en la sección sobre [tuplas del artículo Novedades de C# 7.0](whats-new/csharp-7.md#tuples).

En este artículo conocerá las reglas del lenguaje que rigen las tuplas en C# 7.0 y versiones posteriores, distintas formas de usarlas y una guía inicial sobre cómo trabajar con tuplas.

> [!NOTE]
> Las nuevas características de tupla requieren los tipos <xref:System.ValueTuple>.
> Debe agregar el paquete NuGet [`System.ValueTuple`](https://www.nuget.org/packages/System.ValueTuple/) para usarlo en plataformas que no incluyen los tipos.
>
> Esto es similar a otras características del lenguaje que se basan en tipos que se han proporcionado en el marco. Algunos ejemplos incluyen `async` y `await` que se basan en la interfaz `INotifyCompletion`, y LINQ que se basa en `IEnumerable<T>`. En cambio, el mecanismo de entrega está cambiando a medida que .NET está pasando a ser más independiente de las plataformas. Puede que .NET Framework no proporcione siempre la misma cadencia que el compilador de lenguaje. Cuando las nuevas características del lenguaje se basan en tipos nuevos, esos tipos estarán disponibles como paquetes NuGet cuando se proporcionen las características del lenguaje. Como estos tipos nuevos se agregan a la API de .NET Standard y se proporcionan como parte del marco, el requisito del paquete NuGet se quitará.

Empecemos por las razones para agregar nueva compatibilidad de tupla. Los métodos devuelven un solo objeto. Las tuplas permiten empaquetar varios valores en ese único objeto más fácilmente.

.NET Framework ya incluye clases `Tuple` genéricas. Pero estas clases planteaban dos importantes limitaciones. En primer lugar, las clases `Tuple` denominan a sus propiedades `Item1`, `Item2`, etc. Esos nombres no incluyen ninguna información semántica. El uso de estos tipos `Tuple` no permite comunicar el significado de cada una de las propiedades. Las nuevas características de lenguaje permiten declarar y utilizar nombres semánticamente significativos para los elementos de una tupla.

Las clases `Tuple` provocan más problemas de rendimiento porque son tipos de referencia. El uso de uno de los tipos `Tuple` implica la asignación de objetos. En rutas de acceso activas, la asignación de muchos objetos pequeños puede suponer un importante impacto en el rendimiento de la aplicación. Por lo tanto, la compatibilidad del lenguaje para tuplas aprovecha los nuevos struct `ValueTuple`.

Para evitar esas deficiencias, podría crear un `class` o `struct` que incluya varios elementos. Lamentablemente, esto representa más trabajo para el usuario y oculta la intención del diseño. La creación de un `struct` o `class` implica que se define un tipo con datos y comportamiento. Muchas veces, simplemente quiere almacenar varios valores en un solo objeto.

Las características del lenguaje y los structs genéricos `ValueTuple` aplican la regla que establece que no se puede agregar ningún comportamiento (métodos) a estos tipos de tupla.
Todos los tipos `ValueTuple` son *structs mutables*. Cada campo de miembro es un campo público. Eso los hace muy ligeros. Pero indica que no se deben usar tuplas cuando la inmutabilidad es importante.

Las tuplas son contenedores de datos más sencillos y flexibles que los tipos `class` y `struct`. Examinemos esas diferencias.

## <a name="named-and-unnamed-tuples"></a>Tuplas con nombre y sin nombre

El struct `ValueTuple` incluye campos denominados `Item1`, `Item2`, `Item3`, etc., similares a las propiedades definidas en los tipos `Tuple` existentes.
Estos nombres son los únicos que se pueden usar en *tuplas sin nombre*. Si no proporciona ningún nombre de campo alternativo para una tupla, ha creado una tupla sin nombre:

[!code-csharp[UnnamedTuple](../../samples/snippets/csharp/tuples/program.cs#01_UnNamedTuple "Unnamed tuple")]

La tupla del ejemplo anterior se ha inicializado con constantes literales y no tienen nombres de elementos creados mediante *proyecciones de nombre de campo de tupla* en C# 7.1.

Pero al inicializar una tupla, se pueden usar nuevas características del lenguaje que asignen nombres mejores a cada campo. Así se crea una *tupla con nombre*.
Las tuplas con nombre todavía tienen elementos denominados `Item1`, `Item2`, `Item3`, etc.
Pero también tienen sinónimos para cualquiera de esos elementos a los que haya asignado un nombre.
Cree una tupla con nombre especificando los nombres de cada elemento. Una forma consiste en especificar los nombres como parte de la inicialización de la tupla:

[!code-csharp[NamedTuple](../../samples/snippets/csharp/tuples/program.cs#02_NamedTuple "Named tuple")]

Estos sinónimos los controlan el compilador y el lenguaje para que se puedan usar tuplas con nombre de manera eficaz. Los IDE y los editores pueden leer estos nombres semánticos con las API de Roslyn. Puede hacer referencia a los elementos de una tupla con nombre por esos nombres semánticos en cualquier lugar de un mismo ensamblado. El compilador reemplaza los nombres que ha definido con `Item*` equivalentes al generar la salida compilada. El Lenguaje Intermedio de Microsoft (MSIL) compilado no incluye los nombres que se hayan asignado a estos elementos.

A partir de C# 7.1, se pueden proporcionar nombres de campo a una tupla desde las variables que se utilizan para inicializar la tupla. Esto se conoce como **[inicializadores de proyección de tupla](#tuple-projection-initializers)** . El código siguiente crea una tupla denominada `accumulation` con elementos `count` (un entero) y `sum` (un doble).

[!code-csharp[ProjectedTuple](../../samples/snippets/csharp/tuples/program.cs#ProjectedTupleNames "Named tuple")]

El compilador debe comunicar esos nombres creados por el usuario para tuplas que se devuelvan de métodos o propiedades públicos. En esos casos, el compilador agrega un atributo <xref:System.Runtime.CompilerServices.TupleElementNamesAttribute> en el método. Este atributo contiene una propiedad de lista <xref:System.Runtime.CompilerServices.TupleElementNamesAttribute.TransformNames> que contiene los nombres asignados a cada uno de los elementos de la tupla.

> [!NOTE]
> Las herramientas de desarrollo, como Visual Studio, también leen esos metadatos y proporcionan IntelliSense y otras características con los nombres de campo de metadatos.

Es importante comprender estos aspectos fundamentales subyacentes de las nuevas tuplas y el tipo `ValueTuple` para entender las reglas de asignación de tuplas con nombre entre sí.

## <a name="tuple-projection-initializers"></a>Inicializadores de proyección de tupla

En general, los inicializadores de proyección de tupla funcionan con los nombres de variable o de campo desde el lado derecho de una instrucción de inicialización de tupla.
Si no se proporciona un nombre explícito, tiene prioridad sobre cualquier nombre proyectado. Por ejemplo, en el inicializador siguiente, los elementos son `explicitFieldOne` y `explicitFieldTwo`, no `localVariableOne` y `localVariableTwo`:

[!code-csharp[ExplicitNamedTuple](../../samples/snippets/csharp/tuples/program.cs#ProjectionExample_Explicit "Explicitly named tuple")]

Para cualquier campo en el que no se proporcione un nombre explícito, se proyecta un nombre implícito aplicable. No hay ningún requisito para proporcionar nombres semánticos, ya sea explícita o implícitamente. El inicializador siguiente tiene nombres de campo `Item1`, cuyo valor es `42` y `stringContent`, cuyo valor es "The answer to everything":

[!code-csharp[MixedTuple](../../samples/snippets/csharp/tuples/program.cs#MixedTuple "mixed tuple")]

Hay dos condiciones donde los nombres de campo de candidato no se proyectan en el campo de la tupla:

1. Cuando el nombre del candidato es un nombre de tupla reservado. Los ejemplos incluyen `Item3`, `ToString` o `Rest`.
1. Cuando el nombre del candidato es un duplicado de otro nombre de campo de tupla, ya sea explícita o implícita.

Estas condiciones evitan la ambigüedad. Estos nombres podrían causar una ambigüedad si se usan como nombres de campo para un campo de una tupla. Ninguna de estas condiciones causan errores en tiempo de compilación. En su lugar, los elementos sin nombres proyectados no tienen nombres semánticos proyectados para ellos.  Los ejemplos siguientes explican estas condiciones:

[!code-csharp-interactive[Ambiguity](../../samples/snippets/csharp/tuples/program.cs#ProjectionAmbiguities "tuples where projections are not performed")]

Estas situaciones no causan errores de compilador dado que sería un cambio importante para el código escrito con C# 7.0, cuando las proyecciones del nombre de campo de tupla no estaban disponibles.

## <a name="equality-and-tuples"></a>Igualdad y tuplas

Comenzando con C# 7.3, los tipos de tupla admiten los operadores `==` y `!=`. Estos operadores funcionan comparando cada uno de los miembros del argumento izquierdo con los miembros del argumento derecho en orden. Estas comparaciones cortocircuitan. Dejarán de evaluar a los miembros en cuanto un par no sea igual. Los siguientes ejemplos de código usan `==`, pero todas las reglas de comparación se aplican a `!=`. En el siguiente ejemplo de código se muestra una comparación de igualdad para dos pares de enteros:

[!code-csharp-interactive[TupleEquality](../../samples/snippets/csharp/tuples/program.cs#Equality "Testing tuples for equality")]

Hay varias reglas que hacen que las pruebas de igualdad de tupla sean más prácticas. La igualdad de tupla realiza [conversiones elevadas](~/_csharplang/spec/conversions.md#lifted-conversion-operators) si una de las tuplas es una tupla que admite valores NULL, como se muestra en el siguiente código:

[!code-csharp-interactive[NullableTupleEquality](../../samples/snippets/csharp/tuples/program.cs#NullableEquality "Comparing Tuples and nullable tuples")]

La igualdad de tupla también realiza conversiones implícitas en cada uno de los miembros de ambas tuplas. Entre estas se incluyen conversiones elevadas, conversiones de ampliación u otras conversiones implícitas. En los siguientes ejemplos se muestra que una tupla de 2 entera se puede comparar con una tupla de 2 larga debido a la conversión implícita de entero a largo:

[!code-csharp-interactive[SnippetMemberConversions](../../samples/snippets/csharp/tuples/program.cs#SnippetMemberConversions "converting tuples for equality tests")]

Los nombres de los miembros de las tuplas no participan en las pruebas para la igualdad. Sin embargo, si uno de los operandos es un literal de tupla con nombres explícitos, el compilador genera la advertencia CS8383 si esos nombres no coinciden con los nombres del otro operando.
Cuando ambos operandos son literales de tupla, la advertencia está en el operando derecho como se muestra en el siguiente ejemplo:

[!code-csharp-interactive[MemberNames](../../samples/snippets/csharp/tuples/program.cs#SnippetMemberNames "Tuple member names do not participate in equality tests")]

Por último, las tuplas pueden contener tuplas anidadas. La igualdad de tupla compara la "forma" de cada operando a través de tuplas anidadas como se muestra en el siguiente ejemplo:

[!code-csharp-interactive[NestedTuples](../../samples/snippets/csharp/tuples/program.cs#SnippetNestedTuples "Tuples may contain nested tuples that participate in tuple equality.")]

Es un error de tiempo de compilación comparar la igualdad (o desigualdad) de dos tuplas cuando tienen formas diferentes. El compilador no intenta ninguna deconstrucción de tuplas anidadas para compararlas.

## <a name="assignment-and-tuples"></a>Asignación y tuplas

El lenguaje admite la asignación entre tipos de tupla que tienen el mismo número de elementos, donde cada elemento del lado derecho se puede convertir de forma implícita en su elemento del lado izquierdo correspondiente. Otras conversiones no se tienen en cuenta para las asignaciones. Es un error de tiempo de compilación asignar una tupla a otra cuando tienen formas diferentes. El compilador no intentará ninguna deconstrucción de tuplas anidadas para asignarlas.
Echemos un vistazo a los tipos de asignaciones que se permiten entre los tipos de tupla.

Tenga en cuenta estas variables que se usan en los ejemplos siguientes:

[!code-csharp[VariableCreation](../../samples/snippets/csharp/tuples/program.cs#03_VariableCreation "Variable creation")]

Las dos primeras variables, `unnamed` y `anonymous`, no tienen nombres semánticos proporcionados para los elementos. Los nombres de campo son `Item1` y `Item2`.
Las dos últimas variables, `named` y `differentName`, tienen nombres semánticos asignados a los elementos. Estas dos tuplas tienen nombres diferentes para los elementos.

Estas cuatro tuplas tienen el mismo número de elementos (denominados "cardinalidad") y los tipos de esos elementos son idénticos. Por consiguiente, todas estas asignaciones funcionan:

[!code-csharp[VariableAssignment](../../samples/snippets/csharp/tuples/program.cs#04_VariableAssignment "Variable assignment")]

Observe que los nombres de las tuplas no se asignan. Los valores de los elementos se asignan según el orden de los campos de la tupla.

Las tuplas de diferentes tipos o números de elementos no son asignables:

```csharp
// Does not compile.
// CS0029: Cannot assign Tuple(int,int,int) to Tuple(int, string)
var differentShape = (1, 2, 3);
named = differentShape;
```

## <a name="tuples-as-method-return-values"></a>Tuplas como valores devueltos del método

Uno de los usos más comunes de tuplas es como un valor devuelto del método. Examinemos un ejemplo. Tenga en cuenta este método que calcula la desviación estándar para una secuencia de números:

[!code-csharp[StandardDeviation](../../samples/snippets/csharp/tuples/statistics.cs#05_StandardDeviation "Compute Standard Deviation")]

> [!NOTE]
> En estos ejemplos se calcula la desviación estándar de muestra sin corregir.
> La fórmula de desviación estándar de muestra corregida dividiría la suma de las diferencias al cuadrado de la media por (N-1) en lugar de N, como hace el método de extensión `Average`. Para obtener más detalles sobre las diferencias entre estas fórmulas de desviación estándar, consulte un texto de estadísticas.

El código anterior sigue la fórmula clásica para la desviación estándar. Genera la respuesta correcta, pero es una implementación poco eficaz. Este método enumera la secuencia dos veces: una para generar el promedio y otra para generar el promedio del cuadrado de la diferencia del promedio.
(Recuerde que las consultas LINQ se evalúan de forma diferida, por lo que el cálculo de las diferencias de la media y el promedio de estas diferencias crea una sola enumeración).

Hay una fórmula alternativa que calcula la desviación estándar mediante una sola enumeración de la secuencia.  Este cálculo genera dos valores cuando enumera la secuencia: la suma de todos los elementos de la secuencia y la suma del valor de cada cuadrado:

[!code-csharp[SumOfSquaresFormula](../../samples/snippets/csharp/tuples/statistics.cs#06_SumOfSquaresFormula "Compute Standard Deviation using the sum of squares")]

Esta versión enumera la secuencia exactamente una vez. Pero no se trata de código reutilizable. A medida que siga trabajando, verá que muchos cálculos estadísticos diferentes usan el número de elementos de la secuencia, la suma de la secuencia y la suma de los cuadrados de la secuencia. Vamos a refactorizar este método y escribir un método de utilidad que genera esos tres valores. Los tres valores pueden devolverse como tupla.

Vamos a actualizar este método para que los tres valores calculados durante la enumeración se almacenen en una tupla. Se crea esta versión:

[!code-csharp[TupleVersion](../../samples/snippets/csharp/tuples/statistics.cs#07_TupleVersion "Refactor to use tuples")]

La compatibilidad de refactorización de Visual Studio facilita la extracción de la funcionalidad de las estadísticas principales en un método privado. Le ofrece un método `private static` que devuelve el tipo de tupla con los tres valores de `Sum`, `SumOfSquares` y `Count`:

[!code-csharp[TupleMethodVersion](../../samples/snippets/csharp/tuples/statistics.cs#08_TupleMethodVersion "After extracting utility method")]

El lenguaje permite un par de opciones más que puede usar si quiere realizar algunas modificaciones rápidas manualmente. En primer lugar, puede usar la declaración `var` para inicializar el resultado de la tupla de la llamada al método `ComputeSumAndSumOfSquares`. También puede crear tres variables discretas dentro del método `ComputeSumAndSumOfSquares`. La versión final se muestra en el siguiente código:

[!code-csharp[CleanedTupleVersion](../../samples/snippets/csharp/tuples/statistics.cs#09_CleanedTupleVersion "After final cleanup")]

Esta versión final puede usarse en cualquier método que necesite esas tres variables o cualquier subconjunto de ellas.

El lenguaje admite otras opciones de administración de los nombres de los elementos en estos métodos de devolución de tuplas.

Puede quitar los nombres de campo de la declaración de valor devuelto y devolver una tupla sin nombre:

```csharp
private static (double, double, int) ComputeSumAndSumOfSquares(IEnumerable<double> sequence)
{
    double sum = 0;
    double sumOfSquares = 0;
    int count = 0;

    foreach (var item in sequence)
    {
        count++;
        sum += item;
        sumOfSquares += item * item;
    }

    return (sum, sumOfSquares, count);
}
```

Los campos de esta tupla se denominan `Item1`, `Item2` y `Item3`.
Se recomienda proporcionar nombres semánticos a los elementos de tuplas devueltas por los métodos.

Otra expresión donde las tuplas pueden ser útiles es cuando crea consultas LINQ. El resultado proyectado final suele contener algunas de las propiedades de los objetos que se seleccionan, pero no todas.

Tradicionalmente, los resultados de la consulta se proyectarían en una secuencia de objetos que fueran un tipo anónimo. Eso suponía muchas limitaciones, sobre todo porque a los tipos anónimos no se les podía asignar nombre cómodamente en el tipo de valor devuelto para un método. Las alternativas que usaban `object` o `dynamic` como tipo de resultado acarreaban importantes costos de rendimiento.

Devolver una secuencia de tipo de tupla es fácil, y los nombres y tipos de los elementos están disponibles en tiempo de compilación y a través de herramientas de IDE.
Por ejemplo, consideremos una aplicación de tareas pendientes. Puede definir una clase similar a la siguiente para representar una sola entrada de la lista de tareas pendientes:

[!code-csharp[ToDoItem](../../samples/snippets/csharp/tuples/projectionsample.cs#14_ToDoItem "To Do Item")]

Puede que las aplicaciones móviles admitan una forma compacta de las tareas pendientes actuales que solo muestra el título. Esa consulta LINQ haría una proyección que solo incluya el identificador y el título. Un método que devuelve una secuencia de tuplas expresa bien ese diseño:

[!code-csharp[QueryReturningTuple](../../samples/snippets/csharp/tuples/projectionsample.cs#15_QueryReturningTuple "Query returning a tuple")]

> [!NOTE]
> En C# 7.1, las proyecciones de tupla permiten crear tuplas con nombre mediante elementos, de forma similar a la propiedad en tipos anónimos. En el código anterior, la instrucción `select` de la proyección de consultas crea una tupla con los elementos `ID` y `Title`.

La tupla con nombre puede ser parte de la firma. Permite que el compilador y las herramientas de IDE usen comprobación de tipo estáticos para ver que el resultado se usa correctamente. La tupla con nombre también incluye información de tipos estáticos, por lo que no hay que usar costosas características en tiempo de ejecución tales como la reflexión o los enlaces dinámicos para trabajar con los resultados.

## <a name="deconstruction"></a>Deconstrucción

Puede desempaquetar todos los elementos de una tupla *deconstruyendo* la tupla devuelta por un método. Existen tres enfoques diferentes para deconstruir tuplas.  En primer lugar, se puede declarar explícitamente el tipo de cada campo entre paréntesis para crear variables discretas para cada uno de los elementos de la tupla:

[!code-csharp[Deconstruct](../../samples/snippets/csharp/tuples/statistics.cs#10_Deconstruct "Deconstruct")]

También puede declarar variables con tipo implícito para cada campo de una tupla mediante la palabra clave `var` fuera de los paréntesis:

[!code-csharp[DeconstructToVar](../../samples/snippets/csharp/tuples/statistics.cs#11_DeconstructToVar "Deconstruct to Var")]

También es válido usar la palabra clave `var` con alguna de las declaraciones de variable, o todas, dentro de los paréntesis.

```csharp
(double sum, var sumOfSquares, var count) = ComputeSumAndSumOfSquares(sequence);
```

No se puede usar un tipo específico fuera de los paréntesis, aunque todos los campos de la tupla tengan el mismo tipo.

También puede deconstruir tuplas con declaraciones existentes:

```csharp
public class Point
{
    public int X { get; set; }
    public int Y { get; set; }

    public Point(int x, int y) => (X, Y) = (x, y);
}
```

> [!WARNING]
> No se pueden mezclar declaraciones existentes con declaraciones incluidas en paréntesis. Por ejemplo, no se permite lo siguiente: `(var x, y) = MyMethod();`. Esto produce el error CS8184 porque *x* se declara dentro de los paréntesis e *y* se ha declarado previamente en otro lugar.

### <a name="deconstructing-user-defined-types"></a>Deconstruir tipos definidos por el usuario

Cualquier tipo de tupla puede deconstruirse, tal y como se muestra anteriormente. También resulta fácil habilitar la deconstrucción en cualquier tipo definido por el usuario (clases, structs o incluso interfaces).

El autor del tipo puede definir uno o varios métodos `Deconstruct` que asignen valores a cualquier número de [ variables `out`](language-reference/keywords/out-parameter-modifier.md) que representen los elementos de datos que componen el tipo. Por ejemplo, el tipo `Person` siguiente define un método `Deconstruct` que deconstruye un objeto person en los elementos que representan el nombre y apellido:

[!code-csharp[TypeWithDeconstructMethod](../../samples/snippets/csharp/tuples/person.cs#12_TypeWithDeconstructMethod "Type with a deconstruct method")]

El método deconstruct permite la asignación desde un objeto `Person` en dos cadenas que representan las propiedades `FirstName` y `LastName`:

[!code-csharp[Deconstruct Type](../../samples/snippets/csharp/tuples/program.cs#12A_DeconstructType "Deconstruct a class type")]

Puede habilitar la deconstrucción incluso para tipos que no ha creado.
El método `Deconstruct` puede ser un método de extensión que desempaqueta los miembros de datos accesibles de un objeto. En el ejemplo siguiente se muestra un tipo `Student`, derivado del tipo `Person` y un método de extensión que deconstruye un `Student` en tres variables, que representan el `FirstName`, el `LastName` y `GPA`:

[!code-csharp[ExtensionDeconstructMethod](../../samples/snippets/csharp/tuples/person.cs#13_ExtensionDeconstructMethod "Type with a deconstruct extension method")]

Un objeto `Student` ahora tiene dos métodos `Deconstruct` accesibles: el método de extensión declarado para tipos `Student` y el miembro del tipo `Person`. Ambos están en el ámbito, lo que permite que un `Student` se deconstruya en dos variables o tres.
Si asigna a un alumno tres variables, se devuelven todas, el nombre, el apellido y el GPA. Si asigna a un alumno dos variables, solo se devuelven el nombre y el apellido.

[!code-csharp[Deconstruct extension method](../../samples/snippets/csharp/tuples/program.cs#13A_DeconstructExtension "Deconstruct a class type using an extension method")]

Se debe tener cuidado al definir varios métodos `Deconstruct` en una clase o una jerarquía de clases. Varios métodos `Deconstruct` con el mismo número de parámetros `out` pueden generar ambigüedades rápidamente. Puede que los autores de llamadas no puedan llamar fácilmente al método `Deconstruct` que quieran.

En este ejemplo, la posibilidad de una llamada ambigua es mínima porque el método `Deconstruct` para `Person` tiene dos parámetros de salida y el método `Deconstruct` para `Student` tiene tres.

Los operadores de deconstrucción no participan en la igualdad de las pruebas. El ejemplo siguiente genera el error del compilador CS0019:

```csharp
Person p = new Person("Althea", "Goodwin");
if (("Althea", "Goodwin") == p)
    Console.WriteLine(p);
```

El método `Deconstruct` podría convertir el objeto `Person``p` en una tupla que contiene dos cadenas, pero no se puede aplicar en el contexto de las pruebas de igualdad.

## <a name="tuples-as-out-parameters"></a>Tuplas como parámetros de salida

Las tuplas se pueden usar como [ parámetros `out`](language-reference/keywords/out-parameter-modifier.md) *en sí*. No se deben confundir con ninguna ambigüedad mencionada anteriormente en la sección [Deconstrucción](#deconstruction). En una llamada al método, solo necesita describir la forma de la tupla:

[!code-csharp[TuplesAsOutParameters](~/samples/snippets/csharp/tuples/program.cs#01_TupleAsOutVariable "Tuples as out parameters")]

Como alternativa, puede usar una tupla [_sin nombre_](#named-and-unnamed-tuples) y hacer referencia a sus campos como `Item1` y `Item2`:

```csharp
dict.TryGetValue(2, out (int, string) pair);
// ...
Console.WriteLine($"{pair.Item1}: {pair.Item2}");
```

## <a name="conclusion"></a>Conclusión

La compatibilidad con tuplas con nombre del nuevo lenguaje y la biblioteca hace que resulte mucho más fácil trabajar con diseños que usan estructuras de datos que almacenan varios elementos, pero no definen el comportamiento, como clases y structs. El uso de tuplas para esos tipos resulta fácil y conciso. Se tienen todas las ventajas de la comprobación de tipos estáticos, sin necesidad de crear tipos con la sintaxis más detallada de `class` o `struct`. Aun así, resultan muy útiles para métodos de utilidad que sean `private` o `internal`. Cree tipos definidos por el usuario, tipos `class` o `struct`, cuando los métodos públicos devuelvan un valor con varios elementos.
