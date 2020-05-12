---
title: Herramientas para la portabilidad a .NET Core
description: Más información sobre algunas de las herramientas que puede usar para realizar la portabilidad a .NET Core
author: cartermp
ms.date: 05/03/2020
ms.openlocfilehash: d0cf0abf206950beb34556ca3ba7243d8cad241e
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795591"
---
# <a name="tools-to-help-with-porting-to-net-core"></a><span data-ttu-id="196d1-103">Herramientas útiles para la portabilidad a .NET Core</span><span class="sxs-lookup"><span data-stu-id="196d1-103">Tools to help with porting to .NET Core</span></span>

<span data-ttu-id="196d1-104">Las herramientas enumeradas en este artículo pueden ser útiles cuando realice la portabilidad:</span><span class="sxs-lookup"><span data-stu-id="196d1-104">You may find the tools listed in this article helpful when porting:</span></span>

- <span data-ttu-id="196d1-105">[Analizador de portabilidad de .NET](../../standard/analyzers/portability-analyzer.md): una cadena de herramientas que puede generar un informe de portabilidad del código entre .NET Framework y .NET Core:</span><span class="sxs-lookup"><span data-stu-id="196d1-105">[.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) - A toolchain that can generate a report of how portable your code is between .NET Framework and .NET Core:</span></span>
  - <span data-ttu-id="196d1-106">Como una [herramienta de línea de comandos](https://github.com/Microsoft/dotnet-apiport/releases)</span><span class="sxs-lookup"><span data-stu-id="196d1-106">As a [command-line tool](https://github.com/Microsoft/dotnet-apiport/releases)</span></span>
  - <span data-ttu-id="196d1-107">Como una [extensión de Visual Studio](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)</span><span class="sxs-lookup"><span data-stu-id="196d1-107">As a [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)</span></span>
- <span data-ttu-id="196d1-108">[Analizador de API en .NET](../../standard/analyzers/api-analyzer.md): un analizador de Roslyn que detecta posibles riesgos de compatibilidad de las API de C# en distintas plataformas y detecta llamadas a API en desuso.</span><span class="sxs-lookup"><span data-stu-id="196d1-108">[.NET API analyzer](../../standard/analyzers/api-analyzer.md) - A Roslyn analyzer that discovers potential compatibility risks for C# APIs on different platforms and detects calls to deprecated APIs.</span></span>
- <span data-ttu-id="196d1-109">[try-Convert](https://www.nuget.org/packages/try-convert/): herramienta global de .NET Core que puede convertir un proyecto o una solución completa en el SDK de .NET, así como trasladar aplicaciones de escritorio a .NET Core.</span><span class="sxs-lookup"><span data-stu-id="196d1-109">[try-convert](https://www.nuget.org/packages/try-convert/) - A .NET Core global tool that can convert a project or entire solution to the .NET SDK, including moving desktop apps to .NET Core.</span></span> <span data-ttu-id="196d1-110">No se recomienda si tiene establecida una compilación más complicada (como tareas personalizadas, destinos o importaciones); rechaza muchos tipos de proyecto que no son compatibles con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="196d1-110">It is not recommended if you have a more complicated build established (such as custom tasks, targets, or imports), and it rejects many project types that are incompatible with .NET Core.</span></span>
