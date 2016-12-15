---
title: "El tipo &#39;&lt;nombredetipo&gt;&#39; no tiene ning&#250;n constructor | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc30251"
  - "vbc30251"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30251"
ms.assetid: aff3e1df-abe6-4bc0-9abc-a1e70514c561
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# El tipo &#39;&lt;nombredetipo&gt;&#39; no tiene ning&#250;n constructor
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Un tipo no admite una llamada a `Sub New()`.  Una causa probable puede ser un archivo binario o un compilador dañado.  
  
 **Identificador del error:** BC30251  
  
### Para corregir este error  
  
1.  Si el tipo está en proyecto distinto o en un archivo al que se hace referencia, reinstale el proyecto o archivo en cuestión.  
  
2.  Si el tipo se encuentra en el mismo proyecto, vuelva a compilar el ensamblado que contiene dicho tipo.  
  
3.  Si el error se repite, reinstale el compilador de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
4.  Si el error persiste, reúna información sobre las circunstancias y notifíquelo a los Servicios de soporte técnico de Microsoft.  
  
## Vea también  
 [Objetos y clases](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)   
 [Hable con nosotros](/visual-studio/ide/talk-to-us)