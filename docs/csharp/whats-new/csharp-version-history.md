---
title: Historia de C# - Guía de C#
description: ¿Qué aspecto tenía el lenguaje en sus primeras versiones y cómo ha evolucionado desde entonces?
author: erikdietrich
ms.date: 09/20/2017
ms.openlocfilehash: 3e3bf98d1435b237b2941758b8ed245baa970237
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36207539"
---
# <a name="the-history-of-c"></a>Historia de C# #

¿Qué aspecto tenía el lenguaje en sus primeras versiones? ¿Y cómo ha evolucionado en los años posteriores?

## <a name="c-version-10"></a>C# versión 1.0

Al echar la vista atrás, la versión 1.0 de C# se parecía mucho a Java. Como [parte de sus objetivos de diseño indicados para ECMA](http://feeldotneteasy.blogspot.com/2011/01/c-design-goals.html), intentaba ser un "lenguaje orientado a objetos que fuera sencillo, moderno y para fines generales".  En aquel momento, parecerse a Java significaba que conseguía esos primeros objetivos de diseño.

Pero si volvemos a echarle un vistazo a C# 1.0 ahora, no lo verá tan claro. Carecía de capacidades asincrónicas integradas y de algunas funcionalidades útiles de genéricos que se dan por sentado. De hecho, carecía por completo de genéricos.  ¿Y [LINQ](../linq/index.md)? Aún no estaba disponible. Esas características tardarían unos años más en agregarse.

C# 1.0 parecía estar privado de características, en comparación con la actualidad. Lo normal era tener que escribir código detallado. Pero aun así, hay que empezar por algo. C# 1.0 era una alternativa viable a Java en la plataforma Windows.

Las principales características de C# 1.0 incluían lo siguiente:

- [Clases](../programming-guide/classes-and-structs/classes.md)
- [Structs](../programming-guide/classes-and-structs/structs.md)
- [Interfaces](../programming-guide/interfaces/index.md)
- [Eventos](../events-overview.md)
- [Propiedades](../properties.md)
- [Delegados](../delegates-overview.md)
- [Expresiones](../programming-guide/statements-expressions-operators/expressions.md)
- [Instrucciones](../programming-guide/statements-expressions-operators/statements.md)
- [Atributos](../programming-guide/concepts/attributes/index.md)
- Literales

## <a name="c-version-20"></a>C# versión 2.0

Aquí las cosas empiezan a ponerse interesantes. Echemos un vistazo a algunas de las principales características de C# 2.0, que se publicó en 2005 junto con Visual Studio 2005:

