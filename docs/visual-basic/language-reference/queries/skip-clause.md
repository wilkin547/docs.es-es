---
title: "Skip (Cl&#225;usula, Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.QuerySkip"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "consultas [Visual Basic], Skip"
  - "Skip (cláusula)"
  - "Skip (instrucción)"
ms.assetid: f00eb172-3907-4c43-9745-d8546ab86234
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# Skip (Cl&#225;usula, Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Omite un número especificado de elementos de una colección y, a continuación, devuelve los elementos restantes.  
  
## Sintaxis  
  
```  
Skip count  
```  
  
## Elementos  
 `count`  
 Obligatorio.  Valor o expresión que se evalúa como el número de elementos de la secuencia que se van a omitir.  
  
## Comentarios  
 La cláusula `Skip` hace que una consulta omita elementos al principio de una lista de resultados y devuelva los elementos restantes.  El parámetro `count` especifica el número de elementos que se van a omitir.  
  
 Puede usar la cláusula `Skip` con la cláusula `Take` para que se devuelva un intervalo de datos de cualquier segmento de una consulta.  Para ello, pase el índice del primer elemento del intervalo a la cláusula `Skip` y el tamaño del intervalo a la cláusula `Take`.  
  
 Al usar la cláusula `Skip` en una consulta, puede que también necesite asegurar que los resultados se devuelven en un orden que permita a la cláusula `Skip` omitir los resultados en cuestión.  Para obtener más información sobre cómo ordenar los resultados de una consulta, vea [Order By \(Cláusula\)](../../../visual-basic/language-reference/queries/order-by-clause.md).  
  
 Puede usar la cláusula `SkipWhile` para especificar que únicamente se omitan ciertos elementos, dependiendo de la condición proporcionada.  
  
## Ejemplo  
 En el ejemplo de código siguiente se usa la cláusula `Skip` junto con la cláusula `Take` para que se devuelvan los datos de una consulta en páginas.  La función `GetCustomers` usa la cláusula `Skip` para que se omitan los clientes de la lista hasta el valor de índice de inicio proporcionado, y usa la cláusula `Take` para que se devuelva una página de los clientes a partir de ese valor de índice.  
  
 [!code-vb[VbSimpleQuerySamples#1](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/skip-clause_1.vb)]  
  
## Vea también  
 [Introducción a LINQ en Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Consultas](../../../visual-basic/language-reference/queries/queries.md)   
 [Select \(Cláusula\)](../../../visual-basic/language-reference/queries/select-clause.md)   
 [From \(Cláusula\)](../../../visual-basic/language-reference/queries/from-clause.md)   
 [Order By \(Cláusula\)](../../../visual-basic/language-reference/queries/order-by-clause.md)   
 [Skip While \(Cláusula\)](../../../visual-basic/language-reference/queries/skip-while-clause.md)   
 [Take \(Cláusula\)](../../../visual-basic/language-reference/queries/take-clause.md)