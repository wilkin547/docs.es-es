---
title: 'Novedades de C# 9.0: Guía de C#'
description: Obtenga información general sobre las nuevas características disponibles en C# 9.0.
ms.date: 09/04/2020
ms.openlocfilehash: 6a0227b408b894fe450c2a6bb6017d9059d229c0
ms.sourcegitcommit: c04535ad05e374fb269fcfc6509217755fbc0d54
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2020
ms.locfileid: "91247623"
---
# <a name="whats-new-in-c-90"></a>Novedades de C# 9.0

C# 9.0 agrega las siguientes características y mejoras al lenguaje C#:

- [Registros](#record-types)
- [Establecedores de solo inicialización](#init-only-setters)
- [Instrucciones de nivel superior](#top-level-statements)
- [Mejoras de coincidencia de patrones](#pattern-matching-enhancements)
- Enteros con tamaño nativos
- Punteros de función
- Supresión de la emisión de la marca localsinit
- Expresiones nuevas con tipo de destino
- Funciones anónimas estáticas
- Expresiones condicionales con tipo de destino
- Tipos de valor devueltos de covariante
- Compatibilidad con extensiones `GetEnumerator` para bucles `foreach`
- Parámetros de descarte lambda
- Atributos en funciones locales
- Inicializadores de módulo
- Nuevas características para métodos parciales

C# 9.0 es compatible con **.NET 5**. Para obtener más información, vea [Control de versiones del lenguaje C#](../language-reference/configure-language-version.md).

## <a name="record-types"></a>Tipos de registro

En C# 9.0 se presentan los ***tipos de registro***, un tipo de referencia que ofrece métodos sintetizados para proporcionar semántica de valores para la igualdad. Los registros son inmutables de forma predeterminada.

Los tipos de registro facilitan la creación de tipos de referencia inmutables en .NET. Históricamente, los tipos de .NET se han clasificado principalmente como tipos de referencia (incluidas las clases y los tipos anónimos) y tipos de valor (incluidas las estructuras y tuplas). Aunque se recomiendan los tipos de valor inmutables, los tipos de valor mutable no suelen generar errores. Las variables de tipo de valor contienen los valores para que los cambios se realicen en una copia de los datos originales cuando los tipos de valor se pasan a los métodos.

Los tipos de referencia inmutables también ofrecen muchas ventajas. Estas ventajas son más evidentes en programas simultáneos con datos compartidos. Desafortunadamente, C# le ha obligado a escribir código adicional para crear tipos de referencia inmutables. Los registros proporcionan una declaración de tipos para un tipo de referencia inmutable que usa la semántica de valores para la igualdad. Los métodos sintetizados para los códigos de igualdad y hash consideran que dos registros son iguales si sus propiedades son iguales. Considere esta definición:

:::code language="csharp" source="snippets/whats-new-csharp9/RecordsExamples.cs" ID="RecordDefinition":::

La definición del registro crea un tipo `Person` que contiene dos propiedades de solo lectura: `FirstName` y `LastName`. El tipo `Person` es un tipo de referencia. Si ha examinado el lenguaje intermedio, es una clase. Es inmutable porque ninguna de las propiedades se puede modificar una vez que se ha creado. Al definir un tipo de registro, el compilador sintetiza otros métodos de forma automática:

- Métodos para comparaciones de igualdad basadas en valores
- Invalidación de <xref:System.Object.GetHashCode>
- Copiar y clonar miembros
- `PrintMembers` y <xref:System.Object.ToString>

Los registros admiten la herencia. Puede declarar un nuevo registro derivado de `Person` como se indica a continuación:

:::code language="csharp" source="snippets/whats-new-csharp9/RecordsExamples.cs" ID="InheritedRecord":::

También puede sellar los registros para evitar la derivación adicional:

:::code language="csharp" source="snippets/whats-new-csharp9/RecordsExamples.cs" ID="SealedRecord":::

El compilador sintetiza versiones diferentes de los métodos anteriores. Las signaturas de método dependen de si el tipo de registro está sellado y si la clase base directa es un objeto. Los registros deben tener las funciones siguientes:

- La igualdad se basa en valores e incluye una comprobación de coincidencia de los tipos. Por ejemplo, `Student` no puede ser igual a `Person`, aunque los dos registros compartan el mismo nombre.
- Los registros tienen una representación de cadena coherente que se genera de forma automática.
- Los registros admiten la construcción de copias. La construcción de copias correctas debe incluir las jerarquías de herencia y las propiedades agregadas por los desarrolladores.
- Los registros se pueden copiar con modificaciones. Estas operaciones de copia y modificación admiten la mutación no destructiva.

Además de las sobrecargas de `Equals` conocidas, `operator ==` y `operator !=`, el compilador sintetiza una nueva propiedad `EqualityContract`. La propiedad devuelve un objeto `Type` que coincide con el tipo del registro. Si el tipo base es `object`, la propiedad es `virtual`. Si el tipo base es otro tipo de registro, la propiedad es un `override`. Si el tipo de registro es `sealed`, la propiedad es `sealed`. El método `GetHashCode` sintetizado usa el valor `GetHashCode` de todas las propiedades y campos declarados en el tipo base y el tipo de registro. Estos métodos sintetizados imponen la igualdad basada en valores en una jerarquía de herencia. Esto significa que un registro `Student` nunca se considerará igual que un registro `Person` con el mismo nombre. Los tipos de los dos registros deben coincidir y todas las propiedades compartidas entre los tipos de registro deben ser iguales.

Los registros también tienen un constructor sintetizado y un método "clone" para crear copias. El constructor sintetizado tiene un argumento del tipo de registro. Genera un nuevo registro con los mismos valores para todas las propiedades del registro. Este constructor es privado si el registro está sellado; de lo contrario está protegido. El método "clone" sintetizado admite la construcción de copias para las jerarquías de registros. El término "clone" está entre comillas porque el nombre real es el compilador generado. No se puede crear un método denominado `Clone` en un tipo de registro. El método "clone" sintetizado devuelve el tipo de registro que se copia mediante el envío virtual. El compilador agrega distintos modificadores para el método "clone", en función de los modificadores de acceso de `record`:

- Si el tipo de registro es `abstract`, el método "clone" también es `abstract`. Si el tipo base no es `object`, el método también es `override`.
- Para los tipos de registro que no son `abstract` cuando el tipo base es `object`:
  - Si el registro es `sealed`, no se agregan modificadores adicionales al método "clone" (lo que significa que no es `virtual`).
  - Si el registro no es `sealed`, el método "clone" es `virtual`.
- Para los tipos de registro que no son `abstract` cuando el tipo base no es `object`:
  - Si el registro es `sealed`, el método "clone" también es `sealed`.
  - Si el registro no es `sealed`, el método "clone" es `override`.

El resultado de todas estas reglas es que la igualdad se implementa de forma coherente en cualquier jerarquía de tipos de registro. Dos registros son iguales entre ellos si sus propiedades son iguales y sus tipos son los mismos, como se muestra en el ejemplo siguiente:

:::code language="csharp" source="snippets/whats-new-csharp9/RecordsExamples.cs" ID="RecordsEquality":::

El compilador sintetiza dos métodos que admiten la salida impresa: una invalidación de <xref:System.Object.ToString> y `PrintMembers`. `PrintMembers` toma <xref:System.Text.StringBuilder?displayProperty=nameWithType> como argumento. Anexa una lista separada por comas de nombres de propiedad y valores para todas las propiedades del tipo de registro. `PrintMembers` llama a la implementación base de cualquier registro derivado de otros registros. La invalidación de <xref:System.Object.ToString> devuelve la cadena generada por `PrintMembers`, incluida entre `{` y `}`. Por ejemplo, el método <xref:System.Object.ToString> de `Student` devuelve un objeto `string` como en el código siguiente:

```csharp
"Student { LastName = Wagner, FirstName = Bill, Level = 11 }"
```

En los ejemplos mostrados hasta ahora se usa la sintaxis tradicional para declarar propiedades. Hay una forma más concisa denominada ***registros posicionales***.  Estos son los tres tipos de registro definidos anteriormente como registros posicionales:

:::code language="csharp" source="snippets/whats-new-csharp9/PositionalRecords.cs" ID="PositionalRecords":::

Estas declaraciones crean la misma funcionalidad que la versión anterior (con un par de características adicionales que se describen en la sección siguiente). Estas declaraciones finalizan con un punto y coma en lugar de corchetes, porque estos registros no agregan métodos adicionales. Puede agregar un cuerpo e incluir también otros métodos adicionales:

:::code language="csharp" source="snippets/whats-new-csharp9/PositionalRecords.cs" ID="RecordsWithMethods":::

El compilador genera un método `Deconstruct` para los registros posicionales. El método `Deconstruct` tiene parámetros que coinciden con los nombres de todas las propiedades públicas del tipo de registro. El método `Deconstruct` se puede usar para deconstruir el registro en sus propiedades de componente:

:::code language="csharp" source="snippets/whats-new-csharp9/PositionalRecords.cs" ID="DeconstructRecord":::

Por último, los registros admiten ***expresiones with***. Una ***expresión with*** indica al compilador que cree una copia de un registro, pero *con* (with) propiedades especificadas modificadas:

:::code language="csharp" source="snippets/whats-new-csharp9/PositionalRecords.cs" ID="Wither":::

La línea anterior crea un registro `Person` en el que la propiedad `LastName` es una copia de `person` y el valor `FirstName` es "Paul". Puede establecer cualquier número de propiedades en una expresión with.  El usuario puede escribir cualquiera de los miembros sintetizados excepto el método "clone". Si un tipo de registro tiene un método que coincide con la signatura de cualquier método sintetizado, el compilador no sintetiza ese método. El ejemplo de registro `Dog` anterior contiene un método <xref:System.String.ToString> codificado a mano como ejemplo.

## <a name="init-only-setters"></a>Establecedores de solo inicialización

Los ***establecedores de solo inicialización*** proporcionan una sintaxis coherente para inicializar los miembros de un objeto. Los inicializadores de propiedades indican con claridad qué valor establece cada propiedad. El inconveniente es que esas propiedades se deben establecer. A partir de C# 9.0, puede crear descriptores de acceso `init` en lugar de descriptores de acceso `set` para propiedades e indizadores. Los autores de la llamada pueden usar la sintaxis de inicializador de propiedad para establecer estos valores en expresiones de creación, pero esas propiedades son de solo lectura una vez que se ha completado la construcción. Los establecedores de solo inicialización proporcionan una ventana para cambiar el estado, que se cierra cuando finaliza la fase de construcción. La fase de construcción finaliza de forma eficaz después de que se complete toda la inicialización, incluidos los inicializadores de propiedades y las expresiones with.

En el ejemplo anterior de los registros posicionales se muestra el uso de un establecedor de solo inicialización para establecer una propiedad mediante una expresión with. Puede declarar los establecedores de solo inicialización en cualquier tipo que escriba. Por ejemplo, en la estructura siguiente se define una estructura de observación meteorológica:

:::code language="csharp" source="snippets/whats-new-csharp9/WeatherObservation.cs" ID="DeclareWeatherObservation":::

Los autores de la llamada pueden usar la sintaxis de inicializador de propiedades para establecer los valores, a la vez que conservan la inmutabilidad:

:::code language="csharp" source="snippets/whats-new-csharp9/WeatherObservation.cs" ID="UseWeatherObservation":::

Pero el cambio de una observación después de la inicialización es un error mediante la asignación a una propiedad de solo inicialización fuera de la inicialización:

```csharp
// Error! CS8852.
now.TemperatureInCelsius = 18;
```

Los establecedores de solo inicialización pueden ser útiles para establecer las propiedades de clase base de las clases derivadas. También pueden establecer propiedades derivadas mediante asistentes en una clase base. Los registros posicionales declaran propiedades mediante establecedores de solo inicialización. Esos establecedores se usan en expresiones with. Puede declarar establecedores de solo inicialización para cualquier objeto `class` o `struct` que defina.

## <a name="top-level-statements"></a>Instrucciones de nivel superior

Las ***instrucciones de nivel superior*** eliminación operaciones innecesarias de muchas aplicaciones. Considere el famoso programa "Hola mundo":

```csharp
using System;

namespace HelloWorld
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
        }
    }
}
```

Solo hay una línea de código que haga algo. Con las instrucciones de nivel superior, puede reemplazar todo lo que sea reutilizable por la instrucción `using` y la línea única que realiza el trabajo:

:::code language="csharp" source="snippets/whats-new-csharp9/Program.cs" ID="TopLevelStatements":::

Si quisiera un programa de una línea, podría quitar la directiva `using` y usar el nombre de tipo completo:

```csharp
System.Console.WriteLine("Hello World!");
```

Solo un archivo de la aplicación puede usar instrucciones de nivel superior. Si el compilador encuentra instrucciones de nivel superior en varios archivos de código fuente, se trata de un error. También es un error si combina instrucciones de nivel superior con un método de punto de entrada de programa declarado, normalmente `Main`. En cierto sentido, puede pensar que un archivo contiene las instrucciones que normalmente se encontrarían en el método `Main` de una clase `Program`.  

Uno de los usos más comunes de esta característica es la creación de materiales educativos. Los desarrolladores principiantes de C# pueden escribir el programa "Hola mundo" en una o dos líneas de código. No se necesitan pasos adicionales. Pero los desarrolladores veteranos también encontrarán muchas aplicaciones a esta característica. Las instrucciones de nivel superior permiten una experiencia de experimentación de tipo script similar a la que proporcionan los cuadernos de Jupyter Notebook. Las instrucciones de nivel superior son excelentes para programas y utilidades de consola pequeños. Azure Functions es un caso de uso ideal para las instrucciones de nivel superior.

Y sobre todo, las instrucciones de nivel superior no limitan el ámbito ni la complejidad de la aplicación. Estas instrucciones pueden acceder a cualquier clase de .NET o usarla. Tampoco limitan el uso de argumentos de línea de comandos ni de valores devueltos. Las instrucciones de nivel superior pueden acceder a una matriz de cadenas denominada args. Si las instrucciones de nivel superior devuelven un valor entero, ese valor se convierte en el código devuelto entero de un método `Main` sintetizado. Las instrucciones de nivel superior pueden contener expresiones asincrónicas. En ese caso, el punto de entrada sintetizado devuelve un objeto `Task`, o `Task<int>`.

## <a name="pattern-matching-enhancements"></a>Mejoras de coincidencia de patrones

C# 9 incluye nuevas mejoras de coincidencia de patrones:

- Los ***patrones de tipo*** comparan si una variable es un tipo
- Los ***patrones entre paréntesis*** aplican o resaltan la prioridad de las combinaciones de patrones
- En los ***patrones `and` conjuntivos*** es necesario que los dos patrones coincidan
- En los ***patrones `or` disyuntivo*** es necesario que uno de los dos patrones coincida
- En los ***patrones `not` negados*** es necesario que un patrón no coincida
- Los ***patrones relacionales*** requieren que la entrada sea menor que, mayor que, menor o igual que, o mayor o igual que una constante determinada.

Estos patrones enriquecen la sintaxis de los patrones. Tenga en cuenta estos ejemplos:

:::code language="csharp" source="snippets/whats-new-csharp9/PatternUtilities.cs" ID="IsLetterPattern":::

Como alternativa, con paréntesis opcionales para que quede claro que `and` tiene mayor precedencia que `or`:

:::code language="csharp" source="snippets/whats-new-csharp9/PatternUtilities.cs" ID="IsLetterOrSeparatorPattern":::

Uno de los usos más comunes es una nueva sintaxis para una comprobación NULL:

```csharp
if (e is not null)
{
    // ...
}
```

Cualquiera de estos patrones se puede usar en cualquier contexto en el que se permitan patrones: expresiones de patrón `is`, expresiones `switch`, modelos anidados y el patrón de la etiqueta `case` de una instrucción `switch`.

## <a name="performance-and-interop"></a>Rendimiento e interoperabilidad

Tres nuevas características mejoran la compatibilidad con la interoperabilidad nativa y las bibliotecas de bajo nivel que requieren alto rendimiento: enteros de tamaño nativo, punteros de función y la omisión de la marca `localsinit`.

Los enteros de tamaño nativo, `nint` y `nuint`, son tipos enteros. Se expresan mediante los tipos subyacentes <xref:System.IntPtr?displayProperty=nameWithType> y <xref:System.UIntPtr?displayProperty=nameWithType>. El compilador muestra las conversiones y operaciones adicionales para estos tipos como enteros nativos. Los enteros de tamaño nativo no tienen constantes para `MaxValue` o `MinValue`, excepto `nuint.MinValue`, que tiene un valor `MinValue` de `0`. Otros valores no se pueden expresar como constantes porque depende del tamaño nativo de un entero en el equipo de destino. Puede usar valores constantes para `nint` en el intervalo [`int.MinValue` .. `int.MaxValue`]. Puede usar valores constantes para `nuint` en el intervalo [`uint.MinValue` .. `uint.MaxValue`]. El compilador realiza un plegamiento constante para todos los operadores unarios y binarios que usan los tipos <xref:System.Int32?displayProperty=nameWithType> y <xref:System.UInt32?displayProperty=nameWithType>. Si el resultado no cabe en 32 bits, la operación se ejecuta en tiempo de ejecución y no se considera una constante. Los enteros con tamaño nativo pueden aumentar el rendimiento en escenarios en los que se usa la aritmética de enteros y es necesario tener el rendimiento más rápido posible.

Los punteros de función proporcionan una sintaxis sencilla para acceder a los códigos de operación de lenguaje intermedio `ldftn` y `calli`. Puede declarar punteros de función con la nueva sintaxis de `delegate*`. Un tipo `delegate*` es un tipo de puntero. Al invocar el tipo `delegate*` se usa `calli`, a diferencia de un delegado que usa `callvirt` en el método `Invoke()`. Sintácticamente, las invocaciones son idénticas. La invocación del puntero de función usa la convención de llamada `managed`. Agregue la palabra clave `unmanaged` después de la sintaxis de `delegate*` para declarar que quiere la convención de llamada `unmanaged`. Se pueden especificar otras convenciones de llamada mediante atributos en la declaración de `delegate*`.

Por último, puede agregar <xref:System.Runtime.CompilerServices.SkipLocalsInitAttribute?displayProperty=nameWithType> para indicar al compilador que no emita la marca `localsinit`. Esta marca indica al CLR que inicialice en cero todas las variables locales. La marca `localsinit` ha sido el comportamiento predeterminado en C# desde la versión 1.0. Pero la inicialización en cero adicional puede afectar al rendimiento en algunos escenarios. En concreto, cuando se usa `stackalloc`. En esos casos, puede agregar <xref:System.Runtime.CompilerServices.SkipLocalsInitAttribute>. Puede agregarlo a un único método o propiedad, a un objeto `class`, `struct`, `interface`, o incluso a un módulo. Este atributo no afecta a los métodos `abstract`; afecta al código generado para la implementación.

Estas características pueden aumentar significativamente el rendimiento en algunos escenarios. Solo se deben usar después de realizar pruebas comparativas minuciosamente antes y después de la adopción. El código que implica enteros con tamaño nativo se debe probar en varias plataformas de destino con distintos tamaños de enteros. Las demás características requieren código no seguro.

## <a name="fit-and-finish-features"></a>Características de ajuste y finalización

Muchas de las características restantes ayudan a escribir código de forma más eficaz. En C# 9.0, puede omitir el tipo de una nueva expresión cuando ya se conoce el tipo del objeto creado. El uso más común es en las declaraciones de campo:

:::code language="csharp" source="snippets/whats-new-csharp9/FitAndFinish.cs" ID="WeatherStationField":::

El tipo de destino new también se puede usar cuando es necesario crear un objeto para pasarlo como parámetro a un método. Considere un método `ForecastFor()` con la signatura siguiente:

:::code language="csharp" source="snippets/whats-new-csharp9/FitAndFinish.cs" ID="ForecastSignature":::

Podría llamarlo de esta forma:

:::code language="csharp" source="snippets/whats-new-csharp9/FitAndFinish.cs" ID="TargetTypeNewArgument":::

Otra aplicación muy útil de esta característica es para combinarla con propiedades de solo inicialización para inicializar un objeto nuevo:

:::code language="csharp" source="snippets/whats-new-csharp9/FitAndFinish.cs" ID="InitWeatherStation":::

Puede devolver una instancia creada por el constructor predeterminado mediante una expresión `return new();`.

Una característica similar mejora la resolución de tipos de destino de las [expresiones condicionales](../language-reference/operators/conditional-operator.md). Con este cambio, las dos expresiones no necesitan tener una conversión implícita de una a otra, pero pueden tener conversiones implícitas a un tipo de destino. Lo más probable es que no note este cambio. Lo que observará es que ahora funcionan algunas expresiones condicionales para las que anteriormente se necesitan conversiones o que no se compilaban.

A partir de C# 9.0, puede agregar el modificador `static` a [expresiones lambda](../language-reference/operators/lambda-expressions.md) o [métodos anónimos](../language-reference/operators/delegate-operator.md). Las expresiones lambda estáticas son análogas a las funciones `static` locales: un método anónimo o una expresión lambda estáticos no puede capturar variables locales ni el estado de la instancia. El modificador `static` impide la captura accidental de otras variables.

Los tipos de valor devueltos de covariante proporcionan flexibilidad a los tipos de valor devueltos de las funciones reemplazadas. Una función virtual reemplazada puede devolver un tipo derivado del tipo de valor devuelto declarado en el método de clase base. Esto puede ser útil para los registros y para otros tipos que admiten métodos de generador o clonación virtuales.

Además, el bucle [`foreach` ](../language-reference/keywords/foreach-in.md) reconocerá y usará un método de extensión `GetEnumerator` que, de otro modo, satisface el patrón `foreach`. Este cambio significa que `foreach` es coherente con otras construcciones basadas en patrones, como el patrón asincrónico y la desconstrucción basada en patrones. En la práctica, esto quiere decir que puede agregar compatibilidad con `foreach` a cualquier tipo. Debe limitar su uso a cuando la enumeración de un objeto tiene sentido en el diseño.

Después, puede usar descartes como parámetros para las expresiones lambda. De esta forma no tiene que asignar un nombre al argumento y el compilador puede evitar usarlo. Use `_` para cualquier argumento. Para más información, consulte sección sobre [parámetros de entrada de una expresión lambda](../language-reference/operators/lambda-expressions.md#input-parameters-of-a-lambda-expression) en el artículo sobre [expresiones lambda](../language-reference/operators/lambda-expressions.md).

Por último, ahora puede aplicar atributos a las funciones locales. Por ejemplo, puede aplicar anotaciones de atributo que admiten un valor NULL a las funciones locales.

## <a name="support-for-code-generators"></a>Compatibilidad con generadores de código

Dos últimas características admiten generadores de código de C#. Los generadores de código de C# son un componente que se puede escribir y que es similar a una corrección de código o un analizador Roslyn. La diferencia es que los generadores de código analizan el código y escriben nuevos archivos de código fuente como parte del proceso de compilación. Un generador de código típico busca atributos y otras convenciones en el código.

Un generador de código lee atributos u otros elementos de código mediante las API de análisis de Roslyn. A partir de esa información, agrega código nuevo a la compilación. Los generadores de código fuente solo pueden agregar código; no se les permite modificar ningún código existente en la compilación.

Las dos características agregadas para los generadores de código son las extensiones de la ***sintaxis de métodos parciales*** y los ***inicializadores de módulos***. En primer lugar, los cambios en los métodos parciales. Antes de C# 9.0, los métodos parciales eran `private`, pero no podían especificar un modificador de acceso, tener un valor devuelto `void` ni parámetros `out`. Estas restricciones implican que si no se proporciona ninguna implementación de método, el compilador quita todas las llamadas al método parcial. En C# 9.0 se quitan estas restricciones, pero es necesario que las declaraciones de métodos parciales tengan una implementación. Los generadores de código pueden proporcionar esa implementación. Para evitar la introducción de un cambio importante, el compilador tiene en cuenta cualquier método parcial sin un modificador de acceso para seguir las reglas anteriores. Si el método parcial incluye el modificador de acceso `private`, las nuevas reglas rigen ese método parcial.

La segunda característica nueva para los generadores de código son los ***inicializadores de módulos***. Los inicializadores de módulos son métodos que tienen asociado el atributo <xref:System.Runtime.CompilerServices.ModuleInitializerAttribute>. El tiempo de ejecución llamará a estos métodos cuando se cargue el ensamblado. Un método de inicializador de módulo:

- Debe ser estático
- No debe tener parámetros
- Debe devolver void
- No debe ser un método genérico
- No debe estar incluido en una clase genérica
- Debe ser accesible desde el módulo contenedor

Ese último punto significa en realidad que el método y su clase contenedora deben ser internos o públicos. El método no puede ser una función local.
