---
title: Herramientas para la portabilidad a .NET Core
description: Más información sobre algunas de las herramientas que puede usar para realizar la portabilidad a .NET Core
author: cartermp
ms.date: 05/03/2020
ms.openlocfilehash: b8678ec72fe5d910d5f8cff4768106e7496f9276
ms.sourcegitcommit: 1274a1a4a4c7e2eaf56b38da76ef7cec789726ef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2020
ms.locfileid: "91406133"
---
# <a name="tools-to-help-with-porting-to-net-core"></a><span data-ttu-id="8087b-103">Herramientas útiles para la portabilidad a .NET Core</span><span class="sxs-lookup"><span data-stu-id="8087b-103">Tools to help with porting to .NET Core</span></span>

<span data-ttu-id="8087b-104">Las herramientas enumeradas en este artículo pueden ser útiles cuando realice la portabilidad:</span><span class="sxs-lookup"><span data-stu-id="8087b-104">You may find the tools listed in this article helpful when porting:</span></span>

- <span data-ttu-id="8087b-105">[Analizador de portabilidad de .NET](../../standard/analyzers/portability-analyzer.md): una cadena de herramientas que puede generar un informe de portabilidad del código entre .NET Framework y .NET Core:</span><span class="sxs-lookup"><span data-stu-id="8087b-105">[.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) - A toolchain that can generate a report of how portable your code is between .NET Framework and .NET Core:</span></span>
  - <span data-ttu-id="8087b-106">Como una [herramienta de línea de comandos](https://github.com/Microsoft/dotnet-apiport/releases)</span><span class="sxs-lookup"><span data-stu-id="8087b-106">As a [command-line tool](https://github.com/Microsoft/dotnet-apiport/releases)</span></span>
  - <span data-ttu-id="8087b-107">Como una [extensión de Visual Studio](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)</span><span class="sxs-lookup"><span data-stu-id="8087b-107">As a [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)</span></span>
- <span data-ttu-id="8087b-108">[Analizador de compatibilidad de plataformas](../../standard/analyzers/platform-compat-analyzer.md): analizador de Roslyn que informa a los desarrolladores cuando usan API específicas de la plataforma desde sitios de llamada en los que es posible que la API no esté disponible.</span><span class="sxs-lookup"><span data-stu-id="8087b-108">[Platform compatibility analyzer](../../standard/analyzers/platform-compat-analyzer.md) - A Roslyn analyzer that informs developers when they use platform-specific APIs from call sites where the API might not be available.</span></span>
- <span data-ttu-id="8087b-109">[Analizador de API de .NET](../../standard/analyzers/api-analyzer.md): un analizador de Roslyn que puede ayudar a detectar problemas de compatibilidad de plataformas en aplicaciones y bibliotecas multiplataforma.</span><span class="sxs-lookup"><span data-stu-id="8087b-109">[.NET API analyzer](../../standard/analyzers/api-analyzer.md) - A Roslyn analyzer that can help detect platform compatibility issues in cross-platform apps and libraries.</span></span>
- <span data-ttu-id="8087b-110">[try-Convert](https://www.nuget.org/packages/try-convert/): herramienta global de .NET Core que puede convertir un proyecto o una solución completa en el SDK de .NET, así como trasladar aplicaciones de escritorio a .NET Core.</span><span class="sxs-lookup"><span data-stu-id="8087b-110">[try-convert](https://www.nuget.org/packages/try-convert/) - A .NET Core global tool that can convert a project or entire solution to the .NET SDK, including moving desktop apps to .NET Core.</span></span> <span data-ttu-id="8087b-111">No se recomienda si tiene establecida una compilación más complicada (como tareas personalizadas, destinos o importaciones); rechaza muchos tipos de proyecto que no son compatibles con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="8087b-111">It is not recommended if you have a more complicated build established (such as custom tasks, targets, or imports), and it rejects many project types that are incompatible with .NET Core.</span></span>
