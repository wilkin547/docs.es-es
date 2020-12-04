---
title: Blazor para desarrolladores de ASP.NET Web Forms
description: Aprenda a crear aplicaciones web de pila completa con .NET mediante Blazor y .NET Core de una manera sencilla y familiar.
author: danroth27
ms.author: daroth
no-loc:
- Blazor
- WebAssembly
ms.date: 12/01/2020
ms.openlocfilehash: 47f684e1b48ca95b8d999e6f1429840eb5f541de
ms.sourcegitcommit: 2f485e721f7f34b87856a51181b5b56624b31fd5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2020
ms.locfileid: "96509772"
---
# <a name="no-locblazor-for-aspnet-web-forms-developers"></a>Blazor para desarrolladores de ASP.NET Web Forms

![Captura de pantalla en la que se muestra la portada del libro electrónico Aplicaciones sin servidor.](./media/index/blazor-for-aspnet-web-forms-developers.png)

> DESCARGA disponible en: <https://aka.ms/blazor-ebook>

**EDICIÓN v1.0**

Consulte el [registro de cambios](https://aka.ms/blazor-ebook-changelog) para ver las modificaciones del libro y las colaboraciones para la comunidad.

PUBLICADO POR

Equipos de producto de la División de desarrolladores de Microsoft, .NET y Visual Studio

División de Microsoft Corporation

One Microsoft Way

Redmond, Washington 98052-6399

Copyright © 2020 de Microsoft Corporation

Todos los derechos reservados. No se puede reproducir ni transmitir de ninguna forma ni por ningún medio ninguna parte del contenido de este libro sin la autorización por escrito del publicador.

Este libro se proporciona “tal cual” y expresa las opiniones del autor. Las opiniones y la información expresados en este libro, incluidas las direcciones URL y otras referencias a sitios web de Internet, pueden cambiar sin previo aviso.

Algunos ejemplos descritos aquí se proporcionan únicamente con fines ilustrativos y son ficticios. No debe deducirse ninguna asociación ni conexión reales.

Microsoft y las marcas comerciales indicadas en <https://www.microsoft.com> en la página web "Marcas comerciales" pertenecen al grupo de empresas de Microsoft.

Mac y macOS son marcas comerciales de Apple Inc.

El resto de marcas y logotipos pertenece a sus respectivos propietarios.

Autores:

> **[Daniel Roth](https://github.com/danroth27)** , administrador de programas principal, Microsoft Corp.

> **[Jeff Fritz](https://github.com/csharpfritz)** , administrador de programas sénior, Microsoft Corp.

> **[Taylor Southwick](https://github.com/twsouthwick)** , ingeniero de software sénior, Microsoft Corp.

> **[Scott Addie](https://github.com/scottaddie)** , desarrollador de contenidos sénior, Microsoft Corp.

> **[Steve "ardalis" Smith](https://ardalis.com)** , instructor y arquitecto de software de Ardalis Services LLC

## <a name="introduction"></a>Introducción

Hace mucho tiempo que .NET permite desarrollar aplicaciones web a través de ASP.NET, un conjunto de plataformas y herramientas muy completo para compilar cualquier tipo de aplicación web. ASP.NET tiene su propio linaje de tecnologías y plataformas web, empezando por las clásicas páginas Active Server (ASP). Las plataformas, como ASP.NET Web Forms, ASP.NET MVC, ASP.NET Web Pages y ahora ASP.NET Core, ofrecen una manera productiva y eficaz de compilar aplicaciones web *representadas por el servidor*, donde el contenido de la interfaz de usuario se genera dinámicamente en el servidor en respuesta a las solicitudes HTTP. Cada plataforma de ASP.NET sigue una filosofía de creación de aplicaciones y satisface una audiencia en particular. ASP.NET Web Forms se incluía con la versión original de .NET Framework y permitía el desarrollo web mediante muchos de los patrones conocidos por los desarrolladores de escritorio, como los controles de IU reutilizables con un control de eventos sencillo. Sin embargo, ninguna de las ofertas de ASP.NET ofrece una manera de ejecutar el código que se ejecutaba en el explorador del usuario. Para ello, es necesario escribir en JavaScript y usar cualquiera de las muchas plataformas y herramientas de JavaScript que han ido ganando y perdiendo popularidad con los años: jQuery, Knockout, Angular, React, etc.

[Blazor](https://blazor.net) es una nueva plataforma web que lo cambia todo en la creación de aplicaciones web con .NET. Blazor es una plataforma de interfaz de usuario web del lado cliente basada en C#, en lugar de JavaScript. Con Blazor, puede escribir la lógica del lado cliente y los componentes de la interfaz de usuario en C#, compilarlos en ensamblados .NET normales y ejecutarlos directamente en el explorador mediante un nuevo estándar web abierto denominado WebAssembly. O, si lo prefiere, Blazor puede ejecutar los componentes de la interfaz de usuario de .NET en el servidor y controlar todas las interacciones de la interfaz de usuario de forma fluida a través de una conexión en tiempo real con el explorador. Al emparejar Blazor con la instancia de .NET que se ejecuta en el servidor, permite el desarrollo web de pila completa con .NET. Aunque tiene mucho en común con ASP.NET Web Forms, como un modelo de componentes reutilizable y una forma sencilla de controlar los eventos de usuario, Blazor también se basa en .NET para ofrecer una experiencia de desarrollo web moderna y de alto rendimiento.

Este libro es una introducción de Blazor para los desarrolladores de ASP.NET Web Forms que resulta muy útil y, a su vez, familiar. Se presentan conceptos de Blazor comparándolos con conceptos análogos de ASP.NET Web Forms, a la vez que se explican los nuevos conceptos que pueden resultar menos conocidos. Abarca toda una variedad de temas y problemas, como la creación de componentes, el enrutamiento, el diseño, la configuración y la seguridad. Aunque el contenido de este libro abarca principalmente el desarrollo de nuevas aplicaciones, también incluye instrucciones y estrategias para migrar las instancias de ASP.NET Web Forms existentes a Blazor para cuando se quiera modernizar una aplicación existente.

## <a name="who-should-use-the-book"></a>Destinatarios de este libro

Este libro está dirigido a desarrolladores de ASP.NET Web Forms que buscan una introducción a Blazor, relacionándolo con sus conocimientos y habilidades existentes. Con este libro será más fácil empezar a trabajar rápidamente en un nuevo proyecto de Blazor o crear un mapa de ruta para modernizar una aplicación ASP.NET Web Forms existente.

## <a name="how-to-use-the-book"></a>Cómo usar este libro

En la primera parte de este libro se presenta Blazor y se ofrece una comparación con el desarrollo de aplicaciones web con ASP.NET Web Forms. En los capítulos posteriores se tratan distintos temas sobre Blazor y se relaciona cada concepto de Blazor con el concepto correspondiente de ASP.NET Web Forms, o bien se explica en detalle cualquier concepto que sea completamente nuevo. En el libro también se hace referencia con regularidad a una aplicación de ejemplo completa, implementada en ASP.NET Web Forms y en Blazor, para mostrar las características de Blazor y proporcionar un caso práctico para la migración de ASP.NET Web Forms a Blazor. Puede encontrar ambas implementaciones de la aplicación de ejemplo (ASP.NET Web Forms y Blazor) en [GitHub](https://github.com/dotnet-architecture/eshoponblazor).

## <a name="what-this-book-doesnt-cover"></a>Aspectos no tratados en este libro

Este libro es una introducción a Blazor, no una guía completa sobre la migración. Aunque incluye información sobre cómo enfocar la migración de un proyecto de ASP.NET Web Forms a Blazor, no pretende cubrir todos sus matices y detalles. Si quiere consultar una guía general sobre cómo realizar una migración de ASP.NET a ASP.NET Core, lea la [guía de migración](/aspnet/core/migration/proper-to-2x/) en la documentación de ASP.NET Core.

### <a name="additional-resources"></a>Recursos adicionales

Encontrará la documentación y la página oficial de Blazor en <https://blazor.net>.

## <a name="send-your-feedback"></a>Envíe sus comentarios

Nos gustaría recibir sus comentarios al respecto para contribuir al desarrollo constante del libro y sus ejemplos relacionados. Si tiene algún comentario sobre cómo mejorar este libro, escríbalo en la sección pertinente situada en la parte inferior de cualquier página creada en [Problemas de GitHub](https://github.com/dotnet/docs/issues).

>[!div class="step-by-step"]
>[Siguiente](introduction.md)
