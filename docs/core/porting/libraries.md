---
title: Traslado de bibliotecas a .NET Core
description: Obtenga información sobre cómo portar proyectos de .NET Framework a .NET Core.
author: cartermp
ms.date: 12/07/2018
ms.openlocfilehash: 646587120de2e51280c2af4de36bf3a6b0f60c2d
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920609"
---
# <a name="port-net-framework-libraries-to-net-core"></a>Traslado de bibliotecas de .NET Framework a .NET Core

Obtenga información sobre cómo trasladar el código de biblioteca de .NET Framework a .NET Core para ejecutar como multiplataforma y ampliar el ámbito de las aplicaciones que lo usan.

## <a name="prerequisites"></a>Requisitos previos

En este artículo se asume lo siguiente:

- Se usa Visual Studio 2017 o posterior. .NET Core no es compatible con versiones anteriores de Visual Studio.
- Se conoce el [proceso de portabilidad recomendado](index.md).
- Se han resuelto los problemas con las [dependencias de terceros](third-party-deps.md).

También debe estar familiarizado con el contenido de los artículos siguientes:

[Estándar .NET](../../standard/net-standard.md)\
En este artículo se describe la especificación formal de las API de .NET que se prevé que estén disponibles en todas las implementaciones de .NET.

[Paquetes, metapaquetes y marcos de trabajo](../packages.md)\
En este artículo se trata cómo .NET Core define y usa paquetes y cómo los paquetes admiten el código que se ejecuta en varias implementaciones de .NET.

[Desarrollo de bibliotecas con herramientas multiplataforma](../tutorials/libraries.md)\
En este artículo se explica cómo escribir bibliotecas con la CLI de .NET Core.

[Adiciones al formato *csproj* para .NET Core](../tools/csproj.md)\
En este artículo se describen los cambios que se han agregado al archivo de proyecto como parte del cambio a *csproj* y MSBuild.

[Migración a .NET Core - Análisis de las dependencias de terceros](third-party-deps.md)\
En este artículo se trata la portabilidad de dependencias de terceros y qué hacer cuando una dependencia de paquetes de NuGet no se ejecuta en .NET Core.

## <a name="retarget-to-net-framework-472"></a>Redestinar a .NET Framework 4.7.2

Si el código no apunta a .NET Framework 4.7.2, se recomienda que lo redestine a esta plataforma. De esta forma, se garantiza la disponibilidad de las últimas alternativas de API en los casos donde el estándar .NET no admite las API existentes.

Haga lo siguiente para cada uno de los proyectos de Visual Studio que desea trasladar:

1. Haga clic con el botón derecho en el proyecto y seleccione **Propiedades**.
1. En la lista desplegable **Plataforma de destino**, seleccione **.NET Framework 4.7.2**.
1. Compile de nuevo el proyecto.

Debido a que sus proyectos ahora apuntan a .NET Framework 4.7.2, use esa versión de .NET Framework como la base para portar el código.

## <a name="determine-portability"></a>Determinar la portabilidad

El paso siguiente es ejecutar API Portability Analyzer (ApiPort), a fin de generar un informe de portabilidad para analizarlo.

Asegúrese de que comprende la herramienta [API Portability (ApiPort)](../../standard/analyzers/portability-analyzer.md) y de que puede generar informes de portabilidad que apunten a .NET Core. La forma de hacer esto posiblemente variará en función de sus necesidades y de sus preferencias personales. En las secciones siguientes se detallan algunos enfoques diferentes. Es probable que tenga que combinar los pasos de estos enfoques en función de cómo esté estructurado el código.

### <a name="deal-primarily-with-the-compiler"></a>Trabajar primero con el compilador

Este enfoque funciona bien con proyectos pequeños o proyectos que no usan muchas API de .NET Framework. El enfoque es sencillo:

1. De manera opcional, ejecute ApiPort en el proyecto. Si ejecuta ApiPort, consulte el informe para obtener información sobre los problemas que encontrará.
1. Copie todo el código a un nuevo proyecto de .NET Core.
1. Mientras consulta el informe de portabilidad (en caso de que se haya generado), solucione los errores del compilador hasta que el proyecto esté totalmente compilado.

Aunque no está estructurado, este enfoque centrado en el código suele resolver problemas rápidamente. Un proyecto que solo contiene modelos de datos puede ser un candidato ideal para este enfoque.

### <a name="stay-on-the-net-framework-until-portability-issues-are-resolved"></a>Permanecer en .NET Framework hasta solucionar los problemas de portabilidad

Este puede ser el mejor enfoque si prefiere que el código se compile durante todo el proceso. El enfoque es el siguiente:

1. Ejecute ApiPort en un proyecto.
1. Use distintas API portátiles para solucionar los problemas.
1. Anote todas las áreas en las que no se permite usar una alternativa directa.
1. Repita los pasos anteriores para todos los proyectos que desea trasladar hasta tener la seguridad de haber copiado cada uno de ellos a un proyecto nuevo de .NET Core.
1. Copie el código a un nuevo proyecto de .NET Core.
1. Solucione todos los problemas en los que se indica que no existe una alternativa directa.

Este enfoque prudente es más estructurado que simplemente solucionar los errores del compilador, pero de todos modos está relativamente centrado en el código y tiene la ventaja de que siempre hay código que se puede compilar. La manera en que puede solucionar ciertos problemas que no se podrían solucionar si solo se usa otra API varía considerablemente. Es posible que deba desarrollar un plan más integral para ciertos proyectos, un aspecto que se abarca en el enfoque siguiente.

### <a name="develop-a-comprehensive-plan-of-attack"></a>Desarrollar un plan integral de ataque

