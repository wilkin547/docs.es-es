---
title: "Take While (Cl&#225;usula, Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.QueryTakeWhile"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "consultas [Visual Basic], Take While"
  - "Take While (cláusula)"
  - "Take While (instrucción)"
ms.assetid: db8f9f2f-fc9f-4a6c-b0b8-1bf048147e11
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# Take While (Cl&#225;usula, Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Incluye los elementos de una colección en tanto que una condición especificada sea `true` y omita los elementos restantes.  
  
## Sintaxis  
  
```  
Take While expression  
```  
  
## Elementos  
  
|||  
|-|-|  
|Término|Definición|  
|`expression`|Obligatorio.  Expresión que representa una condición que deben cumplir los elementos.  La expresión debe devolver un valor de tipo `Boolean` o un equivalente funcional, como un valor de tipo `Integer` que debe evaluarse como `Boolean`.|  
  
## Comentarios  
 La cláusula `Take While` incluye los elementos desde el principio del resultado de una consulta hasta que el parámetro `expression` proporcionado devuelva `false`.  Después de que `expression` devuelva `false`, la consulta omitirá todos los elementos restantes.  Se omite `expression` para los resultados restantes.  
  
 La cláusula `Take While` se diferencia de la cláusula `Where` en que la cláusula `Where` se puede usar para incluir todos los elementos de una consulta que cumplan una condición determinada.  La cláusula `Take While` solamente incluye los elementos hasta que no se cumpla la condición por primera vez.  La cláusula `Take While` es muy útil cuando se trabaja con un resultado de consulta ordenado.  
  
## Ejemplo  
 En el ejemplo de código siguiente se usa la cláusula `Take While` para recuperar los resultados hasta que se encuentre el primer cliente sin pedidos.  
  
 [!code-vb[VbSimpleQuerySamples#2](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/take-while-clause_1.vb)]  
  
## Vea también  
 [Introducción a LINQ en Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Consultas](../../../visual-basic/language-reference/queries/queries.md)   
 [Select \(Cláusula\)](../../../visual-basic/language-reference/queries/select-clause.md)   
 [From \(Cláusula\)](../../../visual-basic/language-reference/queries/from-clause.md)   
 [Take \(Cláusula\)](../../../visual-basic/language-reference/queries/take-clause.md)   
 [Skip While \(Cláusula\)](../../../visual-basic/language-reference/queries/skip-while-clause.md)   
 [Where \(Cláusula\)](../../../visual-basic/language-reference/queries/where-clause.md)