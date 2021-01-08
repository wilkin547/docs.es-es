---
title: Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y las herramientas de Microsoft
description: Obtenga información general de alto nivel del proceso de desarrollo e implementación para desarrollar e implementar aplicaciones en contenedores con la plataforma y las herramientas de Microsoft y Docker.
ms.date: 01/06/2021
ms.openlocfilehash: 94c277e349bacee9b9fc7b160043005dd4135958
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970120"
---
# <a name="containerized-docker-application-lifecycle-with-microsoft-platform-and-tools"></a>Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y las herramientas de Microsoft

![Portada del libro](./media/devops-book-cover-large-we.png)

**EDICIÓN v5.0**: actualizada a ASP.NET Core 5.0

Consulte el [registro de cambios](https://aka.ms/DockerLifecycleEbookChangelog) para ver las modificaciones del libro y las colaboraciones para la comunidad.

En esta guía se incluye información general para desarrollar e implementar aplicaciones ASP.NET Core en contenedores con Docker, mediante la plataforma y las herramientas de Microsoft. En ella también se incluye una presentación de alto nivel de Azure DevOps, a fin de implementar canalizaciones de CI/CD, así como Azure Container Registry (ACR) y Azure Kubernetes Services (AKS) para la implementación.

Para obtener detalles de bajo nivel relacionados con el desarrollo, puede ver la guía [Microservicios de .NET: Arquitectura para aplicaciones .NET en contenedor](../microservices/index.md) y su aplicación de referencia relacionada, [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers).

## <a name="send-us-your-feedback"></a>Envíenos sus comentarios.

Hemos creado esta guía para ayudarle a entender la arquitectura de aplicaciones y microservicios en contenedor en .NET. La guía y la aplicación de referencia relacionada irán evolucionando, por lo que le agradecemos sus comentarios. Si tiene comentarios sobre cómo se puede mejorar esta guía, envíelos a <https://aka.ms/ebookfeedback>.

## <a name="credits"></a>Créditos

Autor:

> **Cesar de la Torre**, administrador de programas sénior del equipo de producto de .NET, Microsoft Corp.

Editor de adquisiciones:

> **Janine Patrick**

Editor de desarrollo:

> **Bob Russell**, profesional de soluciones en Microsoft
>
> [**Octal Publishing, Inc.**](http://www.octalpub.com/)

Producción editorial:

> [Dianne Russell](http://www.octalpub.com/)
>
> **Octal Publishing, Inc.**

Revisor:

> **Bob Russell**, profesional de soluciones en Microsoft

Participantes y revisores:

> **Nish Anil**, director de administración de programas, equipo de .NET, Microsoft
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

Copyright &copy; 2021 de Microsoft Corporation

Todos los derechos reservados. No se puede reproducir ni transmitir de ninguna forma ni por ningún medio ninguna parte del contenido de este libro sin la autorización por escrito del publicador.

Este libro se proporciona “tal cual” y expresa las opiniones del autor. Las opiniones y la información expresados en este libro, incluidas las direcciones URL y otras referencias a sitios web de Internet, pueden cambiar sin previo aviso.

Algunos ejemplos descritos aquí se proporcionan únicamente con fines ilustrativos y son ficticios. No debe deducirse ninguna asociación ni conexión reales.

Microsoft y las marcas comerciales indicadas en <https://www.microsoft.com> en la página web "Marcas comerciales" pertenecen al grupo de empresas de Microsoft.

Mac y macOS son marcas comerciales de Apple Inc.

El logotipo de la ballena de Docker es una marca registrada de Docker, Inc. Se usa con permiso.

El resto de marcas y logotipos pertenece a sus respectivos propietarios.

>[!div class="step-by-step"]
>[Siguiente](introduction-to-containers-and-docker.md)
