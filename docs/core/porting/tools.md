---
title: Herramientas para la portabilidad a .NET Core
description: Más información sobre algunas de las herramientas que puede usar para realizar la portabilidad a .NET Core
author: cartermp
ms.date: 12/07/2018
ms.openlocfilehash: 3b71c31b4f26b278b2bd1088adc8e9f64d28ab7b
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215195"
---
# <a name="tools-to-help-with-porting-to-net-core"></a><span data-ttu-id="4716c-103">Herramientas útiles para la portabilidad a .NET Core</span><span class="sxs-lookup"><span data-stu-id="4716c-103">Tools to help with porting to .NET Core</span></span>

<span data-ttu-id="4716c-104">Las herramientas enumeradas en este artículo pueden ser útiles cuando realice la portabilidad:</span><span class="sxs-lookup"><span data-stu-id="4716c-104">You may find the tools listed in this article helpful when porting:</span></span>

- <span data-ttu-id="4716c-105">[Analizador de portabilidad de .NET](../../standard/analyzers/portability-analyzer.md): una cadena de herramientas que puede generar un informe de portabilidad del código entre .NET Framework y .NET Core:</span><span class="sxs-lookup"><span data-stu-id="4716c-105">[.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) - A toolchain that can generate a report of how portable your code is between .NET Framework and .NET Core:</span></span>
  - <span data-ttu-id="4716c-106">Como una [herramienta de línea de comandos](https://github.com/Microsoft/dotnet-apiport/releases)</span><span class="sxs-lookup"><span data-stu-id="4716c-106">As a [command-line tool](https://github.com/Microsoft/dotnet-apiport/releases)</span></span>
  - <span data-ttu-id="4716c-107">Como una [extensión de Visual Studio](https://visualstudiogallery.msdn.microsoft.com/1177943e-cfb7-4822-a8a6-e56c7905292b)</span><span class="sxs-lookup"><span data-stu-id="4716c-107">As a [Visual Studio extension](https://visualstudiogallery.msdn.microsoft.com/1177943e-cfb7-4822-a8a6-e56c7905292b)</span></span>
- <span data-ttu-id="4716c-108">[Analizador de API en .NET](../../standard/analyzers/api-analyzer.md): un analizador de Roslyn que detecta posibles riesgos de compatibilidad de las API de C# en distintas plataformas y detecta llamadas a API en desuso.</span><span class="sxs-lookup"><span data-stu-id="4716c-108">[.NET API analyzer](../../standard/analyzers/api-analyzer.md) - A Roslyn analyzer that discovers potential compatibility risks for C# APIs on different platforms and detects calls to deprecated APIs.</span></span>

<span data-ttu-id="4716c-109">Además, puede intentar portar soluciones más pequeñas o proyectos individuales en el formato de archivo de proyecto de .NET Core con la herramienta [CsprojToVs2017](https://github.com/hvanbakel/CsprojToVs2017).</span><span class="sxs-lookup"><span data-stu-id="4716c-109">Additionally, you can attempt to port smaller solutions or individual projects to the .NET Core project file format with the [CsprojToVs2017](https://github.com/hvanbakel/CsprojToVs2017) tool.</span></span>

> [!WARNING] 
> <span data-ttu-id="4716c-110">CsprojToVs2017 es una herramienta de terceros.</span><span class="sxs-lookup"><span data-stu-id="4716c-110">CsprojToVs2017 is a third-party tool.</span></span> <span data-ttu-id="4716c-111">No hay ninguna garantía de que funcione con todos los proyectos, y podría provocar cambios sutiles de comportamiento de los que dependa.</span><span class="sxs-lookup"><span data-stu-id="4716c-111">There is no guarantee that it will work for all of your projects, and it may cause subtle changes in behavior that you depend on.</span></span> <span data-ttu-id="4716c-112">CsprojToVs2017 debe usarse como _punto de partida_ que automatiza los elementos básicos que se pueden automatizar.</span><span class="sxs-lookup"><span data-stu-id="4716c-112">CsprojToVs2017 should be used as a _starting point_ that automates the basic things that can be automated.</span></span> <span data-ttu-id="4716c-113">No es una solución que se garantice para migrar formatos de archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="4716c-113">It is not a guaranteed solution to migrating project file formats.</span></span>
