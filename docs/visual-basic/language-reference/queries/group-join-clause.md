---
title: "Group Join (Cl&#225;usula, Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.QueryGroupJoinIn"
  - "vb.QueryGroupJoinOn"
  - "vb.QueryGroupJoin"
  - "vb.QueryGroupJoinInto"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Group Join (cláusula)"
  - "Group Join (instrucción)"
  - "consultas [Visual Basic], Combinación agrupada"
ms.assetid: 37dbf79c-7b5c-421b-bbb7-dadfd2b92a1c
caps.latest.revision: 24
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 24
---
# Group Join (Cl&#225;usula, Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Combina dos colecciones en una sola colección jerárquica.  La operación de combinación se basa en claves coincidentes.  
  
## Sintaxis  
  
```  
Group Join element [As type] In collection _  
  On key1 Equals key2 [ And key3 Equals key4 [... ] ] _  
  Into expressionList  
```  
  
## Elementos  
  
|||  
|-|-|  
|Término|Definición|  
|`element`|Obligatorio.  Variable de control de la colección que se va a combinar.|  
|`type`|Opcional.  Tipo de `element`.  Si no se especifica ningún `type`, el tipo de `element` se infiere de `collection`.|  
|`collection`|Obligatorio.  Colección que se va a combinar con la colección que está a la izquierda del operador `Group Join`.  Una cláusula `Group Join` puede estar anidada en una cláusula `Join` o en otra cláusula `Group Join`.|  
|`key1` `Equals` `key2`|Obligatorio.  Identifica las claves de las colecciones que se van a combinar.  Debe usar el operador `Equals` para comparar las claves de las colecciones que se van a combinar.  Puede combinar las condiciones de combinación mediante el operador `And` para identificar varias claves.  El parámetro `key1` debe ser de la colección de la izquierda del operador `Join`.  El parámetro `key2` debe ser de la colección de la derecha del operador `Join`.<br /><br /> Las claves que se usan en la condición de combinación pueden ser expresiones que incluyen más de un elemento de la colección.  Sin embargo, cada expresión de clave solamente puede contener elementos de su colección respectiva.|  
|`expressionList`|Obligatorio.  Una o más expresiones que identifican cómo se agregan los grupos de elementos desde la colección.  Para identificar un nombre de miembro de los resultados agrupados, utilice la palabra clave `Group` \(`<alias> = Group`\).  También puede incluir las funciones de agregado que se van a aplicar al grupo.|  
  
## Comentarios  
 La cláusula `Group Join` combina dos colecciones basándose en los valores de clave coincidentes de las colecciones que se van a combinar.  La colección resultante puede contener un miembro que haga referencia a una colección de elementos de la segunda colección que coincidan con el valor de clave de la primera colección.  También puede especificar las funciones de agregado que se van a aplicar a los elementos agrupados de la segunda colección.  Para obtener información acerca de las funciones de agregado, vea [Aggregate \(Cláusula\)](../../../visual-basic/language-reference/queries/aggregate-clause.md).  
  
 Por ejemplo, considere una colección de administradores y una colección de empleados.  Los elementos de ambas colecciones tienen una propiedad ManagerID que identifica a los empleados que informan a un administrador concreto.  Los resultados de una operación de combinación contendrían un resultado por cada administrador y empleado con un valor ManagerID coincidente.  Los resultados de una operación de `Group Join` contendrían la lista completa de administradores.  Cada resultado de administrador tendría un miembro que hizo referencia a la lista de empleados que fueron una coincidencia para el administrador concreto.  
  
 La colección resultante de una operación de `Group Join` puede contener cualquier combinación de valores de la colección identificada en la cláusula `From` y de las expresiones identificadas en la cláusula `Into` de la cláusula `Group Join`.  Para obtener más información sobre expresiones válidas de la cláusula `Into`, vea [Aggregate \(Cláusula\)](../../../visual-basic/language-reference/queries/aggregate-clause.md).  
  
 Una operación de `Group Join` devolverá todos los resultados de la colección identificada a la izquierda del operador `Group Join` Esto es así aunque no haya ninguna coincidencia en la colección que se está combinando  Esto equivale a `LEFT OUTER JOIN` en SQL.  
  
 Puede usar la cláusula `Join` para combinar colecciones en una sola colección  Esto es equivalente a `INNER JOIN` en SQL.  
  
## Ejemplo  
 En el ejemplo de código siguiente se combinan dos colecciones mediante la cláusula `Group Join`.  
  
 [!code-vb[VbSimpleQuerySamples#14](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/group-join-clause_1.vb)]  
  
## Vea también  
 [Introducción a LINQ en Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Consultas](../../../visual-basic/language-reference/queries/queries.md)   
 [Select \(Cláusula\)](../../../visual-basic/language-reference/queries/select-clause.md)   
 [From \(Cláusula\)](../../../visual-basic/language-reference/queries/from-clause.md)   
 [Join \(Cláusula\)](../../../visual-basic/language-reference/queries/join-clause.md)   
 [Where \(Cláusula\)](../../../visual-basic/language-reference/queries/where-clause.md)   
 [Group By \(Cláusula\)](../../../visual-basic/language-reference/queries/group-by-clause.md)