---
title: "Join (Cl&#225;usula, Visual Basic) | Microsoft Docs"
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
  - "vb.QueryJoinIn"
  - "vb.QueryJoin"
  - "vb.QueryJoinOn"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Join (cláusula)"
  - "Join (instrucción)"
  - "consultas [Visual Basic], Join"
ms.assetid: 6dd37936-b27c-4e00-98ad-154b23f4de64
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Join (Cl&#225;usula, Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Combina dos colecciones en una sola.  La operación de combinación se basa en claves coincidentes y usa el operador `Equals`.  
  
## Sintaxis  
  
```  
Join element In collection _  
  [ joinClause _ ]   
  [ groupJoinClause ... _ ]   
On key1 Equals key2 [ And key3 Equals key4 [... ]  
```  
  
## Elementos  
 `element`  
 Requerido.  Variable de control de la colección que se va a combinar.  
  
 `collection`  
 Requerido.  Colección que se va a combinar con la colección identificada a la izquierda del operador `Join`.  Una cláusula `Join` puede estar anidada en otra cláusula `Join` o en una cláusula `Group Join`.  
  
 `joinClause`  
 Opcional.  Una o varias cláusulas `Join` adicionales para delimitar más la consulta.  
  
 `groupJoinClause`  
 Opcional.  Una o varias cláusulas `Group Join` adicionales para delimitar más la consulta.  
  
 `key1` `Equals` `key2`  
 Requerido.  Identifica las claves de las colecciones que se van a combinar.  Debe usar el operador `Equals` para comparar las claves de las colecciones que se van a combinar.  Puede combinar las condiciones de combinación mediante el operador `And` para identificar varias claves.  El parámetro `key1` debe proceder de la colección de la izquierda del operador `Join`.  `key2` debe proceder de la colección de la derecha del operador `Join`.  
  
 Las claves que se usan en la condición de combinación pueden ser expresiones que incluyen más de un elemento de la colección.  Sin embargo, cada expresión de clave solamente puede contener elementos de su colección respectiva.  
  
## Comentarios  
 La cláusula `Join` combina dos colecciones basándose en los valores de clave coincidentes de las colecciones que se van a combinar.  La colección resultante puede contener cualquier combinación de valores de la colección identificada a la izquierda del operador `Join` y de la colección identificada en la cláusula `Join`.  La consulta solamente devolverá los resultados para los que se cumpla la condición especificada en el operador `Equals`.  Esto es equivalente a `INNER JOIN` en SQL.  
  
 Puede usar varias cláusulas `Join` en una consulta para combinar dos o más colecciones en una sola colección.  
  
 Puede realizar una combinación implícita para combinar las colecciones sin la cláusula `Join`.  Para ello, incluya varias cláusulas `In` en la cláusula `From` y especifique una cláusula `Where` que identifique las claves que desee usar para la combinación.  
  
 Puede usar la cláusula `Group Join` para combinar colecciones en una sola colección jerárquica.  Esto equivale a `LEFT OUTER JOIN` en SQL.  
  
## Ejemplo  
 En el ejemplo de código siguiente se realiza una combinación implícita para combinar una lista de clientes con sus pedidos.  
  
 [!code-vb[VbSimpleQuerySamples#13](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/join-clause_1.vb)]  
  
## Ejemplo  
 En el ejemplo de código siguiente se combinan dos colecciones mediante la cláusula `Join`.  
  
 [!code-vb[VbSimpleQuerySamples#12](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/join-clause_2.vb)]  
  
 Este ejemplo generará un resultado similar al siguiente:  
  
 `winlogon (968), Windows Logon`  
  
 `explorer (2424), File Explorer`  
  
 `cmd (5136), Command Window`  
  
## Ejemplo  
 En el ejemplo de código siguiente se combinan dos colecciones mediante la cláusula `Join` con dos columnas de clave.  
  
 [!code-vb[VbSimpleQuerySamples#17](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/join-clause_3.vb)]  
  
 El ejemplo generará un resultado similar al siguiente:  
  
 `winlogon (968), Windows Logon, Priority = 13`  
  
 `cmd (700), Command Window, Priority = 8`  
  
 `explorer (2424), File Explorer, Priority = 8`  
  
## Vea también  
 [Introducción a LINQ en Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Consultas](../../../visual-basic/language-reference/queries/queries.md)   
 [Select \(Cláusula\)](../../../visual-basic/language-reference/queries/select-clause.md)   
 [From \(Cláusula\)](../../../visual-basic/language-reference/queries/from-clause.md)   
 [Group Join \(Cláusula\)](../../../visual-basic/language-reference/queries/group-join-clause.md)   
 [Where \(Cláusula\)](../../../visual-basic/language-reference/queries/where-clause.md)