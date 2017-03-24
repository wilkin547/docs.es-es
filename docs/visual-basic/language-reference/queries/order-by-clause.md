---
title: "Order By (Cl&#225;usula, Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.QueryOrderBy"
  - "vb.QueryAscending"
  - "vb.QueryDescending"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Order By (cláusula)"
  - "Order By (instrucción)"
  - "consultas [Visual Basic], Order By"
ms.assetid: fa911282-6b81-44c7-acfa-46b5bb93df75
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Order By (Cl&#225;usula, Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Especifica el criterio de ordenación del resultado de una consulta.  
  
## Sintaxis  
  
```  
Order By orderExp1 [ Ascending | Descending ] [, orderExp2 [...] ]  
```  
  
## Elementos  
 `orderExp1`  
 Obligatorio.  Uno o más campos del resultado de la consulta actual que identifican cómo ordenar los valores devueltos.  Los nombres de campo deben estar separados por una coma \(,\).  Puede identificar cada campo como ordenado en orden ascendente o descendente utilizando las palabras clave `Ascending` o `Descending`.  Si no se especifican las palabras clave `Ascending` o `Descending`, el criterio de ordenación predeterminado es ascendente.  La prioridad de los campos del criterio de ordenación es de izquierda a derecha.  
  
## Comentarios  
 Puede utilizar la cláusula `Order By` para ordenar los resultados de una consulta.  La cláusula `Order By` sólo puede ordenar un resultado basándose en la variable de rango del ámbito actual.  Por ejemplo, la cláusula `Select` presenta un nuevo ámbito en una expresión de consulta con nuevas variables de iteración para el mismo.  Las variables de rango definidas delante de una cláusula `Select` en una consulta no están disponibles detrás de la cláusula `Select`.  Por consiguiente, si desea ordenar los resultados por un campo que no esté disponible en la cláusula `Select`, debe colocar la cláusula `Order By` delante de la cláusula `Select`.  Un ejemplo de cuándo debería hacer esto es si desea ordenar la consulta por campos que no se devuelven como parte del resultado.  
  
 La implementación de la interfaz <xref:System.IComparable> determina el orden ascendente o descendente de un campo para el tipo de datos del campo.  Si el tipo de datos no implementa la interfaz <xref:System.IComparable>, se omite el criterio de ordenación.  
  
## Ejemplo  
 La siguiente expresión de consulta usa una cláusula `From` para declarar una variable de rango `book` de la colección `books`.  La cláusula `Order By` ordena el resultado de la consulta por precio en orden ascendente \(el valor predeterminado\).  Los libros con el mismo precio se ordenan por título en orden ascendente.  La cláusula `Select` selecciona las propiedades `Title` y `Price` como los valores devueltos por la consulta.  
  
 [!code-vb[VbSimpleQuerySamples#24](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_1.vb)]  
  
## Ejemplo  
 La expresión de consulta siguiente utiliza la cláusula `Order By` para ordenar el resultado de la consulta por precio en orden descendente.  Los libros con el mismo precio se ordenan por título en orden ascendente.  
  
 [!code-vb[VbSimpleQuerySamples#25](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_2.vb)]  
  
## Ejemplo  
 La expresión de consulta siguiente utiliza una cláusula `Select` para seleccionar el título, precio, fecha de publicación y autor del libro.  Después rellena los campos `Title`, `Price`, `PublishDate` y `Author` de la variable de rango del nuevo ámbito.  La cláusula `Order By` ordena la nueva variable de rango por el nombre del autor, título del libro y, a continuación, precio.  Cada columna está ordenada en el orden predeterminado \(ascendente\).  
  
 [!code-vb[VbSimpleQuerySamples#26](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_3.vb)]  
  
## Vea también  
 [Introducción a LINQ en Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Consultas](../../../visual-basic/language-reference/queries/queries.md)   
 [Select \(Cláusula\)](../../../visual-basic/language-reference/queries/select-clause.md)   
 [From \(Cláusula\)](../../../visual-basic/language-reference/queries/from-clause.md)