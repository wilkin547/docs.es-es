---
title: "Cómo: Consultar el contenido de la memoria caché global de ensamblados"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: db5714c6669ac5fbdfd81656aa7659fdde05922a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-view-the-contents-of-the-global-assembly-cache"></a><span data-ttu-id="41850-102">Cómo: Consultar el contenido de la memoria caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="41850-102">How to: View the Contents of the Global Assembly Cache</span></span>
<span data-ttu-id="41850-103">Use la [herramienta Caché global de ensamblados (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) para ver el contenido de la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="41850-103">Use the [Global Assembly Cache tool (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) to view the contents of the global assembly cache.</span></span>  
  
### <a name="to-view-a-list-of-the-assemblies-in-the-global-assembly-cache"></a><span data-ttu-id="41850-104">Para ver una lista de los ensamblados de la caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="41850-104">To view a list of the assemblies in the global assembly cache</span></span>  
  
1.  <span data-ttu-id="41850-105">En el [símbolo del sistema de Visual Studio](../../../docs/framework/tools/developer-command-prompt-for-vs.md), escriba el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="41850-105">At the [Visual Studio command prompt](../../../docs/framework/tools/developer-command-prompt-for-vs.md), type the following command:</span></span>  
  
     <span data-ttu-id="41850-106">**gacutil -l** </span><span class="sxs-lookup"><span data-stu-id="41850-106">**gacutil -l** </span></span>  
     <span data-ttu-id="41850-107">O bien</span><span class="sxs-lookup"><span data-stu-id="41850-107">-or-</span></span>  
    <span data-ttu-id="41850-108">**gacutil /l**</span><span class="sxs-lookup"><span data-stu-id="41850-108">**gacutil /l**</span></span>  
  
 <span data-ttu-id="41850-109">En versiones anteriores de .NET Framework, la extensión [Shfusion.dll](http://msdn.microsoft.com/en-us/0d9464cf-ddba-4ca9-bbec-f678fb58f380) del shell de Windows permitía ver la caché global de ensamblados en el Explorador de archivos.</span><span class="sxs-lookup"><span data-stu-id="41850-109">In earlier versions of the .NET Framework, the [Shfusion.dll](http://msdn.microsoft.com/en-us/0d9464cf-ddba-4ca9-bbec-f678fb58f380) Windows shell extension enabled you to view the global assembly cache in File Explorer.</span></span> <span data-ttu-id="41850-110">A partir de [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], Shfusion.dll está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="41850-110">Beginning with the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], Shfusion.dll is obsolete.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41850-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="41850-111">See Also</span></span>  
 [<span data-ttu-id="41850-112">Trabajar con ensamblados y la memoria caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="41850-112">Working with Assemblies and the Global Assembly Cache</span></span>](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)  
 [<span data-ttu-id="41850-113">Gacutil.exe (Herramienta Caché global de ensamblados)</span><span class="sxs-lookup"><span data-stu-id="41850-113">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../../../docs/framework/tools/gacutil-exe-gac-tool.md)
