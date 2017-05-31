---
title: "Tuplas | Guía de C#"
description: "Más información sobre tipos de tupla con nombre y sin nombre en C#"
keywords: .NET, .NET Core, C#
author: BillWagner
ms-author: wiwagn
ms.date: 11/23/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: ee8bf7c3-aa3e-4c9e-a5c6-e05cc6138baa
ms.translationtype: Human Translation
ms.sourcegitcommit: 6b30f41e3fb07a962542a09a41c698efee7ebb5a
ms.openlocfilehash: 0ea7299d87dc69784e3bed93e48d83e4a0076a20
ms.contentlocale: es-es
ms.lasthandoff: 04/26/2017

---

# <a name="c-tuple-types"></a>Tipos de tupla de C# #

Las tuplas de C# son tipos que se definen mediante una sintaxis ligera. Entre otras ventajas, incluyen una sintaxis más sencilla, reglas para conversiones en función de un número (denominadas "aridad") y tipos de campos y reglas coherentes para copias y asignaciones. Como contrapartida, las tuplas no admiten algunas de las expresiones orientadas a objetos que se asocian a la herencia. Puede obtener información general de la sección sobre [tuplas en el tema Novedades de C# 7](whats-new/csharp-7.md#tuples).

En este tema, conocerá las reglas del lenguaje que rigen las tuplas en C# 7, distintas formas de usarlas y una guía inicial sobre cómo trabajar con tuplas.

