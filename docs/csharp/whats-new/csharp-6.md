---
title: Novedades de C# 6 - Guía de C#
description: Obtenga información sobre las nuevas características de la versión 6 de C#
ms.date: 09/22/2016
ms.assetid: 4d879f69-f889-4d3f-a781-75194e143400
ms.openlocfilehash: ad3515e1fc7d70e1377f007276c369d2884780f0
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
ms.locfileid: "50194038"
---
# <a name="whats-new-in-c-6"></a>Novedades de C# 6

La versión 6.0 de C# incluye muchas características que mejoran la productividad para los desarrolladores. Estas son algunas de las características de esta versión:

* [Propiedades automáticas de solo lectura](#read-only-auto-properties):
    - Se pueden crear propiedades automáticas de solo lectura que solo se puedan establecer en los constructores.
* [Inicializadores de propiedades automáticas](#auto-property-initializers):
    - Se pueden escribir expresiones de inicialización para establecer el valor inicial de una propiedad automática.
* [Miembros de función con cuerpos de expresión](#expression-bodied-function-members):
    - Se pueden crear métodos de una línea mediante expresiones lambda.
* [using static](#using-static):
    - Se pueden importar todos los métodos de una clase única al espacio de nombres actual.
* [Operadores condicionales NULL](#null-conditional-operators):
    - Se puede obtener acceso de forma concisa y segura a los miembros de un objeto mientras continúa la comprobación de NULL con el operador condicional NULL.
* [Interpolación de cadenas](#string-interpolation):
    - Se pueden escribir expresiones de formato de cadena mediante expresiones insertadas en lugar de argumentos posicionales.
* [Filtros de excepciones](#exception-filters):
    - Se pueden detectar expresiones basadas en propiedades de la excepción o en otro estado del programa. 
* [Expresión `nameof`](#the-nameof-expression):
    - Se puede permitir que el compilador genere las representaciones de cadena de símbolos.
* [await en bloques catch y finally](#await-in-catch-and-finally-blocks):
    - Se pueden usar expresiones `await` en ubicaciones que previamente no las permitían.
* [Inicializadores de índice](#index-initializers):
    - Se pueden crear expresiones de inicialización para contenedores asociativos y también para contenedores de secuencias.
* [Métodos de extensión para inicializadores de colección](#extension-add-methods-in-collection-initializers):
    - Los inicializadores de colección pueden basarse en métodos de extensión accesibles, además de métodos miembro.
* [Mejoras en la resolución de sobrecarga](#improved-overload-resolution):
    - Algunas construcciones que previamente generaban llamadas de método ambiguas ahora se resuelven correctamente.
* [Opción del compilador `deterministic`](#deterministic-compiler-output):
    - La opción del compilador determinista garantiza que las compilaciones posteriores del mismo origen generan el mismo resultado binario.

El efecto general de estas características es que se escribe código más conciso y legible. La sintaxis contiene menos complejidad para muchas de las prácticas habituales. Es más fácil ver la intención del diseño con menos complejidad. Aprender bien estas características le permitirá ser más productivo, escribir código más legible y concentrarse más en las características principales que en las construcciones del lenguaje.

En el resto de este tema se proporcionan detalles sobre cada una de estas características.

## <a name="auto-property-enhancements"></a>Mejoras de propiedades automáticas

La sintaxis de las propiedades implementadas automáticamente (normalmente denominadas "propiedades automáticas") facilitó la creación de propiedades que tenían descriptores de acceso get y set sencillos:

[!code-csharp[ClassicAutoProperty](../../../samples/snippets/csharp/new-in-6/oldcode.cs#ClassicAutoProperty)]

Pero esta sintaxis simple limitaba los tipos de diseños que se podían admitir mediante las propiedades automáticas. C# 6 mejora las capacidades de las propiedades automáticas para que se puedan usar en más escenarios. No será necesario recurrir con tanta frecuencia a la sintaxis más detallada de la declaración y manipulación del campo de respaldo a mano.

La nueva sintaxis está dirigida a escenarios para propiedades de solo lectura y a la inicialización del almacenamiento de variables detrás de una propiedad automática.

### <a name="read-only-auto-properties"></a>Propiedades automáticas de solo lectura

*Las propiedades automáticas de solo lectura* proporcionan una sintaxis más concisa para crear tipos inmutables. Lo más cerca que se podía llegar a los tipos inmutables en versiones anteriores de C# era declarar establecedores privados:

[!code-csharp[ClassicReadOnlyAutoProperty](../../../samples/snippets/csharp/new-in-6/oldcode.cs#ClassicReadOnlyAutoProperty)]
 
Con esta sintaxis, el compilador no garantiza que el tipo sea realmente inmutable. Solo exige que las propiedades `FirstName` y `LastName` no se modifiquen desde ningún código fuera de la clase.

Las propiedades automáticas de solo lectura habilitan el comportamiento real de solo lectura. La propiedad automática se declara solo con un descriptor de acceso get:

[!code-csharp[ReadOnlyAutoProperty](../../../samples/snippets/csharp/new-in-6/newcode.cs#ReadOnlyAutoProperty)]

Las propiedades `FirstName` y `LastName` solo se pueden establecer en el cuerpo de un constructor:

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

Esta característica habilita la compatibilidad del lenguaje real para crear tipos inmutables y usar la sintaxis de propiedades automáticas más concisa y cómoda.

Si al agregar esta sintaxis no se quita un método accesible, se trata de un [cambio compatible con los elementos binarios](version-update-considerations.md#binary-compatible-changes).

### <a name="auto-property-initializers"></a>Inicializadores de propiedades automáticas

Los *inicializadores de propiedades automáticas* permiten declarar el valor inicial de una propiedad automática como parte de la declaración de la propiedad.  En versiones anteriores, estas propiedades debían tener establecedores y era necesario usar ese establecedor para inicializar el almacenamiento de datos usado por el campo de respaldo. Considere esta clase para un alumno que contiene el nombre y una lista de las notas del alumno:

[!code-csharp[Construction](../../../samples/snippets/csharp/new-in-6/oldcode.cs#Construction)]
 
A medida que esta clase crece, se pueden incluir otros constructores. Cada constructor debe inicializar este campo o se producirán errores.

C# 6 le permite asignar un valor inicial para el almacenamiento usado por una propiedad automática en la declaración de la propiedad automática:

[!code-csharp[Initialization](../../../samples/snippets/csharp/new-in-6/newcode.cs#Initialization)]

El miembro `Grades` se inicializa cuando se declara. Eso hace que sea más fácil realizar la inicialización exactamente una sola vez. La inicialización es parte de la declaración de la propiedad, lo que facilita igualar la asignación de almacenamiento con la interfaz pública para objetos `Student`.

Los inicializadores de propiedad se pueden usar con propiedades de lectura y escritura, y también con propiedades de solo lectura, como se muestra aquí.

[!code-csharp[ReadWriteInitialization](../../../samples/snippets/csharp/new-in-6/newcode.cs#ReadWriteInitialization)]

## <a name="expression-bodied-function-members"></a>Miembros de función con cuerpos de expresión

El cuerpo de muchos miembros que se escriben consta de una sola instrucción que se puede representar como una expresión. Se puede reducir esa sintaxis escribiendo en su lugar un miembro con cuerpo de expresión. Funciona para métodos y propiedades de solo lectura. Por ejemplo, un reemplazo de `ToString()` suele ser un excelente candidato:

[!code-csharp[ToStringExpressionMember](../../../samples/snippets/csharp/new-in-6/newcode.cs#ToStringExpressionMember)]

También se pueden usar miembros con cuerpo de expresión en propiedades de solo lectura:

[!code-csharp[FullNameExpressionMember](../../../samples/snippets/csharp/new-in-6/newcode.cs#FullNameExpressionMember)]

Cambiar un miembro existente por un miembro con cuerpo de expresión es un [cambio compatible con un elemento binario](version-update-considerations.md#binary-compatible-changes).


## <a name="using-static"></a>uso de versión estática

La mejora *using static* permite importar los métodos estáticos de una sola clase. Anteriormente, la instrucción `using` importaba todos los tipos en un espacio de nombres. 

A menudo, se usan los métodos estáticos de una clase a lo largo del código. Escribir repetidamente el nombre de clase puede oscurecer el significado del código. Un ejemplo común es cuando se escriben clases que realizan muchos cálculos numéricos.
El código se llenará de <xref:System.Math.Sin%2A>, <xref:System.Math.Sqrt%2A> y otras llamadas a métodos diferentes en la clase <xref:System.Math>. La nueva sintaxis `using static` puede hacer que estas clases sean mucho más fáciles de leer. Se especifica la clase que se está usando:

[!code-csharp[UsingStaticMath](../../../samples/snippets/csharp/new-in-6/newcode.cs#UsingStaticMath)]

Y ahora, se puede usar cualquier método estático de la clase <xref:System.Math> sin calificar la clase <xref:System.Math>. La clase <xref:System.Math> es un excelente caso de uso para esta característica porque no contiene ningún método de instancia. También se puede usar `using static` para importar los métodos estáticos de una clase para una clase que tiene métodos estáticos y de instancia. Uno de los ejemplos más útiles es <xref:System.String>:

[!code-csharp[UsingStatic](../../../samples/snippets/csharp/new-in-6/newcode.cs#UsingStatic)]

> [!NOTE]
> Se debe usar el nombre de clase completo, `System.String`, en una instrucción static using. No se puede usar la palabra clave `string` en su lugar. 

Ahora se puede llamar a los métodos estáticos definidos en la clase <xref:System.String> sin calificar esos métodos como miembros de la clase:

[!code-csharp[UsingStaticString](../../../samples/snippets/csharp/new-in-6/newcode.cs#UsingStaticString)]

La característica `static using` y los métodos de extensión interactúan de formas interesantes y el diseño del lenguaje incluye algunas reglas dedicadas específicamente a esas interacciones. El objetivo es minimizar las posibilidades de cambios bruscos en códigos base existentes, incluido el suyo.

Los métodos de extensión solo están en ámbito cuando se llaman mediante la sintaxis de invocación de métodos de extensión, no cuando se llaman como un método estático.
A menudo verá esto en las consultas LINQ. Puede importar el modelo LINQ mediante la importación de <xref:System.Linq.Enumerable>.

[!code-csharp[UsingStaticLinq](../../../samples/snippets/csharp/new-in-6/newcode.cs#usingStaticLinq)]

Esto importa todos los métodos de la clase <xref:System.Linq.Enumerable>.
Pero los métodos de extensión solo están en ámbito cuando se llaman como métodos de extensión. No están en el ámbito si se llaman usando la sintaxis de métodos estáticos:

[!code-csharp[UsingStaticLinqMethod](../../../samples/snippets/csharp/new-in-6/newcode.cs#UsingStaticLinkMethod)]

Esta decisión se debe a que normalmente los métodos de extensión se llaman mediante expresiones de invocación de método de extensión. El caso excepcional de que se llamen mediante la sintaxis de llamada de método estático es para resolver ambigüedades.
Parece aconsejable que se requiera el nombre de clase como parte de la llamada.

Hay una última característica de `static using`. La directiva `static using` también importa cualquier tipo anidado. Esto permite hacer referencia a los tipos anidados sin calificación.

## <a name="null-conditional-operators"></a>Operadores condicionales NULL

Los valores NULL complican el código. Es necesario comprobar todos los accesos de variables para asegurarse de que no se va a desreferenciar `null`. El *operador condicional NULL* realiza esas comprobaciones de una forma mucho más sencilla y fluida.

Simplemente reemplace el acceso a miembros `.` por `?.`:

[!code-csharp[NullConditional](../../../samples/snippets/csharp/new-in-6/program.cs#NullConditional)]

En el ejemplo anterior, se asigna `null` a la variable `first` si el objeto person es `null`. De lo contrario, se le asigna el valor de la propiedad `FirstName`. Lo más importante, `?.` significa que esta línea de código no genera una excepción `NullReferenceException` cuando la variable `person` es `null`. En su lugar, se cortocircuita y genera `null`.

Además, tenga en cuenta que esta expresión devuelve `string`, independientemente del valor de `person`.
En caso de cortocircuito, se devuelve el valor `null` con tipo para que coincida con la expresión completa.

A menudo se puede usar esta construcción con el operador de *fusión nula* para asignar valores predeterminados cuando una de las propiedades es `null`:

[!code-csharp[NullCoalescing](../../../samples/snippets/csharp/new-in-6/program.cs#NullCoalescing)]

El operando del lado derecho del operador `?.` no se limita a propiedades o campos.
También se puede usar para invocar métodos de forma condicional. El uso más común de las funciones miembro con el operador condicional NULL es invocar de forma segura delegados (o controladores de eventos) que puedan ser `null`.  Para ello, se llama al método `Invoke` del delegado usando el operador `?.` para obtener acceso al miembro. Puede ver un ejemplo en el  
tema de [patrones de delegado](../delegates-patterns.md#handling-null-delegates).

Las reglas del operador `?.` garantizan que el lado izquierdo del operador solo se evalúa una vez. Esto es importante y permite muchos elementos, incluidos el ejemplo mediante controladores de eventos. Comencemos con el uso del controlador de eventos. En versiones anteriores de C#, se recomendaba escribir código como este:

```csharp
var handler = this.SomethingHappened;
if (handler != null)
    handler(this, eventArgs);
```

Esto se prefería a una sintaxis más sencilla:

```csharp
// Not recommended
if (this.SomethingHappened != null)
    this.SomethingHappened(this, eventArgs);
```

> [!IMPORTANT]
> El ejemplo anterior presenta una condición de carrera. El evento `SomethingHappened` puede tener suscriptores cuando se comprueba `null`, y los suscriptores se pueden haber quitado antes de que se genere el evento. Esto supondría que se produjera una excepción <xref:System.NullReferenceException>.

En esta segunda versión, es posible que el controlador de eventos `SomethingHappened` sea distinto de NULL cuando se prueba, pero si otro código quita un controlador, aún podría ser NULL cuando se llama al controlador de eventos.

El compilador genera código para el operador `?.` que garantiza que el lado izquierdo (`this.SomethingHappened`) de la expresión `?.` se evalúa una vez y el resultado se almacena en caché:

```csharp
// preferred in C# 6:
this.SomethingHappened?.Invoke(this, eventArgs);
```

Asegurarse de que el lado izquierdo se evalúa solo una vez también le permite usar cualquier expresión, incluidas las llamadas de método, en el lado izquierdo del `?.`. Incluso si hay efectos secundarios, se evalúan una vez, por lo que los efectos secundarios solo se producen una vez. Puede ver un ejemplo en nuestro contenido en [eventos](../events-overview.md#language-support-for-events).

## <a name="string-interpolation"></a>Interpolación de cadenas

C# 6 contiene nueva sintaxis para crear cadenas a partir de una cadena y expresiones insertadas que se evalúan para generar otros valores de cadena.

Tradicionalmente, era necesario usar parámetros posicionales en un método como <xref:System.String.Format%2A?displayProperty=nameWithType>:

[!code-csharp[stringFormat](../../../samples/snippets/csharp/new-in-6/oldcode.cs#stringFormat)]

Con C# 6, la nueva característica [interpolación de cadenas](../language-reference/tokens/interpolated.md) permite insertar las expresiones en una cadena. Solo hay que anteponer la cadena con `$`:

[!code-csharp[stringInterpolation](../../../samples/snippets/csharp/new-in-6/newcode.cs#FullNameExpressionMember)]

Este ejemplo usa expresiones de propiedad para las expresiones sustituidas. Se puede expandir esta sintaxis para usar cualquier expresión. Por ejemplo, se podría calcular la puntuación media de un alumno como parte de la interpolación:

[!code-csharp[stringInterpolationExpression](../../../samples/snippets/csharp/new-in-6/newcode.cs#stringInterpolationExpression)]

Al ejecutar el ejemplo anterior, encontrará que es posible que la salida de `Grades.Average()` tenga más posiciones decimales de las que querría. La sintaxis de interpolación de cadena admite todas las cadenas de formato disponibles mediante el uso de los métodos de formato anteriores. La cadena de formato se especifica entre las llaves. Agregue un signo `:` después de la expresión a la que se va a dar formato:

[!code-csharp[stringInterpolationFormat](../../../samples/snippets/csharp/new-in-6/newcode.cs#stringInterpolationFormat)]

La línea de código anterior dará formato al valor de `Grades.Average()` como un número de punto flotante con dos posiciones decimales.

El símbolo `:` siempre se interpreta como el separador entre la expresión a la que se va a dar formato y la cadena de formato. Esto puede ocasionar problemas cuando la expresión usa un signo `:` de otra manera, por ejemplo un [operador condicional](../language-reference/operators/conditional-operator.md):

```csharp
public string GetGradePointPercentages() =>
    $"Name: {LastName}, {FirstName}. G.P.A: {Grades.Any() ? Grades.Average() : double.NaN:F2}";
```

En el ejemplo anterior, `:` se analiza como el principio de la cadena de formato, no como parte del operador condicional. En todos los casos en los que sucede esto, se puede escribir la expresión entre paréntesis para forzar a que el compilador la interprete de la forma esperada:

[!code-csharp[stringInterpolationConditional](../../../samples/snippets/csharp/new-in-6/newcode.cs#stringInterpolationConditional)]

No hay ninguna limitación en cuanto a las expresiones que se pueden colocar entre las llaves. Se puede ejecutar una consulta LINQ compleja dentro de una cadena interpolada para realizar cálculos y mostrar el resultado:

[!code-csharp[stringInterpolationLinq](../../../samples/snippets/csharp/new-in-6/newcode.cs#stringInterpolationLinq)]

En este ejemplo se puede ver que incluso se puede anidar una expresión de interpolación de cadena dentro de otra expresión de interpolación de cadena. Este ejemplo probablemente es más complejo de lo que sería aconsejable en código de producción,
pero es ilustrativo de la amplitud de la característica. Cualquier expresión de C# puede colocarse entre las llaves de una cadena interpolada.

Para empezar a trabajar con la interpolación de cadenas, consulte el tutorial interactivo [Interpolación de cadenas en C#](../tutorials/intro-to-csharp/interpolated-strings.yml).

### <a name="string-interpolation-and-specific-cultures"></a>Interpolación de cadena y referencias culturales específicas

Todos los ejemplos que se muestran en la sección anterior dan formato a las cadenas utilizando la referencia cultural del equipo donde se ejecuta el código. A menudo puede ser necesario dar formato a la cadena generada con una referencia cultural concreta.
Para hacerlo, aprovechan que el objeto producido por una interpolación de cadena puede convertirse implícitamente a <xref:System.FormattableString?displayProperty=nameWithType>.

La instancia de <xref:System.FormattableString> contiene la cadena de formato compuesto y los resultados de la evaluación de las expresiones antes de convertirlas en cadenas. Use el método <xref:System.FormattableString.ToString(System.IFormatProvider)> para especificar la referencia cultural cuando de formato a una cadena. Por ejemplo, en el ejemplo siguiente se genera una cadena con la referencia cultural de alemán. (Usa el carácter "," para el separador de decimales y el carácter "." como separador de miles).

```csharp
FormattableString str = $"Average grade is {s.Grades.Average()}";
var gradeStr = str.ToString(new System.Globalization.CultureInfo("de-DE"));
```

Para más información, vea el artículo [Interpolación de cadenas](../language-reference/tokens/interpolated.md) y el tutorial [Interpolación de cadenas en C#](../tutorials/string-interpolation.md).

## <a name="exception-filters"></a>Filtros de excepciones

Otra característica nueva de C# 6 son los *filtros de excepciones*. Los filtros de excepciones son cláusulas que determinan cuándo se debe aplicar una cláusula catch determinada.
Si la expresión usada para un filtro de excepciones se evalúa como `true`, la cláusula catch realiza su procesamiento normal en una excepción. Si la expresión se evalúa como `false`, entonces se omite la cláusula `catch`.

Un uso consiste en examinar la información sobre una excepción para determinar si una cláusula `catch` puede procesar la excepción:

[!code-csharp[ExceptionFilter](../../../samples/snippets/csharp/new-in-6/NetworkClient.cs#ExceptionFilter)]

El código generado por los filtros de excepciones proporciona una mejor información sobre una excepción que se produce y no se procesa. Antes de que se agregaran los filtros de excepciones al lenguaje, era necesario crear un código similar al siguiente:

[!code-csharp[ExceptionFilterOld](../../../samples/snippets/csharp/new-in-6/NetworkClient.cs#ExceptionFilterOld)]

El punto donde se produce la excepción cambia entre estos dos ejemplos.
En el código anterior, donde se usa una cláusula `throw`, cualquier análisis de seguimiento de pila o examen de volcado de memoria mostrará que la excepción se produjo desde la instrucción `throw` en la cláusula catch. El objeto de excepción real contendrá la pila de llamadas original, pero el resto de la información sobre las variables en la pila de llamadas entre este punto de inicio y la ubicación del punto de inicio original se perdió. 

Compare esto con cómo se procesa el código mediante un filtro de excepciones: la expresión de filtro de excepciones se evalúa como `false`. Por tanto, la ejecución nunca entra en la cláusula `catch`. Dado que la cláusula `catch` no se ejecuta, no se produce el desenredo de la pila. Esto significa que la ubicación de inicio original se conserva para cualquier actividad de depuración que tenga lugar más adelante.

Siempre que necesite evaluar los campos o las propiedades de una excepción, en lugar de confiar únicamente en el tipo de excepción, use un filtro de excepciones para conservar más información de depuración.

Otro patrón recomendado con los filtros de excepciones es usarlos para rutinas de registro. Este uso también aprovecha la manera en la que se conserva el punto de inicio de excepción cuando un filtro de excepciones se evalúa como `false`.

Un método de registro sería un método cuyo argumento es la excepción que devuelve incondicionalmente `false`:

[!code-csharp[ExceptionFilterLogging](../../../samples/snippets/csharp/new-in-6/ExceptionFilterHelpers.cs#ExceptionFilterLogging)]

Siempre que quiera registrar una excepción, puede agregar una cláusula catch y usar este método como el filtro de excepciones:

[!code-csharp[LogException](../../../samples/snippets/csharp/new-in-6/program.cs#LogException)]

Las excepciones no se detectan nunca, porque el método `LogException` siempre devuelve `false`. Ese filtro de excepciones que siempre es false significa que se puede colocar este controlador de registro antes de otros controladores de excepciones:

[!code-csharp[LogExceptionRecovery](../../../samples/snippets/csharp/new-in-6/program.cs#LogExceptionRecovery)]

El ejemplo anterior resalta un aspecto muy importante de los filtros de excepciones.
Los filtros de excepciones permiten escenarios en los que una cláusula de excepción catch más general puede aparecer antes que otra más específica. También es posible que el mismo tipo de excepción aparezca en varias cláusulas catch:

[!code-csharp[HandleNotChanged](../../../samples/snippets/csharp/new-in-6/NetworkClient.cs#HandleNotChanged)]

Otro patrón recomendado hace que sea más fácil impedir que las cláusulas catch procesen las excepciones cuando se adjunta un depurador. Esta técnica permite ejecutar una aplicación con el depurador y detener la ejecución cuando se produce una excepción.

En el código, agregue un filtro de excepciones para que cualquier código de recuperación se ejecute solo cuando no haya un depurador asociado:

[!code-csharp[LogExceptionDebugger](../../../samples/snippets/csharp/new-in-6/program.cs#LogExceptionDebugger)]

Después de agregar este código, establezca el depurador para que se interrumpa en todas las excepciones no controladas. Ejecute el programa en el depurador, y el depurador siempre se interrumpe cuando `PerformFailingOperation()` produce una excepción `RecoverableException`.
El depurador interrumpe el programa, porque la cláusula catch no se ejecutará debido al filtro de excepciones que devuelve false.

## <a name="the-nameof-expression"></a>La expresión `nameof`

La expresión `nameof` se evalúa como el nombre de un símbolo. Es una excelente manera de hacer que las herramientas funcionen siempre que se necesita el nombre de una variable, una propiedad o un campo de miembro.

Uno de los usos más comunes de `nameof` es para proporcionar el nombre de un símbolo que produjo una excepción:

[!code-csharp[nameof](../../../samples/snippets/csharp/new-in-6/NewCode.cs#UsingStaticString)]

Otro uso es con aplicaciones basadas en XAML que implementan la interfaz `INotifyPropertyChanged`:

[!code-csharp[nameofNotify](../../../samples/snippets/csharp/new-in-6/viewmodel.cs#nameofNotify)]

La ventaja de usar el operador `nameof` en lugar de una cadena de constante es que las herramientas pueden entender el símbolo. Si usa herramientas de refactorización para cambiar el nombre del símbolo, se cambiará en la expresión `nameof`. Las cadenas constantes no tienen esta ventaja. Pruébelo en su editor favorito: cambie el nombre de una variable y todas las expresiones `nameof` también se actualizarán.

La expresión `nameof` produce el nombre no completo de su argumento (`LastName` en los ejemplos anteriores) incluso si se usa el nombre completo para el argumento:

[!code-csharp[QualifiedNameofNotify](../../../samples/snippets/csharp/new-in-6/viewmodel.cs#QualifiedNameofNotify)]

Esta expresión `nameof` produce `FirstName`, no `UXComponents.ViewModel.FirstName`.

## <a name="await-in-catch-and-finally-blocks"></a>Await en bloques Catch y Finally

C# 5 tenía varias limitaciones en cuanto a dónde se podían colocar las expresiones `await`.
Una de ellas se ha quitado en C# 6. Ahora se puede usar `await` en expresiones `catch` o `finally`. 

La adición de expresiones await en bloques catch y finally puede parecer que complica cómo se procesan. Vamos a agregar un ejemplo para explicar cómo aparece esto. En cualquier método asincrónico, se puede usar una expresión await en una cláusula finally.

Con C# 6, también se puede usar await en expresiones catch. Se suele usar principalmente con escenarios de registro:

[!code-csharp[AwaitFinally](../../../samples/snippets/csharp/new-in-6/NetworkClient.cs#AwaitFinally)]

Los detalles de implementación para agregar compatibilidad con `await` dentro de cláusulas `catch` y `finally` garantizan que el comportamiento es coherente con el comportamiento del código sincrónico. Cuando el código que se ejecuta en una cláusula `catch` o `finally` produce una excepción, la ejecución busca una cláusula `catch` adecuada en el siguiente bloque adyacente. Si había una excepción actual, esa excepción se pierde. Lo mismo sucede con las expresiones de await en cláusulas `catch` y `finally`: se busca una cláusula `catch` adecuada y se pierde la excepción actual, si existe.  

> [!NOTE]
> Este comportamiento es el motivo por el que se recomienda escribir cláusulas `catch` y `finally` con cuidado, para evitar la introducción de nuevas excepciones.

## <a name="index-initializers"></a>Inicializadores de índice

Los *inicializadores de índice* son una de las dos características que hacen que los inicializadores de colección sean más coherentes con el uso del índice. En versiones anteriores de C#, solo se podían usar los *inicializadores de colección* con colecciones de estilos de secuencia, incluido <xref:System.Collections.Generic.Dictionary%602> con llaves alrededor de los pares de clave-valor:

[!code-csharp[ListInitializer](../../../samples/snippets/csharp/new-in-6/initializers.cs#ListInitializer)]

Ahora se pueden usar con colecciones <xref:System.Collections.Generic.Dictionary%602> y tipos similares. La nueva sintaxis admite la asignación con un índice en la colección:

[!code-csharp[DictionaryInitializer](../../../samples/snippets/csharp/new-in-6/initializers.cs#DictionaryInitializer)]

Esta característica significa que los contenedores asociativos se pueden inicializar mediante una sintaxis similar a la que se lleva usando en varias versiones para los contenedores de secuencia.

## <a name="extension-add-methods-in-collection-initializers"></a>Métodos `Add` de extensión para inicializadores de colección

Otra característica que facilita la inicialización de colecciones es la capacidad de usar un *método de extensión* para el método `Add`. Esta característica se agregó por motivos de paridad con Visual Basic. 

La característica es más útil cuando se tiene una clase de colección personalizada que tiene un método con un nombre diferente para agregar nuevos elementos de forma semántica.

Por ejemplo, considere una colección de alumnos similar a la siguiente:

[!code-csharp[Enrollment](../../../samples/snippets/csharp/new-in-6/enrollment.cs#Enrollment)]

El método `Enroll` agrega un alumno. Pero no sigue el patrón de `Add`.
En versiones anteriores de C#, no se podían usar inicializadores de colección con un objeto `Enrollment`:

[!code-csharp[InitializeEnrollment](../../../samples/snippets/csharp/new-in-6/classList.cs#InitializeEnrollment)]

Ahora se puede, pero solo si se crea un método de extensión que asigna `Add` a `Enroll`:

[!code-csharp[ExtensionAdd](../../../samples/snippets/csharp/new-in-6/classList.cs#ExtensionAdd)]

Lo que hace esta característica es asignar cualquier método que agrega elementos a una colección a un método denominado `Add` mediante la creación de un método de extensión.

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
