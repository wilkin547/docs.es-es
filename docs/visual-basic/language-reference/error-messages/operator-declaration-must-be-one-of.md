---
title: "La declaraci&#243;n de un operador debe ser una de las siguientes: +,-,*,\,/,^, &amp;, Like, Mod, And, Or, Xor, Not, &lt;&lt;, &gt;&gt;, =, &lt;&gt;, &lt;, &lt;=, &gt;, &gt;=, CType, IsTrue, IsFalse | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc33000"
  - "vbc33000"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC33000"
ms.assetid: 15c5d8eb-3a8c-4141-8f41-33151afabf97
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# La declaraci&#243;n de un operador debe ser una de las siguientes: +,-,*,\,/,^, &amp;, Like, Mod, And, Or, Xor, Not, &lt;&lt;, &gt;&gt;, =, &lt;&gt;, &lt;, &lt;=, &gt;, &gt;=, CType, IsTrue, IsFalse
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Sólo puede declarar un operador que sea reúna los requisitos necesarios para la sobrecarga.  La tabla siguiente muestra los operadores que se pueden declarar.  
  
|Tipo|Operadores|  
|----------|----------------|  
|Unario|`+`, `-`, `IsFalse`, `IsTrue`, `Not`|  
|Binary|`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`|  
|Conversión \(unario\)|`CType`|  
  
 Observe que el operador `=` en la lista binaria es el operador de comparación, no el operador de asignación.  
  
 **Identificador de error:** BC33000  
  
### Para corregir este error  
  
1.  Seleccione a un operador del conjunto de operadores sobrecargables.  
  
2.  Si necesita la funcionalidad de sobrecarga de un operador que no pueda sobrecargar directamente, cree un procedimiento `Function` que tome los parámetros adecuados y devuelva el valor apropiado.  
  
## Vea también  
 [Operator \(Instrucción\)](../../../visual-basic/language-reference/statements/operator-statement.md)   
 [Procedimientos de operador](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [Cómo: Definir un operador](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)   
 [Cómo: Definir un operador de conversión](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)   
 [Function \(Instrucción\)](../../../visual-basic/language-reference/statements/function-statement.md)