---
title: Microservicios de .NET. Arquitectura para aplicaciones .NET en contenedor
description: Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Los microservicios son servicios modulares que se pueden implementar de forma independiente. Los contenedores de Docker (para Linux y Windows) simplifican la implementación y las pruebas mediante la unión de un servicio y sus dependencias en una sola unidad que, después, se ejecuta en un entorno aislado.
ms.date: 02/02/2021
ms.openlocfilehash: e9862445414dbe0bf9a1c5d36d790b57710028f0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99665318"
---
# <a name="net-microservices-architecture-for-containerized-net-applications"></a>Microservicios de .NET: Arquitectura para aplicaciones .NET en contenedor

![Portada del libro](./media/cover-large.png)

**EDICIÓN v5.0**: actualizada a ASP.NET Core 5.0

Consulte el [registro de cambios](https://aka.ms/MicroservicesEbookChangelog) para ver las modificaciones del libro y las colaboraciones para la comunidad.

Esta guía es una introducción al desarrollo de aplicaciones basadas en microservicios y a su administración mediante contenedores. En ella se trata el diseño de la arquitectura y los métodos de implementación con .NET 5 y contenedores de Docker.

Para que sea más fácil empezar a trabajar, la guía se centra en una aplicación de referencia en contenedor y basada en microservicios que puede explorar. La aplicación de referencia está disponible en el repositorio de GitHub [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers).

## <a name="action-links"></a>Vínculos de acción

- Este libro electrónico también está disponible en formato PDF (solo versión en inglés) [Descargar](https://aka.ms/microservicesebook)

- Clone o bifurque la aplicación de referencia [eShopOnContainers en GitHub](https://github.com/dotnet-architecture/eShopOnContainers)

- Vea el [vídeo de introducción en Channel 9](https://aka.ms/microservices-video)

- Conozca la [arquitectura de microservicios](https://aka.ms/MicroservicesArchitecture) inmediatamente

## <a name="introduction"></a>Introducción

Las empresas cada vez ahorran más costos, resuelven más problemas de implementación y mejoran más las operaciones de DevOps y producción mediante el uso de contenedores. Microsoft ha lanzado recientemente innovaciones en los contenedores de Windows y Linux con la creación de productos como Azure Kubernetes Service y Azure Service Fabric, contando además con la colaboración de líderes del sector como Docker, Mesosphere y Kubernetes. Estos productos ofrecen soluciones de contenedores que ayudan a las empresas a compilar e implementar aplicaciones a velocidad y escala de nube, sea cual sea la plataforma o las herramientas que hayan elegido.

Docker se está convirtiendo en el estándar de facto del sector de los contenedores, ya que es compatible con los proveedores más importantes del ecosistema de Windows y Linux. (Microsoft es uno de los principales proveedores de nube que admite Docker). En el futuro, Docker probablemente estará omnipresente en todos los centros de datos en la nube o locales.

Además, la arquitectura de [microservicios](https://martinfowler.com/articles/microservices.html) se está convirtiendo en un enfoque fundamental para las aplicaciones críticas distribuidas. En una arquitectura basada en microservicios, la aplicación se basa en una colección de servicios que se pueden desarrollar, probar, implementar y versionar por separado.

## <a name="about-this-guide"></a>Acerca de esta guía

Esta guía es una introducción al desarrollo de aplicaciones basadas en microservicios y a su administración mediante contenedores. En ella se trata el diseño de la arquitectura y los métodos de implementación con .NET 5 y contenedores de Docker. Para que sea más fácil empezar a trabajar con contenedores y microservicios, la guía se centra en una aplicación de referencia en contenedor y basada en microservicios que puede explorar. Esta misma aplicación de ejemplo está disponible en el repositorio de GitHub [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers).

Esta guía incluye el desarrollo fundamental y una guía de arquitectura principalmente en el nivel del entorno de desarrollo con especial hincapié en dos tecnologías: Docker y .NET. Nuestra intención es que lea esta guía cuando reflexione sobre el diseño de las aplicaciones sin centrarse en la infraestructura (en la nube o local) de su entorno de producción. Tomará decisiones sobre la infraestructura más adelante, cuando cree aplicaciones listas para la producción. Por lo tanto, esta guía está diseñada para ser independiente de la infraestructura y centrarse en el desarrollo y el entorno.

Una vez que haya estudiado esta guía, el siguiente paso que debería dar es obtener información sobre los microservicios listos para la producción en Microsoft Azure.

## <a name="version"></a>Versión

Esta guía se ha revisado para abarcar la versión **.NET 5** junto con muchas actualizaciones adicionales relacionadas con la misma "oleada" de tecnologías (es decir, Azure y otras tecnologías de terceros) que coincidan en el tiempo con la versión de .NET 5. Este es el motivo por el que la versión del libro se ha actualizado también a la versión **5.0**.

## <a name="what-this-guide-does-not-cover"></a>Aspectos no tratados en esta guía

Esta guía no se centra en el ciclo de vida de la aplicación, DevOps, las canalizaciones CI/CD ni el trabajo de equipo. La guía complementaria [Containerized Docker Application Lifecycle with Microsoft Platform and Tools](https://aka.ms/dockerlifecycleebook) (Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y herramientas de Microsoft) se centra en esas cuestiones. La guía actual tampoco proporciona detalles de implementación de la infraestructura de Azure, como información sobre orquestadores específicos.

### <a name="additional-resources"></a>Recursos adicionales

- **Containerized Docker Application Lifecycle with Microsoft Platform and Tools** (Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y las herramientas de Microsoft; libro electrónico descargable)  
    <https://aka.ms/dockerlifecycleebook>

## <a name="who-should-use-this-guide"></a>Destinatarios de esta guía

Esta guía se ha escrito para desarrolladores y arquitectos de soluciones que no están familiarizados con el desarrollo de aplicaciones basado en Docker y la arquitectura basada en microservicios. Esta guía será de su interés si quiere obtener información sobre cómo crear arquitecturas, diseñar e implementar aplicaciones de prueba de concepto con tecnologías de desarrollo de Microsoft (con un hincapié especial en .NET) y con contenedores de Docker.

También le resultará útil si es el responsable de tomar decisiones técnicas (por ejemplo, un arquitecto empresarial) y necesita una descripción de la arquitectura y la tecnología antes de decidir qué enfoque tomar para el diseño de aplicaciones distribuidas tanto nuevas como modernas.

### <a name="how-to-use-this-guide"></a>Cómo usar esta guía

La primera parte de esta guía presenta los contenedores de Docker, describe cómo elegir entre .NET 5 y .NET Framework como marco de desarrollo y proporciona una visión general de los microservicios. Este contenido está destinado a arquitectos y responsables de la toma de decisiones técnicas que quieren obtener información general pero que no necesitan centrarse en los detalles de la implementación de código.

La segunda parte de la guía comienza con la sección [Proceso de desarrollo de aplicaciones basadas en Docker](./docker-application-development-process/index.md). Se centra en los patrones de desarrollo y microservicios empleados en la implementación de aplicaciones que usan .NET y Docker. Esta sección será de gran interés para los desarrolladores y los arquitectos que quieran centrarse en el código, en los patrones y los detalles de implementación.

## <a name="related-microservice-and-container-based-reference-application-eshoponcontainers"></a>Aplicación de referencia relacionada de microservicios y basada en contenedor: eShopOnContainers

La aplicación eShopOnContainers es una aplicación de referencia de código abierto para .NET y microservicios que está diseñada para implementarse mediante contenedores de Docker. La aplicación consta de varios subsistemas, incluidos varios front-end de interfaz de usuario de almacén electrónico (una aplicación web de MVC, una SPA web y una aplicación móvil nativa). También incluye microservicios y contenedores de back-end para todas las operaciones del lado servidor necesarias.

El propósito de la aplicación es presentar patrones arquitectónicos. **NO SE TRATA DE UNA PLANTILLA LISTA PARA PRODUCCIÓN** para iniciar aplicaciones del mundo real. De hecho, la aplicación se encuentra en un estado beta permanente, ya que también se usa para probar nuevas tecnologías potencialmente interesantes a medida que aparecen.

## <a name="send-us-your-feedback"></a>Envíenos sus comentarios.

Hemos creado esta guía para ayudarle a entender la arquitectura de aplicaciones y microservicios en contenedor en .NET. La guía y la aplicación de referencia relacionada irán evolucionando, por lo que le agradecemos sus comentarios. Si tiene comentarios sobre cómo se puede mejorar esta guía, envíelos a <https://aka.ms/ebookfeedback>.

## <a name="credits"></a>Créditos

Coautores:

> **Cesar de la Torre**, administrador de programas sénior del equipo de producto de .NET, Microsoft Corp.
>
> **Bill Wagner**, desarrollador de contenido sénior de C+E, Microsoft Corp.
>
> **Mike Rousos**, ingeniero de software principal del equipo de CAT de la división de desarrollo, Microsoft

Editores:

> **Mike Pope**
>
> **Steve Hoag**

Participantes y revisores:

> **Jeffrey Richter**, ingeniero de software asociado del equipo de Azure, Microsoft
>
> **Jimmy Bogard**, arquitecto jefe de Headspring
>
> **Udi Dahan**, fundador y director general de Particular Software
>
> **Jimmy Nilsson**, cofundador y director general de Factor10
>
> **Glenn Condron**, director de programas sénior del equipo de ASP.NET
>
> **Mark Fussell**, responsable principal de administración de programas del equipo de Azure Service Fabric, Microsoft
>
> **Diego Vega**, responsable de administración de programas del equipo de Entity Framework, Microsoft
>
> **Barry Dorrans**, director de programas de seguridad sénior
>
> **Rowan Miller**, director de programas sénior, Microsoft
>
> **Ankit Asthana**, director principal de administración de programas del equipo de .NET, Microsoft
>
> **Scott Hunter**, director asociado de administración de programas del equipo de .NET, Microsoft
>
> **Nish Anil**, director de administración de programas, equipo de .NET, Microsoft
>
> **Dylan Reisenberger**, arquitecto y responsable de desarrollo de Polly
>
> **Steve "ardalis" Smith**: instructor y arquitecto de software de [Ardalis.com](https://ardalis.com)
>
> **Cooper Ian**, arquitecto de codificación de Brighter
>
> **Unai Zorrilla**, arquitecto y responsable de desarrollo de Plain Concepts
>
> **Eduard Tomas**, responsable de desarrollo de Plain Concepts
>
> **Ramon Tomas**, desarrollador de Plain Concepts
>
> **David Sanz**, desarrollador de Plain Concepts
>
> **Javier Valero**, director de operaciones de Grupo Solutio
>
> **Pierre Millet**, consultor sénior, Microsoft
>
> **Michael Friis**, administrador de productos de Docker Inc.
>
> **Charles Lowell**, ingeniero de software del equipo de CAT de VS, Microsoft
>
> **Miguel Veloso**, ingeniero de desarrollo de software en Plain Concepts
>
> **Sumit Ghosh**, asesor principal en Neudesic

## <a name="copyright"></a>Copyright

PUBLICADO POR

Equipos de producto de la División de desarrolladores de Microsoft, .NET y Visual Studio

División de Microsoft Corporation

One Microsoft Way

Redmond, Washington 98052-6399

Copyright © 2021 de Microsoft Corporation

Todos los derechos reservados. No se puede reproducir ni transmitir de ninguna forma ni por ningún medio ninguna parte del contenido de este libro sin la autorización por escrito del publicador.

Este libro se proporciona “tal cual” y expresa las opiniones del autor. Las opiniones y la información expresados en este libro, incluidas las direcciones URL y otras referencias a sitios web de Internet, pueden cambiar sin previo aviso.

Algunos ejemplos descritos aquí se proporcionan únicamente con fines ilustrativos y son ficticios. No debe deducirse ninguna asociación ni conexión reales.

Microsoft y las marcas comerciales indicadas en <https://www.microsoft.com> en la página web "Marcas comerciales" pertenecen al grupo de empresas de Microsoft.

Mac y macOS son marcas comerciales de Apple Inc.

El logotipo de la ballena de Docker es una marca registrada de Docker, Inc. Se usa con permiso.

El resto de marcas y logotipos pertenece a sus respectivos propietarios.

>[!div class="step-by-step"]
>[Siguiente](container-docker-introduction/index.md)
