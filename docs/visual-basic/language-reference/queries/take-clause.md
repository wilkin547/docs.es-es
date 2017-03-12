---
title: "Take (Cl&#225;usula, Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.QueryTake"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "consultas [Visual Basic], Take"
  - "Take (cláusula)"
  - "Take (instrucción)"
ms.assetid: 77bf87b2-1476-4456-957f-fee922fbad8c
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# Take (Cl&#225;usula, Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Devuelve un número especificado de elementos contiguos desde el principio de una colección.  
  
## Sintaxis  
  
```  
Take count  
```  
  
## Elementos  
 `count`  
 Obligatorio.  Valor o expresión que se evalúa como el número de elementos de la secuencia que se van a devolver.  
  
## Comentarios  
 La cláusula `Take` hace que una consulta incluya el número especificado de elementos contiguos desde el inicio de una lista de resultados.  El parámetro `count` especifica el número de elementos que se van a incluir.  
  
 Puede usar la cláusula `Take` con la cláusula `Skip` para que se devuelva un intervalo de datos de cualquier segmento de una consulta.  Para ello, pase el índice del primer elemento del intervalo a la cláusula `Skip` y el tamaño del intervalo a la cláusula `Take`.  En este caso, la cláusula `Take` se debe especificar después de la cláusula `Skip`.  
  
 Al usar la cláusula `Take` en una consulta, puede que también necesite asegurar que los resultados se devuelven en un orden que permita a la cláusula `Take` incluir los resultados en cuestión.  Para obtener más información sobre cómo ordenar los resultados de una consulta, vea [Order By \(Cláusula\)](../../../visual-basic/language-reference/queries/order-by-clause.md).  
  
 Puede usar la cláusula `TakeWhile` para especificar que únicamente se devuelvan ciertos elementos, dependiendo de la condición proporcionada.  
  
## Ejemplo  
 En el ejemplo de código siguiente se usa la cláusula `Take` junto con la cláusula `Skip` para que se devuelvan los datos de una consulta en páginas.  La función GetCustomers usa la cláusula `Skip` para que se omitan los clientes de la lista hasta el valor de índice de inicio proporcionado, y usa la cláusula `Take` para que se devuelva una página de los clientes a partir de ese valor de índice.  
  
 [!code-vb[VbSimpleQuerySamples#1](../../../visual-basic/language-reference/queries/codesnippet/visualbasic/VbSimpleQuerySamples/QuerySamples1.vb#1)]  
  
## Vea también  
 [Introducción a LINQ en Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Consultas](../../../visual-basic/language-reference/queries/queries.md)   
 [Select \(Cláusula\)](../../../visual-basic/language-reference/queries/select-clause.md)   
 [From \(Cláusula\)](../../../visual-basic/language-reference/queries/from-clause.md)   
 [Order By \(Cláusula\)](../../../visual-basic/language-reference/queries/order-by-clause.md)   
 [Take While \(Cláusula\)](../../../visual-basic/language-reference/queries/take-while-clause.md)   
 [Skip \(Cláusula\)](../../../visual-basic/language-reference/queries/skip-clause.md)