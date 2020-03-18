---
ms.openlocfilehash: 99153bb9cf3287951a1e52e716c799ee64eb82ad
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "78950990"
---
# <a name="labels-and-projects-roadmap"></a>Hoja de ruta de etiquetas y proyectos

El equipo de documentación de .NET usan mucho las [etiquetas de GitHub](https://github.com/dotnet/docs/labels) para organizar nuestro trabajo. Al filtrar por combinaciones de etiquetas, podemos centrarnos rápidamente en las secciones de interés en el [sitio web de documentación de .NET](https://docs.microsoft.com/dotnet).

También usamos [proyectos de GitHub](https://github.com/dotnet/docs/projects) para organizar sprints y otras epopeyas orientadas a objetivos.

En esta hoja de ruta se explica cómo se usan estas herramientas organizativas y se incluyen vínculos a filtros útiles que se usan para buscar áreas de interés.

## <a name="labels"></a>Etiquetas

Si esta es la primera experiencia en la contribución a [dotnet/docs](https://github.com/dotnet/docs), empiece con las incidencias [up-for-grabs](https://github.com/dotnet/docs/labels/up-for-grabs). Se trata de incidencias que tienen un ámbito más específico. Son una excelente manera de realizar la primera contribución. Desde la vista de up-for-grabs, puede filtrar aún más las incidencias en función de las áreas y la prioridad. Hemos identificado incidencias adecuadas para principiantes con la etiqueta [good-first-issue](https://github.com/dotnet/docs/labels/good-first-issue) (primera incidencia adecuada), en caso de que quiera probar una contribución inicial más pequeña.

Usamos etiquetas para clasificar las incidencias de muchas maneras diferentes:

- [Guías de .NET](#find-a-single-net-guide) y [secciones de una guía](#search-one-section-of-a-guide).
- [Versión de destino](#releases)
- [Prioridad](#priority)

Puede combinar una etiqueta de cada conjunto (guía, versión, prioridad) para crear un enfoque centrado a fin de buscar las incidencias en las que quiere trabajar.

### <a name="find-a-single-net-guide"></a>Búsqueda de una sola guía de .NET

Usamos etiquetas para cada uno de los libros electrónicos de la arquitectura y para cada guía de .NET.

![Guía :book: sobre un fondo de color verde claro](./images/guide.png "Prefijo para etiquetas de guía de arquitectura")

Los libros electrónicos de la arquitectura se anotan con el prefijo `:book: guide` y tienen un fondo de color verde claro. Son las áreas de formato largo que abarcan la arquitectura recomendada. Estas son las incidencias actuales filtradas para cada una de las guías de arquitectura de .NET.

- [Aplicaciones web ASP.NET Core](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20ASP.NET%20Core%20web%20apps)
- [Blazor](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Blazor)
- [Nativa de la nube](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Cloud%20Native)
- [Ciclo de vida de Docker](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Docker%20lifecycle)
- [gRPC](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20gRPC)
- [Modernización con contenedores de Windows](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Modernizing%20w%2F%20Windows%20containers)
- [Microservicios de .NET](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20.NET%20Microservices)
- [Aplicaciones sin servidor](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Serverless%20apps)

Este estilo de etiqueta también se aplica a las [instrucciones de diseño de Framework](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Framework%20Design%20Guidelines). Esta área tiene el mismo diseño de etiqueta, pero no se recomiendan las PR de la comunidad. Se trata de material reimpreso con permiso y no se debe editar.

![Área :books: sobre un fondo de color azul oscuro](./images/area.png "Prefijo para etiquetas de área de guía de .NET")

Cada guía de .NET se anota con el prefijo `:books: Area` y tiene un fondo de color azul oscuro. Estas son las incidencias actuales filtradas para cada una de las guías de .NET.

- [Referencia de API](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20API%20Reference)
- [SDK de .NET para Azure](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20Azure%20.NET%20SDk)
- [Guía de C#](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20C%23%20Guide)
- [Guía de escritorio](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20Desktop%20Guide)
- [Guía de F#](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20F%23%20Guide)
- [Guía de ML.NET](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20ML.NET%20Guide)
- [Guía de arquitectura de .NET](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20.NET%20Architecture%20Guide): se puede quitar
- [Guía de .NET Core](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20.NET%20Core%20Guide)
- [Guía de .NET para Apache Spark](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20.NET%20for%20Apache%20Spark%20Guide)
- [Guía de .NET Framework](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20.NET%20Framework%20Guide)
- [Guía de .NET](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20.NET%20Guide)
- [Referencia de API de Roslyn](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20Roslyn%20API%20Reference): se puede quitar.
- [Guía de Visual Basic](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20Visual%20Basic%20Guide)

#### <a name="search-one-section-of-a-guide"></a>Búsqueda de una sección de una guía

![Área :card_file_box: sobre un fondo de color azul medio](./images/technology.png "Prefijo para etiquetas de subárea de guía de .NET")

Las guías de .NET son grandes, por lo que estas etiquetas limitan aún más el ámbito a una sección de una guía. Cada subárea de guía de .NET se anota con el prefijo `:card_file_box: Technology` y tiene un fondo de color azul medio. Muchas de estas etiquetas se aplican a varias guías, mientras que otras se encuentran en una sola. Después de filtrar por un área, agregue una de estas etiquetas para limitar todavía más el ámbito de las incidencias.

- AppCompat
- Tarea asincrónica
- Conceptos avanzados de C#
- Compilador de C#
- Aspectos básicos de C#
- Introducción a C#
- Referencia del lenguaje C#
- Seguridad de tipos NULL en C#
- Novedades de C#
- CLI
- Acceso a datos en ASP.NET (Visual Studio)
- Docker
- Instaladores
- LINQ
- NCL
- .NET Standard
- API de Roslyn
- Seguridad
- WCF
- WF
- WIF
- WinForms
- WPF

### <a name="releases"></a>Versiones

![:checkered_flag: Versión: en color amarillo oscuro](./images/release.png "Prefijo para etiquetas de versión")

Las incidencias etiquetadas para una versión específica se anotan con el prefijo `:checkered_flag: Release:` y tienen un fondo de color amarillo oscuro.

- .NET Core 2.2
- .NET Core 3.0

### <a name="priority"></a>Prioridad

Todas las etiquetas de prioridad son `P`, seguidas de un solo dígito. Los números más bajos son de mayor prioridad:

- P0
- P1
- P2

### <a name="what-about-the-other-labels"></a>¿Y las otras etiquetas?

Los equipos de contenido usan muchas otras etiquetas para administrar distintas clasificaciones de incidencias. Si no está en el equipo de contenido, puede omitir estas otras etiquetas.

## <a name="projects"></a>Proyectos

Los colaboradores deben comprobar los [Proyectos para colaboradores de la comunidad .NET](https://github.com/dotnet/docs/projects/35). Hemos creado columnas diferentes para el mantenimiento, las actualizaciones de documentos y las nuevas tareas de contenido. Puede ser una manera de buscar tareas de interés. (Tenga en cuenta que la vista de proyecto se puede filtrar con las etiquetas descritas antes).

También usamos proyectos de otras dos maneras:

- Tipos de proyecto AAAA mensuales: se trata de paneles de tareas para el plan de trabajo de cada mes.
- Epopeyas de larga duración: se usan para organizar las tareas hacia un objetivo cuando el trabajo se realizará durante varios meses.
