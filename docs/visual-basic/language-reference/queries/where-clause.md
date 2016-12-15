---
title: "Where (Cl&#225;usula, Visual Basic) | Microsoft Docs"
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
  - "vb.QueryWhere"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "consultas [Visual Basic], Where"
  - "Where (cláusula)"
  - "Where (instrucción)"
ms.assetid: 48b5c2c5-3181-429c-8545-894296798c89
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Where (Cl&#225;usula, Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Especifica la condición de filtrado de una consulta.  
  
## Sintaxis  
  
```  
Where condition  
```  
  
## Elementos  
 `condition`  
 Obligatorio.  Expresión que determina si se incluyen en la colección de salida los valores del elemento actual de la colección.  La expresión debe evaluarse como un valor de tipo `Boolean` o el equivalente de un valor de tipo `Boolean`.  Si la condición se evalúa como `True`, se incluye el elemento en el resultado de la consulta; de lo contrario, se excluye el elemento del resultado.  
  
## Comentarios  
 La cláusula `Where` permite filtrar los datos de una consulta seleccionando únicamente los elementos que cumplen determinados criterios.  Los elementos cuyos valores hacen que la cláusula `Where` se evalúe como `True` se incluyen en el resultado de la consulta; los demás elementos se excluyen.  La expresión que se usa en una cláusula `Where` debe evaluarse como un valor de tipo `Boolean` o el equivalente de un valor de tipo `Boolean`, como un entero que se evalúa como `False` cuando su valor es cero.  Puede combinar varias expresiones en una cláusula `Where` mediante operadores lógicos, como `And`, `Or`, `AndAlso`, `OrElse`, `Is` e `IsNot`.  
  
 De forma predeterminada, no se evalúan las expresiones de consulta hasta que se obtenga acceso a ellas; por ejemplo, cuando se enlazan a datos o se recorren en iteración en un bucle `For`.  Como resultado, no se evalúa la cláusula `Where` hasta que se obtenga acceso a la consulta.  Si se usan valores externos a la consulta en la cláusula `Where`, asegúrese de que se usa el valor adecuado en la cláusula `Where` cuando se ejecute la consulta.  Para obtener más información sobre la ejecución de consultas, vea [Escribir la primera consulta con LINQ](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).  
  
 Puede llamar a las funciones en una cláusula `Where` para realizar un cálculo u operación con un valor del elemento actual de la colección.  Al llamar a una función en una cláusula `Where`, es posible que la consulte se ejecute inmediatamente en el momento de su definición y no cuando se obtiene acceso a ella.  Para obtener más información sobre la ejecución de consultas, vea [Escribir la primera consulta con LINQ](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).  
  
## Ejemplo  
 La siguiente expresión de consulta usa una cláusula `From` para declarar una variable de rango `cust` para cada objeto `Customer` de la colección `customers`.  La cláusula `Where` usa la variable de rango para restringir el resultado a los clientes de la región especificada.  El bucle `For Each` muestra el nombre de la compañía de cada cliente en el resultado de la consulta.  
  
 [!code-vb[VbSimpleQuerySamples#23](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/where-clause_1.vb)]  
  
## Ejemplo  
 El ejemplo siguiente utiliza `And` y operadores lógicos de `Or` en la cláusula de `Where` .  
  
 [!code-vb[VbSimpleQuerySamples#31](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/where-clause_2.vb)]  
  
## Vea también  
 [Introducción a LINQ en Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Consultas](../../../visual-basic/language-reference/queries/queries.md)   
 [From \(Cláusula\)](../../../visual-basic/language-reference/queries/from-clause.md)   
 [Select \(Cláusula\)](../../../visual-basic/language-reference/queries/select-clause.md)   
 [For Each...Next \(Instrucción\)](../../../visual-basic/language-reference/statements/for-each-next-statement.md)