---
title: Dapr para desarrolladores de .NET
description: Una guía para que los desarrolladores de .NET comprendan y aprovechen toda la eficacia de Distributed Apps Runtime de código abierto de Microsoft.
author: robvet
ms.date: 02/07/2021
ms.openlocfilehash: 53d5356c8e010f0c4e168a2186d48dd9af369ff6
ms.sourcegitcommit: b924ade6426cf61a4604c4e2ee54cb3592c29317
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "101096737"
---
# <a name="dapr-for-net-developers"></a>Dapr para desarrolladores de .NET

![imagen de portada](./media/cover.png)

**EDICIÓN EN VERSIÓN PRELIMINAR**

PUBLICADO POR

Equipos de Microsoft Developer Division, .NET y Azure Incubations

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

Autores:

> **Rob Vettor**, arquitecto principal de soluciones en la nube, [thinkingincloudnative.com](https://thinkingincloudnative.com/about/), Microsoft
>
> **Sander Molenkamp**, arquitecto de la nube principal/MVP de Microsoft, [sandermolenkamp.com](https://www.sandermolenkamp.com), [Info Support](https://www.infosupport.com/en/)
>
> **Edwin van Wijk**, arquitecto de soluciones principales/MVP de Microsoft,[defaultconstructor.com](https://defaultconstructor.com), [Info Support](https://www.infosupport.com/en/)

Participantes y revisores:

> **Mark Russinovich**, CTO de Azure y técnico, Azure Office de CTO, Microsoft
>
> **Nish Anil**, director de administración de programas, equipo de .NET, Microsoft
>
> **Mark Fussell**, director de programas principales, Azure Incubations, Microsoft
>
> **Yaron Schneider**, ingeniero de software principal, Azure Incubations, Microsoft
>
> **Ori Zohar**, director de programas sénior, Azure Incubations, Microsoft

Editores:

> **David Pine**, desarrollador de contenidos sénior, equipo de .NET, Microsoft

> **Maira Wenzel**, administradora de programas sénior, equipo de .NET, Microsoft

## <a name="version"></a>Versión

Esta guía se ha escrito para cubrir la versión **Dapr 1.0**. Los ejemplos de .NET Core se basan en **.NET Core 3.1**.

## <a name="who-should-use-this-guide"></a>Destinatarios de esta guía

Esta guía está dirigida principalmente a desarrolladores, responsables de desarrollo y arquitectos interesados en aprender a crear aplicaciones diseñadas para la nube.

También puede resultar útil a aquellas personas responsables de tomar decisiones técnicas que tengan previsto elegir si quieren crear sus aplicaciones con un enfoque nativo en la nube.

## <a name="how-you-can-use-this-guide"></a>Cómo leer esta guía

Esta guía está disponible en formato [PDF](https://aka.ms/dapr-ebook) y en línea. No dude en reenviar este documento o los vínculos a la versión en línea a su equipo para que todos los miembros puedan consultarla. La mayoría de estos temas presentan unos conocimientos sólidos de los principios y los patrones subyacentes, así como los inconvenientes de las decisiones relacionadas con estos temas. Con este documento, nuestro objetivo es facilitar a los equipos y sus responsables la información necesaria para tomar decisiones fundamentadas en lo que respecta al diseño, el desarrollo y el hospedaje de las aplicaciones.

## <a name="send-your-feedback"></a>Envíe sus comentarios

Nos gustaría recibir sus comentarios al respecto para contribuir al desarrollo constante del libro y sus ejemplos relacionados. Si tiene algún comentario sobre cómo mejorar este libro, escríbalo en la sección pertinente situada en la parte inferior de cualquier página creada en [Problemas de GitHub](https://github.com/dotnet/docs/issues).

>[!div class="step-by-step"]
>[Siguiente](foreword.md)