- [Genéricos](../programming-guide/generics/index.md)
- [Tipos parciales](../programming-guide/classes-and-structs/partial-classes-and-methods.md#partial-classes)
- [Métodos anónimos](../programming-guide/statements-expressions-operators/anonymous-methods.md)
- [Nullable types](../programming-guide/nullable-types/index.md) (Tipos que aceptan valores NULL [Guía de programación de C#])
- [Iteradores](../programming-guide/concepts/iterators.md)
- [Covarianza y contravarianza](../programming-guide/concepts/covariance-contravariance/index.md)

Otras características de C# 2.0 agregaron capacidades a las características existentes:

- Accesibilidad independiente de captador o establecedor
- Conversiones de grupos de métodos (delegados)
- Clases estáticas
- Inferencia de delegados

Aunque puede que C# haya comenzado como un lenguaje genérico orientado a objetos, la versión 2.0 de C# cambió esto enseguida. En cuanto se pusieron con ella, se centraron en algunos puntos problemáticos graves para los desarrolladores. Y lo hicieron a lo grande.

Con los genéricos, los tipos y métodos pueden operar en un tipo arbitrario a la vez que conservan la seguridad de tipos. Por ejemplo, tener <xref:System.Collections.Generic.List%601> nos permite tener `List<string>` o `List<int>` y realizar operaciones de tipo seguro en esas cadenas o en enteros mientras los recorremos en iteración. Usar genéricos es mejor que crear un `ListInt` que derive de `ArrayList` o se convierta desde `Object` en cada operación.

C# 2.0 incorporó los iteradores. Para explicarlo brevemente, los iteradores permiten examinar todos los elementos de `List` (u otros tipos enumerables) con un bucle de `foreach`. Tener iteradores como una parte de primera clase del lenguaje mejoró drásticamente la facilidad de lectura del lenguaje y la capacidad de las personas de razonar sobre el código.

Aun así, C# seguía yendo por detrás de Java. Java ya había publicado versiones que incluían genéricos e iteradores. Pero esto cambiaría pronto a medida que los idiomas siguieran evolucionando.

## <a name="c-version-30"></a>C# versión 3.0

La versión 3.0 de C# llegó a finales de 2007, junto con Visual Studio 2008, aunque la cartera completa de características de lenguaje no llegaría realmente hasta la versión 3.5 de .NET Framework. Esta versión marcó un cambio importante en el crecimiento de C#. Estableció C# como un lenguaje de programación realmente formidable. Echemos un vistazo a algunas de las principales características de esta versión:

- [Propiedades implementadas automáticamente](../programming-guide/classes-and-structs/auto-implemented-properties.md).
- [Anonymous Types](../programming-guide/classes-and-structs/anonymous-types.md) (Tipos anónimos [Guía de programación de C#])
- [Expresiones de consulta](../linq/query-expression-basics.md)
- [Expresión lambda](https://www.daedtech.com/introduction-to-c-lambda-expressions/)
- [Árboles de expresión](https://blogs.msdn.microsoft.com/charlie/2008/01/31/expression-tree-basics/)
- [Métodos de extensión](https://www.codeproject.com/Tips/709310/Extension-Method-In-Csharp)
- [Variables locales con asignación implícita de tipos](../language-reference/keywords/var.md)
- [Métodos parciales](../language-reference/keywords/partial-method.md)
- Inicializadores de objeto y colección

En retrospectiva, muchas de estas características parecen inevitables e indivisibles. Todas ellas encajan estratégicamente. Por lo general se considera que la mejor característica de la versión de C# fue la expresión de consulta, también conocida como Language-Integrated Query (LINQ).

Una vista más matizada examina árboles de expresión, expresiones lambda y tipos anónimos como la base sobre la que se construye LINQ. Sin embargo, en cualquier caso, C# 3.0 presentó un concepto revolucionario. C# 3.0 había comenzado a sentar las bases para convertir C# en un lenguaje híbrido funcional y orientado a objetos.

En concreto, permitía escribir consultas declarativas en estilo de SQL para realizar operaciones en colecciones, entre otras cosas. En lugar de escribir un bucle de `for` para calcular el promedio de una lista de enteros, permitía hacerlo fácilmente como `list.Average()`. La combinación de métodos de extensión y expresiones de consulta hizo que esa lista de enteros pareciera haberse vuelto más inteligente.

Llevó tiempo hasta que los usuarios realmente captaron e integraron el concepto, pero ocurrió gradualmente. Ahora, años más tarde, el código es mucho más conciso, sencillo y funcional.

## <a name="c-version-40"></a>C# versión 4.0

La versión 4.0 de C# tuvo que lidiar con el carácter innovador que había adquirido la versión 3.0. Con la versión 3.0, el lenguaje de C# dejó de estar a la sombra de Java y alcanzó una posición prominente. El lenguaje se estaba convirtiendo rápidamente en algo elegante.

La siguiente versión introdujo algunas nuevas características interesantes:

- [Enlace dinámico](../language-reference/keywords/dynamic.md)
- [Argumentos opcionales/con nombre](../programming-guide/classes-and-structs/named-and-optional-arguments.md)
- [Covariante y contravariante de genéricos](../../standard/generics/covariance-and-contravariance.md)
- [Tipos de interoperabilidad insertados](https://stackoverflow.com/questions/20514240/whats-the-difference-setting-embed-interop-types-true-and-false-in-visual-studi)

Los tipos de interoperabilidad insertados solucionaron un problema de implementación. La covarianza y contravarianza de genéricos proporcionan más capacidad para usar genéricos, pero son más bien académicos y probablemente más valorados por autores de bibliotecas y Framework. Los parámetros opcionales y con nombre permiten eliminar muchas sobrecargas de métodos y proporcionan mayor comodidad. Pero ninguna de esas características está modificando el paradigma exactamente.

La característica más importante fue la introducción de la palabra clave `dynamic`. Con la palabra clave `dynamic`, en la versión 4.0 de C# se introdujo la capacidad de invalidar el compilador durante la escritura en tiempo de compilación. Al usar la palabra clave dinámica, puede crear constructos similares a los lenguajes tipados dinámicamente, como JavaScript. Puede crear `dynamic x = "a string"` y luego agregarle seis, dejando que el runtime decida qué debería suceder después.

Los enlaces dinámicos pueden dar lugar a errores, pero también otorgan un gran poder sobre el lenguaje.

## <a name="c-version-50"></a>C# versión 5.0

La versión 5.0 de C# era una versión del lenguaje centrada. Casi todo el trabajo de esa versión se centró en otro concepto de lenguaje innovador: el modelo `async` y `await` para la programación asincrónica.  Estas son las principales características:

- [Miembros asincrónicos](../async.md)
- [Atributos de información del llamador](https://www.codeproject.com/Tips/606379/Caller-Info-Attributes-in-Csharp)

El atributo de información del autor de la llamada permite recuperar fácilmente información sobre el contexto donde se está ejecutando sin tener que recurrir a una gran cantidad de código de reflexión reutilizable. Tiene muchos usos en tareas de registro y diagnóstico.

Pero `async` y `await` son los auténticos protagonistas de esta versión. Cuando estas características salieron a la luz en 2012, C# cambió de nuevo las reglas del juego al integrar la asincronía en el lenguaje como un participante de primera clase. Si alguna vez ha trabajado con operaciones de larga duración y la implementación de sitios web de devoluciones de llamada, probablemente le haya encantado esta característica del lenguaje.

## <a name="c-version-60"></a>C# versión 6.0

Con las versiones 3.0 y 5.0, C# había agregado nuevas características destacables a un lenguaje orientado a objetos. Con la versión 6.0, en lugar de introducir una característica innovadora y predominante, se publicaron muchas características menores que aumentaron la productividad de la programación de C#. Estas son algunas de ellas:

- [Importaciones estáticas](../language-reference/keywords/using-static.md)
- [Filtros de excepciones](https://www.thomaslevesque.com/2015/06/21/exception-filters-in-c-6/)
- [Inicializadores de propiedades](http://geekswithblogs.net/WinAZ/archive/2015/06/30/whatrsquos-new-in-c-6.0-auto-property-initializers.aspx)
- [Miembros de cuerpo de expresión](https://lostechies.com/jimmybogard/2015/12/17/c-6-feature-review-expression-bodied-function-members/)
- [Propagador de null](https://davefancher.com/2014/08/14/c-6-0-null-propagation-operator/)
- [Interpolación de cadenas](../language-reference/tokens/interpolated.md)
- [operador nameof](https://stackoverflow.com/questions/31695900/what-is-the-purpose-of-nameof)
- [Inicializadores de índice](csharp-6.md#index-initializers)

Entre las otras características nuevas se incluyen estas:

- Await en bloques catch y finally
- Valores predeterminados para las propiedades solo de captador

Cada una de estas características es interesante en sí misma. Pero si las observamos en su conjunto, vemos un patrón interesante. En esta versión, C# eliminó lenguaje reutilizable para que el código fuera más fluido y fácil de leer. Así que, para los que adoran el código simple y limpio, esta versión del lenguaje fue una gran aportación.

En esta versión también se hizo otra cosa, aunque no es una característica de lenguaje tradicional: publicaron el [compilador Roslyn como un servicio](https://github.com/dotnet/roslyn). Ahora, el compilador de C# está escrito en C# y puede usarlo como parte de su trabajo de programación.

## <a name="c-version-70"></a>C# versión 7.0

La versión principal más reciente es la versión 7.0 de C#. Esta versión tiene algunas cosas interesantes y evolutivas en la misma línea que C# 6.0, pero sin el compilador como servicio. Estas son algunas de las nuevas características:

- [Variables out](http://www.c-sharpcorner.com/article/out-variables-in-c-sharp-7-0/)
- [Tuplas y deconstrucción](https://www.thomaslevesque.com/2016/08/23/tuple-deconstruction-in-c-7/)
- [Coincidencia de patrones](./csharp-7.md#pattern-matching)
- [Funciones locales](http://www.infoworld.com/article/3182416/application-development/c-7-in-depth-exploring-local-functions.html)
- [Miembros con forma de expresión expandidos](./csharp-7.md#more-expression-bodied-members)
- [Devoluciones y variables locales ref](./csharp-7.md#ref-locals-and-returns)

Otras características incluidas:

- [Descartes](../discards.md)
- [Literales binarios](https://github.com/dotnet/csharplang/blob/master/proposals/csharp-7.0/binary-literals.md)
- [Separadores de dígitos](https://github.com/dotnet/csharplang/blob/master/proposals/csharp-7.0/digit-separators.md)
- Valores devueltos y variables locales
- [Expresiones throw](https://github.com/dotnet/csharplang/blob/master/proposals/csharp-7.0/throw-expression.md)

Todas estas características ofrecen capacidades nuevas e interesantes para los desarrolladores y la posibilidad de escribir un código de manera más clara que nunca. De manera destacada, condensan la declaración de variables que se van a usar con la palabra clave `out` y permiten varios valores devueltos a través de tuplas.

Pero C# se está usando cada vez más. .NET Core ahora tiene como destino cualquier sistema operativo y tiene puesta la mirada en la nube y la portabilidad.  Por supuesto, esas nuevas capacidades ocupan las ideas y el tiempo de los diseñadores de lenguaje, además de ofrecer nuevas características.

_Artículo_ [_publicado originalmente en el blog de NDepend_](https://blog.ndepend.com/c-versions-look-language-history/)_, por cortesía de Erik Dietrich y Patrick Smacchia._
