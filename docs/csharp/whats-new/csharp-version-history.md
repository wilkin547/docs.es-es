---
title: Historia de C# - Guía de C#
description: ¿Qué aspecto tenía el lenguaje en sus primeras versiones y cómo ha evolucionado desde entonces?
author: erikdietrich
ms.date: 04/08/2020
ms.openlocfilehash: 0c427563701bd3bff87178022feab19f4dcfc519
ms.sourcegitcommit: c7f0beaa2bd66ebca86362ca17d673f7e8256ca6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104877064"
---
# <a name="the-history-of-c"></a>Historia de C\#

En este artículo se proporciona un historial de cada versión principal del lenguaje C#. El equipo de C# continúa innovando y agregando nuevas características. Se puede encontrar información sobre el estado detallado de las características de lenguaje, incluidas las características consideradas para las próximas versiones, [en el repositorio dotnet/roslyn](https://github.com/dotnet/roslyn/blob/main/docs/Language%20Feature%20Status.md) de GitHub.

> [!IMPORTANT]
> El lenguaje C# se basa en tipos y métodos en lo que la especificación de C# define como una *biblioteca estándar* para algunas de las características. La plataforma .NET ofrece los tipos y métodos en un número de paquetes. Un ejemplo es el procesamiento de excepciones. Cada expresión o instrucción `throw` se comprueba para asegurarse de que el objeto que se genera deriva de <xref:System.Exception>. Del mismo modo, cada `catch` se comprueba para asegurarse de que el tipo que se captura deriva de <xref:System.Exception>. Cada versión puede agregar requisitos nuevos. Para usar las características más recientes del lenguaje en entornos anteriores, es posible que tenga que instalar bibliotecas específicas. Estas dependencias están documentadas en la página de cada versión específica. Puede obtener más información sobre las [relaciones entre lenguaje y biblioteca](relationships-between-language-and-library.md) para tener más antecedentes sobre esta dependencia.

Las herramientas de compilación de C# consideran que la última versión principal del lenguaje es la versión predeterminada. Puede haber versiones secundarias entre versiones principales, que se detallan en los otros artículos de esta sección. Para usar las características más recientes en una versión secundaria, tendrá que [configurar la versión del idioma de compilador](../language-reference/configure-language-version.md) y seleccionar la versión. Ha habido tres versiones secundarias desde C# 7.0:

- C# 7.3:
  - C# 7.3 está disponible a partir de la [versión 15.7 de Visual Studio 2017](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) y el [SDK de .NET Core 2.1](../../core/whats-new/dotnet-core-2-1.md).
- C# 7.2:
  - C# 7.2 está disponible a partir de la [versión 15.5 de Visual Studio 2017](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) y el [SDK de .NET Core 2.0](../../core/whats-new/dotnet-core-2-0.md).
- C# 7.1:
  - C# 7.1 está disponible a partir de la [versión 15.3 de Visual Studio 2017](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) y el [SDK de .NET Core 2.0](../../core/whats-new/dotnet-core-2-0.md).

## <a name="c-version-10"></a>C# versión 1.0

Si echa la vista atrás, la versión 1.0 de C#, publicada con Visual Studio .NET 2002, se parecía mucho a Java. Como [parte de sus objetivos de diseño indicados para ECMA](https://feeldotneteasy.blogspot.com/2011/01/c-design-goals.html), intentaba ser un "lenguaje orientado a objetos que fuera sencillo, moderno y para fines generales".  En aquel momento, parecerse a Java significaba que conseguía esos primeros objetivos de diseño.

Pero si volvemos a echarle un vistazo a C# 1.0 ahora, no lo verá tan claro. Carecía de capacidades asincrónicas integradas y de algunas funcionalidades útiles de genéricos que se dan por sentado. De hecho, carecía por completo de genéricos.  ¿Y [LINQ](../linq/index.md)? Aún no estaba disponible. Esas características tardarían unos años más en agregarse.

C# 1.0 parecía estar privado de características, en comparación con la actualidad. Lo normal era tener que escribir código detallado. Pero aun así, hay que empezar por algo. C# 1.0 era una alternativa viable a Java en la plataforma Windows.

Las principales características de C# 1.0 incluían lo siguiente:

- [Clases](../programming-guide/classes-and-structs/classes.md)
- [Structs](../language-reference/builtin-types/struct.md)
- [Interfaces](../programming-guide/interfaces/index.md)
- [Eventos](../events-overview.md)
- [Propiedades](../properties.md)
- [Delegados](../delegates-overview.md)
- [Operadores y expresiones](../language-reference/operators/index.md)
- [Instrucciones](../programming-guide/statements-expressions-operators/statements.md)
- [Atributos](../programming-guide/concepts/attributes/index.md)

