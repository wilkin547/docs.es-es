---
title: "Cómo: Consultar el contenido de la caché global de ensamblados | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
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
caps.latest.revision: 15
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 9f51fbaddf7de524a0025e87aa598726fc6f1db4
ms.contentlocale: es-es
ms.lasthandoff: 06/02/2017

---
# <a name="how-to-view-the-contents-of-the-global-assembly-cache"></a>Cómo: Consultar el contenido de la memoria caché global de ensamblados
Use la [herramienta Caché global de ensamblados (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) para ver el contenido de la caché global de ensamblados.  
  
### <a name="to-view-a-list-of-the-assemblies-in-the-global-assembly-cache"></a>Para ver una lista de los ensamblados de la caché global de ensamblados  
  
1.  En el [símbolo del sistema de Visual Studio](../../../docs/framework/tools/developer-command-prompt-for-vs.md), escriba el comando siguiente:  
  
     **gacutil -l**   
     O bien  
    **gacutil /l**  
  
 En versiones anteriores de .NET Framework, la extensión [Shfusion.dll](http://msdn.microsoft.com/en-us/0d9464cf-ddba-4ca9-bbec-f678fb58f380) del shell de Windows permitía ver la caché global de ensamblados en el Explorador de archivos. A partir de [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], Shfusion.dll está obsoleto.  
  
## <a name="see-also"></a>Vea también  
 [Trabajar con ensamblados y la memoria caché global de ensamblados](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)   
 [Gacutil.exe (Herramienta Caché global de ensamblados)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)
