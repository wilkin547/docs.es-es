---
title: SDK de .NET Compiler Platform (API de Roslyn)
description: Aprenda a usar el SDK de .NET Compiler Platform (también denominado API de Roslyn) para comprender el código. NET, detectar errores y corregir dichos errores.
ms.date: 10/10/2017
ms.custom: mvc
ms.openlocfilehash: a1ceb1d11cf846e67be2c6558978e01133e591da
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "76742743"
---
# <a name="the-net-compiler-platform-sdk"></a>SDK de .NET Compiler Platform

Los compiladores crean un modelo detallado de código de aplicación a medida que validan la sintaxis y semántica de ese código. Utilizan este modelo para generar la salida ejecutable desde el código fuente. El SDK de .NET Compiler Platform proporciona acceso a este modelo. Cada vez confiamos más en las características del entorno de desarrollo integrado (IDE), como IntelliSense, la refactorización, el cambio de nombre inteligente, "Buscar todas las referencias" e "Ir a definición" para aumentar la productividad. Nos basamos en herramientas de análisis de código para mejorar la calidad de nuestro código y en generadores de código para ayudar en la construcción de la aplicación. A medida que la inteligencia de estas herramientas aumenta, cada vez necesitan más acceso del modelo que solo los compiladores crean cuando procesan el código de la aplicación. Se trata de la misión principal de las API de Roslyn: abrir las cajas negras y permitir a las herramientas y a los usuarios finales compartir en la gran cantidad de información que los compiladores tienen sobre nuestro código.
En lugar de traductores opacos de entrada de código fuente y salida de código objeto, a través de Roslyn, los compiladores se convierten en plataformas: las API que puede usar para tareas relacionadas con el código en las herramientas y aplicaciones.

## <a name="net-compiler-platform-sdk-concepts"></a>Conceptos del SDK de .NET Compiler Platform

El SDK de .NET Compiler Platform reduce notablemente la barrera de entrada para crear herramientas y aplicaciones centradas en código. Crea numerosas oportunidades para la innovación en áreas como la metaprogramación, la generación y la transformación de código, el uso interactivo de los lenguajes C# y Visual Basic, y la inserción de C# y Visual Basic en lenguajes específicos del dominio.

El SDK de .NET Compiler Platform le permite crear ***analizadores*** y ***correcciones de código*** que buscan y corrigen errores de codificación. Los ***analizadores*** comprenden la sintaxis y la estructura del código y detectan las prácticas que se deben corregir. Las ***correcciones de código*** sugieren una o varias correcciones para tratar los errores de codificación que los analizadores encuentran. Por lo general, un analizador y las correcciones de código asociadas se empaquetan conjuntamente en un solo proyecto.

Los analizadores y las correcciones de código usan el análisis estático para comprender el código. No ejecutan el código o proporcionan otras ventajas de pruebas. Sin embargo, pueden señalar prácticas que suelen dar lugar a errores, código que no se puede mantener o validación de guías estándar.

El SDK de .NET Compiler Platform proporciona un único conjunto de API que le permite examinar y entender un código base de C# o Visual Basic. Dado que puede usar este código base único, puede escribir analizadores y correcciones de código más fácilmente aprovechando las API de análisis sintáctico y semántico que proporciona el SDK de .NET Compiler Platform. Una vez liberado de la ardua tarea de replicar el análisis realizado por el compilador, puede concentrarse en la tarea más específica de encontrar y corregir errores de codificación comunes para el proyecto o la biblioteca.

Una ventaja menor es que los analizadores y las correcciones de código son más pequeños y usan muchos menos memoria cuando se cargan en Visual Studio que si escribiera su propio código base para entender el código de un proyecto. Aprovechando las mismas clases que usa el compilador y Visual Studio, puede crear sus propias herramientas de análisis estático. Esto significa que el equipo puede usar los analizadores y las correcciones de código sin un impacto perceptible en el rendimiento del IDE.

Hay tres escenarios principales para escribir analizadores y correcciones de código:

