---
title: "El historial de C# - Guía de C#"
description: "¿Qué el lenguaje aspecto en sus versiones anteriores, y cómo ha evolucionado desde?"
keywords: C#,. NET, .NET Core, ' s New, historial de C#
author: erikdietrich
ms.author: wiwagn
ms.date: 09/20/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.openlocfilehash: 207c97c5dd7e04f815da61bff7f44393aea86222
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="the-history-of-c"></a>El historial de C# #

¿Qué le gusta el aspecto del lenguaje en sus primeras versiones? ¿Y cómo ha evolucionado en los años desde?

## <a name="c-version-10"></a>La versión 1.0 de C#

Al volver atrás y buscar, versión de C# 1.0 aspecto mucho Java. Como [parte de sus objetivos de diseño indicados para ECMA](http://feeldotneteasy.blogspot.com/2011/01/c-design-goals.html), lo busca como "simple, moderno para fines generales orientada a objetos lengua."  En el momento, parezca que Java significaba logra los objetivos de diseño temprano.

Pero si echa un vistazo en C# 1.0 ahora, encontrará usted mismo mareadas un poco. Carecía de las capacidades integradas asincrónico y parte de la funcionalidad de un alrededor de los genéricos que se dan por sentado. De hecho, carecía genéricos por completo.  ¿Y [LINQ](../linq/index.md)? No está disponible todavía. Que tardaría algunos años para saldrá.

La versión 1.0 de C# busca eliminada de características, en comparación con hoy en día. Se encuentre escribiendo código detallado. Pero aún, tendrá que iniciar en algún lugar. La versión 1.0 de C# es una alternativa viable para Java en la plataforma Windows.

## <a name="c-version-20"></a>La versión 2.0 de C#

Ahora cosas empiezan a ponerse interesante. ¡Eche un vistazo a algunas características principales de C# 2.0, que se publicó en 2005, junto con Visual Studio 2005:

