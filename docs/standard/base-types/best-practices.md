---
title: Procedimientos recomendados con expresiones regulares en .NET
description: Obtenga información sobre cómo crear expresiones regulares eficaces y efectivas en .NET.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- .NET Framework regular expressions, best practices
- regular expressions, best practices
ms.assetid: 618e5afb-3a97-440d-831a-70e4c526a51c
ms.openlocfilehash: 158964d1e04091faaa9b3acf82bf4ce2b5aba797
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711498"
---
# <a name="best-practices-for-regular-expressions-in-net"></a>Procedimientos recomendados con expresiones regulares en .NET

El motor de expresiones regulares de .NET es una herramienta eficaz y completa que procesa texto basándose en coincidencias de patrones en lugar de comparar y buscar coincidencias con texto literal. En la mayoría de los casos, realiza la coincidencia de modelos de manera rápida y eficaz. Sin embargo, en algunos casos, puede parecer que el motor de expresiones regulares es muy lento. En casos extremos, incluso puede parecer que deja de responder mientras procesa una entrada relativamente pequeña a lo largo de las horas o incluso los días.

En este tema se describen algunos de los procedimientos recomendados que los desarrolladores pueden adoptar para garantizar que sus expresiones regulares alcancen un rendimiento óptimo.

## <a name="consider-the-input-source"></a>Considerar el origen de entrada

En general, las expresiones regulares pueden aceptar dos tipos de datos de entrada: restringidos o sin restricciones. La entrada restringida es texto que se origina en una fuente conocida o confiable y sigue un formato predefinido. La entrada sin restricciones es texto que se origina en un origen no confiable, como un usuario web, y puede no seguir un formato predefinido o esperado.

Los patrones de expresiones regulares se suelen escribir para buscar coincidencias con entradas válidas. Es decir, los desarrolladores examinan el texto que desean buscar y escriben un patrón de expresión regular que coincida con él. A continuación, los desarrolladores determinan si este patrón necesita alguna corrección o algún procesamiento adicional probándolo con varios elementos de entrada válidos. Cuando el modelo coincide con todas las entradas válidas previstas, se declara que está listo para producción y se puede incluir en una aplicación comercial. Esto hace que un patrón de expresión regular sea adecuado para entradas restringidas coincidentes. Sin embargo, no es adecuado para datos de entrada sin restricciones coincidentes.

Para buscar coincidencias con datos de entrada sin restricciones, una expresión regular debe poder administrar eficazmente tres clases de texto:

- Texto que coincide con el patrón de expresión regular.

- Texto que no coincide con el patrón de expresión regular.

- Texto que casi coincide con el patrón de expresión regular.

El último tipo de texto es especialmente problemático para una expresión regular que se ha escrito para tratar datos de entrada restringidos. Si esa expresión regular también usa mucho [retroceso](../../../docs/standard/base-types/backtracking-in-regular-expressions.md), el motor de expresiones regulares puede dedicar una cantidad de tiempo excesiva (en algunos casos, muchas horas o días) procesando texto aparentemente inofensivo.

> [!WARNING]
> En el ejemplo siguiente se utiliza una expresión regular que es propensa a un retroceso excesivo y que es probable que rechace direcciones de correo electrónico válidas. No debería utilizarse en una rutina de validación de correo electrónico. Si desea que una expresión regular valide las direcciones de correo electrónico, vea [Procedimiento: Comprobación de que las cadenas están en un formato de correo electrónico válido](../../../docs/standard/base-types/how-to-verify-that-strings-are-in-valid-email-format.md).

Por ejemplo, considere una expresión regular de uso muy frecuente pero sumamente problemática para validar el alias de una dirección de correo electrónico. Se escribe la expresión regular `^[0-9A-Z]([-.\w]*[0-9A-Z])*$` para procesar qué se considera una dirección de correo electrónico válida, que consta de un carácter alfanumérico seguido de cero o más caracteres que pueden ser alfanuméricos, puntos o guiones. La expresión regular debe finalizar con un carácter alfanumérico. Sin embargo, como se muestra en el ejemplo siguiente, aunque esta expresión regular trata la entrada válida fácilmente, su rendimiento es muy ineficaz cuando está procesando datos de entrada casi válidos.

