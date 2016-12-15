---
title: "&#39;.&#39; o &#39;!&#39; inicial s&#243;lo puede aparecer dentro de una instrucci&#243;n &#39;With&#39; | Microsoft Docs"
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
  - "vbc30157"
  - "bc30157"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30157"
ms.assetid: 70daaee1-14f9-45b7-9f30-53794310b95e
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;.&#39; o &#39;!&#39; inicial s&#243;lo puede aparecer dentro de una instrucci&#243;n &#39;With&#39;
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Aparece un punto \(.\) o signo de exclamación \(\!\) no situado dentro de un bloque `With` sin una expresión a la izquierda.  El acceso a miembros \(`.`\) y el acceso a miembros de tipo diccionario \(`!`\) requieren una expresión que especifique el elemento que contiene el miembro.  Ésta debe aparecer inmediatamente a la izquierda del descriptor de acceso o como destino de un bloque `With` que contenga el acceso a miembros.  
  
 **Identificador de error:** BC30157  
  
### Para corregir este error  
  
1.  Compruebe que el bloque `With` tiene el formato correcto.  
  
2.  Si no hay un bloque `With`, agregue una expresión a la izquierda del descriptor de acceso que se evalúe como un elemento definido que contiene el miembro.  
  
## Vea también  
 [Caracteres especiales en código](../../../visual-basic/programming-guide/program-structure/special-characters-in-code.md)   
 [With...End With \(Instrucción\)](../../../visual-basic/language-reference/statements/with-end-with-statement.md)