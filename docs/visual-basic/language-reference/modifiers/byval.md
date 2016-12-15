---
title: "ByVal (Visual Basic) | Microsoft Docs"
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
  - "vb.ByVal"
  - "ByVal"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "ByVal (palabra clave)"
  - "ByVal (palabra clave), contextos"
ms.assetid: 1eaf4e58-b305-4785-9e3d-e416b9c75598
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# ByVal (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Indica que un argumento se pasa de tal forma que el procedimiento o la propiedad a la que se ha llamado no puede cambiar el valor de una variable subyacente al argumento en el código que realiza la llamada.  
  
## Comentarios  
 El modificador `ByVal` se puede utilizar en estos contextos:  
  
 [Declare \(Instrucción\)](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Function \(Instrucción\)](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Operator \(Instrucción\)](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [Property \(Instrucción\)](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub \(Instrucción\)](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## Ejemplo  
 En el ejemplo siguiente se muestra el uso del mecanismo de paso del parámetro `ByVal` con un argumento de tipo de referencia.  En el ejemplo, el argumento es `c1`, una instancia de la clase `Class1`.  `ByVal` evita que el código en los procedimientos cambie el valor subyacente del argumento de referencia, `c1`, pero no protege las propiedades y campos accesibles de `c1`.  
  
 [!code-vb[VbVbalrKeywords#10](../../../visual-basic/language-reference/codesnippet/VisualBasic/byval_1.vb)]  
  
## Vea también  
 [Palabras clave](../../../visual-basic/language-reference/keywords/index.md)   
 [Pasar argumentos por valor y por referencia](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)