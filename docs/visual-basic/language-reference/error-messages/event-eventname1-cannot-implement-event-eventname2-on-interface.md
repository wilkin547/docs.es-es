---
title: "El evento &#39;&lt;nombreDeEvento1&gt;&#39; no puede implementar el evento &#39;&lt;nombreDeEvento2&gt;&#39; en la interfaz &#39;&lt;interfaz&gt;&#39; porque sus tipos delegados &#39;&lt;delegado1&gt;&#39; y &#39;&lt;delegado2&gt;&#39; no coinciden | Microsoft Docs"
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
  - "vbc31423"
  - "bc31423"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC31423"
ms.assetid: 2e754b66-5836-48ff-9697-b9c0d7085f18
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# El evento &#39;&lt;nombreDeEvento1&gt;&#39; no puede implementar el evento &#39;&lt;nombreDeEvento2&gt;&#39; en la interfaz &#39;&lt;interfaz&gt;&#39; porque sus tipos delegados &#39;&lt;delegado1&gt;&#39; y &#39;&lt;delegado2&gt;&#39; no coinciden
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] no puede implementar un evento porque el tipo delegado del evento no coincide con el tipo delegado del evento de la interfaz.  Este error se puede producir al definir múltiples eventos en una interfaz e intentar implementarlos en el mismo evento.  Un evento puede implementar dos o más eventos sólo si se declaran todos los eventos implementados con la sintaxis `As` y se especifica el mismo tipo delegado.  
  
 **Identificador de error:** BC31423  
  
### Para corregir este error  
  
-   Implemente los eventos por separado.  
  
     \-O bien\-  
  
-   Defina los eventos en la interfaz mediante la sintaxis `As` y especifique el mismo tipo delegado.  
  
## Vea también  
 [Event \(Instrucción\)](../../../visual-basic/language-reference/statements/event-statement.md)   
 [Delegate \(Instrucción\)](../../../visual-basic/language-reference/statements/delegate-statement.md)   
 [Eventos](../../../visual-basic/programming-guide/language-features/events/events.md)