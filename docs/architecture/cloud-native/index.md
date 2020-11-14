---
title: Diseño de aplicaciones .NET nativas en la nube para Azure
description: Guía para crear aplicaciones nativas en la nube con la ayuda de contenedores, microservicios y características sin servidor de Azure.
author: ardalis
ms.date: 11/10/2020
ms.openlocfilehash: 673bfef27c3767f68b1c30d4383cee010ba377f0
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506654"
---
# <a name="architecting-cloud-native-net-applications-for-azure"></a>Diseño de aplicaciones .NET nativas en la nube para Azure

![imagen de portada](./media/cover.png)

**EDICIÓN v1.0**

Consulte el [registro de cambios](https://aka.ms/cn-ebook-changelog) para ver las modificaciones del libro y las colaboraciones para la comunidad.

PUBLICADO POR

Equipos de producto de la División de desarrolladores de Microsoft, .NET y Visual Studio

División de Microsoft Corporation

One Microsoft Way

Redmond, Washington 98052-6399

Copyright &copy; 2020 de Microsoft Corporation

Todos los derechos reservados. No se puede reproducir ni transmitir de ninguna forma ni por ningún medio ninguna parte del contenido de este libro sin la autorización por escrito del publicador.

Este libro se proporciona “tal cual” y expresa las opiniones del autor. Las opiniones y la información expresados en este libro, incluidas las direcciones URL y otras referencias a sitios web de Internet, pueden cambiar sin previo aviso.

Algunos ejemplos descritos aquí se proporcionan únicamente con fines ilustrativos y son ficticios. No debe deducirse ninguna asociación ni conexión reales.

Microsoft y las marcas comerciales indicadas en <https://www.microsoft.com> en la página web "Marcas comerciales" pertenecen al grupo de empresas de Microsoft.

Mac y macOS son marcas comerciales de Apple Inc.

El logotipo de la ballena de Docker es una marca registrada de Docker, Inc. Se usa con permiso.

El resto de marcas y logotipos pertenece a sus respectivos propietarios.

Autores:

> **Rob Vettor** , arquitecto principal de IP y sistemas de [thinkingincloudnative.com](https://thinkingincloudnative.com/about/), Microsoft
>
> **Steve "ardalis" Smith** , instructor y arquitecto de software de [Ardalis.com](https://ardalis.com)

Participantes y revisores:

> **Cesar de la Torre** , administrador de programas principal, equipo de .NET, Microsoft
>
> **Nish Anil** , director de administración de programas, equipo de .NET, Microsoft
>
> **Jeremy Likness** , director de administración de programas, equipo de .NET, Microsoft
>
> **Cecil Phillip** , director de promoción de la nube, Microsoft

Editores:

> **Maira Wenzel** , directora de administración de programas, equipo de .NET, Microsoft

## <a name="version"></a>Versión

Esta guía se ha redactado para **.NET Core 3.1** , junto con muchas actualizaciones adicionales relacionadas con la misma "ola" de tecnologías (es decir, Azure y otras tecnologías de terceros) que coincidan en el tiempo con .NET Core 3.1.

## <a name="who-should-use-this-guide"></a>Destinatarios de esta guía

Esta guía está dirigida principalmente a desarrolladores, responsables de desarrollo y arquitectos interesados en aprender a crear aplicaciones diseñadas para la nube.

También puede resultar útil a aquellas personas responsables de tomar decisiones técnicas que tengan previsto elegir si quieren crear sus aplicaciones con un enfoque nativo en la nube.

## <a name="how-you-can-use-this-guide"></a>Cómo leer esta guía

Esta guía empieza definiendo el enfoque nativo en la nube y presenta una aplicación de referencia creada mediante tecnologías y principios nativos en la nube. Tras los dos primeros capítulos, el resto del libro se divide en capítulos específicos centrados en temas comunes para la mayoría de las aplicaciones nativas en la nube. Puede ir directamente a cualquiera de estos capítulos para obtener más información más sobre los enfoques nativos en la nube relativos a lo siguiente:

- Datos y acceso a datos
- Patrones de comunicación
- Escalado y escalabilidad
- Resistencia de las aplicaciones
- Supervisión y estado
- Identidad y seguridad
- DevOps

Esta guía está disponible en formato [PDF](https://dotnet.microsoft.com/download/e-book/cloud-native-azure/pdf) y en línea. No dude en reenviar este documento o los vínculos a la versión en línea a su equipo para que todos los miembros puedan consultarla. La mayoría de estos temas presentan unos conocimientos sólidos de los principios y los patrones subyacentes, así como los inconvenientes de las decisiones relacionadas con estos temas. Con este documento, nuestro objetivo es facilitar a los equipos y sus responsables la información necesaria para tomar decisiones fundamentadas en lo que respecta al diseño, el desarrollo y el hospedaje de las aplicaciones.

## <a name="send-your-feedback"></a>Envíe sus comentarios

Nos gustaría recibir sus comentarios al respecto para contribuir al desarrollo constante del libro y sus ejemplos relacionados. Si tiene algún comentario sobre cómo mejorar este libro, escríbalo en la sección pertinente situada en la parte inferior de cualquier página creada en [Problemas de GitHub](https://github.com/dotnet/docs/issues).

>[!div class="step-by-step"]
>[Siguiente](introduction.md)
