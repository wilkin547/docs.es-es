---
title: Herramientas adicionales de .NET Core
description: Información general sobre las herramientas adicionales compatibles con las funcionalidades de .NET Core y que las amplían.
author: mlacouture
ms.author: johalex
ms.date: 01/19/2018
ms.custom: mvc
ms.openlocfilehash: c64dddbe36b789a695c2603e78b29b38d8718f95
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2018
ms.locfileid: "46586888"
---
# <a name="net-core-additional-tools"></a>Herramientas adicionales de .NET Core

En esta sección se recopila una lista de herramientas compatibles con las funcionalidades de .NET Core y que las amplían, además de las herramientas de la [interfaz de la línea de comandos (CLI) de .NET Core](../tools/index.md).

## <a name="wcf-web-service-reference-toolwcf-web-service-reference-guidemd"></a>[Herramienta WCF Web Service Reference](wcf-web-service-reference-guide.md)

WCF (Windows Communication Foundation) Web Services Reference es un proveedor de servicios conectados de Visual Studio que se estrenó en la [versión 15.5 de Visual Studio 2017](https://visualstudio.microsoft.com/news/releasenotes/vs2017-relnotes#WCFTools). Esta herramienta recupera metadatos de un servicio web en la solución actual, en una ubicación de red o de un archivo WSDL, y genera un archivo de origen compatible con .NET Core, definiendo una clase de proxy de WCF con métodos que pueden usarse para acceder a las operaciones del servicio web.

## <a name="wcf-dotnet-svcutil-tooldotnet-svcutil-guidemd"></a>[Herramienta dotnet-svcutil de WCF](dotnet-svcutil-guide.md)

La herramienta dotnet-svcutil de WCF (Windows Communication Foundation) es una herramienta de la CLI de .NET Core que recupera metadatos de un servicio web en una ubicación de red o de un archivo WSDL, y genera un archivo de origen compatible con .NET Core, definiendo una clase de proxy de WCF con métodos que pueden usarse para acceder a las operaciones del servicio web. La herramienta **dotnet-svcutil** es una alternativa al proveedor de servicios conectados de Visual Studio [**WCF Web Service Reference**](wcf-web-service-reference-guide.md) que se distribuyó por primera vez en la versión 15.5 de Visual Studio 2017. La herramienta **dotnet-svcutil**, como herramienta de la CLI de .NET Core, está disponible en las distintas plataformas de Linux, Mac OS y Windows.

## <a name="xml-serializer-generatorxml-serializer-generatormd"></a>[Generador de serializador XML](xml-serializer-generator.md)

Tal y como sucede con el [generador serializador de XML (sgen.exe)](../../standard/serialization/xml-serializer-generator-tool-sgen-exe.md) para .NET Framework, el [paquete NuGet Microsoft.XmlSerializer.Generator](https://www.nuget.org/packages/Microsoft.XmlSerializer.Generator) es la solución para las bibliotecas .NET Core y .NET Standard. Crea un ensamblado de serialización de XML para los tipos contenidos en un ensamblado para mejorar el rendimiento de inicio de la serialización XML al serializar o deserializar objetos de esos tipos con <xref:System.Xml.Serialization.XmlSerializer>.