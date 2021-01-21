---
title: Modernización de aplicaciones de escritorio en Windows 10 con .NET 5
description: Información sobre cómo modernizar aplicaciones de escritorio con .NET 5
ms.date: 01/06/2021
ms.openlocfilehash: de8a451b0598b5eabd99028d377c161dace61623
ms.sourcegitcommit: 632818f4b527e5bf3c48fc04e0c7f3b4bdb8a248
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/20/2021
ms.locfileid: "98615714"
---
# <a name="modernizing-desktop-apps-on-windows-10-with-net-5"></a>Modernización de aplicaciones de escritorio en Windows 10 con .NET 5

![Captura de pantalla en la que se muestra la portada del libro electrónico de modernización de aplicaciones de escritorio.](./media/modernizing-existing-desktop-apps-ebook-cover.png)

**EDICIÓN v1.0.1**: actualizada a .NET 5

Consulte el [registro de cambios](https://aka.ms/desktop-ebook-changelog) para ver las modificaciones del libro y las colaboraciones para la comunidad.

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

El resto de marcas y logotipos pertenece a sus respectivos propietarios.

Coautores:

> **Olia Gavrysh**, directora de administración de programas, equipo de .NET, Microsoft

> **Miguel Ángel Castejón Dominguez**, arquitecto de innovación, Kabel

Participantes y revisores:

> **Maira Wenzel**, administradora de programas sénior, equipo de .NET, Microsoft

> **Andy De Gorge**, desarrollador de contenido sénior, equipo de documentación de .NET, Microsoft

> **Miguel Ramos**, administrador de programas sénior, equipo de la plataforma de desarrolladores de Windows, Microsoft

> **Adam Braden**, administrador de programas principal, equipo de la plataforma de desarrolladores de Windows, Microsoft

> **Ricardo Minguez Pablos**, administrador de programas sénior, equipo de Azure IoT, Microsoft

> **Nish Anil**, director de administración de programas, equipo de .NET, Microsoft

> **Beth Massi**, administradora sénior de marketing de producto, Microsoft

> **Scott Hunter**, director asociado de administración de programas, equipo de .NET, Microsoft

> **Marta Fuentes Lara**, Kabel

> **Raúl Fernández de Córdoba**, Kabel

> **Antonio Manuel Fernández Cantos**, Kabel

## <a name="introduction"></a>Introducción

Este libro trata sobre las estrategias que puede adoptar para llevar sus aplicaciones de escritorio a la modernización e incorporación de las características más recientes sobre runtime, idioma y plataformas. Descubrirá que no existe un único método, ya que cada aplicación es distinta, y también lo son sus requisitos y preferencias. Sin embargo, la buena noticia es que puede aplicar enfoques comunes para agregar nuevas características y funcionalidades a sus aplicaciones. Para algunos de estos enfoques no será necesario aplicar ninguna modificación importante al código. En este libro, explicaremos cómo funcionan todas esas características en segundo plano, así como la mecánica de sus implementaciones. Además, encontrará algunos escenarios habituales para modernizar aplicaciones de escritorio explicados en detalle, así que seguro que tendrá la inspiración necesaria para hacer evolucionar sus proyectos.

El enfoque de Microsoft para modernizar las aplicaciones consiste en proporcionarle la flexibilidad necesaria para crear una ruta de acceso personalizada. Todas las estrategias de modernización descritas en este libro son mayoritariamente independientes. Puede elegir las que sean pertinentes para su aplicación y omitir las que no considere importantes. Dicho de otra forma, puede combinar las estrategias para cubrir de la mejor forma las necesidades de sus aplicaciones.

## <a name="who-should-use-the-book"></a>Destinatarios de este libro

Libro para los desarrolladores y arquitectos de soluciones que quieren modernizar las aplicaciones de escritorio existentes de Windows Forms y WPF para aprovechar las ventajas que ofrecen .NET y Windows 10.

También es posible que este libro le resulte útil si se dedica a tomar decisiones técnicas, por ejemplo, si es arquitecto empresarial o un director o responsable de desarrollo que quiere disponer de información general relacionada con las ventajas de actualizar las aplicaciones de escritorio.

## <a name="how-to-use-the-book"></a>Cómo usar este libro

En este libro se aborda el motivo por el que es recomendable modernizar las aplicaciones existentes y, además, se explican las ventajas específicas derivadas del uso de .NET y MSIX para hacerlo. El contenido del libro está diseñado para arquitectos y responsables de la toma de decisiones técnicas que quieren obtener información general, pero que no tienen que centrarse en información detallada de carácter técnico ni de implementación.

A lo largo de los distintos capítulos, se proporcionan fragmentos de códigos de implementación de ejemplo y capturas de pantalla. Además, el capítulo 5 se ha dedicado a mostrar el proceso de migración completo de unas aplicaciones de muestra.

## <a name="what-this-book-doesnt-cover"></a>Aspectos no tratados en este libro

Este libro trata sobre un subconjunto específico de escenarios centrados en la migración mediante lift-and-shift. En él, se describe la forma de conseguir las ventajas que ofrece la modernización sin necesidad de volver a escribir el código.

Este libro no trata sobre el desarrollo desde cero de aplicaciones modernas con .NET ni sobre cómo empezar a usar Windows Forms y WPF, sino que se centra en cómo actualizar las aplicaciones de escritorio con las características tecnológicas más recientes para el desarrollo de escritorio.

## <a name="samples-used-in-this-book"></a>Ejemplos usados en este libro

Para indicar los pasos necesarios para realizar una modernización, usaremos una aplicación de ejemplo llamada `eShopModernizing`. Esta aplicación tiene dos tipos, Windows Forms y WPF, y nosotros explicaremos un proceso detallado sobre cómo llevar a cabo la modernización de los dos en .NET.

Además, en el repositorio de GitHub de este libro, encontrará los resultados del proceso, que puede consultar si decide seguir el tutorial paso a paso.

## <a name="send-your-feedback"></a>Envíe sus comentarios

Nos gustaría recibir sus comentarios al respecto para contribuir al desarrollo constante del libro y sus ejemplos relacionados. Si tiene algún comentario sobre cómo mejorar este libro, escríbalo en la sección pertinente situada en la parte inferior de cualquier página creada en [Problemas de GitHub](https://github.com/dotnet/docs/issues).

>[!div class="step-by-step"]
>[Siguiente](why-modern-applications.md)
