---
title: 'Cómo: Consultar el contenido de la memoria caché global de ensamblados'
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
ms.openlocfilehash: 3650de934cb3d2940d0e8e971d03aff856bddfd7
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2018
ms.locfileid: "43394470"
---
# <a name="how-to-view-the-contents-of-the-global-assembly-cache"></a><span data-ttu-id="1aa74-102">Cómo: Consultar el contenido de la memoria caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="1aa74-102">How to: View the Contents of the Global Assembly Cache</span></span>
<span data-ttu-id="1aa74-103">Use la [herramienta Caché global de ensamblados (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) para ver el contenido de la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="1aa74-103">Use the [Global Assembly Cache tool (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) to view the contents of the global assembly cache.</span></span>  
  
### <a name="to-view-a-list-of-the-assemblies-in-the-global-assembly-cache"></a><span data-ttu-id="1aa74-104">Para ver una lista de los ensamblados de la caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="1aa74-104">To view a list of the assemblies in the global assembly cache</span></span>  
  
1.  <span data-ttu-id="1aa74-105">En el [símbolo del sistema de Visual Studio](../../../docs/framework/tools/developer-command-prompt-for-vs.md), escriba el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="1aa74-105">At the [Visual Studio command prompt](../../../docs/framework/tools/developer-command-prompt-for-vs.md), type the following command:</span></span>  
  
     <span data-ttu-id="1aa74-106">**gacutil -l** </span><span class="sxs-lookup"><span data-stu-id="1aa74-106">**gacutil -l** </span></span>  
     <span data-ttu-id="1aa74-107">O bien</span><span class="sxs-lookup"><span data-stu-id="1aa74-107">-or-</span></span>  
    <span data-ttu-id="1aa74-108">**gacutil /l**</span><span class="sxs-lookup"><span data-stu-id="1aa74-108">**gacutil /l**</span></span>  
  
 <span data-ttu-id="1aa74-109">En versiones anteriores de .NET Framework, la extensión [Shfusion.dll](https://msdn.microsoft.com/library/0d9464cf-ddba-4ca9-bbec-f678fb58f380) del shell de Windows permitía ver la caché global de ensamblados en el Explorador de archivos.</span><span class="sxs-lookup"><span data-stu-id="1aa74-109">In earlier versions of the .NET Framework, the [Shfusion.dll](https://msdn.microsoft.com/library/0d9464cf-ddba-4ca9-bbec-f678fb58f380) Windows shell extension enabled you to view the global assembly cache in File Explorer.</span></span> <span data-ttu-id="1aa74-110">A partir de [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], Shfusion.dll está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="1aa74-110">Beginning with the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], Shfusion.dll is obsolete.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1aa74-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="1aa74-111">See Also</span></span>  
 [<span data-ttu-id="1aa74-112">Trabajar con ensamblados y la memoria caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="1aa74-112">Working with Assemblies and the Global Assembly Cache</span></span>](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)  
 [<span data-ttu-id="1aa74-113">Gacutil.exe (Herramienta Caché global de ensamblados)</span><span class="sxs-lookup"><span data-stu-id="1aa74-113">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../../../docs/framework/tools/gacutil-exe-gac-tool.md)