[!code-csharp[Conceptual.RegularExpressions.BestPractices#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.bestpractices/cs/design2.cs#1)]
[!code-vb[Conceptual.RegularExpressions.BestPractices#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.bestpractices/vb/design2.vb#1)]

Como muestra el resultado del ejemplo, el motor de expresiones regulares procesa el alias válido de correo electrónico casi en el mismo intervalo de tiempo independientemente de su longitud. Por otra parte, cuando la dirección de correo electrónico casi válida tiene más de cinco caracteres, el tiempo de procesamiento se duplica aproximadamente por cada carácter de la cadena. Esto significa que una cadena casi válida de 28 caracteres tardaría más de una hora en procesarse y una cadena casi válida de 33 caracteres tardaría casi un día en procesarse.

Como esta expresión regular se desarrolló teniendo en cuenta solamente el formato de entrada que había que hacer coincidir, no tiene en cuenta los datos de entrada que no coinciden con el patrón. A su vez, esto puede permitir que unos datos de entrada sin restricciones que casi coinciden con el patrón de expresión regular reduzcan considerablemente el rendimiento.

Para resolver este problema, puede hacer lo siguiente:

- A la hora de desarrollar un modelo, debe considerar cómo puede afectar el retroceso al rendimiento del motor de expresiones regulares, especialmente si la expresión regular está diseñada para procesar datos de entrada sin restricciones. Para obtener más información, consulte la sección [Controlar el retroceso](#take-charge-of-backtracking).

- Probar exhaustivamente la expresión regular usando datos de entrada no válidos y casi válidos, así como datos de entrada válidos. Para generar de forma aleatoria la entrada para una expresión regular determinada, puede usar [Rex](https://www.microsoft.com/research/project/rex-regular-expression-exploration/), que es una herramienta de exploración de expresiones regulares de Microsoft Research.

## <a name="handle-object-instantiation-appropriately"></a>Controlar la creación de instancias de objeto correctamente

El núcleo del modelo de objetos de expresiones regulares de .NET es la clase <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType>, que representa el motor de expresiones regulares. A menudo, el mayor factor único que afecta al rendimiento de las expresiones regulares es la manera en que se emplea el motor de <xref:System.Text.RegularExpressions.Regex>. La definición de una expresión regular implica acoplar estrechamente el motor de expresiones regulares con un patrón de expresión regular. Ese proceso de acoplamiento, tanto si consiste en crear una instancia de un objeto <xref:System.Text.RegularExpressions.Regex> pasando a su constructor una expresión regular como en llamar a un método estático pasándole el patrón de expresión regular junto con la cadena que se va a analizar, es necesariamente costoso.

> [!NOTE]
> Para obtener una explicación más detallada de las implicaciones sobre el rendimiento de usar expresiones regulares interpretadas y compiladas, vea [Optimizing Regular Expression Performance, Part II: (Optimización del rendimiento de expresiones regulares, Parte II: Control del retroceso](https://blogs.msdn.microsoft.com/bclteam/2010/08/03/optimizing-regular-expression-performance-part-ii-taking-charge-of-backtracking-ron-petrusha/)) en el blog del equipo de BCL.

Puede acoplar el motor de expresiones regulares con un determinado patrón de expresión regular y, a continuación, usar el motor para buscar coincidencias con texto de varias maneras:

- Puede llamar a un método estático de coincidencia de patrones como <xref:System.Text.RegularExpressions.Regex.Match%28System.String%2CSystem.String%29?displayProperty=nameWithType>. Para ello no es necesario crear instancias de un objeto de expresión regular.

- Puede crear instancias de un objeto <xref:System.Text.RegularExpressions.Regex> y llamar a una instancia de un método de coincidencia de modelos de una expresión regular interpretada. Este es el método predeterminado para enlazar el motor de expresiones regulares a un patrón de expresión regular. Se produce cuando se crea una instancia de un objeto <xref:System.Text.RegularExpressions.Regex> sin un argumento `options` que incluya la marca <xref:System.Text.RegularExpressions.RegexOptions.Compiled>.

- Puede crear instancias de un objeto <xref:System.Text.RegularExpressions.Regex> y llamar a una instancia de un método de coincidencia de modelos de una expresión regular compilada. Los objetos de expresiones regulares representan modelos compilados cuando se crea una instancia de un objeto <xref:System.Text.RegularExpressions.Regex> con un argumento `options` que incluye la marca <xref:System.Text.RegularExpressions.RegexOptions.Compiled>.

- Puede crear un objeto <xref:System.Text.RegularExpressions.Regex> especial que esté acoplado estrechamente con un determinado patrón de expresión regular, compilarlo y guardarlo en un ensamblado independiente. Puede hacerlo llamando al método <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A?displayProperty=nameWithType>.

La forma de llamar a los métodos de coincidencia de expresiones regulares puede tener un impacto significativo en la aplicación. En las próximas secciones se explica cómo usar llamadas a métodos estáticos, expresiones regulares interpretadas y expresiones regulares compiladas para mejorar el rendimiento de la aplicación.

> [!IMPORTANT]
> El formato de la llamada al método (estático, interpretado o compilado) afecta al rendimiento si la misma expresión regular se usa repetidamente en llamadas a métodos o si una aplicación usa muchos objetos de expresiones regulares.

### <a name="static-regular-expressions"></a>Expresiones regulares estáticas

Se recomienda el uso de métodos de expresiones regulares estáticas como alternativa a crear repetidamente instancias de un objeto de expresión regular con la misma expresión regular. A diferencia de los patrones de expresiones regulares usados por los objetos de expresiones regulares, el motor de expresiones regulares almacena internamente en memoria caché los códigos de operación o el lenguaje intermedio de Microsoft (MSIL) compilado de los patrones empleados en las llamadas al método estático.

Por ejemplo, un controlador de eventos llama con frecuencia a otro método para validar los datos proporcionados por el usuario. Esto se refleja en el código siguiente, en el que se usa el evento <xref:System.Windows.Forms.Button> de un control <xref:System.Windows.Forms.Control.Click> para llamar a un método denominado `IsValidCurrency`, que comprueba si el usuario ha escrito un símbolo de moneda seguido al menos de un dígito decimal.

[!code-csharp[Conceptual.RegularExpressions.BestPractices#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.bestpractices/cs/static1.cs#2)]
[!code-vb[Conceptual.RegularExpressions.BestPractices#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.bestpractices/vb/static1.vb#2)]

En el ejemplo siguiente se muestra una implementación muy poco eficaz del método `IsValidCurrency`. Observe que cada llamada al método vuelve a crear una instancia de un objeto <xref:System.Text.RegularExpressions.Regex> con el mismo modelo. Esto, a su vez, significa que el patrón de expresión regular se debe volver a compilar cada vez que se llama al método.

[!code-csharp[Conceptual.RegularExpressions.BestPractices#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.bestpractices/cs/static1.cs#3)]
[!code-vb[Conceptual.RegularExpressions.BestPractices#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.bestpractices/vb/static1.vb#3)]

Debe reemplazar este código ineficaz con una llamada al método estático <xref:System.Text.RegularExpressions.Regex.IsMatch%28System.String%2CSystem.String%29?displayProperty=nameWithType>. Esto elimina la necesidad de crear instancias de un objeto <xref:System.Text.RegularExpressions.Regex> cada vez que desea llamar a un método de coincidencia de modelos y permite que el motor de expresiones regulares recupere una versión compilada de la expresión regular de su memoria caché.

[!code-csharp[Conceptual.RegularExpressions.BestPractices#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.bestpractices/cs/static2.cs#4)]
[!code-vb[Conceptual.RegularExpressions.BestPractices#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.bestpractices/vb/static2.vb#4)]

De forma predeterminada, se almacenan en caché los 15 últimos patrones de expresiones regulares estáticas usados recientemente. En el caso de las aplicaciones que necesitan un mayor número de expresiones regulares estáticas almacenadas en caché, el tamaño de la memoria caché se puede ajustar estableciendo la propiedad <xref:System.Text.RegularExpressions.Regex.CacheSize%2A?displayProperty=nameWithType>.

La expresión regular `\p{Sc}+\s*\d+` que se usa en este ejemplo comprueba que la cadena de entrada consta de un símbolo de moneda y al menos un dígito decimal. El patrón se define como se muestra en la tabla siguiente.

|Modelo|Descripción|
|-------------|-----------------|
|`\p{Sc}+`|Buscar coincidencias con uno o más caracteres de la categoría Símbolo Unicode, Moneda.|
|`\s*`|Busca coincidencias con cero o más caracteres de espacio en blanco.|
|`\d+`|Buscar coincidencias con uno o más dígitos decimales.|

### <a name="interpreted-vs-compiled-regular-expressions"></a>Expresiones regulares interpretadas y compiladas

Los patrones de expresiones regulares que no están enlazados al motor de expresiones regulares mediante la especificación de la opción <xref:System.Text.RegularExpressions.RegexOptions.Compiled> se interpretan. Cuando se crea una instancia de un objeto de expresión regular, el motor de expresiones regulares convierte la expresión regular en un conjunto de códigos de operación. Cuando se llama a un método de instancia, el compilador JIT ejecuta y convierte a MSIL los códigos de operación. Del mismo modo, cuando se llama a un método estático de expresión regular y la expresión regular no se encuentra en la memoria caché, el motor de expresiones regulares convierte la expresión regular en un conjunto de códigos de operación y los almacena en memoria caché. A continuación, convierte estos códigos de operación a MSIL para que el compilador JIT pueda ejecutarlos. Las expresiones regulares interpretadas reducen el tiempo de inicio a costa de un tiempo de ejecución más lento. Por eso, son más adecuadas cuando la expresión regular se usa en un número reducido de llamadas a métodos o si el número exacto de llamadas a métodos de expresión regular es desconocido pero se espera que sea pequeño. A medida que aumenta el número de llamadas al método, la mejora de rendimiento del tiempo de inicio reducido queda oscurecida por una velocidad de ejecución más lenta.

Los patrones de expresiones regulares que están enlazados al motor de expresiones regulares mediante la especificación de la opción <xref:System.Text.RegularExpressions.RegexOptions.Compiled> se compilan. Esto significa que, cuando se crea una instancia de un objeto de expresión regular, o cuando se llama a un método estático de expresión regular y la expresión regular no se encuentra en la memoria caché, el motor de expresiones regulares convierte la expresión regular a un conjunto intermedio de códigos de operación que, a continuación, convierte a MSIL. Cuando se llama a un método, el compilador JIT ejecuta el código MSIL. A diferencia de las expresiones regulares interpretadas, las expresiones regulares compiladas aumentan el tiempo de inicio pero ejecutan más deprisa los métodos individuales de coincidencia de patrones. Por tanto, la ventaja de rendimiento resultante de compilar la expresión regular aumenta en proporción al número de métodos de expresiones regulares llamados.

En resumen, se recomienda usar expresiones regulares interpretadas al llamar a métodos de expresión regular con una expresión regular concreta con poca frecuencia relativamente. Debe usar expresiones regulares compiladas al llamar a métodos de expresión regular con una expresión regular concreta con relativa frecuencia. Es difícil determinar el umbral exacto en el que las velocidades de ejecución más lentas de las expresiones regulares interpretadas superan las mejoras de su menor tiempo de inicio, o el umbral en el que los tiempos de inicio más lentos de las expresiones regulares compiladas superan las mejoras de sus velocidades de ejecución más rápidas. Depende de diversos factores, como la complejidad de la expresión regular y los datos específicos que procesa. Para determinar si las expresiones regulares interpretadas o compiladas ofrecen el mejor rendimiento para su escenario de aplicación concreto, puede usar la clase <xref:System.Diagnostics.Stopwatch> para comparar sus tiempos de ejecución.

En el ejemplo siguiente, se compara el rendimiento de las expresiones regulares compiladas e interpretadas al leer las diez primeras frases y al leer todas las frases del texto *The Financier* de Theodore Dreiser. Como muestra el resultado del ejemplo, cuando solo se realizan diez llamadas a métodos de coincidencia de expresión regular, una expresión regular interpreta proporciona un rendimiento mejor que una expresión regular compilada. Sin embargo, una expresión regular compilada ofrece mejor rendimiento cuando se realiza un gran número de llamadas (en este caso, más de 13000).

[!code-csharp[Conceptual.RegularExpressions.BestPractices#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.bestpractices/cs/compare1.cs#5)]
[!code-vb[Conceptual.RegularExpressions.BestPractices#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.bestpractices/vb/compare1.vb#5)]

El patrón de expresión regular usado en el ejemplo, `\b(\w+((\r?\n)|,?\s))*\w+[.?:;!]`, se define como se muestra en la tabla siguiente.

|Modelo|Descripción|
|-------------|-----------------|
|`\b`|Iniciar la búsqueda de coincidencias en un límite de palabras.|
|`\w+`|Buscar coincidencias con uno o más caracteres alfabéticos.|
|<code>(\r?\n)&#124;,?\s)</code>|Buscar una coincidencia con cero o un retorno de carro seguido de un carácter de nueva línea, o cero o una coma seguida de un carácter de espacio en blanco.|
|<code>(\w+((\r?\n)&#124;,?\s))*</code>|Buscar coincidencias con cero o más apariciones de uno o más caracteres alfabéticos que van seguidos de cero o un retorno de carro y un carácter de nueva línea, o de cero o una coma seguida de un carácter de espacio en blanco.|
|`\w+`|Buscar coincidencias con uno o más caracteres alfabéticos.|
|`[.?:;!]`|Buscar una coincidencia con un punto, un signo de interrogación, dos puntos, punto y coma o un signo de exclamación.|

### <a name="regular-expressions-compiled-to-an-assembly"></a>Expresiones regulares: compiladas en un ensamblado

.NET también permite crear un ensamblado que contenga expresiones regulares compiladas. Esto lleva la merma de rendimiento de la compilación de la expresión regular del tiempo de ejecución al tiempo de diseño. Aunque también implica cierto trabajo adicional: Hay que definir las expresiones regulares de antemano y compilarlas en un ensamblado. El compilador puede hacer referencia a este ensamblado al compilar código fuente que usa expresiones regulares del ensamblado. Cada expresión regular compilada del ensamblado está representada por una clase que se deriva de <xref:System.Text.RegularExpressions.Regex>.

Para compilar expresiones regulares en un ensamblado, se llama al método <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%28System.Text.RegularExpressions.RegexCompilationInfo%5B%5D%2CSystem.Reflection.AssemblyName%29?displayProperty=nameWithType> y se le pasa una matriz de objetos <xref:System.Text.RegularExpressions.RegexCompilationInfo> que representan las expresiones regulares que se van a compilar y un objeto <xref:System.Reflection.AssemblyName> que contiene información sobre el ensamblado que se va a crear.

Se recomienda compilar expresiones regulares en un ensamblado en las situaciones siguientes:

- Si es un desarrollador de componentes que desea crear una biblioteca de expresiones regulares reutilizables.

- Si espera que los métodos de coincidencia de modelos de la expresión regular se llamen un número indeterminado de veces, desde una o dos veces hasta miles o decenas de miles de veces. A diferencia de las expresiones regulares compiladas o interpretadas, las expresiones regulares que se compilan en ensamblados independientes proporcionan un rendimiento coherente independientemente del número de llamadas a métodos.

Si emplea expresiones regulares compiladas para optimizar el rendimiento, no debe usar la reflexión para crear el ensamblado, cargar el motor de expresiones regulares y ejecutar sus métodos de coincidencia con modelos. Para ello es necesario evitar la creación dinámica de expresiones regulares y especificar cualquier opción de coincidencia de modelos (como la coincidencia de modelos sin distinción entre mayúsculas y minúsculas) en el momento en que se crea el ensamblado. También debe separar el código que crea el ensamblado del código que usa la expresión regular.

En el ejemplo siguiente se muestra cómo crear un ensamblado que contiene una expresión regular compilada. Crea un ensamblado denominado `RegexLib.dll` con una única clase de expresión regular, `SentencePattern`, que contiene el patrón de expresión regular de coincidencia con frases usado en la sección [Expresiones regulares interpretadas frente a expresiones regulares compiladas](#interpreted-vs-compiled-regular-expressions).

[!code-csharp[Conceptual.RegularExpressions.BestPractices#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.bestpractices/cs/compile1.cs#6)]
[!code-vb[Conceptual.RegularExpressions.BestPractices#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.bestpractices/vb/compile1.vb#6)]

Cuando el ejemplo se compila en un ejecutable y se ejecuta, crea un ensamblado denominado `RegexLib.dll`. La expresión regular se representa mediante una clase denominada `Utilities.RegularExpressions.SentencePattern` que se deriva de <xref:System.Text.RegularExpressions.Regex>. En el ejemplo siguiente, se usa después la expresión regular compilada para extraer las frases del texto *The Financier* de Theodore Dreiser.

[!code-csharp[Conceptual.RegularExpressions.BestPractices#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.bestpractices/cs/compile2.cs#7)]
[!code-vb[Conceptual.RegularExpressions.BestPractices#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.bestpractices/vb/compile2.vb#7)]

## <a name="take-charge-of-backtracking"></a>Controlar el retroceso

Normalmente, el motor de expresiones regulares usa la progresión lineal para desplazarse a través de una cadena de entrada y compararla con un patrón de expresión regular. Sin embargo, cuando en un patrón de expresión regular se usan cuantificadores indeterminados como `*`, `+` y`?`, el motor de expresiones regulares puede abandonar una parte de las coincidencias parciales correctas y volver a un estado guardado previamente para buscar una coincidencia correcta de todo el patron. Este proceso se denomina retroceso.

> [!NOTE]
> Para obtener más información acerca del retroceso, consulte [Detalles del comportamiento de expresiones regulares](../../../docs/standard/base-types/details-of-regular-expression-behavior.md) y [Retroceso](../../../docs/standard/base-types/backtracking-in-regular-expressions.md). Para obtener una explicación detallada del retroceso, vea [Optimizing Regular Expression Performance, Part II: (Optimización del rendimiento de expresiones regulares, Parte II: Control del retroceso](https://blogs.msdn.microsoft.com/bclteam/2010/08/03/optimizing-regular-expression-performance-part-ii-taking-charge-of-backtracking-ron-petrusha/)) en el blog del equipo de BCL.

La compatibilidad con el retroceso aporta a las expresiones regulares eficacia y flexibilidad. También deja la responsabilidad de controlar el funcionamiento del motor de expresiones regulares en manos de los desarrolladores de expresiones regulares. Puesto que los desarrolladores no suelen ser conscientes de esta responsabilidad, su uso incorrecto del retroceso o su dependencia de un retroceso excesivo suele desempeñar el rol más significativo en la degradación del rendimiento de las expresiones regulares. En un escenario de caso peor, el tiempo de ejecución puede duplicarse por cada carácter adicional de la cadena de entrada. De hecho, usando excesivamente el retroceso, es fácil crear el equivalente en programación de un bucle infinito si la entrada coincide casi con el patrón de expresiones regulares; el motor de expresiones regulares puede tardar horas o incluso días en procesar una cadena de entrada relativamente corta.

A menudo, las aplicaciones sufren una reducción del rendimiento por usar el retroceso a pesar de que el retroceso no es esencial para una coincidencia. Por ejemplo, la expresión regular `\b\p{Lu}\w*\b` busca una coincidencia con todas las palabras que comienzan por un carácter en mayúsculas, como se muestra en la tabla siguiente.

|Modelo|Descripción|
|-|-|
|`\b`|Iniciar la búsqueda de coincidencias en un límite de palabras.|
|`\p{Lu}`|Busca una coincidencia con un carácter en mayúsculas.|
|`\w*`|Buscar una coincidencia con cero o más caracteres alfabéticos.|
|`\b`|Finalizar la búsqueda de coincidencias en un límite de palabras.|

Puesto que un límite de palabra no es igual, o un subconjunto de, que un carácter alfabético, no hay ninguna posibilidad de que el motor de expresiones regulares cruce un límite de palabra cuando busca coincidencias con caracteres alfabéticos. Esto significa que para esta expresión regular, el retroceso nunca puede contribuir al éxito global de cualquier coincidencia; solo puede degradar el rendimiento, ya que se fuerza que el motor de expresiones regulares guarde su estado para cada coincidencia preliminar correcta de un carácter alfabético.

Si determina que el retroceso no es necesario, puede deshabilitarlo mediante el elemento de lenguaje `(?>subexpression)`. En el ejemplo siguiente se analiza una cadena de entrada usando dos expresiones regulares. La primera, `\b\p{Lu}\w*\b`, se basa en el retroceso. La segunda, `\b\p{Lu}(?>\w*)\b`, deshabilita el retroceso. Como muestra el resultado del ejemplo, ambas producen el mismo resultado.

[!code-csharp[Conceptual.RegularExpressions.BestPractices#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.bestpractices/cs/backtrack2.cs#10)]
[!code-vb[Conceptual.RegularExpressions.BestPractices#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.bestpractices/vb/backtrack2.vb#10)]

En muchos casos, el retroceso es esencial para buscar una coincidencia de un patrón de expresión regular con el texto de entrada. Sin embargo, el retroceso excesivo puede degradar gravemente el rendimiento y dar la impresión de que una aplicación ha dejado de responder. En concreto, esto ocurre cuando se anidan los cuantificadores y el texto que coincide con la subexpresión externa es un subconjunto del texto que coincide con la subexpresión interna.

> [!WARNING]
> Además de evitar el retroceso excesivo, se debe utilizar la característica de tiempo de espera para garantizar que el retroceso excesivo no reduzca gravemente el rendimiento de la expresión regular. Para obtener más información, consulte la sección [Usar valores de tiempo de espera](#use-time-out-values).

Por ejemplo, el patrón de expresión regular `^[0-9A-Z]([-.\w]*[0-9A-Z])*\$$` está diseñado para buscar coincidencias con un número de pieza que contiene al menos un carácter alfanumérico. Cualquier carácter adicional puede constar de un carácter alfanumérico, un guión, un carácter de subrayado o un punto, aunque el último carácter debe ser alfanumérico. El número de pieza termina con un signo de dólar. En algunos casos, este patrón de expresión regular puede presentar un rendimiento muy deficiente porque los cuantificadores están anidados y porque la subexpresión `[0-9A-Z]` es un subconjunto de la subexpresión `[-.\w]*`.

En estos casos, puede optimizar el rendimiento de la expresión regular quitando los cuantificadores anidados y reemplazando la subexpresión externa con una aserción de búsqueda anticipada o de búsqueda tardía de ancho cero. Las aserciones de búsqueda anticipada y de búsqueda tardía son delimitadores; no mueven el puntero en la cadena de entrada, sino que realizan una búsqueda hacia delante o hacia atrás para comprobar si se cumple una condición especificada. Por ejemplo, la expresión regular de número de pieza se puede volver a escribir como `^[0-9A-Z][-.\w]*(?<=[0-9A-Z])\$$`. Este patrón de expresión regular se define como se muestra en la tabla siguiente.

|Modelo|Descripción|
|-------------|-----------------|
|`^`|Iniciar la búsqueda de coincidencias con el principio de la cadena de entrada.|
|`[0-9A-Z]`|Buscar coincidencias de un carácter alfanumérico. El número de pieza debe constar al menos de este carácter.|
|`[-.\w]*`|Buscar coincidencias con cero o más apariciones de cualquier carácter alfabético, guión o punto.|
|`\$`|Buscar coincidencias con un signo de dólar.|
|`(?<=[0-9A-Z])`|Realizar una búsqueda anticipada del signo de dólar final para asegurarse de que el carácter anterior es alfanumérico.|
|`$`|Finalizar la búsqueda de coincidencias al final de la cadena de entrada.|

En el ejemplo siguiente se muestra el uso de esta expresión regular para encontrar una matriz que contiene los números de pieza posibles.

[!code-csharp[Conceptual.RegularExpressions.BestPractices#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.bestpractices/cs/backtrack4.cs#11)]
[!code-vb[Conceptual.RegularExpressions.BestPractices#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.bestpractices/vb/backtrack4.vb#11)]

El lenguaje de expresiones regulares de .NET incluye los elementos del lenguaje siguientes, que puede usar para eliminar cuantificadores anidados. Para obtener más información, consulte [Construcciones de agrupamiento](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).

|Elemento del lenguaje|Descripción|
|----------------------|-----------------|
|`(?=` `subexpression` `)`|Búsqueda anticipada positiva de ancho cero. Realizar una búsqueda anticipada de la posición actual para determinar si `subexpression` coincide con la cadena de entrada.|
|`(?!` `subexpression` `)`|Búsqueda anticipada negativa de ancho cero. Realizar una búsqueda anticipada de la posición actual para determinar si `subexpression` no coincide con la cadena de entrada.|
|`(?<=` `subexpression` `)`|Búsqueda tardía positiva de ancho cero. Realizar una búsqueda tardía de la posición actual para determinar si `subexpression` coincide con la cadena de entrada.|
|`(?<!` `subexpression` `)`|Búsqueda tardía negativa de ancho cero. Realizar una búsqueda tardía de la posición actual para determinar si `subexpression` no coincide con la cadena de entrada.|

## <a name="use-time-out-values"></a>Usar valores de tiempo de espera

Si sus expresiones regulares procesan datos de entrada que prácticamente coinciden con el patrón de expresiones regulares, normalmente se puede usar el retroceso excesivo, que afecta enormemente al rendimiento. Además de analizar cuidadosamente el uso del retroceso y probar la expresión regular en entradas casi coincidentes, debe establecer siempre un valor de tiempo de espera para garantizar que el impacto del retroceso excesivo, si aparece, se reduzca al mínimo.

El intervalo de tiempo de espera de la expresión regular define el período de tiempo que el motor de expresiones regulares buscará una coincidencia única antes de que el tiempo se agote. El intervalo de tiempo de espera predeterminado es <xref:System.Text.RegularExpressions.Regex.InfiniteMatchTimeout?displayProperty=nameWithType>, que significa que no se agotará el tiempo de la expresión regular. Puede invalidar este valor y definir un intervalo de tiempo de espera de la siguiente manera:

- Proporcionando un valor de tiempo de espera al crear una instancia del objeto <xref:System.Text.RegularExpressions.Regex> llamando al constructor <xref:System.Text.RegularExpressions.Regex.%23ctor%28System.String%2CSystem.Text.RegularExpressions.RegexOptions%2CSystem.TimeSpan%29?displayProperty=nameWithType>.

- Llamando a un método estático de coincidencia de patrones, como <xref:System.Text.RegularExpressions.Regex.Match%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%2CSystem.TimeSpan%29?displayProperty=nameWithType> o <xref:System.Text.RegularExpressions.Regex.Replace%28System.String%2CSystem.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%2CSystem.TimeSpan%29?displayProperty=nameWithType>, que incluya un parámetro `matchTimeout`.

- Para las expresiones regulares compiladas que se crean mediante una llamada al método <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A?displayProperty=nameWithType>, llamando al constructor que tiene un parámetro de tipo <xref:System.TimeSpan>.

Si ha definido un intervalo de tiempo de espera y no se encuentra ninguna coincidencia al final del intervalo, el método de expresiones regulares produce una excepción <xref:System.Text.RegularExpressions.RegexMatchTimeoutException>. En el controlador de excepciones, puede elegir reintentar la búsqueda de coincidencias con un intervalo de tiempo de espera más largo, abandonar el intento de búsqueda de coincidencias y asumir que no hay ninguna coincidencia o abandonar el intento de búsqueda de coincidencias y registrar la información de excepción para futuros análisis.

En el ejemplo siguiente se define un método `GetWordData` que crea una instancia de una expresión regular con un tiempo de espera de 350 milisegundos para calcular el número de palabras y el promedio de caracteres de una palabra en un documento de texto. Si se agota el tiempo de espera de la operación de coincidencia, el intervalo de tiempo de espera aumenta en 350 milisegundos y se vuelve a crear una instancia del objeto <xref:System.Text.RegularExpressions.Regex>. Si el nuevo intervalo de tiempo de espera es mayor de 1 segundo, el método vuelve a producir la excepción y se la envía al llamador.

[!code-csharp[Conceptual.RegularExpressions.BestPractices#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.bestpractices/cs/timeout1.cs#12)]
[!code-vb[Conceptual.RegularExpressions.BestPractices#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.bestpractices/vb/timeout1.vb#12)]

## <a name="capture-only-when-necessary"></a>Capturar solo cuando sea necesario

Las expresiones regulares de .NET admiten varias construcciones de agrupación, que permiten agrupar un patrón de expresión regular en una o más subexpresiones. Las construcciones de agrupación que más se usan en el lenguaje de expresiones regulares de .NET son `(`*subexpression*`)`, que define un grupo de captura numerado, y `(?<`*name*`>`*subexpression*`)`, que define un grupo de captura con nombre. Las construcciones de agrupación son esenciales para crear referencias inversas y para definir una subexpresión a la que se aplica un cuantificador.

Sin embargo, el uso de estos elementos de lenguaje tiene un costo. Hacen que el objeto <xref:System.Text.RegularExpressions.GroupCollection> devuelto por la propiedad <xref:System.Text.RegularExpressions.Match.Groups%2A?displayProperty=nameWithType> se rellene con las capturas sin nombre o con nombre más recientes, y si una única construcción de agrupación ha capturado varias subcadenas en la cadena de entrada, también rellenan el objeto <xref:System.Text.RegularExpressions.CaptureCollection> devuelto por la propiedad <xref:System.Text.RegularExpressions.Group.Captures%2A?displayProperty=nameWithType> de un grupo de captura determinado con varios objetos <xref:System.Text.RegularExpressions.Capture>.

A menudo, las construcciones de agrupación se usan en una expresión regular solo para poder aplicarles cuantificadores y los grupos capturados por estas subexpresiones no se usan posteriormente. Por ejemplo, la expresión regular `\b(\w+[;,]?\s?)+[.?!]` está diseñada para capturar una frase completa. En la tabla siguiente se describen los elementos del lenguaje de este patrón de expresión regular y su efecto sobre las colecciones <xref:System.Text.RegularExpressions.Match> y <xref:System.Text.RegularExpressions.Match.Groups%2A?displayProperty=nameWithType> del objeto <xref:System.Text.RegularExpressions.Group.Captures%2A?displayProperty=nameWithType>.

|Modelo|Descripción|
|-------------|-----------------|
|`\b`|Iniciar la búsqueda de coincidencias en un límite de palabras.|
|`\w+`|Buscar coincidencias con uno o más caracteres alfabéticos.|
|`[;,]?`|Buscar coincidencias con cero o una coma o un punto y coma.|
|`\s?`|Busca coincidencias con cero o un carácter de espacio en blanco.|
|`(\w+[;,]?\s?)+`|Buscar coincidencias con una o más apariciones de uno o más caracteres alfabéticos seguidos de una coma o un punto y coma opcional, seguido de un carácter opcional de espacio en blanco. Esto define al primer grupo de captura, que es necesario para que la combinación de varios caracteres alfabéticos (es decir, una palabra) seguidos de un signo de puntuación opcional se repita hasta que el motor de expresiones regulares llegue al final de una frase.|
|`[.?!]`|Buscar coincidencias con un punto, un signo de interrogación o un signo de exclamación.|

Como se muestra en el ejemplo siguiente, cuando se encuentra una coincidencia, los objetos <xref:System.Text.RegularExpressions.GroupCollection> y <xref:System.Text.RegularExpressions.CaptureCollection> se rellenan con capturas de la coincidencia. En este caso, el grupo de captura `(\w+[;,]?\s?)` existe para que se le pueda aplicar el cuantificador `+`, que permite que el patrón de expresión regular coincida con cada palabra de una frase. De lo contrario, coincidiría con la última palabra de una frase.

[!code-csharp[Conceptual.RegularExpressions.BestPractices#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.bestpractices/cs/group1.cs#8)]
[!code-vb[Conceptual.RegularExpressions.BestPractices#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.bestpractices/vb/group1.vb#8)]

Cuando use subexpresiones solo para aplicarles cuantificadores y no le interese el texto capturado, debe deshabilitar las capturas de grupo. Por ejemplo, el elemento de lenguaje `(?:subexpression)` impide al grupo al que se aplica que capture subcadenas coincidentes. En el ejemplo siguiente, el patrón de expresión regular del ejemplo anterior se cambia a `\b(?:\w+[;,]?\s?)+[.?!]`. Como muestra el resultado, evita que el motor de expresiones regulares rellene las colecciones <xref:System.Text.RegularExpressions.GroupCollection> y <xref:System.Text.RegularExpressions.CaptureCollection>.

[!code-csharp[Conceptual.RegularExpressions.BestPractices#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.bestpractices/cs/group2.cs#9)]
[!code-vb[Conceptual.RegularExpressions.BestPractices#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.bestpractices/vb/group2.vb#9)]

Puede deshabilitar las capturas de una de las maneras siguientes:

- Use el elemento de lenguaje `(?:subexpression)`. Este elemento impide la captura de subcadenas coincidentes en el grupo al que se aplica. No deshabilita las capturas de subcadenas en ningún grupo anidado.

- Use la opción <xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture>. Deshabilita todas las capturas sin nombre o implícitas en el patrón de expresión regular. Cuando se usa esta opción, solo se pueden capturar las subcadenas que coinciden con grupos con nombre definidos con el elemento de lenguaje `(?<name>subexpression)`. La marca <xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture> se puede pasar al parámetro `options` de un constructor de clase <xref:System.Text.RegularExpressions.Regex> o al parámetro `options` de un método coincidente estático <xref:System.Text.RegularExpressions.Regex>.

- Use la opción `n` del elemento de lenguaje `(?imnsx)`. Esta opción deshabilita todas las capturas sin nombre o implícitas desde el punto del patrón de expresión regular en el que aparece el elemento. Las capturas se deshabilitan hasta el final del modelo o hasta que la opción `(-n)` habilita las capturas sin nombre o implícitas. Para obtener más información, consulte [Construcciones misceláneas](../../../docs/standard/base-types/miscellaneous-constructs-in-regular-expressions.md).

- Use la opción `n` del elemento de lenguaje `(?imnsx:subexpression)`. Esta opción deshabilita todas las capturas sin nombre o implícitas en `subexpression`. Las capturas por grupos de captura anidados sin nombre o implícitos también se deshabilitan.

## <a name="related-topics"></a>Temas relacionados

|Title|Descripción|
|-----------|-----------------|
|[Detalles del comportamiento de expresiones regulares](../../../docs/standard/base-types/details-of-regular-expression-behavior.md)|Examina la implementación del motor de expresiones regulares de .NET. El tema se centra en la flexibilidad de las expresiones regulares y explica la responsabilidad del desarrollador para garantizar un funcionamiento eficaz y sólido del motor de expresiones regulares.|
|[Retroceso](../../../docs/standard/base-types/backtracking-in-regular-expressions.md)|Explica qué es el retroceso y cómo afecta al rendimiento de las expresiones regulares, y examine los elementos del lenguaje que proporcionan alternativas al retroceso.|
|[Lenguaje de expresiones regulares: referencia rápida](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)|Describe los elementos del lenguaje de expresiones regulares de .NET y proporciona vínculos a documentación detallada sobre cada elemento del lenguaje.|
