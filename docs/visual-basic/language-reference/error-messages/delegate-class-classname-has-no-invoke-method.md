---
title: "La clase delegada &#39;&lt;nombredeclase&gt;&#39; no tiene ning&#250;n m&#233;todo Invoke y, por tanto, una expresi&#243;n de este tipo no puede ser el destino de una llamada a m&#233;todo | Microsoft Docs"
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
  - "vbc30220"
  - "bc30220"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30220"
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# La clase delegada &#39;&lt;nombredeclase&gt;&#39; no tiene ning&#250;n m&#233;todo Invoke y, por tanto, una expresi&#243;n de este tipo no puede ser el destino de una llamada a m&#233;todo
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Hubo un error en la llamada a `Invoke` a través de un delegado, ya que `Invoke` no está implementada en la clase de delegado.  
  
 **Identificador de error:** BC30220  
  
### Para corregir este error  
  
1.  Asegúrese de que se haya creado una instancia de la clase de delegado con una instrucción `Dim` y se haya asignado un procedimiento a la instancia de delegado con el operador `AddressOf`.  
  
2.  Busque el código que implementa la clase de delegado y asegúrese de que implementa el procedimiento `Invoke`.  
  
## Vea también  
 [Delegados](../../../visual-basic/programming-guide/language-features/delegates/delegates.md)   
 [Delegate \(Instrucción\)](../../../visual-basic/language-reference/statements/delegate-statement.md)   
 [AddressOf \(Operador\)](../../../visual-basic/language-reference/operators/addressof-operator.md)   
 [Dim \(Instrucción\)](../../../visual-basic/language-reference/statements/dim-statement.md)