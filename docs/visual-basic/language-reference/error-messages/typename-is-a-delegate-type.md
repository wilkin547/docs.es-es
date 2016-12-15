---
title: "&#39;&lt;tipo&gt;&#39; es un tipo delegado | Microsoft Docs"
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
  - "bc32008"
  - "vbc32008"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC32008"
ms.assetid: dc6abba0-a9ad-450f-8899-87265bc84abc
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;tipo&gt;&#39; es un tipo delegado
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

'\<nombreDeTipo\>' es un tipo delegadoLa construcción de delegado permite una única expresión AddressOf como lista de argumentos.A menudo se puede usar la expresión AddressOf en lugar de una construcción de delegado.  
  
 Una cláusula `New` que crea una instancia de una clase de delegado le proporciona una lista de argumentos no válidos al constructor del delegado.  
  
 Sólo puede suministrarse una expresión `AddressOf` cuando se crea una instancia de delegado nueva.  
  
 Se puede producir este error si no se pasa ningún argumento al constructor del delegado, si se pasa más de un argumento o si se pasa un solo argumento que no es una expresión `AddressOf` válida.  
  
 **Identificador de error:** BC32008  
  
### Para corregir este error  
  
-   Use una expresión `AddressOf` única en la lista de argumentos de la clase de delegado en la cláusula `New`.  
  
## Vea también  
 [New \(Operador\)](../../../visual-basic/language-reference/operators/new-operator.md)   
 [AddressOf \(Operador\)](../../../visual-basic/language-reference/operators/addressof-operator.md)   
 [Delegados](../../../visual-basic/programming-guide/language-features/delegates/delegates.md)   
 [Cómo: Invocar un método delegado](../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)