- [Genéricos](../programming-guide/generics/index.md)
- [Tipos parciales](../programming-guide/classes-and-structs/partial-classes-and-methods.md#partial-classes)
- [Métodos anónimos](../programming-guide/statements-expressions-operators/anonymous-methods.md)
- [Nullable types](../programming-guide/nullable-types/index.md) (Tipos que aceptan valores NULL [Guía de programación de C#])
- [Iteradores](../programming-guide/concepts/iterators.md)
- [Covarianza y contravarianza](../programming-guide/concepts/covariance-contravariance/index.md)

Aunque podría haber comenzado C# como lenguaje orientada a objetos (orientado a objetos) bastante genérica, la versión 2.0 de C# cambió tiene prisa. Una vez que tenían sus pies en ellos, fueron después de algunos puntos débiles de desarrollador graves. Y fueron después de ellos de forma grande.

Con los genéricos, tienen tipos y métodos que pueden operar en un tipo arbitrario mientras se conservan la seguridad de tipos. Por lo tanto, por ejemplo, tener un <xref:System.Collections.Generic.List%601> le permite tener `List<string>` o `List<int>` y realizar operaciones de tipo seguro en esas cadenas o enteros mientras recorrerlos en iteración. Esto es mejor que crear `ListInt` los herederos o la conversión de `Object` para cada operación.

Iteradores versión 2.0 pone de C#. Para colocar brevemente, esto le permite recorrer en iteración los elementos de un `List` (u otros tipos Enumerable) con un `foreach` bucle. Recientes esto como parte del lenguaje de primera clase drásticamente mejoran la legibilidad del idioma y la capacidad de personas razonar sobre el código.

Y aún, C# continuado reproducir un poco de puesta al día con Java. Java ya había publicado versiones que incluyan genéricos e iteradores. Pero pronto que cambiaría como los idiomas seguidos evolucionando alejados.

## <a name="c-version-30"></a>La versión 3.0 de C#

La versión 3.0 de C# suministrada en tiempo de ejecución 2007, junto con Visual Studio 2008, aunque lo barco completo de características del lenguaje sería realmente con la versión 3.5 de C#. Esta versión marca un cambio importante en el crecimiento de C#. Establece C# como lenguaje de programación realmente enormes. ¡Eche un vistazo a algunas características importantes en esta versión:

- [Propiedades de automático implementado](../programming-guide/classes-and-structs/auto-implemented-properties.md)
- [Anonymous Types](../programming-guide/classes-and-structs/anonymous-types.md) (Tipos anónimos [Guía de programación de C#])
- [Expresiones de consulta](../linq/query-expression-basics.md)
- [Expresión lambda](https://www.daedtech.com/introduction-to-c-lambda-expressions/)
- [Árboles de expresión](https://blogs.msdn.microsoft.com/charlie/2008/01/31/expression-tree-basics/)
- [Métodos de extensión](https://www.codeproject.com/Tips/709310/Extension-Method-In-Csharp)

En retrospectiva, muchas de estas características parecen inevitable y no separable. Todas ellas encajan estratégicamente. Por lo general se considera que mejor característica de la versión de C# fue la expresión de consulta, también conocido como Language-Integrated Query (LINQ).

Una vista más matizada examina los tipos anónimos, las expresiones lambda y árboles de expresión como la base en el que se construye LINQ. Sin embargo, en cualquier caso, C# 3.0 presenta un concepto revolucionario. En C# 3.0 había comenzado a sentar las bases para activar C# en un híbrido orientado a objetos / funcional idioma.

En concreto, ahora puede escribir estilo de SQL, consultas declarativas para realizar operaciones en las colecciones, entre otras cosas. En lugar de escribir un `for` de bucle para calcular el promedio de una lista de enteros, ahora puede hacerlo simplemente como `list.Average()`. La combinación de métodos de extensión y las expresiones de consulta hizo parezca esa lista de enteros había recibido mucho más inteligentes.

Necesita tiempo para las personas realmente captar e integrar el concepto, pero lo hacían gradualmente. Y ahora, años más tarde, código es mucho más concisa, simple y funcional.

## <a name="c-version-40"></a>La versión 4.0 de C#

La versión 4.0 de C# habría tenido dificultades a la hora cumple con el estado innovador de versión 3.0. Con la versión 3.0, C# habían movido el idioma bien horizontal de la sombra de Java y en importancia. El idioma se está convirtiendo rápidamente en elegante.

La próxima versión ha introducido algunas nuevas características interesantes:

- [Enlace dinámico](../language-reference/keywords/dynamic.md)
- [Argumentos opcionales y con nombre](../programming-guide/classes-and-structs/named-and-optional-arguments.md)
- [Genérico covariante y contravariante](../../standard/generics/covariance-and-contravariance.md)
- [Tipos de interoperabilidad incrustados](https://stackoverflow.com/questions/20514240/whats-the-difference-setting-embed-interop-types-true-and-false-in-visual-studi)

Tipos de interoperabilidad insertados habían solucionado un problema de implementación. Contravarianza y covarianza genérica proporcionan más capacidad para que utilicen genéricos, pero son un poco académico y probablemente más valora los autores de framework y la biblioteca. Parámetros opcionales y con nombre permiten eliminar muchas de las sobrecargas de método y proporcionan mayor comodidad. Pero ninguna de esas características está modificando el paradigma exactamente.

La característica principal era la introducción de la `dynamic` (palabra clave). El `dynamic` palabra clave introducida en la versión 4.0 de C# la capacidad de invalidar el compilador sobre cómo asignar tipos de tiempo de compilación. Mediante el uso de la palabra clave dynamic, puede crear construcciones similares a dinámicamente tipados lenguajes como JavaScript. Puede crear un `dynamic x = "a string"` y, a continuación, agregar seis, dejando hasta el tiempo de ejecución para solucionar los qué debe suceder a continuación.

Esto proporciona el potencial para errores, sino también gran eficacia dentro del lenguaje.

## <a name="c-version-50"></a>La versión 5.0 de C#

La versión 5.0 de C# era una versión muy tiene el foco del lenguaje. Casi todo el trabajo de esa versión se incluyó en otro concepto de lenguaje innovador.  Esta es la lista de características principales:

- [Miembros asincrónicos](../async.md)
- [Atributos de información del autor de llamada](https://www.codeproject.com/Tips/606379/Caller-Info-Attributes-in-Csharp)

El atributo de información de llamador permite recuperar información sobre el contexto en el que está ejecutando sin tener que recurrir a una gran cantidad de código de reflexión reutilizable con facilidad. Tiene muchos usos en tareas de registro y diagnóstico.

Pero `async` y `await` son los auténticos protagonistas de esta versión. Cuando estas características se imprimieron 2012, C# cambia el juego nuevo al integrar asincronía en el idioma que un participante de primera clase. Si alguna vez ha trabajado con las operaciones de larga duración y la implementación de sitios Web de devoluciones de llamada, probablemente encantó esta característica de lenguaje.

## <a name="c-version-60"></a>La versión 6.0 de C#

Con las versiones 3.0 y 5.0, C# tenía agrega algunas características impresionante en un lenguaje orientado a objetos. Con la versión 6.0, usaría ir fuera de una mejor característica dominante y muchas características que encantado usuarios del idioma de la versión en su lugar. Estas son algunas de ellas:

- [Importaciones estáticas](../language-reference/keywords/using-static.md)
- [Filtros de excepciones](https://www.thomaslevesque.com/2015/06/21/exception-filters-in-c-6/)
- [Inicializadores de propiedades](http://geekswithblogs.net/WinAZ/archive/2015/06/30/whatrsquos-new-in-c-6.0-auto-property-initializers.aspx)
- [Miembros de cuerpo de expresión](https://lostechies.com/jimmybogard/2015/12/17/c-6-feature-review-expression-bodied-function-members/)
- [Propagador de null](https://davefancher.com/2014/08/14/c-6-0-null-propagation-operator/)
- [Interpolación de cadenas](../language-reference/keywords/interpolated-strings.md)
- [nameof (operador)](https://stackoverflow.com/questions/31695900/what-is-the-purpose-of-nameof)
- [Inicializador de diccionario](../programming-guide/classes-and-structs/how-to-initialize-a-dictionary-with-a-collection-initializer.md)

Cada una de estas características es interesante derecho propio. Pero si observa por completo a ellos, verá un patrón interesante. En esta versión, C# elimina reutilizable de lenguaje para que el código más concisas y legibles. Por lo que para ventiladores de código sencillo, esta versión de idioma era una gran victoria.

Lo hacían otra cuestión que hay junto con esta versión, aunque no es una característica del lenguaje tradicional en sí mismo. Liberan [Roslyn el compilador como un servicio](https://github.com/dotnet/roslyn). Ahora, el compilador de C# se escribe en C#, y puede usar el compilador como parte de sus esfuerzos de programación.

## <a name="c-version-70"></a>La versión 7.0 de C#

La versión principal más reciente es la versión 7.0 de C#. Esta versión tiene algunas cosas interesantes y evolutivo en el modo de C# 6.0, pero sin que el compilador como un servicio. Estas son algunas de las nuevas características:

- [Variables](http://www.c-sharpcorner.com/article/out-variables-in-c-sharp-7-0/)
- [Tuplas y anulación de la construcción](https://www.thomaslevesque.com/2016/08/23/tuple-deconstruction-in-c-7/)
- [Coincidencia de patrones](./csharp-7.md#pattern-matching)
- [Funciones locales](http://www.infoworld.com/article/3182416/application-development/c-7-in-depth-exploring-local-functions.html)
- [Miembros de cuerpo de expresión expandida](./csharp-7.md#more-expression-bodied-members)
- [Devuelve y variables locales de ref](./csharp-7.md#ref-locals-and-returns)

Todas estas características ofrecen capacidades nuevas más interesantes para los desarrolladores y la posibilidad de escribir un código incluso más claro que nunca. Un resaltado comprime la declaración de variables que se va a usar con el `out` palabra clave y por lo que permite varios valores devueltos a través de la tupla.

Pero C# se está poniendo en uso cada vez más amplio. .NET core ahora tiene como destino cualquier sistema operativo y sus ojos bien en la nube y a la portabilidad.  Por supuesto, esto ocupa ideas y la hora, además de a continuación con las nuevas características de los diseñadores del lenguaje.

_Artículo_ [ _publicó originalmente en el blog de NDepend_](https://blog.ndepend.com/c-versions-look-language-history/)_, por cortesía de Erik Dietrich y Patrick Smacchia._
