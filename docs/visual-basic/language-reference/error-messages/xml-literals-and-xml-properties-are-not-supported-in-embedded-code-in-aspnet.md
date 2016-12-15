---
title: "No se admiten literales XML ni propiedades XML en c&#243;digo incrustado en ASP.NET | Microsoft Docs"
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
  - "vbc31200"
  - "bc31200"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC31200"
ms.assetid: 053e8cba-8584-45cc-9fa0-43d122779772
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# No se admiten literales XML ni propiedades XML en c&#243;digo incrustado en ASP.NET
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

No se admiten literales XML ni propiedades XML en el código incrustado en ASP.NET.Para usar características XML, mueva el código a código subyacente.  
  
 Se ha definido un literal XML o la propiedad de eje XML dentro del código incrustado \(`<%= =>`\) en un archivo ASP.NET.  
  
 **Id. de error:** BC31200  
  
### Para corregir este error  
  
-   Mueva el código que incluye el literal XML o la propiedad de eje XML a un archivo de código subyacente de ASP.NET.  
  
## Vea también  
 [Literales XML](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Propiedades de eje XML](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)   
 [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)