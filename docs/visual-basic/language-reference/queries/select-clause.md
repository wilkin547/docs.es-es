---
title: "Select (Cl&#225;usula, Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.QuerySelect"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "consultas [Visual Basic], Select"
  - "Select (cláusula)"
  - "Select (instrucción)"
ms.assetid: 27a3f61c-5960-4692-9b91-4d0c4b6178fe
caps.latest.revision: 21
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 21
---
# Select (Cl&#225;usula, Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Define el resultado de una consulta.  
  
## Sintaxis  
  
```  
Select [ var1 = ] fieldName1 [, [ var2 = ] fieldName2 [...] ]  
```  
  
## Elementos  
 `var1`  
 Opcional.  Alias que se puede usar para hacer referencia a los resultados de la expresión de columna.  
  
 `fieldName1`  
 Obligatorio.  Nombre del campo que se va a devolver en el resultado de la consulta.  
  
## Comentarios  
 Puede usar la cláusula `Select` para definir los resultados que se van a devolver desde una consulta.  De esta forma, puede definir los miembros de un nuevo tipo anónimo creado por una consulta o destinar los miembros de un tipo con nombre devuelto por una consulta.  No se requiere la cláusula `Select` para una consulta.  Si no se especifica ninguna cláusula `Select`, la consulta devolverá un tipo basado en todos los miembros de las variables de rango identificado para el ámbito actual.  Para obtener más información, vea [Tipos anónimos](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  Cuando una consulta crea un tipo con nombre, devolverá un resultado de tipo <xref:System.Collections.Generic.IEnumerable%601> donde `T` es el tipo creado.  
  
 La cláusula `Select` puede hacer referencia a cualquier variable del ámbito actual.  Se incluyen las variables de rango identificado en la cláusula `From` \(o cláusulas `From`\).  También se incluyen cualquier variable nueva creada con un alias por las cláusulas `Aggregate`, `Let`, `Group By` o `Group Join` o las variables de una cláusula `Select` anterior de la expresión de consulta.  La cláusula `Select` también puede incluir valores estáticos.  Por ejemplo, el ejemplo de código siguiente muestra una expresión de consulta en la que la cláusula `Select` define el resultado de la consulta como nuevo tipo anónimo con cuatro miembros: `ProductName`, `Price`, `Discount` y `DiscountedPrice`.  Los valores de los miembros `ProductName` y `Price` se toman de la variable de rango de producto definida en la cláusula `From`.  El valor del miembro `DiscountedPrice` se calcula en la cláusula `Let`.  El miembro `Discount` es un valor estático.  
  
 [!code-vb[VbSimpleQuerySamples#27](../../../visual-basic/language-reference/queries/codesnippet/visualbasic/VbSimpleQuerySamples/QuerySamples1.vb#27)]  
  
 La cláusula `Select` presenta un nuevo conjunto de variables de rango para las cláusulas de consulta subsiguientes y las variables de rango anteriores ya no están en el ámbito.  La última cláusula `Select` de una expresión de consulta determina el valor devuelto de la consulta.  Por ejemplo, la consulta siguiente devuelve el nombre de la compañía y el identificador de cada pedido del cliente cuyo total sea superior a 500.  La primera cláusula `Select` identifica las variables de rango de la cláusula `Where` y la segunda cláusula `Select`.  La segunda cláusula `Select` identifica los valores devueltos por la consulta como nuevo tipo anónimo.  
  
 [!code-vb[VbSimpleQuerySamples#28](../../../visual-basic/language-reference/queries/codesnippet/visualbasic/VbSimpleQuerySamples/QuerySamples1.vb#28)]  
  
 Si la cláusula `Select` identifica un solo elemento que se va a devolver, la expresión de consulta devuelve una colección del tipo de ese elemento único.  Si la cláusula `Select` identifica varios elementos que se van a devolver, la expresión de consulta devuelve una colección de un nuevo tipo anónimo, basado en los elementos seleccionados.  Por ejemplo, las dos consultas siguientes devuelven las colecciones de dos tipos diferentes basadas en la cláusula `Select`.  La primera consulta devuelve una colección de nombres de compañía como cadenas.  La segunda consulta devuelve una colección de objetos `Customer` rellenados con los nombres y la información de dirección de las compañías.  
  
 [!code-vb[VbSimpleQuerySamples#29](../../../visual-basic/language-reference/queries/codesnippet/visualbasic/VbSimpleQuerySamples/QuerySamples1.vb#29)]  
  
## Ejemplo  
 La siguiente expresión de consulta usa una cláusula `From` para declarar una variable de rango `cust` de la colección `customers`.  La cláusula `Select` selecciona el nombre del cliente y el valor de identificación y rellena las columnas `CompanyName` e `CustomerID` de la nueva variable de rango.  La instrucción `For Each` crea un bucle en cada objeto devuelto y muestra las columnas `CompanyName` y `CustomerID` de cada registro.  
  
 [!code-vb[VbSimpleQuerySamples#30](../../../visual-basic/language-reference/queries/codesnippet/visualbasic/VbSimpleQuerySamples/QuerySamples1.vb#30)]  
  
## Vea también  
 [Introducción a LINQ en Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Consultas](../../../visual-basic/language-reference/queries/queries.md)   
 [From \(Cláusula\)](../../../visual-basic/language-reference/queries/from-clause.md)   
 [Where \(Cláusula\)](../../../visual-basic/language-reference/queries/where-clause.md)   
 [Order By \(Cláusula\)](../../../visual-basic/language-reference/queries/order-by-clause.md)   
 [Tipos anónimos](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)