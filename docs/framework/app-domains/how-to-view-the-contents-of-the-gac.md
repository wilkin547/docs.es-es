---
title: Procedimiento para consultar el contenido de la caché global de ensamblados
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c319c5f7c9bb808b2ce7ee10178722287e456339
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2019
ms.locfileid: "66486428"
---
# <a name="how-to-view-the-contents-of-the-global-assembly-cache"></a><span data-ttu-id="749d8-102">Procedimiento para consultar el contenido de la caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="749d8-102">How to: View the contents of the global assembly cache</span></span>

<span data-ttu-id="749d8-103">Use la [herramienta de caché global de ensamblados (gacutil.exe)](../tools/gacutil-exe-gac-tool.md) para ver el contenido de la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="749d8-103">Use the [global assembly cache tool (gacutil.exe)](../tools/gacutil-exe-gac-tool.md) to view the contents of the global assembly cache (GAC).</span></span>

## <a name="view-the-assemblies-in-the-gac"></a><span data-ttu-id="749d8-104">Ver los ensamblados en la caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="749d8-104">View the assemblies in the GAC</span></span>

<span data-ttu-id="749d8-105">Para ver una lista de los ensamblados en la caché global de ensamblados, abra el [Símbolo del sistema para desarrolladores de Visual Studio](../tools/developer-command-prompt-for-vs.md) y, a continuación, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="749d8-105">To view a list of the assemblies in the global assembly cache, open [Developer Command Prompt for Visual Studio](../tools/developer-command-prompt-for-vs.md), and then enter the following command:</span></span>

```shell
gacutil -l
```

<span data-ttu-id="749d8-106">o bien</span><span class="sxs-lookup"><span data-stu-id="749d8-106">-or-</span></span>

```shell
gacutil /l
```

> [!NOTE]
> <span data-ttu-id="749d8-107">En versiones anteriores de .NET Framework, la extensión [Shfusion.dll](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/34149zk3(v=vs.100)) del shell de Windows permitía ver la caché global de ensamblados en el Explorador de archivos.</span><span class="sxs-lookup"><span data-stu-id="749d8-107">In earlier versions of the .NET Framework, the [Shfusion.dll](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/34149zk3(v=vs.100)) Windows shell extension enabled you to view the global assembly cache in File Explorer.</span></span> <span data-ttu-id="749d8-108">A partir de .NET Framework 4, Shfusion.dll está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="749d8-108">Beginning with the .NET Framework 4, Shfusion.dll is obsolete.</span></span>

## <a name="see-also"></a><span data-ttu-id="749d8-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="749d8-109">See also</span></span>

- [<span data-ttu-id="749d8-110">Trabajar con ensamblados y la memoria caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="749d8-110">Working with Assemblies and the Global Assembly Cache</span></span>](working-with-assemblies-and-the-gac.md)
- [<span data-ttu-id="749d8-111">Gacutil.exe (Herramienta Caché global de ensamblados)</span><span class="sxs-lookup"><span data-stu-id="749d8-111">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../tools/gacutil-exe-gac-tool.md)
