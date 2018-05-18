---
title: Analizador de portabilidad de .NET | .NET
description: Obtenga información sobre cómo usar la herramienta Analizador de portabilidad de .NET para evaluar la portabilidad de su código entre las diferentes implementaciones de .NET, incluidos .NET Core, .NET Standard, UWP y Xamarin.
author: blackdwarf
ms.author: mairaw
ms.date: 07/26/2017
ms.technology: dotnet-standard
ms.assetid: 0375250f-5704-4993-a6d5-e21c499cea1e
ms.openlocfilehash: f310e5fe45315dfa41d596c92d9412dc6b3bc125
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="the-net-portability-analyzer"></a>Analizador de portabilidad de .NET

¿Quiere que sus bibliotecas sean multiplataforma? ¿Desea saber cuánto trabajo se necesita para que la aplicación sea compatible con otras implementaciones y perfiles de .NET, incluidos .NET Core, .NET Standard, UWP y Xamarin para iOS, Android y Mac? El [Analizador de portabilidad de .NET](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer) es una herramienta que le proporciona un informe detallado sobre el grado de flexibilidad de su programa en las implementaciones de .NET mediante el análisis de ensamblados. El Analizador de portabilidad se ofrece como extensión de Visual Studio y como aplicación de consola.

## <a name="new-targets"></a>Nuevos destinos

* [.NET Core](../../core/index.md): tiene un diseño modular, emplea el modo en paralelo y tiene como destino escenarios multiplataforma. El modo en paralelo permite adoptar nuevas versiones de .NET Core sin que ello afecte a otras aplicaciones.
* [ASP.NET Core](/aspnet/core): es un marco web moderno basado en .NET Core, por lo que ofrece a los desarrolladores las mismas ventajas.
* [Plataforma universal de Windows](https://blogs.msdn.microsoft.com/dotnet/2014/04/24/net-native-performance): mejora el rendimiento de las aplicaciones de la Tienda Windows que se ejecutan en máquinas ARM y x64 mediante la compilación estática de .NET Native. 
* .NET Core + extensiones de plataforma: incluye las API de .NET Core además de otras API del ecosistema de .NET, como WCF, ASP.NET Core, FSharp y Azure.
* .NET Standard + extensiones de plataforma: incluye las API de .NET Standard además de otro ecosistema de .NET, como WCF, ASP.NET Core, FSharp y Azure.

## <a name="how-to-use-portability-analyzer"></a>Cómo usar el Analizador de portabilidad

Para empezar a usar el Analizador de portabilidad. de NET, primero debe descargar e instalar la extensión desde [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer). Funciona en Visual Studio 2015 y Visual Studio 2017. Puede configurarlo en Visual Studio en **Analizar** > **Portability Analyzer Settings** (Configuración del Analizador de portabilidad) y seleccionar las plataformas de destino.

![Captura de pantalla de la portabilidad](./media/portability-analyzer/portability-screenshot.png)

Para analizar todo el proyecto, haga clic con el botón derecho en el proyecto en **Explorador de soluciones** y seleccione **Analyze Assembly Portability** (Analizar la portabilidad del ensamblado). También puede ir al menú **Analizar** y seleccionar **Analyze Assembly Portability** (Analizar la portabilidad del ensamblado). Desde allí, seleccione el ejecutable o .dll del proyecto.

![Explorador de soluciones de portabilidad](./media/portability-analyzer/portability-solution-explorer.png)

Después de ejecutar el análisis, verá un informe de portabilidad de .NET. Solo aparecen en la lista los tipos que no son compatibles con una plataforma de destino. Puede revisar las recomendaciones en la pestaña **Mensajes** de la **Lista de errores**. También puede saltar a áreas problemáticas directamente desde la pestaña **Mensajes**.

![Informe de portabilidad](./media/portability-analyzer/portability-report.png)

¿No quiere usar Visual Studio? También puede usar el Analizador de portabilidad desde el símbolo del sistema. Simplemente descargue la [API del Analizador de portabilidad](http://www.microsoft.com/download/details.aspx?id=42678).

*   Escriba el comando siguiente para analizar el directorio actual: `\...\ApiPort.exe analyze -f .`
*   Para analizar una lista específica de archivos .dll, escriba el comando siguiente: `\...\ApiPort.exe analyze -f first.dll -f second.dll -f third.dll`

El informe de portabilidad de .NET se guarda como un archivo *.xlsx* de Excel en el directorio actual. La pestaña **Detalles** del libro de Excel contiene más información.

Para obtener más información sobre el Analizador de portabilidad de .NET, visite la [documentación de GitHub](https://github.com/Microsoft/dotnet-apiport#documentation) y el vídeo de Channel 9 [A Brief Look at the .NET Portability Analyzer](https://channel9.msdn.com/Blogs/Seth-Juarez/A-Brief-Look-at-the-NET-Portability-Analyzer) (Información breve sobre el Analizador de portabilidad de .NET).
