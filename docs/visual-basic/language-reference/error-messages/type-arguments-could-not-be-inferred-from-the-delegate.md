---
title: "No se pudieron inferir los argumentos de tipo a partir del delegado | Microsoft Docs"
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
  - "bc36564"
  - "vbc36564"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC36564"
ms.assetid: 21312807-e1cd-4ac1-ae1c-c28a9c25164d
caps.latest.revision: 5
caps.handback.revision: 5
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# No se pudieron inferir los argumentos de tipo a partir del delegado
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Una instrucción de asignación utiliza `AddressOf` para asignar la dirección de un procedimiento genérico a un delegado, pero no proporciona ningún argumento de tipo al procedimiento genérico.  
  
 Normalmente, cuando se invoca un tipo genérico, se proporciona un argumento de tipo para cada parámetro de tipo definido por el tipo genérico.  Si no se proporciona ningún argumento de tipo, el compilador intenta deducir los tipos que se deben pasar a los parámetros de tipo.  Si el contexto no proporciona suficiente información para que el compilador deduzca los tipos, se genera un error.  
  
 **Id. de error:** BC36564  
  
### Para corregir este error  
  
-   Especifique los argumentos de tipo para el procedimiento genérico en la expresión `AddressOf`.  
  
## Vea también  
 [Tipos genéricos en Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [AddressOf \(Operador\)](../../../visual-basic/language-reference/operators/addressof-operator.md)   
 [Procedimientos genéricos en Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md)   
 [Lista de tipos](../../../visual-basic/language-reference/statements/type-list.md)   
 [métodos de extensión.](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)