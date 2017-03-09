---
title: "No se pueden combinar SimplifiedChinese y VbStrConv.TraditionalChinese | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrArgument_StrConvSCandTC"
ms.assetid: d8e6a11b-f549-43b5-8337-0594340e1325
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# No se pueden combinar SimplifiedChinese y VbStrConv.TraditionalChinese
La aplicación está intentando combinar los `VbStrConv` miembros de la enumeración `SimplifiedChinese` y `TraditionalChinese`, que son mutuamente excluyentes.  
  
### Para corregir este error  
  
-   Quite  `VbStrConv.SimplifiedChinese` o `VbStrConv.TraditionalChinese`.  
  
## Vea también  
 <xref:System.Globalization>   
 [NOTINBUILD: Enumeración VbStrConv](http://msdn.microsoft.com/es-es/59f83dd9-6361-47df-a836-02ba9d4cb936)   
 [Introducción a aplicaciones internacionales basadas en .NET Framework](/visual-studio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)