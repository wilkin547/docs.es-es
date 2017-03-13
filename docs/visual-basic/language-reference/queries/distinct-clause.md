---
title: "Distinct (Cl&#225;usula, Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.QueryDistinct"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Distinct (cláusula)"
  - "Distinct (instrucción)"
  - "consultas [Visual Basic], Distinct"
ms.assetid: 86f42614-0d8f-4ffc-b888-ce8a37a8d36a
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# Distinct (Cl&#225;usula, Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Restringe los valores de la variable de rango actual para eliminar los valores duplicados en las cláusulas de consulta subsiguientes.  
  
## Sintaxis  
  
```  
Distinct  
```  
  
## Comentarios  
 Puede usar la cláusula `Distinct` para que se devuelva una lista de elementos únicos.  La cláusula `Distinct` hace que la consulta omita los resultados duplicados.  La cláusula `Distinct` se aplica a los valores duplicados de todos los campos devueltos que la cláusula `Select` especifica.  Si no se especifica ninguna cláusula `Select`, la cláusula `Distinct` se aplica a la variable de rango de la consulta identificada en la cláusula `From`.  Si la variable de rango no es un tipo inmutable, la consulta omitirá únicamente un resultado si todos los miembros del tipo coinciden con un resultado de consulta existente.  
  
## Ejemplo  
 La expresión de consulta siguiente combina una lista de clientes y una lista de pedidos de los clientes.  Se incluye la cláusula `Distinct` para que se devuelva una lista de nombres de cliente y fechas de pedido únicos.  
  
 [!code-vb[VbSimpleQuerySamples#20](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/distinct-clause_1.vb)]  
  
## Vea también  
 [Introducción a LINQ en Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Consultas](../../../visual-basic/language-reference/queries/queries.md)   
 [From \(Cláusula\)](../../../visual-basic/language-reference/queries/from-clause.md)   
 [Select \(Cláusula\)](../../../visual-basic/language-reference/queries/select-clause.md)   
 [Where \(Cláusula\)](../../../visual-basic/language-reference/queries/where-clause.md)