## <a name="c-version-12"></a>Versión 1.2 de C#

Versión 1.2 de C# incluida en Visual Studio .NET 2003. Contenía algunas pequeñas mejoras del lenguaje. Lo más notable es que, a partir de esa versión, el código se generaba en un bucle `foreach` llamado <xref:System.IDisposable.Dispose%2A> en un <xref:System.Collections.IEnumerator> cuando ese <xref:System.Collections.IEnumerator> implementaba <xref:System.IDisposable>.

## <a name="c-version-20"></a>C# versión 2.0

Aquí las cosas empiezan a ponerse interesantes. Echemos un vistazo a algunas de las principales características de C# 2.0, que se publicó en 2005 junto con Visual Studio 2005:

- [Genéricos](../programming-guide/generics/index.md)
- [Tipos parciales](../programming-guide/classes-and-structs/partial-classes-and-methods.md#partial-classes)
- [Métodos anónimos](../language-reference/operators/delegate-operator.md)
- [Tipos de valores que aceptan valores NULL](../language-reference/builtin-types/nullable-value-types.md)
- [Iteradores](../programming-guide/concepts/iterators.md)
- [Covarianza y contravarianza](../programming-guide/concepts/covariance-contravariance/index.md)

Otras características de C# 2.0 agregaron capacidades a las características existentes:

- Accesibilidad independiente de captador o establecedor
- Conversiones de grupos de métodos (delegados)
- Clases estáticas
- Inferencia de delegados

Aunque puede que C# haya comenzado como un lenguaje genérico orientado a objetos, la versión 2.0 de C# cambió esto enseguida. En cuanto se pusieron con ella, se centraron en algunos puntos problemáticos graves para los desarrolladores. Y lo hicieron a lo grande.

Con los genéricos, los tipos y métodos pueden operar en un tipo arbitrario a la vez que conservan la seguridad de tipos. Por ejemplo, tener <xref:System.Collections.Generic.List%601> nos permite tener `List<string>` o `List<int>` y realizar operaciones de tipo seguro en esas cadenas o en enteros mientras los recorremos en iteración. Es mejor usar genéricos que crear un tipo `ListInt` que derive de `ArrayList`, o que convertir desde `Object` en cada operación.

C# 2.0 incorporó los iteradores. Para explicarlo brevemente, los iteradores permiten examinar todos los elementos de `List` (u otros tipos enumerables) con un bucle de `foreach`. Tener iteradores como una parte de primera clase del lenguaje mejoró drásticamente la facilidad de lectura del lenguaje y la capacidad de las personas de razonar sobre el código.

Aun así, C# seguía yendo por detrás de Java. Java ya había publicado versiones que incluían genéricos e iteradores. Pero esto cambiaría pronto a medida que los idiomas siguieran evolucionando.

## <a name="c-version-30"></a>C# versión 3.0

La versión 3.0 de C# llegó a finales de 2007, junto con Visual Studio 2008, aunque la cartera completa de características de lenguaje no llegaría realmente hasta la versión 3.5 de .NET Framework. Esta versión marcó un cambio importante en el crecimiento de C#. Estableció C# como un lenguaje de programación realmente formidable. Echemos un vistazo a algunas de las principales características de esta versión:

- [Propiedades implementadas automáticamente](../programming-guide/classes-and-structs/auto-implemented-properties.md)
- [Tipos anónimos (Guía de programación de C#)](../programming-guide/classes-and-structs/anonymous-types.md).
- [Expresiones de consulta](../linq/query-expression-basics.md)
- [Expresiones lambda](../language-reference/operators/lambda-expressions.md)
- [Árboles de expresión](../expression-trees.md)
- [Métodos de extensión](../programming-guide/classes-and-structs/extension-methods.md)
- [Variables locales con asignación implícita de tipos](../language-reference/keywords/var.md)
- [Métodos parciales](../language-reference/keywords/partial-method.md)
- [Inicializadores de objeto y colección](../programming-guide/classes-and-structs/object-and-collection-initializers.md)

En retrospectiva, muchas de estas características parecen inevitables e indivisibles. Todas ellas encajan estratégicamente. Por lo general se considera que la mejor característica de la versión de C# fue la expresión de consulta, también conocida como Language-Integrated Query (LINQ).

Una vista más matizada examina árboles de expresión, expresiones lambda y tipos anónimos como la base sobre la que se construye LINQ. Sin embargo, en cualquier caso, C# 3.0 presentó un concepto revolucionario. C# 3.0 había comenzado a sentar las bases para convertir C# en un lenguaje híbrido funcional y orientado a objetos.

En concreto, permitía escribir consultas declarativas en estilo de SQL para realizar operaciones en colecciones, entre otras cosas. En lugar de escribir un bucle de `for` para calcular el promedio de una lista de enteros, permitía hacerlo fácilmente como `list.Average()`. La combinación de métodos de extensión y expresiones de consulta hizo que esa lista de enteros pareciera haberse vuelto más inteligente.

Llevó tiempo hasta que los usuarios realmente captaron e integraron el concepto, pero ocurrió gradualmente. Ahora, años más tarde, el código es mucho más conciso, sencillo y funcional.

## <a name="c-version-40"></a>C# versión 4.0

La versión 4.0 de C#, publicada con Visual Studio 2010, tuvo que lidiar con el carácter innovador que había adquirido la versión 3.0. Con la versión 3.0, el lenguaje de C# dejó de estar a la sombra de Java y alcanzó una posición prominente. El lenguaje se estaba convirtiendo rápidamente en algo elegante.

La siguiente versión introdujo algunas nuevas características interesantes:

- [Enlace dinámico](../language-reference/builtin-types/reference-types.md)
- [Argumentos opcionales/con nombre](../programming-guide/classes-and-structs/named-and-optional-arguments.md)
- [Covariante y contravariante de genéricos](../../standard/generics/covariance-and-contravariance.md)
- [Tipos de interoperabilidad insertados](../../framework/interop/type-equivalence-and-embedded-interop-types.md)

Los tipos de interoperabilidad insertados solucionaron un problema de implementación. La covarianza y contravarianza de genéricos proporcionan más capacidad para usar genéricos, pero son más bien académicos y probablemente más valorados por autores de bibliotecas y Framework. Los parámetros opcionales y con nombre permiten eliminar muchas sobrecargas de métodos y proporcionan mayor comodidad. Pero ninguna de esas características está modificando el paradigma exactamente.

La característica más importante fue la introducción de la palabra clave `dynamic`. Con la palabra clave `dynamic`, en la versión 4.0 de C# se introdujo la capacidad de invalidar el compilador durante la escritura en tiempo de compilación. Al usar la palabra clave dinámica, puede crear constructos similares a los lenguajes tipados dinámicamente, como JavaScript. Puede crear `dynamic x = "a string"` y luego agregarle seis, dejando que el runtime decida qué debería suceder después.

Los enlaces dinámicos pueden dar lugar a errores, pero también otorgan un gran poder sobre el lenguaje.

## <a name="c-version-50"></a>C# versión 5.0

La versión 5.0 de C#, publicada con Visual Studio 2012, era una versión centrada del lenguaje. Casi todo el trabajo de esa versión se centró en otro concepto de lenguaje innovador: el modelo `async` y `await` para la programación asincrónica.  Estas son las principales características:

- [Miembros asincrónicos](../async.md)
- [Atributos de información del llamador](../language-reference/attributes/caller-information.md)

### <a name="see-also"></a>Vea también

- [Proyecto de código: Atributos de información del autor de llamada en C# 5.0](https://www.codeproject.com/Tips/606379/Caller-Info-Attributes-in-Csharp)

El atributo de información del autor de la llamada permite recuperar fácilmente información sobre el contexto donde se está ejecutando sin tener que recurrir a una gran cantidad de código de reflexión reutilizable. Tiene muchos usos en tareas de registro y diagnóstico.

Pero `async` y `await` son los auténticos protagonistas de esta versión. Cuando estas características salieron a la luz en 2012, C# cambió de nuevo las reglas del juego al integrar la asincronía en el lenguaje como un participante de primera clase. Si alguna vez ha trabajado con operaciones de larga duración y la implementación de sitios web de devoluciones de llamada, probablemente le haya encantado esta característica del lenguaje.

## <a name="c-version-60"></a>C# versión 6.0

Con las versiones 3.0 y 5.0, C# había agregado nuevas características destacables a un lenguaje orientado a objetos. Con la versión 6.0, publicada con Visual Studio 2015, en lugar de introducir una característica innovadora y predominante, se publicaron muchas características menores que aumentaron la productividad de la programación de C#. Estas son algunas de ellas:

- [Importaciones estáticas](../language-reference/keywords/using-static.md)
- [Filtros de excepciones](../language-reference/keywords/when.md)
- [Inicializadores de propiedades automáticas](../properties.md)
- [Miembros de cuerpo de expresión](../language-reference/operators/lambda-operator.md#expression-body-definition)
- [Propagador de null](../language-reference/operators/member-access-operators.md#null-conditional-operators--and-)
- [Interpolación de cadenas](../language-reference/tokens/interpolated.md)
- [operador nameof](../language-reference/operators/nameof.md)

Entre las otras características nuevas se incluyen estas:

- Inicializadores de índice
- Await en bloques catch y finally
- Valores predeterminados para las propiedades solo de captador

Cada una de estas características es interesante en sí misma. Pero si las observamos en su conjunto, vemos un patrón interesante. En esta versión, C# eliminó lenguaje reutilizable para que el código fuera más fluido y fácil de leer. Así que, para los que adoran el código simple y limpio, esta versión del lenguaje fue una gran aportación.

En esta versión también se hizo otra cosa, aunque no es una característica de lenguaje tradicional: publicaron el [compilador Roslyn como un servicio](https://github.com/dotnet/roslyn). Ahora, el compilador de C# está escrito en C# y puede usarlo como parte de su trabajo de programación.

## <a name="c-version-70"></a>C# versión 7.0

C# versión 7.0 se comercializó con Visual Studio 2017. Esta versión tiene algunas cosas interesantes y evolutivas en la misma línea que C# 6.0, pero sin el compilador como servicio. Estas son algunas de las nuevas características:

- [Variables out](./csharp-7.md#out-variables)
- [Tuplas y deconstrucción](./csharp-7.md#tuples-and-discards)
- [Coincidencia de patrones](./csharp-7.md#pattern-matching)
- [Funciones locales](./csharp-7.md#local-functions)
- [Miembros con forma de expresión expandidos](./csharp-7.md#more-expression-bodied-members)
- [Devoluciones y variables locales ref](./csharp-7.md#ref-locals-and-returns)

Otras características incluidas:

- [Descartes](./csharp-7.md#tuples-and-discards)
- [Literales binarios y separadores de dígitos](./csharp-7.md#numeric-literal-syntax-improvements)
- [Expresiones throw](./csharp-7.md#throw-expressions)

Todas estas características ofrecen capacidades nuevas e interesantes para los desarrolladores y la posibilidad de escribir un código de manera más clara que nunca. De manera destacada, condensan la declaración de variables que se van a usar con la palabra clave `out` y permiten varios valores devueltos a través de tuplas.

Pero C# se está usando cada vez más. .NET Core ahora tiene como destino cualquier sistema operativo y tiene puesta la mirada en la nube y la portabilidad.  Por supuesto, esas nuevas capacidades ocupan las ideas y el tiempo de los diseñadores de lenguaje, además de ofrecer nuevas características.

## <a name="c-version-71"></a>C# versión 7.1

C# empezó a publicar *versiones de punto* con C# 7.1. Esta versión agregó el elemento de configuración de [selección de versión de lenguaje](../language-reference/configure-language-version.md), tres nuevas características de lenguaje y un nuevo comportamiento del compilador.

Las nuevas características de lenguaje de esta versión son las siguientes:

- [Método `async` `Main`](./csharp-7.md#async-main)
  - El punto de entrada de una aplicación puede tener el modificador `async`.
- [Expresiones literales `default`](./csharp-7.md#default-literal-expressions)
  - Se pueden usar expresiones literales predeterminadas en expresiones de valor predeterminadas cuando el tipo de destino se pueda inferir.
- [Nombres de elementos de tupla inferidos](./csharp-7.md#tuples-and-discards)
  - En muchos casos, los nombres de elementos de tupla se pueden deducir de la inicialización de la tupla.
- [Coincidencia de patrones en parámetros de tipo genérico](./csharp-7.md#pattern-matching)
  - Puede usar expresiones de coincidencia de patrones en variables cuyo tipo es un parámetro de tipo genérico.

Por último, el compilador tiene dos opciones, `-refout` y `-refonly`, que controlan la [generación de ensamblados de referencia](./csharp-7.md#reference-assembly-generation).

## <a name="c-version-72"></a>C# versión 7.2

C#7.2 agregó varias características de lenguaje pequeñas:

- [Técnicas para escribir código eficiente seguro](./csharp-7.md#enabling-more-efficient-safe-code)
  - Una combinación de mejoras en la sintaxis que permiten trabajar con tipos de valor mediante la semántica de referencia.
- [Argumentos con nombre no finales](./csharp-7.md#non-trailing-named-arguments)
  - Los argumentos con nombre pueden ir seguidos de argumentos posicionales.
- [Caracteres de subrayado iniciales en literales numéricos](./csharp-7.md#numeric-literal-syntax-improvements)
  - Los literales numéricos ahora pueden tener caracteres de subrayado iniciales antes de los dígitos impresos.
- [Modificador de acceso `private protected`](./csharp-7.md#private-protected-access-modifier)
  - El modificador de acceso `private protected` permite el acceso de clases derivadas en el mismo ensamblado.
- [Expresiones `ref` condicionales](./csharp-7.md#conditional-ref-expressions)
  - El resultado de una expresión condicional (`?:`) ahora puede ser una referencia.

## <a name="c-version-73"></a>C# versión 7.3

Hay dos temas principales para la versión C# 7.3. Un tema proporciona características que permiten al código seguro ser tan eficaz como el código no seguro. El segundo tema proporciona mejoras incrementales en las características existentes. Además, se han agregado nuevas opciones de compilador en esta versión.

Las siguientes características nuevas admiten el tema del mejor rendimiento para código seguro:

- [Puede acceder a campos fijos sin anclar.](csharp-7.md#indexing-fixed-fields-does-not-require-pinning)
- [Puede reasignar variables locales `ref`.](csharp-7.md#enabling-more-efficient-safe-code)
- [Puede usar inicializadores en matrices `stackalloc`.](csharp-7.md#stackalloc-arrays-support-initializers)
- [Puede usar instrucciones `fixed` con cualquier tipo que admita un patrón.](csharp-7.md#more-types-support-the-fixed-statement)
- [Puede usar restricciones genéricas adicionales.](csharp-7.md#enhanced-generic-constraints)

Se hicieron las mejoras siguientes a las características existentes:

- Puede probar `==` y `!=` con los tipos de tupla.
- Puede usar variables de expresión en más ubicaciones.
- Puede asociar atributos al campo de respaldo de las propiedades autoimplementadas.
- Se ha mejorado la resolución de métodos cuando los argumentos difieren por `in`.
- Ahora, la resolución de sobrecarga tiene menos casos ambiguos.

Las nuevas opciones del compilador son:

- `-publicsign` para habilitar la firma de ensamblados de software de código abierto (OSS).
- `-pathmap` para proporcionar una asignación para los directorios de origen.

## <a name="c-version-80"></a>C# versión 8.0

C# 8.0 es la primera versión C# principal que tiene como destino específicamente .NET Core. Algunas características se basan en nuevas funcionalidades de CLR, otras en tipos de biblioteca agregados solo a .NET Core. C# 8.0 agrega las siguientes características y mejoras al lenguaje C#:

- [Miembros de solo lectura](./csharp-8.md#readonly-members)
- [Métodos de interfaz predeterminados](./csharp-8.md#default-interface-methods)
- [Mejoras de coincidencia de patrones](./csharp-8.md#more-patterns-in-more-places):
  - [Expresiones switch](./csharp-8.md#switch-expressions)
  - [Patrones de propiedades](./csharp-8.md#property-patterns)
  - [Patrones de tupla](./csharp-8.md#tuple-patterns)
  - [Patrones posicionales](./csharp-8.md#positional-patterns)
- [Declaraciones using](./csharp-8.md#using-declarations)
- [Funciones locales estáticas](./csharp-8.md#static-local-functions)
- [Estructuras ref descartables](./csharp-8.md#disposable-ref-structs)
- [Tipos de referencia que aceptan valores null](../language-reference/builtin-types/nullable-reference-types.md)
- [Secuencias asincrónicas](./csharp-8.md#asynchronous-streams)
- [Índices y rangos](./csharp-8.md#indices-and-ranges)
- [Asignación de uso combinado de NULL](./csharp-8.md#null-coalescing-assignment)
- [Tipos construidos no administrados](./csharp-8.md#unmanaged-constructed-types)
- [Stackalloc en expresiones anidadas](./csharp-8.md#stackalloc-in-nested-expressions)
- [Mejora de las cadenas textuales interpoladas](./csharp-8.md#enhancement-of-interpolated-verbatim-strings)

Los miembros de interfaz predeterminados requieren mejoras en CLR. Estas características se agregaron en CLR para .NET Core 3.0. Los intervalos y los índices, y los flujos asincrónicos requieren nuevos tipos en las bibliotecas de .NET Core 3.0. Los tipos de referencia que aceptan valores NULL, aunque se implementan en el compilador, son mucho más útiles cuando se anotan bibliotecas para proporcionar información semántica relativa al estado NULL de los argumentos y los valores devueltos. Esas anotaciones se agregan a las bibliotecas de .NET Core.

_Artículo_ [_publicado originalmente en el blog de NDepend_](https://blog.ndepend.com/c-versions-look-language-history/) _, por cortesía de Erik Dietrich y Patrick Smacchia._
