---
title: "Let (Cl&#225;usula, Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.QueryLet"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Let (cláusula)"
  - "Let (instrucción)"
  - "consultas [Visual Basic], Let"
ms.assetid: 981aa516-16eb-4c53-b1f1-5aa3e82f316e
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Let (Cl&#225;usula, Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Calcula un valor y lo asigna a una nueva variable en la consulta.  
  
## Sintaxis  
  
```  
Let variable = expression [, ...]  
```  
  
## Elementos  
  
|||  
|-|-|  
|Término|Definición|  
|`variable`|Obligatorio.  Alias que se puede usar para hacer referencia a los resultados de la expresión proporcionada.|  
|`expression`|Obligatorio.  Expresión que se va a evaluar y asignar a la variable especificada.|  
  
## Comentarios  
 La cláusula `Let` permite calcular los valores para cada resultado de consulta y hacer referencia a ellos mediante un alias.  El alias se puede usar en otras cláusulas, como la cláusula `Where`.  La cláusula `Let` permite crear una instrucción de consulta que resulta más fácil de leer porque se puede especificar un alias para una cláusula de expresión incluida en la consulta y sustituir el alias cada vez que se usa la cláusula de expresión.  
  
 Puede incluir cualquier número de asignaciones de `variable` y `expression` en la cláusula `Let`.  Separe cada asignación con una coma \(,\).  
  
## Ejemplo  
 En el ejemplo de código siguiente se usa la cláusula `Let` para calcular un 10 por ciento de descuento en los productos.  
  
 [!code-vb[VbSimpleQuerySamples#16](../../../visual-basic/language-reference/queries/codesnippet/visualbasic/VbSimpleQuerySamples/QuerySamples1.vb#16)]  
  
## Vea también  
 [Introducción a LINQ en Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Consultas](../../../visual-basic/language-reference/queries/queries.md)   
 [Select \(Cláusula\)](../../../visual-basic/language-reference/queries/select-clause.md)   
 [From \(Cláusula\)](../../../visual-basic/language-reference/queries/from-clause.md)   
 [Where \(Cláusula\)](../../../visual-basic/language-reference/queries/where-clause.md)