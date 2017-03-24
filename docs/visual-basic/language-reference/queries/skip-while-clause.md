---
title: "Skip While (Cl&#225;usula, Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.QuerySkipWhile"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "consultas [Visual Basic], Skip While"
  - "Skip While (cláusula)"
  - "Skip While (instrucción)"
ms.assetid: 5dee8350-7520-4f1a-b00d-590cacd572d6
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Skip While (Cl&#225;usula, Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Omite los elementos de una colección en tanto que una condición especificada sea `true` y, a continuación, devuelva los elementos restantes.  
  
## Sintaxis  
  
```  
Skip While expression  
```  
  
## Elementos  
  
|||  
|-|-|  
|Término|Definición|  
|`expression`|Obligatorio.  Expresión que representa una condición que deben cumplir los elementos.  La expresión debe devolver un valor de tipo `Boolean` o un equivalente funcional, como un valor de tipo `Integer` que debe evaluarse como `Boolean`.|  
  
## Comentarios  
 La cláusula `Skip While` omite los elementos desde el principio del resultado de una consulta hasta que el parámetro `expression` proporcionado devuelva `false`.  Después de que `expression` devuelva `false`, la consulta devuelve todos los elementos restantes.  Se omite `expression` para los resultados restantes.  
  
 La cláusula `Skip While` se diferencia de la cláusula `Where` en que la cláusula `Where` se puede usar para excluir todos los elementos de una consulta que no cumplan una condición determinada.  La cláusula `Skip While` solamente excluye los elementos hasta que no se cumpla la condición por primera vez.  La cláusula `Skip While` es muy útil cuando se trabaja con un resultado de consulta ordenado.  
  
 Se puede omitir un número concreto de resultados desde el principio del resultado de una consulta mediante la cláusula `Skip`.  
  
## Ejemplo  
 En el ejemplo de código siguiente se usa la cláusula `Skip While` para omitir los resultados hasta que se encuentre el primer cliente de Estados Unidos.  
  
 [!code-vb[VbSimpleQuerySamples#3](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/skip-while-clause_1.vb)]  
  
## Vea también  
 [Introducción a LINQ en Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Consultas](../../../visual-basic/language-reference/queries/queries.md)   
 [Select \(Cláusula\)](../../../visual-basic/language-reference/queries/select-clause.md)   
 [From \(Cláusula\)](../../../visual-basic/language-reference/queries/from-clause.md)   
 [Skip \(Cláusula\)](../../../visual-basic/language-reference/queries/skip-clause.md)   
 [Take While \(Cláusula\)](../../../visual-basic/language-reference/queries/take-while-clause.md)   
 [Where \(Cláusula\)](../../../visual-basic/language-reference/queries/where-clause.md)