---
title: Herramientas para la portabilidad a .NET Core
description: Más información sobre algunas de las herramientas que puede usar para realizar la portabilidad a .NET Core
author: cartermp
ms.author: mairaw
ms.date: 12/07/2018
ms.openlocfilehash: 0478719617741946768cfe8e220a1dd402667998
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "72521342"
---
# <a name="tools-to-help-with-porting-to-net-core"></a><span data-ttu-id="aa09b-103">Herramientas útiles para la portabilidad a .NET Core</span><span class="sxs-lookup"><span data-stu-id="aa09b-103">Tools to help with porting to .NET Core</span></span>

<span data-ttu-id="aa09b-104">Las herramientas enumeradas en este artículo pueden ser útiles cuando realice la portabilidad:</span><span class="sxs-lookup"><span data-stu-id="aa09b-104">You may find the tools listed in this article helpful when porting:</span></span>

- <span data-ttu-id="aa09b-105">[Analizador de portabilidad de .NET](../../standard/analyzers/portability-analyzer.md): una cadena de herramientas que puede generar un informe de portabilidad del código entre .NET Framework y .NET Core:  como [herramienta de línea de comandos](https://github.com/Microsoft/dotnet-apiport/releases) como [extensión de Visual Studio](https://visualstudiogallery.msdn.microsoft.com/1177943e-cfb7-4822-a8a6-e56c7905292b).</span><span class="sxs-lookup"><span data-stu-id="aa09b-105">[.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) - A toolchain that can generate a report of how portable your code is between .NET Framework and .NET Core:  As a [command-line tool](https://github.com/Microsoft/dotnet-apiport/releases) As a [Visual Studio Extension](https://visualstudiogallery.msdn.microsoft.com/1177943e-cfb7-4822-a8a6-e56c7905292b)</span></span>
- <span data-ttu-id="aa09b-106">[Analizador de API en .NET](../../standard/analyzers/api-analyzer.md): un analizador de Roslyn que detecta posibles riesgos de compatibilidad de las API de C# en distintas plataformas y detecta llamadas a API en desuso.</span><span class="sxs-lookup"><span data-stu-id="aa09b-106">[.NET API analyzer](../../standard/analyzers/api-analyzer.md) - A Roslyn analyzer that discovers potential compatibility risks for C# APIs on different platforms and detects calls to deprecated APIs.</span></span>

<span data-ttu-id="aa09b-107">Además, puede intentar portar soluciones más pequeñas o proyectos individuales en el formato de archivo de proyecto de .NET Core con la herramienta [CsprojToVs2017](https://github.com/hvanbakel/CsprojToVs2017).</span><span class="sxs-lookup"><span data-stu-id="aa09b-107">Additionally, you can attempt to port smaller solutions or individual projects to the .NET Core project file format with the [CsprojToVs2017](https://github.com/hvanbakel/CsprojToVs2017) tool.</span></span>

> [!WARNING] 
> <span data-ttu-id="aa09b-108">CsprojToVs2017 es una herramienta de terceros.</span><span class="sxs-lookup"><span data-stu-id="aa09b-108">CsprojToVs2017 is a third-party tool.</span></span> <span data-ttu-id="aa09b-109">No hay ninguna garantía de que funcione con todos los proyectos, y podría provocar cambios sutiles de comportamiento de los que dependa.</span><span class="sxs-lookup"><span data-stu-id="aa09b-109">There is no guarantee that it will work for all of your projects, and it may cause subtle changes in behavior that you depend on.</span></span> <span data-ttu-id="aa09b-110">CsprojToVs2017 debe usarse como _punto de partida_ que automatiza los elementos básicos que se pueden automatizar.</span><span class="sxs-lookup"><span data-stu-id="aa09b-110">CsprojToVs2017 should be used as a _starting point_ that automates the basic things that can be automated.</span></span> <span data-ttu-id="aa09b-111">No es una solución que se garantice para migrar formatos de archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="aa09b-111">It is not a guaranteed solution to migrating project file formats.</span></span>