> [!NOTE]
> Las nuevas características de tupla requieren el tipo `System.ValueTuple`. Para Visual Studio 2017, debe agregar el paquete NuGet [System.ValueTuple](https://www.nuget.org/packages/System.ValueTuple/), disponible en la galería de NuGet.
> Puede que sin este paquete obtenga un error de compilación similar a `error CS8179: Predefined type 'System.ValueTuple``2' is not defined or imported` o `error CS8137: Cannot define a class or member that utilizes tuples because the compiler required type 'System.Runtime.CompilerServices.TupleElementNamesAttribute' cannot be found.`

Empecemos por las razones para agregar nueva compatibilidad de tupla. Los métodos devuelven un solo objeto. Las tuplas permiten empaquetar varios valores en ese único objeto más fácilmente. 

.NET Framework ya incluye clases `Tuple` genéricas. Pero estas clases planteaban dos importantes limitaciones. En primer lugar, las clases `Tuple` denominan sus campos `Item1`, `Item2`, etc. Esos nombres no incluyen ninguna información semántica. El uso de estos tipos `Tuple` no permite comunicar el significado de cada uno de los campos. Otro inconveniente es que las clases `Tuple` son tipos de referencia. El uso de uno de los tipos `Tuple` implica la asignación de objetos. En rutas de acceso activas, esto puede suponer un importante impacto en el rendimiento de la aplicación.

Para evitar esas deficiencias, podría crear un `class` o `struct` que incluya varios campos. Lamentablemente, esto representa más trabajo para el usuario y oculta la intención del diseño. La creación de un `struct` o `class` implica que se define un tipo con datos y comportamiento. Muchas veces, simplemente quiere almacenar varios valores en un solo objeto.

Las nuevas características de lenguaje para tuplas, combinadas con un nuevo conjunto de clases de Framework, abordan estas deficiencias. Estas nuevas tuplas usan los nuevos structs genéricos `ValueTuple`. Como su nombre indica, este tipo es un `struct` en lugar de un `class`. Hay diferentes versiones de este struct que admiten tuplas con un número diferente de campos. La compatibilidad del nuevo lenguaje proporciona nombres semánticos para los campos del tipo de tupla, junto con características que facilitan la construcción o el acceso a campos de tupla.

Las características del lenguaje y los structs genéricos `ValueTuple` aplican la regla que establece que no se puede agregar ningún comportamiento (métodos) a estos tipos de tupla.
Todos los tipos `ValueTuple` son *structs mutables*. Cada campo de miembro es un campo público. Eso los hace muy ligeros. Pero indica que no se deben usar tuplas cuando la inmutabilidad es importante.

Las tuplas son contenedores de datos más sencillos y flexibles que los tipos `class` y `struct`. Examinemos esas diferencias.

## <a name="named-and-unnamed-tuples"></a>Tuplas con nombre y sin nombre

El struct `ValueTuple` incluye campos denominados `Item1`, `Item2`, `Item3`, etc., similares a las propiedades definidas en los tipos `Tuple` existentes.
Estos nombres son los únicos que se pueden usar en *tuplas sin nombre*. Si no proporciona ningún nombre de campo alternativo para una tupla, ha creado una tupla sin nombre:

[!code-csharp[UnnamedTuple](../../samples/snippets/csharp/tuples/tuples/program.cs#01_UnNamedTuple "Tupla sin nombre")]

Pero al inicializar una tupla, se pueden usar nuevas características del lenguaje que asignen nombres mejores a cada campo. Así se crea una *tupla con nombre*.
Las tuplas con nombre todavía tienen campos denominados `Item1`, `Item2`, `Item3`, etc.
Pero también tienen sinónimos para cualquiera de los campos a los que haya asignado un nombre.
Cree una tupla con nombre especificando los nombres de cada campo. Una forma consiste en especificar los nombres como parte de la inicialización de la tupla:

[!code-csharp[NamedTuple](../../samples/snippets/csharp/tuples/tuples/program.cs#02_NamedTuple "Tupla con nombre")]

Estos sinónimos los controlan el compilador y el lenguaje para que se puedan usar tuplas con nombre de manera eficaz. Los IDE y los editores pueden leer estos nombres semánticos con las API de Roslyn. Esto le permite hacer referencia a los campos de una tupla con nombre por esos nombres semánticos en cualquier lugar de un mismo ensamblado. El compilador reemplaza los nombres que ha definido con `Item*` equivalentes al generar la salida compilada. El Lenguaje Intermedio de Microsoft (MSIL) compilado no incluye los nombres que se hayan asignado a estos campos. 

El compilador debe comunicar esos nombres creados por el usuario para tuplas que se devuelvan de métodos o propiedades públicos. En esos casos, el compilador agrega un atributo `TupleElementNames` en el método. Este atributo contiene una propiedad de lista `TransformNames` que contiene los nombres asignados a cada uno de los campos de la tupla. 

> [!NOTE]
> Las herramientas de desarrollo, como Visual Studio, también leen esos metadatos y proporcionan IntelliSense y otras características con los nombres de campo de metadatos.

Es importante comprender estos aspectos fundamentales subyacentes de las nuevas tuplas y el tipo `ValueTuple` para entender las reglas de asignación de tuplas con nombre entre sí.

## <a name="assignment-and-tuples"></a>Asignación y tuplas

El lenguaje admite la asignación entre tipos de tupla con el mismo número de campos y conversiones implícitas para los tipos para cada uno de esos campos. Otras conversiones no se tienen en cuenta para las asignaciones. Echemos un vistazo a los tipos de asignaciones que se permiten entre los tipos de tupla.

Tenga en cuenta estas variables que se usan en los ejemplos siguientes:

[!code-csharp[VariableCreation](../../samples/snippets/csharp/tuples/tuples/program.cs#03_VariableCreation "Creación de variables")]

Las dos primeras variables, `unnamed` y `anonymous`, no tienen nombres semánticos proporcionados para los campos. Los nombres de campo son `Item1` y `Item2`.
Las dos últimas variables, `named` y `differentName`, tienen nombres semánticos asignados a los campos. Tenga en cuenta que estas dos tuplas tienen nombres diferentes para los campos.

Estas cuatro tuplas tiene el mismo número de campos (denominados "aridad") y los tipos de esos campos son idénticos. Por consiguiente, todas estas asignaciones funcionan:

[!code-csharp[VariableAssignment](../../samples/snippets/csharp/tuples/tuples/program.cs#04_VariableAssignment "Asignación de variables")]

Observe que los nombres de las tuplas no se asignan. Los valores de los campos se asignan según el orden de los campos de la tupla.

Las tuplas de diferentes tipos o números de campos no son asignables:

```csharp
// Does not compile.
// CS0029: Cannot assign Tuple(int,int,int) to Tuple(int, string)
var differentShape = (1, 2, 3);
named = differentShape;
```

## <a name="tuples-as-method-return-values"></a>Tuplas como valores devueltos del método

Uno de los usos más comunes de tuplas es como un valor devuelto del método. Examinemos un ejemplo. Tenga en cuenta este método que calcula la desviación estándar para una secuencia de números:

[!code-csharp[StandardDeviation](../../samples/snippets/csharp/tuples/tuples/statistics.cs#05_StandardDeviation "Calcular la desviación estándar")]

> [!NOTE]
> En estos ejemplos se calcula la desviación estándar de muestra sin corregir.
> La fórmula de desviación estándar de muestra corregida dividiría la suma de las diferencias al cuadrado de la media por (N-1) en lugar de N, como hace el método de extensión `Average`. Para obtener más detalles sobre las diferencias entre estas fórmulas de desviación estándar, consulte un texto de estadísticas.

Se sigue la fórmula clásica para la desviación estándar. Genera la respuesta correcta, pero es una implementación muy poco eficaz. Este método enumera la secuencia dos veces: una para generar el promedio y otra para generar el promedio del cuadrado de la diferencia del promedio.
(Recuerde que las consultas LINQ se evalúan de forma diferida, por lo que el cálculo de las diferencias de la media y el promedio de estas diferencias crea una sola enumeración).

Hay una fórmula alternativa que calcula la desviación estándar mediante una sola enumeración de la secuencia.  Este cálculo genera dos valores cuando enumera la secuencia: la suma de todos los elementos de la secuencia y la suma del valor de cada cuadrado:

[!code-csharp[SumOfSquaresFormula](../../samples/snippets/csharp/tuples/tuples/statistics.cs#06_SumOfSquaresFormula "Calcular la desviación estándar mediante la suma de cuadrados")]

Este versión enumera la secuencia exactamente una vez. Pero no se trata de código muy reutilizable. A medida que siga trabajando, verá que muchos cálculos estadísticos diferentes usan el número de elementos de la secuencia, la suma de la secuencia y la suma de los cuadrados de la secuencia. Vamos a refactorizar este método y escribir un método de utilidad que genera esos tres valores.

Aquí es donde las tuplas resultan de gran utilidad. 

Vamos a actualizar este método para que los tres valores calculados durante la enumeración se almacenen en una tupla. Se crea esta versión:

[!code-csharp[TupleVersion](../../samples/snippets/csharp/tuples/tuples/statistics.cs#07_TupleVersion "Refactorizar para usar tuplas")]

La compatibilidad de refactorización de Visual Studio facilita la extracción de la funcionalidad de las estadísticas de núcleo en un método privado. Le ofrece un método `private static` que devuelve el tipo de tupla con los tres valores de `Sum`, `SumOfSquares` y `Count`:

[!code-csharp[TupleMethodVersion](../../samples/snippets/csharp/tuples/tuples/statistics.cs#08_TupleMethodVersion "Después de extraer un método de utilidad")]
 
El lenguaje permite un par de opciones más que puede usar si quiere realizar algunas modificaciones rápidas manualmente. En primer lugar, puede usar la declaración `var` para inicializar el resultado de la tupla de la llamada al método `ComputeSumAndSumOfSquares`. También puede crear tres variables discretas dentro del método `ComputeSumAndSumOfSquares`. Aquí tiene la versión final:

[!code-csharp[CleanedTupleVersion](../../samples/snippets/csharp/tuples/tuples/statistics.cs#09_CleanedTupleVersion "Después de la última limpieza")]

Esta versión final puede usarse en cualquier método que necesite esas tres variables o cualquier subconjunto de ellas.

El lenguaje admite otras opciones de administración de los nombres de los campos en estos métodos de devolución de tupla.

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

Debe resolver los campos de esta tupla como `Item1`, `Item2` y `Item3`.
Se recomienda proporcionar nombres semánticos a los campos de tuplas devueltas por los métodos.

Otra expresión en donde las tuplas pueden resultar muy útiles se da al crear consultas LINQ cuyo resultado final es una proyección que contiene algunas, pero no todas, las propiedades de los objetos que se seleccionan.

Tradicionalmente, los resultados de la consulta se proyectarían en una secuencia de objetos que fueran un tipo anónimo. Eso suponía muchas limitaciones, sobre todo porque a los tipos anónimos no se les podía asignar nombre cómodamente en el tipo de valor devuelto para un método. Las alternativas que usaban `object` o `dynamic` como tipo de resultado acarreaban importantes costos de rendimiento.

Devolver una secuencia de tipo de tupla es fácil, y los nombres y tipos de los campos están disponibles en tiempo de compilación y a través de herramientas de IDE.
Por ejemplo, consideremos una aplicación de tareas pendientes. Puede definir una clase similar a la siguiente para representar una sola entrada de la lista de tareas pendientes:

[!code-csharp[ToDoItem](../../samples/snippets/csharp/tuples/tuples/projectionsample.cs#14_ToDoItem "Tarea pendiente")]

Puede que las aplicaciones móviles admitan una forma compacta de las tareas pendientes actuales que solo muestra el título. Esa consulta LINQ haría una proyección que solo incluya el identificador y el título. Un método que devuelve una secuencia de tuplas expresa muy bien ese diseño:

[!code-csharp[QueryReturningTuple](../../samples/snippets/csharp/tuples/tuples/projectionsample.cs#15_QueryReturningTuple "Consulta que devuelve una tupla")]

La tupla con nombre puede ser parte de la firma. Permite que el compilador y las herramientas de IDE usen comprobación de tipo estáticos para ver que el resultado se usa correctamente. La tupla con nombre también incluye información de tipos estáticos, por lo que no hay que usar costosas características en tiempo de ejecución tales como la reflexión o los enlaces dinámicos para trabajar con los resultados.

## <a name="deconstruction"></a>Deconstrucción

Puede desempaquetar todos los elementos de una tupla *deconstruyendo* la tupla devuelta por un método. Existen dos enfoques diferentes para deconstruir tuplas.  En primer lugar, se puede declarar explícitamente el tipo de cada campo entre paréntesis para crear variables discretas para cada uno de los campos de la tupla:

[!code-csharp[Deconstruct](../../samples/snippets/csharp/tuples/tuples/statistics.cs#10_Deconstruct "Deconstruir")]

También puede declarar variables con tipo implícito para cada campo de una tupla mediante la palabra clave `var` fuera de los paréntesis:

[!code-csharp[DeconstructToVar](../../samples/snippets/csharp/tuples/tuples/statistics.cs#11_DeconstructToVar "Deconstruir a variable")]

También es válido usar la palabra clave `var` con alguna de las declaraciones de variable, o todas, dentro de los paréntesis. 

```csharp
(double sum, var sumOfSquares, var count) = ComputeSumAndSumOfSquares(sequence);
```
Tenga en cuenta que no se puede usar un tipo específico fuera de los paréntesis, aunque todos los campos de la tupla tengan el mismo tipo.

### <a name="deconstructing-user-defined-types"></a>Deconstruir tipos definidos por el usuario

Cualquier tipo de tupla puede deconstruirse, tal y como se muestra anteriormente. También resulta fácil habilitar la deconstrucción en cualquier tipo definido por el usuario (clases, structs o incluso interfaces).

El autor del tipo puede definir uno o varios métodos `Deconstruct` que asignen valores a cualquier número de variables `out` que representen los elementos de datos que componen el tipo. Por ejemplo, el tipo `Person` siguiente define un método `Deconstruct` que deconstruye un objeto person en los campos que representan el nombre y apellido:

[!code-csharp[TypeWithDeconstructMethod](../../samples/snippets/csharp/tuples/tuples/person.cs#12_TypeWithDeconstructMethod "Tipo con un método deconstruct")]

El método deconstruct permite la asignación desde un objeto `Person` en dos cadenas que representan las propiedades `FirstName` y `LastName`:

[!code-csharp[Deconstruir tipo](../../samples/snippets/csharp/tuples/tuples/program.cs#12A_DeconstructType "Deconstruir un tipo de clase")]

Puede habilitar la deconstrucción incluso para tipos que no ha creado.
El método `Deconstruct` puede ser un método de extensión que desempaqueta los miembros de datos accesibles de un objeto. El ejemplo siguiente muestra un tipo `Student`, derivado del tipo `Person` y un método de extensión que deconstruye un `Student` en tres variables, que representan el `FirstName`, el `LastName` y `GPA`:

[!code-csharp[ExtensionDeconstructMethod](../../samples/snippets/csharp/tuples/tuples/person.cs#13_ExtensionDeconstructMethod "Tipo con un método de extensión deconstruct")]

Un objeto `Student` ahora tiene dos métodos `Deconstruct` accesibles: el método de extensión declarado para tipos `Student` y el miembro del tipo `Person`. Ambos están en el ámbito, lo que permite que un `Student` se deconstruya en dos variables o tres.
Si asigna a un alumno tres variables, se devuelven todas, el nombre, el apellido y el GPA. Si asigna a un alumno dos variables, solo se devuelven el nombre y el apellido.

[!code-csharp[Método de extensión deconstruct](../../samples/snippets/csharp/tuples/tuples/program.cs#13A_DeconstructExtension "Deconstruir un tipo de clase con un método de extensión")]

Se debe tener mucho cuidado al definir varios métodos `Deconstruct` en una clase o una jerarquía de clases. Varios métodos `Deconstruct` con el mismo número de parámetros `out` pueden generar ambigüedades rápidamente. Puede que los autores de llamadas no puedan llamar fácilmente al método `Deconstruct` que quieran.

En este ejemplo, la posibilidad de una llamada ambigua es mínima porque el método `Deconstruct` para `Person` tiene dos parámetros de salida y el método `Deconstruct` para `Student` tiene tres.

## <a name="conclusion"></a>Conclusión 

La compatibilidad con tuplas con nombre del nuevo lenguaje y la biblioteca hace que resulte mucho más fácil trabajar con diseños que usan estructuras de datos que almacenan varios campos, pero no definen el comportamiento, como clases y structs. El uso de tuplas para esos tipos resulta fácil y conciso. Se tienen todas las ventajas de la comprobación de tipos estáticos, sin necesidad de crear tipos con la sintaxis más detallada de `class` o `struct`. Aun así, resultan muy útiles para métodos de utilidad que sean `private` o `internal`. Cree tipos definidos por el usuario, tipos `class` o `struct`, cuando los métodos públicos devuelvan un valor con varios campos.

