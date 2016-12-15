---
title: "Ya no se admiten instrucciones &#39;Line&#39; (error del compilador de Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc30830"
  - "vbc30830"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30830"
ms.assetid: 4734bc1d-882e-4555-b498-1f1ec0399d16
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Ya no se admiten instrucciones &#39;Line&#39; (error del compilador de Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Ya no se admiten las instrucciones Line.  La funcionalidad de E\/S de archivos está disponible como `Microsoft.VisualBasic.FileSystem.LineInput` y la funcionalidad de gráficos está disponible como `System.Drawing.Graphics.DrawLine`.  
  
 **Identificador de error:** BC30830  
  
### Para corregir este error  
  
1.  Si está ejecutando un acceso a archivos, utilice `Microsoft.VisualBasic.FileSystem.LineInput`.  
  
2.  Si está ejecutando gráficos, utilice `System.Drawing.Graphics.Drawline`.  
  
## Vea también  
 <xref:System.IO>   
 <xref:System.Drawing>   
 [Acceso a archivos con Visual Basic](../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)