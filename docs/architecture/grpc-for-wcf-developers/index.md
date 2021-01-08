---
title: 'gRPC de ASP.NET Core para desarrolladores de WCF: gRPC para desarrolladores de WCF'
description: Introducción a la creación de servicios gRPC en ASP.NET Core 5.0 para desarrolladores de WCF
ms.date: 01/06/2021
ms.openlocfilehash: 26cce6bb784c08a5b59623ff5882fcf2fbb9e9ac
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970198"
---
# <a name="aspnet-core-grpc-for-wcf-developers"></a>gRPC de ASP.NET Core para desarrolladores de WCF

![imagen de portada](./media/cover.png)

EDICIÓN v1.0.1: actualizada a ASP.NET Core 5.0

Consulte el [registro de cambios](https://aka.ms/grpc-ebook-changelog) para ver las modificaciones del libro y las colaboraciones para la comunidad.

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

El logotipo de la ballena de Docker es una marca registrada de Docker, Inc. Se usa con permiso.

El resto de marcas y logotipos pertenece a sus respectivos propietarios.

Autores:

> **Mark Rendle**, director técnico, [recodificación visual](https://visualrecode.com)
>
> **Miranda Steiner**, autora técnica

Editor:

> **Maira Wenzel**, desarrolladora de contenidos sénior, Microsoft

## <a name="introduction"></a>Introducción

gRPC es una plataforma de trabajo moderna para compilar servicios en red y aplicaciones distribuidas. Imagínese el rendimiento de los enlaces de NetTCP de Windows Communication Foundation (WCF), junto con la interoperabilidad multiplataforma de SOAP. gRPC se basa en HTTP/2 y el protocolo de codificación de mensajes Protobuf para proporcionar una comunicación de alto rendimiento y bajo ancho de banda entre aplicaciones y servicios. Admite la generación de código de cliente y servidor en las plataformas y los lenguajes de programación más populares, como .NET, Java, Python, Node.js, Go y C++. Con la compatibilidad de primera clase con gRPC en ASP.NET Core 5.0, junto con las herramientas y las bibliotecas de gRPC existentes para .NET Framework 4.x, es una alternativa excelente a WCF para los equipos de desarrollo que quieran adoptar .NET en sus organizaciones.

## <a name="who-should-use-this-guide"></a>Destinatarios de esta guía

Esta guía se ha escrito para desarrolladores que trabajan con .NET Framework o .NET, que han usado WCF antes y que buscan migrar sus aplicaciones a un entorno de RPC moderno para .NET Core 3.0 y versiones posteriores. En general, si va a realizar una actualización a .NET 5, o si se lo está pensando, y quiere usar las herramientas de gRPC integradas, esta guía también le será útil.

## <a name="how-you-can-use-this-guide"></a>Cómo leer esta guía

Esta es una breve introducción a la creación de servicios de gRPC en ASP.NET Core 5.0 en la que se hace referencia a WCF como plataforma análoga. Se explican los principios de gRPC, relacionando cada concepto con las características equivalentes de WCF, y se ofrecen instrucciones para migrar una aplicación WCF actual a gRPC. También es útil para los desarrolladores que tienen experiencia con WCF y quieren aprender a crear nuevos servicios con gRPC. Puede usar las aplicaciones de ejemplo como una plantilla o como referencia para proyectos propios, y el código del libro o sus ejemplos también se puede copiar y reutilizar.

No dude en reenviar esta guía a su equipo para ayudarlo a garantizar una comprensión común de estas consideraciones y oportunidades. El hecho de que todos los usuarios trabajen a partir de un conjunto común de principios subyacentes y de términos permite garantizar una aplicación coherente de las prácticas y los patrones de diseño.

## <a name="references"></a>Referencias

- **Sitio web de gRPC**
  <https://grpc.io>
- **Elección entre .NET 5 y .NET Framework para aplicaciones de servidor**
  <https://docs.microsoft.com/dotnet/standard/choosing-core-framework-server>

>[!div class="step-by-step"]
>[Siguiente](introduction.md)
