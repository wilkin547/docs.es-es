---
title: Procedimiento para consultar el contenido de la caché global de ensamblados
description: Obtenga información sobre cómo visualizar el contenido de la caché global de ensamblados en .NET mediante el uso de la herramienta de caché global de ensamblados (gacutil.exe).
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- global assembly cache, viewing contents
- viewing assemblies in global assembly cache
- Gacutil.exe
- strong-named assemblies, global assembly cache
- GAC (global assembly cache), viewing contents
- list of assemblies in global assembly cache
- Global Assembly Cache tool
ms.assetid: c5f786a0-969b-4f14-9f02-e77c3384d9af
ms.openlocfilehash: a40c371e6f95f6c90ecbfbf28183226632a58e5b
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102258317"
---
# <a name="how-to-view-the-contents-of-the-global-assembly-cache"></a><span data-ttu-id="696c4-103">Procedimiento para consultar el contenido de la caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="696c4-103">How to: View the contents of the global assembly cache</span></span>

<span data-ttu-id="696c4-104">Use la [herramienta de caché global de ensamblados (gacutil.exe)](../tools/gacutil-exe-gac-tool.md) para ver el contenido de la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="696c4-104">Use the [global assembly cache tool (gacutil.exe)](../tools/gacutil-exe-gac-tool.md) to view the contents of the global assembly cache (GAC).</span></span>

## <a name="view-the-assemblies-in-the-gac"></a><span data-ttu-id="696c4-105">Ver los ensamblados en la caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="696c4-105">View the assemblies in the GAC</span></span>

<span data-ttu-id="696c4-106">Para ver una lista de los ensamblados en la caché global de ensamblados, abra un [shell de línea de comandos para desarrolladores](/visualstudio/ide/reference/command-prompt-powershell) y, a continuación, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="696c4-106">To view a list of the assemblies in the global assembly cache, open a [command-line shell for developers](/visualstudio/ide/reference/command-prompt-powershell), and then enter the following command:</span></span>

```shell
gacutil -l
```

<span data-ttu-id="696c4-107">o bien</span><span class="sxs-lookup"><span data-stu-id="696c4-107">-or-</span></span>

```shell
gacutil /l
```

> [!NOTE]
> <span data-ttu-id="696c4-108">En versiones anteriores de .NET Framework, la extensión [Shfusion.dll](/previous-versions/dotnet/netframework-4.0/34149zk3(v=vs.100)) del shell de Windows permitía ver la caché global de ensamblados en el Explorador de archivos.</span><span class="sxs-lookup"><span data-stu-id="696c4-108">In earlier versions of .NET Framework, the [Shfusion.dll](/previous-versions/dotnet/netframework-4.0/34149zk3(v=vs.100)) Windows shell extension enabled you to view the global assembly cache in File Explorer.</span></span> <span data-ttu-id="696c4-109">A partir de .NET Framework 4, Shfusion.dll está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="696c4-109">Beginning with .NET Framework 4, Shfusion.dll is obsolete.</span></span>

## <a name="see-also"></a><span data-ttu-id="696c4-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="696c4-110">See also</span></span>

- [<span data-ttu-id="696c4-111">Trabajar con ensamblados y la memoria caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="696c4-111">Working with Assemblies and the Global Assembly Cache</span></span>](working-with-assemblies-and-the-gac.md)
- [<span data-ttu-id="696c4-112">Gacutil.exe (Herramienta Caché global de ensamblados)</span><span class="sxs-lookup"><span data-stu-id="696c4-112">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../tools/gacutil-exe-gac-tool.md)