Este puede ser el mejor enfoque para proyectos de mayor tamaño y más complejos, en los que puede ser necesario volver a estructurar el código o reescribir ciertas áreas de código por completo para admitir .NET Core. El enfoque es el siguiente:

1. Ejecute ApiPort en un proyecto.
1. Observe dónde se usa cada tipo no portátil y cómo ese uso afecta a la portabilidad general.
   - Comprenda la naturaleza de esos tipos. ¿Son pocos, pero se usan con frecuencia? ¿Son muchos, pero no se usan con frecuencia? ¿Se usan de manera concentrada o se distribuyen en todo el código?
   - ¿Es simple aislar código no portátil para poder trabajar con él con más eficacia?
   - ¿Es necesario refactorizar el código?
   - En el caso de los tipos no portátiles, ¿existen API alternativas que permitan realizar la misma tarea? Por ejemplo, si usa la clase <xref:System.Net.WebClient>, es posible que, en lugar de esta, pueda usar la clase <xref:System.Net.Http.HttpClient>.
   - ¿Hay API portátiles distintas disponibles para realizar una tarea, incluso si no se trata de un reemplazo? Por ejemplo, si usa <xref:System.Xml.Schema.XmlSchema> para analizar un archivo XML, pero no necesita la detección de esquemas XML, puede usar las API <xref:System.Xml.Linq> e implementar el análisis por su cuenta en lugar de depender de una API.
1. Si tiene ensamblados difíciles de trasladar, ¿debe pensarse en dejarlos en .NET Framework por ahora? Algunos aspectos que debe considerar:
   - Puede que en la biblioteca tenga alguna funcionalidad no compatible con .NET Core, porque depende demasiado de la funcionalidad específica de Windows o específica de .NET Framework. ¿Debe considerarse la posibilidad de dejar atrás esa funcionalidad por ahora y lanzar una versión temporal para .NET Core de la biblioteca con menos características, hasta que haya recursos disponibles para portar las características?
   - ¿Sería útil una refactorización en este caso?
1. ¿Es razonable escribir su propia implementación de una API de .NET Framework no disponible?
   Podría considerar copiar, modificar y usar código del [código fuente de referencia de .NET Framework](https://github.com/Microsoft/referencesource). El código fuente de referencia está sujeto a la [licencia de MIT](https://github.com/Microsoft/referencesource/blob/master/LICENSE.txt), por lo que tiene plena libertad para usar la fuente como base para su propio código. Solo debe asegurarse de atribuir adecuadamente la propiedad de Microsoft en el código.
1. Repita este proceso las veces que sea necesario para proyectos distintos.
 
La fase de análisis puede tardar un poco en función del tamaño de la base de código. Dedicar tiempo en esta fase a comprender profundamente el ámbito de los cambios que se necesitan y para desarrollar un plan suele ahorrarle tiempo a largo plazo, principalmente si tiene una base de código compleja.

El plan podría significar realizar cambios importantes en la base de código mientras se sigue apuntando a .NET Framework 4.7.2, lo que hace que esta sea una versión más estructurada del enfoque anterior. La forma de ejecutar el plan depende de la base de código.

### <a name="mixed-approach"></a>Enfoque mixto

Es probable que vaya a combinar los enfoques anteriores en función de cada proyecto. Debe hacer lo que corresponda para usted y su base de código.

## <a name="port-your-tests"></a>Portar las pruebas

La mejor forma de asegurarse de que todo funciona correctamente cuando traslada el código es probarlo mientras lo traslada a .NET Core. Para ello, debe usar un marco de pruebas que compila y ejecuta pruebas para .NET Core. Actualmente tiene 3 opciones:

- [xUnit](https://xunit.github.io/)
  - [Introducción](https://xunit.github.io/docs/getting-started-dotnet-core.html)
  - [Herramienta para convertir un proyecto MSTest en xUnit](https://github.com/dotnet/codeformatter/tree/master/src/XUnitConverter)
- [NUnit](https://nunit.org/)
  - [Introducción](https://github.com/nunit/docs/wiki/Installation)
  - [Entrada de blog sobre la migración de MSTest a NUnit.](https://www.florian-rappl.de/News/Page/275/convert-mstest-to-nunit)
- [MSTest](/visualstudio/test/unit-test-basics)

## <a name="recommended-approach"></a>Enfoque recomendado

En última instancia, el esfuerzo de portabilidad depende significativamente de la estructura del código .NET Framework. Una forma conveniente de portar el código consiste en comenzar por la *base* de la biblioteca, que son los componentes fundamentales del código. Pueden ser los modelos de datos u otras clases y métodos fundamentales que todo lo demás usa directa o indirectamente.

1. Porte el proyecto de prueba que comprueba el nivel de la biblioteca cuya portabilidad se está realizando actualmente.
1. Copie la base de la biblioteca en un nuevo proyecto .NET Core y seleccione la versión del estándar .NET que desea admitir.
1. Haga los cambios necesarios para la compilación del código. Muchas de estas acciones pueden requerir agregar dependencias del paquete NuGet al archivo *csproj*.
1. Ejecute las pruebas y haga los ajustes que sean necesarios.
1. Elija el nivel de código siguiente que se va a portar y repita los pasos anteriores.

Si empieza por la base de la biblioteca y avanza a partir de ella para probar cada nivel según sea necesario, la portabilidad es un proceso sistemático en el que se aíslan los problemas a un nivel de código a la vez.

## <a name="next-steps"></a>Pasos siguientes

>[!div class="nextstepaction"]
>[Organización de proyectos para .NET Core](project-structure.md)
