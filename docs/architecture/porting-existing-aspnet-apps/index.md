---
title: Migración de aplicaciones existentes de ASP.NET a .NET Core
description: Una guía gratuita para convertir aplicaciones de ASP.NET MVC y Web API a ASP.NET Core.
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: 848f0e9533a65b59055853f1d502307abb69118c
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102105950"
---
# <a name="porting-existing-aspnet-apps-to-net-core"></a>Migración de aplicaciones existentes de ASP.NET a .NET Core

![imagen de portada](./media/index/porting-existing-aspnet-apps.png)

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

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

> **Steve "ardalis" Smith**, instructor y arquitecto de software de [Ardalis.com](https://ardalis.com)

Participantes y revisores:

> **Nish Anil**, director de administración de programas, equipo de .NET, Microsoft

> **Mike Rousos**, ingeniero de software principal, equipo de .NET, Microsoft

> **Scott Addie**, desarrollador de contenidos sénior, equipo de .NET, Microsoft

> **David Pine**, desarrollador de contenidos sénior, equipo de .NET, Microsoft

## <a name="version"></a>Versión

En esta guía se describe **.NET Core 3.1** y las actualizaciones relacionadas con la misma "ola" tecnológica (esto es, Azure y otras tecnologías de terceros) que coincidan en el tiempo con la versión de .NET Core 3.1. La actualización de .NET Core 3.1 a .NET 5.0 (la versión siguiente) es relativamente sencilla y, por lo tanto, requiere menos esfuerzo que la migración de .NET Framework a .NET Core. La migración de .NET Framework 4.x a .NET 5.0 será similar a la migración a .NET Core 3.1. Para obtener más información, vea [Selección de la versión correcta de .NET Core](choose-net-core-version.md).

## <a name="who-should-use-this-guide"></a>Destinatarios de esta guía

Esta guía está dirigida a desarrolladores, jefes de desarrollo y arquitectos que estén interesados en migrar sus aplicaciones existentes escritas para ASP.NET MVC y Web API (.NET Framework 4.x) a .NET Core. Los desarrolladores de ASP.NET Web Forms se beneficiarán de esta guía, pero también deberían leer el libro electrónico [Blazor para desarrolladores de ASP.NET Web Forms](../blazor-for-web-forms-developers/index.md).

Un público secundario es el de los responsables de la toma de decisiones técnicas que planean cuándo migrar sus aplicaciones a .NET Core.

El público objetivo de este libro son los desarrolladores de .NET con grandes aplicaciones existentes que se ejecutan en ASP.NET MVC y Web API. Las aplicaciones basadas en ASP.NET Web Forms quedan fuera del ámbito central de este libro, aunque gran parte de la información que compara .NET Framework y .NET Core puede seguir siendo pertinente.

## <a name="how-you-can-use-this-guide"></a>Cómo leer esta guía

Puede leer este libro de corrido, como esperamos que hagan muchos lectores. Este libro le proporcionará, en primer lugar, consideraciones sobre si debe migrar su aplicación. A ese contenido le siguen las diferencias arquitectónicas entre .NET Framework y .NET Core. A partir de ahí, aprenderá estrategias para migrar una solución de gran tamaño en el tiempo y para trasladar una aplicación real. Después, el libro incluye escenarios de implementación que solucionan la necesidad de ejecutar aplicaciones diferentes al tiempo que aparecen como una sola aplicación para los usuarios. El libro concluye con dos casos prácticos en los que se describen aplicaciones reales que se han migrado de ASP.NET MVC a ASP.NET Core.

Tanto si decide empezar por el primer capítulo como si no, puede consultar cualquiera de estos capítulos para obtener información sobre conceptos específicos:

- [Diferencias arquitectónicas](architectural-differences.md)
- [Migración de soluciones de gran tamaño](migrate-large-solutions.md)
- [Migración de ejemplo](example-migration-eshop.md)
- [Escenarios de implementación](deployment-scenarios.md)

Esta guía está disponible en [formato PDF](https://aka.ms/aspnet-porting-ebook) y en línea. No dude en reenviar este documento o los vínculos a la versión en línea a su equipo para garantizar que todos los integrantes hayan comprendido estos conceptos.

## <a name="send-your-feedback"></a>Envíe sus comentarios

Nos gustaría recibir sus comentarios al respecto para contribuir al desarrollo constante del libro y sus ejemplos relacionados. Si tiene algún comentario sobre cómo mejorar este libro, escríbalo en la sección pertinente situada en la parte inferior de cualquier página creada en [Problemas de GitHub](https://github.com/dotnet/docs/issues).

>[!div class="step-by-step"]
>[Siguiente](introduction.md)
