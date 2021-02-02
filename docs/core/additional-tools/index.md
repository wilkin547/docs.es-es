---
title: Herramientas adicionales
description: Información general sobre las herramientas adicionales que puede instalar, las cuales admiten y extienden la funcionalidad de .NET.
author: mlacouture
ms.date: 02/13/2020
ms.custom: mvc
ms.openlocfilehash: 243f2da1c6f7809ac710c9700ea4cbde6f289295
ms.sourcegitcommit: 68c9d9d9a97aab3b59d388914004b5474cf1dbd7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2021
ms.locfileid: "99216400"
---
# <a name="net-additional-tools-overview"></a>Información general sobre las herramientas adicionales de .NET

En esta sección se recopila una lista de herramientas compatibles con las funcionalidades de .NET y que las amplían, además de la CLI de .NET.

## <a name="net-uninstall-tool"></a>Herramienta de desinstalación de .NET

La [herramienta de desinstalación de .NET](https://github.com/dotnet/cli-lab/releases) (`dotnet-core-uninstall`) permite limpiar los SDK y los entornos de ejecución de .NET en un sistema, de modo que solo queden las versiones especificadas. Hay una colección de opciones disponible para especificar las versiones que se van a desinstalar.

## <a name="net-diagnostic-tools"></a>Herramientas de diagnóstico de .NET

[dotnet-counters](../diagnostics/dotnet-counters.md) es una herramienta diseñada para la investigación del rendimiento y la supervisión del estado de primer nivel.

[dotnet-dump](../diagnostics/dotnet-dump.md) permite recopilar y analizar los volcados de Windows y Linux sin necesidad de un depurador nativo.

[dotnet-gcdump](../diagnostics/dotnet-gcdump.md) permite recopilar volcados de memoria de GC (recolector de elementos no utilizados) de procesos de .NET dinámicos.

[dotnet-trace](../diagnostics/dotnet-trace.md) recopila datos de generación de perfiles de la aplicación que pueden ayudar en escenarios en los que es necesario averiguar lo que causa que una aplicación se ejecute lentamente.

## <a name="net-install-tool-for-extension-authors"></a>Herramienta de instalación de .NET para autores de extensiones

La [herramienta de instalación de .NET para creadores de extensiones](https://github.com/dotnet/vscode-dotnet-runtime) es una extensión de Visual Studio Code que permite la adquisición del entorno de ejecución de .NET específicamente para creadores de extensiones de VS Code. Esta herramienta está diseñada para aprovecharse en extensiones escritas en .NET y requiere que .NET arranque partes de la extensión (por ejemplo, un servidor de lenguaje). La extensión no está pensada para que la usen directamente los usuarios con el fin de instalar .NET para el desarrollo.

## <a name="wcf-web-service-reference-tool"></a>Herramienta WCF Web Service Reference

La herramienta WCF (Windows Communication Foundation) [Web Service Reference](wcf-web-service-reference-guide.md) es un proveedor de servicios conectados de Visual Studio que se estrenó en la [versión 15.5 de Visual Studio 2017](/visualstudio/releasenotes/vs2017-relnotes-v15.5#WCFTools). Esta herramienta recupera metadatos de un servicio web en la solución actual, en una ubicación de red o desde un archivo WSDL. Genera un archivo de código fuente compatible con .NET, el cual define una clase de proxy de WCF con métodos que es posible usar para acceder a las operaciones del servicio web.

## <a name="wcf-dotnet-svcutil-tool"></a>Herramienta dotnet-svcutil de WCF

La herramienta [dotnet-svcutil](dotnet-svcutil-guide.md) de WCF es una herramienta de .NET que recupera los metadatos de un servicio web en una ubicación de red o en un archivo WSDL. Genera un archivo de código fuente compatible con .NET, el cual define una clase de proxy de WCF con métodos que es posible usar para acceder a las operaciones del servicio web.

La herramienta **dotnet-svcutil** es una alternativa al proveedor de servicios conectados de Visual Studio [**WCF Web Service Reference**](wcf-web-service-reference-guide.md), que se distribuyó por primera vez en la versión 15.5 de Visual Studio 2017. La herramienta **dotnet-svcutil**, como herramienta de .NET, está disponible en Linux, macOS y Windows.

## <a name="wcf-dotnet-svcutilxmlserializer-tool"></a>Herramienta dotnet-svcutil.xmlserializer de WCF

En .NET Framework, puede generar previamente un ensamblado de serialización con la herramienta svcutil. La [herramienta dotnet-svcutil.xmlserializer](dotnet-svcutil.xmlserializer-guide.md) de WCF proporciona una funcionalidad parecida en .NET 5 (y .NET Core) y versiones posteriores. Genera previamente código de serialización de C# para los tipos de la aplicación cliente que usa el contrato de servicio de WCF y que puede serializar <xref:System.Xml.Serialization.XmlSerializer>. Esto mejora el rendimiento de inicio de la serialización de XML al serializar o deserializar objetos de esos tipos.

## <a name="xml-serializer-generator"></a>Generador de serializador XML

Como sucede con el [generador serializador de XML (sgen.exe)](../../standard/serialization/xml-serializer-generator-tool-sgen-exe.md) para .NET Framework, el [paquete NuGet Microsoft.XmlSerializer.Generator](https://www.nuget.org/packages/Microsoft.XmlSerializer.Generator) es la solución para las bibliotecas que tienen como destino .NET 5 (y .NET Core) y versiones posteriores. Crea un ensamblado de serialización de XML para los tipos contenidos en un ensamblado para mejorar el rendimiento de inicio de la serialización XML al serializar o deserializar objetos de esos tipos con <xref:System.Xml.Serialization.XmlSerializer>.

## <a name="generating-self-signed-certificates"></a>Generación de certificados autofirmados

Puede usar [dotnet-dev-certs](self-signed-certificates-guide.md) para crear certificados autofirmados para escenarios de desarrollo y pruebas.
