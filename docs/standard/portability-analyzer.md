---
title: Analizador de portabilidad de .NET | .NET
description: "Obtenga información sobre cómo usar la herramienta Analizador de portabilidad de .NET para evaluar la portabilidad de su código entre las diferentes plataformas de .NET."
keywords: .NET, .NET Core
author: blackdwarf
ms.author: mairaw
manager: wpickett
ms.date: 07/05/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 0375250f-5704-4993-a6d5-e21c499cea1e
translationtype: Human Translation
ms.sourcegitcommit: 8599be1eadcd6f005ef344bf173e8c06fce80725
ms.openlocfilehash: 9e35fd4dff15cec688ee11f98682eb7cb96e9403

---

# <a name="the-net-portability-analyzer"></a>Analizador de portabilidad de .NET

¿Quiere que sus bibliotecas sean multiplataforma? ¿Quiere ver cuánto trabajo se requiere para que su aplicación sea compatible con otras plataformas de .NET? El [Analizador de portabilidad de .NET](http://go.microsoft.com/fwlink/?LinkID=507467) es una herramienta que le proporciona un informe detallado sobre el grado de flexibilidad de su programa en las plataformas de .NET mediante el análisis de ensamblados. El Analizador de portabilidad se ofrece como extensión de Visual Studio y como aplicación de consola.

## <a name="new-targets"></a>Nuevos destinos

*   [.NET Core](https://www.dotnetfoundation.org/netcore): tiene un diseño modular, emplea el modo en paralelo y tiene como destino escenarios multiplataforma. El modo en paralelo permite adoptar nuevas versiones de .NET Core sin que ello afecte a otras aplicaciones.
*   [ASP.NET Core](https://www.dotnetfoundation.org/aspnet-core): es un marco web moderno basado en .NET Core, por lo que ofrece a los desarrolladores las mismas ventajas.
*   [.NET Native](https://blogs.msdn.microsoft.com/dotnet/2014/04/24/net-native-performance): mejora el rendimiento de las aplicaciones de la Tienda Windows que se ejecutan en máquinas ARM y x64 mediante la compilación estática de .NET Native.

## <a name="how-to-use-portability-analyzer"></a>Cómo usar el Analizador de portabilidad

Para empezar a usar el Analizador de portabilidad. de NET, primero debe descargar e instalar la extensión de la [Galería de Visual Studio](http://go.microsoft.com/fwlink/?LinkID=507467). Puede configurarla en Visual Studio en **Herramientas** > **Opciones** > **.NET Portability Analyzer (Analizador de portabilidad de .NET** y seleccionar las plataformas de destino. Por ahora, use ASP.NET Core como proxy para todas las plataformas basadas en .NET Core (por ejemplo, [aplicaciones UAP de .NET de Windows 10](http://blogs.windows.com/buildingapps/2015/03/02/a-first-look-at-the-windows-10-universal-app-platform/)).

![Captura de pantalla de la portabilidad](./media/portability-analyzer/portability-screenshot.png)

Para analizar todo el proyecto, haga clic con el botón derecho en el proyecto en **Explorador de soluciones** y seleccione **Analizar** > **Analizar la portabilidad del ensamblado**. También puede ir al menú **Analizar** y seleccionar **Analyze Assembly Portability** (Analizar la portabilidad del ensamblado). Desde allí, seleccione el ejecutable o .dll del proyecto.

![Explorador de soluciones de portabilidad](./media/portability-analyzer/portability-solution-explorer.png)

Después de ejecutar el análisis, verá un informe de portabilidad de .NET. Solo aparecerán en la lista los tipos que no son compatibles con una plataforma de destino. Puede revisar las recomendaciones en la pestaña **Mensajes** de la **Lista de errores**. También puede saltar a áreas problemáticas directamente desde la pestaña **Mensajes**.

![Informe de portabilidad](./media/portability-analyzer/portability-report.png)

¿No quiere usar Visual Studio? También puede usar el Analizador de portabilidad desde el símbolo del sistema. Simplemente descargue la [API del Analizador de portabilidad](http://www.microsoft.com/download/details.aspx?id=42678).

*   Escriba el comando siguiente para analizar el directorio actual: `\...\ApiPort.exe .`
*   Para analizar una lista específica de archivos .dll, escriba el comando siguiente: `\...\ApiPort.exe first.dll second.dll third.dll`

El informe de portabilidad de .NET se guardará como un archivo *.xlsx* de Excel en el directorio actual. La pestaña **Detalles** del libro de Excel contiene más información.

Para obtener más información sobre el Analizador de portabilidad. de NET, vea el artículo [Utilización del código existente entre plataformas .NET](https://blogs.msdn.microsoft.com/dotnet/2014/08/06/leveraging-existing-code-across-net-platforms/) en el blog de .NET.



<!--HONumber=Nov16_HO3-->