1. [*Aplicar estándares de codificación de equipo*](#enforce-team-coding-standards)
1. [*Proporcionar instrucciones con paquetes de biblioteca*](#provide-guidance-with-library-packages)
1. [*Suministro de una guía general*](#provide-general-guidance)

## <a name="enforce-team-coding-standards"></a>Aplicación de estándares de codificación de equipo

Muchos equipos tienen estándares de codificación que se aplican a través de revisiones del código con otros miembros del equipo. Los analizadores y las correcciones de código pueden hacer este proceso mucho más eficiente. Las revisiones de código se producen cuando un desarrollador comparte su trabajo con otros usuarios en el equipo. Dicho desarrollador habrá invertido todo el tiempo necesario para completar una nueva característica antes de obtener los comentarios. Pueden pasar semanas mientras que refuerza los hábitos que no coinciden con las prácticas del equipo.

Los analizadores se ejecutan a medida que un desarrollador escribe código. Obtiene comentarios al instante que animan a seguir la guía de inmediato. Crea hábitos para escribir código compatible tan pronto como comienza la creación de prototipos. Cuando la característica está lista para que las personas la revisen, se habrá aplicado toda la guía estándar.

Los equipos pueden crear analizadores y correcciones de código que busquen las prácticas más comunes que infringen las prácticas de codificación del equipo. Se pueden instalar en el equipo del desarrollador para aplicar los estándares.

## <a name="provide-guidance-with-library-packages"></a>Suministro de instrucciones con paquetes de biblioteca

Hay una gran cantidad de bibliotecas disponibles para los desarrolladores de .NET en NuGet.
Algunos de ellas proceden de Microsoft, algunas de compañías de terceros y otras de voluntarios y miembros de la comunidad. Estas bibliotecas consiguen más adopción y revisiones superiores cuando los desarrolladores pueden tener éxito con ellas.

Además de proporcionar documentación, puede proporcionar analizadores y correcciones de código que busquen y corrijan los usos incorrectos habituales de la biblioteca. Estas correcciones inmediatas ayudarán a los desarrolladores a tener éxito más rápidamente.

Puede empaquetar los analizadores y las correcciones de código con la biblioteca en NuGet. En ese escenario, todos los desarrolladores que instalan el paquete de NuGet también instalarán el paquete de analizador. Todos los programadores que utilicen la biblioteca obtendrán instrucciones de su equipo al instante en forma de comentarios inmediatos sobre errores y correcciones sugeridas.

## <a name="provide-general-guidance"></a>Suministro de una guía general

La comunidad de desarrolladores de .NET ha detectado patrones de experiencia que funcionan bien y patrones que es mejor evitar. Varios miembros de la comunidad han creado analizadores que aplican esos patrones recomendados. A medida que aprendemos más, siempre hay espacio para nuevas ideas.

Estos analizadores se puedan cargar en [Visual Studio Marketplace](https://marketplace.visualstudio.com/vs) y los desarrolladores los pueden descargar mediante Visual Studio. Los recién llegados al lenguaje y a la plataforma aprenden rápidamente las prácticas aceptadas y consiguen ser productivos antes en su recorrido por .NET. A medida que su uso se amplía, la comunidad adopta estas prácticas.

## <a name="next-steps"></a>Pasos siguientes

El SDK de .NET Compiler Platform incluye los modelos de objetos de idioma más recientes para generación de código, análisis y refactorización. Esta sección proporciona información general conceptual del SDK de .NET Compiler Platform. Encontrará más detalles en las secciones de guías de inicio rápido, ejemplos y tutoriales.

Puede obtener más información sobre los conceptos del SDK de .NET Compiler Platform en estos cinco temas:

- [Exploración de código con el visualizador de sintaxis](syntax-visualizer.md)
- [Entender el modelo de API de compilador](compiler-api-model.md)
- [Trabajar con sintaxis](work-with-syntax.md)
- [Trabajar con semántica](work-with-semantics.md)
- [Trabajar con un área de trabajo](work-with-workspace.md)

Para empezar, debe instalar el **SDK de .NET Compiler Platform**:

[!INCLUDE[interactive-note](~/includes/roslyn-installation.md)]

<!--

Turn this on as more of the conceptual content is in place:
- Try the [Quickstarts](quickstart/index.md) to create your first tutorial.
- Experiment with one of the [Tutorials](tutorials/index.md).
- Explore the [Samples](samples/index.md) to see some simple analyzers.
- Read the [Concepts](concepts/index.md) to understand the ideas behind analyzers and code fixes.

-->
