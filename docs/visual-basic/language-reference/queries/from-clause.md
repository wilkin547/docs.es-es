---
title: "From (Cl&#225;usula, Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.QueryFrom"
  - "vb.QueryFromIn"
  - "vb.QueryFromLet"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "From (cláusula)"
  - "From (instrucción)"
  - "consultas [Visual Basic], From"
ms.assetid: 83e3665e-68a0-4540-a3a3-3d777a0f95d5
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# From (Cl&#225;usula, Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Especifica una o más variables de rango y una colección que se va a consultar.  
  
## Sintaxis  
  
```  
From element [ As type ] In collection [ _ ]  
  [, element2 [ As type2 ] In collection2 [, ... ] ]  
```  
  
## Elementos  
  
|||  
|-|-|  
|Término|Definición|  
|`element`|Obligatorio.  *Variable de rango* usada para recorrer en iteración los elementos de la colección.  Una variable de rango se utiliza para hacer referencia a cada miembro de `collection` a medida que la consulta recorre en iteración `collection`.  Debe ser un tipo enumerable.|  
|`type`|Opcional.  Tipo de `element`.  Si no se especifica ningún `type`, el tipo de `element` se infiere de `collection`.|  
|`collection`|Obligatorio.  Hace referencia a la colección que se va a consultar.  Debe ser un tipo enumerable.|  
  
## Comentarios  
 La cláusula `From` se utiliza para identificar los datos de origen de una consulta y las variables que se usan para hacer referencia a un elemento de la colección de origen.  Estas variables se denominan *variables de rango*.  La cláusula `From` se requiere para una consulta, excepto cuando la cláusula `Aggregate` se usa para identificar una consulta que devuelve sólo resultados agregados.  Para obtener más información, vea [Aggregate \(Cláusula\)](../../../visual-basic/language-reference/queries/aggregate-clause.md).  
  
 Puede especificar varias cláusulas `From` en una consulta para identificar varias colecciones que se van a combinar.  Cuando se especifican varias colecciones, se iteran en ellas independientemente o puede combinarlas si están relacionadas.  Puede combinar colecciones implícitamente mediante la cláusula `Select` o explícitamente mediante las cláusulas `Join` o `Group Join` Como alternativa, puede especificar varias variables de rango y colecciones en una sola cláusula `From`, con cada variable de rango y colección relacionadas separadas del resto por una coma.  El ejemplo de código siguiente muestra ambas opciones de sintaxis para la cláusula `From`.  
  
 [!code-vb[VbSimpleQuerySamples#21](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/from-clause_1.vb)]  
  
 La cláusula `From` define el ámbito de una consulta, que es similar al ámbito de un bucle `For`.  Por consiguiente, cada variable de rango `element` del ámbito de una consulta debe tener un nombre único.  Dado que puede especificar varias cláusulas `From` para una consulta, las cláusulas `From` subsiguientes pueden hacer referencia a las variables de rango de la cláusula `From` o pueden hacer referencia a las variables de rango de una cláusula `From` previa.  Por ejemplo, el ejemplo siguiente muestra una cláusula `From` anidada en la que la colección de la segunda cláusula se basa en una propiedad de variable de rango de la primera cláusula.  
  
 [!code-vb[VbSimpleQuerySamples#22](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/from-clause_2.vb)]  
  
 Cada cláusula `From` puede ir seguida de cualquier combinación de cláusulas de consulta adicionales para refinar la consulta.  Puede refinarla de las siguientes maneras:  
  
-   Combine varias colecciones implícitamente mediante las cláusulas `From` y `Select` o explícitamente mediante las cláusulas `Join` o `Group Join`.  
  
-   Utilice la cláusula `Where` para filtrar el resultado de la consulta.  
  
-   Ordene el resultado con la cláusula `Order By`.  
  
-   Agrupe los resultados similares usando la cláusula `Group By`.  
  
-   Utilice la cláusula `Aggregate` para identificar las funciones de agregado que se van a evaluar para todo el resultado de la consulta.  
  
-   Utilice la cláusula `Let` para presentar una variable de iteración cuyo valor lo determina una expresión en lugar de una colección.  
  
-   Use la cláusula `Distinct` para omitir resultados duplicados.  
  
-   Identifique las partes del resultado que se van a devolver mediante las cláusulas `Skip`, `Take`, `Skip While` y `Take While`.  
  
## Ejemplo  
 La siguiente expresión de consulta usa una cláusula `From` para declarar una variable de rango `cust` para cada objeto `Customer` de la colección `customers`.  La cláusula `Where` usa la variable de rango para restringir el resultado a los clientes de la región especificada.  El bucle `For Each` muestra el nombre de la compañía de cada cliente en el resultado de la consulta.  
  
 [!code-vb[VbSimpleQuerySamples#23](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/from-clause_3.vb)]  
  
## Vea también  
 [Consultas](../../../visual-basic/language-reference/queries/queries.md)   
 [Introducción a LINQ en Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [For Each...Next \(Instrucción\)](../../../visual-basic/language-reference/statements/for-each-next-statement.md)   
 [For...Next \(Instrucción\)](../../../visual-basic/language-reference/statements/for-next-statement.md)   
 [Select \(Cláusula\)](../../../visual-basic/language-reference/queries/select-clause.md)   
 [Where \(Cláusula\)](../../../visual-basic/language-reference/queries/where-clause.md)   
 [Aggregate \(Cláusula\)](../../../visual-basic/language-reference/queries/aggregate-clause.md)   
 [Distinct \(Cláusula\)](../../../visual-basic/language-reference/queries/distinct-clause.md)   
 [Join \(Cláusula\)](../../../visual-basic/language-reference/queries/join-clause.md)   
 [Group Join \(Cláusula\)](../../../visual-basic/language-reference/queries/group-join-clause.md)   
 [Order By \(Cláusula\)](../../../visual-basic/language-reference/queries/order-by-clause.md)   
 [Let \(Cláusula\)](../../../visual-basic/language-reference/queries/let-clause.md)   
 [Skip \(Cláusula\)](../../../visual-basic/language-reference/queries/skip-clause.md)   
 [Take \(Cláusula\)](../../../visual-basic/language-reference/queries/take-clause.md)   
 [Skip While \(Cláusula\)](../../../visual-basic/language-reference/queries/skip-while-clause.md)   
 [Take While \(Cláusula\)](../../../visual-basic/language-reference/queries/take-while-clause.md)