---
title: Herramientas de la CLI adicionales de .NET Core
description: Información general sobre las herramientas adicionales que puede instalar que admiten y extienden la funcionalidad de .NET Core.
author: mlacouture
ms.date: 11/27/2018
ms.custom: mvc, seodec18
ms.openlocfilehash: 5f42cddc31204bba2aafaee0b909bbf92d232fde
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53243603"
---
# <a name="net-core-additional-tools-overview"></a>Herramientas adicionales de .NET Core

En esta sección se recopila una lista de herramientas compatibles con las funcionalidades de .NET Core y que las amplían, además de las herramientas de la [interfaz de la línea de comandos (CLI) de .NET Core](../tools/index.md).

## <a name="wcf-web-service-reference-toolwcf-web-service-reference-guidemd"></a>[Herramienta WCF Web Service Reference](wcf-web-service-reference-guide.md)

WCF (Windows Communication Foundation) Web Services Reference es un proveedor de servicios conectados de Visual Studio que se estrenó en la [versión 15.5 de Visual Studio 2017](/visualstudio/releasenotes/vs2017-relnotes-v15.5#WCFTools). Esta herramienta recupera metadatos de un servicio web en la solución actual, en una ubicación de red o de un archivo WSDL, y genera un archivo de origen compatible con .NET Core, definiendo una clase de proxy de WCF con métodos que pueden usarse para acceder a las operaciones del servicio web.

## <a name="wcf-dotnet-svcutil-tooldotnet-svcutil-guidemd"></a>[Herramienta dotnet-svcutil de WCF](dotnet-svcutil-guide.md)

La herramienta dotnet-svcutil de WCF (Windows Communication Foundation) es una herramienta de la CLI de .NET Core que recupera metadatos de un servicio web en una ubicación de red o de un archivo WSDL, y genera un archivo de origen compatible con .NET Core, definiendo una clase de proxy de WCF con métodos que pueden usarse para acceder a las operaciones del servicio web.
La herramienta **dotnet-svcutil** es una alternativa al proveedor de servicios conectados de Visual Studio [**WCF Web Service Reference**](wcf-web-service-reference-guide.md) que se distribuyó por primera vez en la versión 15.5 de Visual Studio 2017. La herramienta **dotnet-svcutil**, como herramienta de la CLI de .NET Core, está disponible en las distintas plataformas de Linux, Mac OS y Windows.

## <a name="wcf-dotnet-svcutilxmlserializer-tooldotnet-svcutilxmlserializer-guidemd"></a>[Herramienta dotnet-svcutil.xmlserializer de WCF](dotnet-svcutil.xmlserializer-guide.md)

En .NET Framework, puede generar previamente un ensamblado de serialización con la herramienta svcutil. El paquete NuGet dotnet-svcutil.xmlserializer proporciona una funcionalidad parecida en .NET Core. Genera previamente código de serialización de C# para los tipos de la aplicación cliente que usa el contrato de servicio de WCF y que puede serializar <xref:System.Xml.Serialization.XmlSerializer>. Esto mejora el rendimiento de inicio de la serialización de XML al serializar o deserializar objetos de esos tipos.

## <a name="xml-serializer-generatorxml-serializer-generatormd"></a>[Generador de serializador XML](xml-serializer-generator.md)

Tal y como sucede con el [generador serializador de XML (sgen.exe)](../../standard/serialization/xml-serializer-generator-tool-sgen-exe.md) para .NET Framework, el [paquete NuGet Microsoft.XmlSerializer.Generator](https://www.nuget.org/packages/Microsoft.XmlSerializer.Generator) es la solución para las bibliotecas .NET Core y .NET Standard. Crea un ensamblado de serialización de XML para los tipos contenidos en un ensamblado para mejorar el rendimiento de inicio de la serialización XML al serializar o deserializar objetos de esos tipos con <xref:System.Xml.Serialization.XmlSerializer>.