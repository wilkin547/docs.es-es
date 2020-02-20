---
title: Herramientas adicionales
description: Información general sobre las herramientas adicionales que puede instalar que admiten y extienden la funcionalidad de .NET Core.
author: mlacouture
ms.date: 02/13/2020
ms.custom: mvc
ms.openlocfilehash: c0224a1cc6cbb9ae6fa88e5f869c47a1e84289e0
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77451530"
---
# <a name="net-core-additional-tools-overview"></a>Herramientas adicionales de .NET Core

En esta sección se recopila una lista de herramientas compatibles con las funcionalidades de .NET Core y que las amplían, además de las herramientas de la CLI de .NET Core.

## <a name="net-core-uninstall-tool"></a>Herramienta de desinstalación de .NET Core

La [herramienta de desinstalación de .NET Core](https://github.com/dotnet/cli-lab/releases) (`dotnet-core-uninstall`) permite limpiar los SDK y los entornos de ejecución de .NET Core en un sistema, de modo que solo queden las versiones especificadas. Hay una colección de opciones disponible para especificar las versiones que se van a desinstalar.

## <a name="net-core-diagnostic-tools"></a>Herramientas de diagnóstico de .NET Core

[dotnet-counters](../diagnostics/dotnet-counters.md) es una herramienta diseñada para la investigación del rendimiento y la supervisión del estado de primer nivel.

[dotnet-dump](../diagnostics/dotnet-dump.md) permite recopilar y analizar los volcados de Windows y Linux sin necesidad de un depurador nativo.

[dotnet-trace](../diagnostics/dotnet-trace.md) recopila datos de generación de perfiles de la aplicación que pueden ayudar en escenarios en los que es necesario averiguar lo que causa que una aplicación se ejecute lentamente.

## <a name="wcf-web-service-reference-tool"></a>Herramienta WCF Web Service Reference

La herramienta WCF (Windows Communication Foundation) [Web Service Reference](wcf-web-service-reference-guide.md) es un proveedor de servicios conectados de Visual Studio que se estrenó en la [versión 15.5 de Visual Studio 2017](/visualstudio/releasenotes/vs2017-relnotes-v15.5#WCFTools). Esta herramienta recupera metadatos de un servicio web en la solución actual, en una ubicación de red o desde un archivo WSDL. Genera un archivo de código fuente compatible con .NET Core, que define una clase de proxy de WCF con métodos que se pueden usar para acceder a las operaciones del servicio web.

## <a name="wcf-dotnet-svcutil-tool"></a>Herramienta dotnet-svcutil de WCF

La herramienta [dotnet-svcutil](dotnet-svcutil-guide.md) de WCF es una herramienta de .NET que recupera los metadatos de un servicio web en una ubicación de red o en un archivo WSDL. Genera un archivo de código fuente compatible con .NET Core, que define una clase de proxy de WCF con métodos que se pueden usar para acceder a las operaciones del servicio web.

La herramienta **dotnet-svcutil** es una alternativa al proveedor de servicios conectados de Visual Studio [**WCF Web Service Reference**](wcf-web-service-reference-guide.md), que se distribuyó por primera vez en la versión 15.5 de Visual Studio 2017. La herramienta **dotnet-svcutil**, como herramienta de .NET, está disponible en Linux, macOS y Windows.

## <a name="wcf-dotnet-svcutilxmlserializer-tool"></a>Herramienta dotnet-svcutil.xmlserializer de WCF

En .NET Framework, puede generar previamente un ensamblado de serialización con la herramienta svcutil. La [herramienta dotnet-svcutil.xmlserializer](dotnet-svcutil.xmlserializer-guide.md) de WCF proporciona una funcionalidad parecida en .NET Core. Genera previamente código de serialización de C# para los tipos de la aplicación cliente que usa el contrato de servicio de WCF y que puede serializar <xref:System.Xml.Serialization.XmlSerializer>. Esto mejora el rendimiento de inicio de la serialización de XML al serializar o deserializar objetos de esos tipos.

## <a name="xml-serializer-generator"></a>Generador de serializador XML

Tal y como sucede con el [generador serializador de XML (sgen.exe)](../../standard/serialization/xml-serializer-generator-tool-sgen-exe.md) para .NET Framework, el [paquete NuGet Microsoft.XmlSerializer.Generator](https://www.nuget.org/packages/Microsoft.XmlSerializer.Generator) es la solución para las bibliotecas .NET Core y .NET Standard. Crea un ensamblado de serialización de XML para los tipos contenidos en un ensamblado para mejorar el rendimiento de inicio de la serialización XML al serializar o deserializar objetos de esos tipos con <xref:System.Xml.Serialization.XmlSerializer>.
