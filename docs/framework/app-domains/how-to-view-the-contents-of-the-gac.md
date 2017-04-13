---
title: "C&#243;mo: Consultar el contenido de la memoria cach&#233; global de ensamblados | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ensamblados [.NET Framework], caché global de ensamblados"
  - "GAC (caché global de ensamblados), ver contenido"
  - "Gacutil.exe"
  - "Caché global de ensamblados (herramienta)"
  - "caché global de ensamblados, ver contenido"
  - "lista de ensamblados de caché global de ensamblados"
  - "ensamblados con nombre seguro, caché global de ensamblados"
  - "ver ensamblados en caché global de ensamblados"
ms.assetid: c5f786a0-969b-4f14-9f02-e77c3384d9af
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# C&#243;mo: Consultar el contenido de la memoria cach&#233; global de ensamblados
Use la [herramienta Caché global de ensamblados \(Gacutil.exe\)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) para ver el contenido de la caché global de ensamblados.  
  
### Para ver una lista de los ensamblados de la caché global de ensamblados  
  
1.  En el [símbolo del sistema de Visual Studio](../../../docs/framework/tools/developer-command-prompt-for-vs.md), escriba el siguiente comando:  
  
     **gacutil \-l**   
     O bien               
     **gacutil \/l**  
  
 En versiones anteriores de .NET Framework, la extensión [Shfusion.dll](http://msdn.microsoft.com/es-es/0d9464cf-ddba-4ca9-bbec-f678fb58f380) del shell de Windows permitía ver la memoria caché global de ensamblados en el Explorador de archivos.  A partir de [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], Shfusion.dll está obsoleto.  
  
## Vea también  
 [Trabajar con ensamblados y la memoria caché global de ensamblados](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)   
 [Gacutil.exe \(Global Assembly Cache Tool\)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)