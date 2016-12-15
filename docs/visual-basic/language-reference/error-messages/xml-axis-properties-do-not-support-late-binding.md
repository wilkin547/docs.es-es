---
title: "Las propiedades del eje XML no admiten enlace en tiempo de ejecuci&#243;n | Microsoft Docs"
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
  - "bc31168"
  - "vbc31168"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC31168"
ms.assetid: 45707363-55e4-4151-892d-d8729106355b
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Las propiedades del eje XML no admiten enlace en tiempo de ejecuci&#243;n
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Se ha hecho referencia a una propiedad de eje XML para un objeto sin tipo.  
  
 **Id. de error:** BC31168  
  
### Para corregir este error  
  
-   Asegúrese de que el objeto es un objeto <xref:System.Xml.Linq.XElement> con establecimiento inflexible de tipos antes de hacer referencia a la propiedad de eje XML.  
  
## Vea también  
 [Propiedades de eje XML](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)   
 [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)