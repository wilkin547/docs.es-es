---
title: "C&#243;mo: Combinar datos con LINQ usando cl&#225;usulas Join (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Group Join (cláusula) [Visual Basic]"
  - "Join (cláusula) [LINQ en Visual Basic]"
  - "combinar [LINQ en Visual Basic]"
  - "combinaciones [LINQ en Visual Basic]"
  - "consultas [LINQ en Visual Basic], temas Cómo"
  - "consultas [LINQ en Visual Basic], combinaciones"
ms.assetid: 5b00a478-035b-41c6-8918-be1a97728396
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# C&#243;mo: Combinar datos con LINQ usando cl&#225;usulas Join (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Visual Basic proporciona las cláusulas de consulta `Group Join` y `Join` para permitir combinar el contenido de varias colecciones basándose en valores comunes entre colecciones.  Estos valores se conocen como valores de *clave*.  Los programadores familiarizados con conceptos de bases de datos relacionales reconocerán la cláusula `Join` como INNER JOIN y la cláusula `Group Join` como LEFT OUTER JOIN.  
  
 Los ejemplos de este tema muestran una cuantas formas de combinar datos utilizando las cláusulas de consulta `Group Join` y `Join`.  
  
## Crear un proyecto y agregar datos de ejemplo  
  
#### Para crear un proyecto que contiene datos y tipos de ejemplo  
  
1.  Para ejecutar los ejemplos de este tema, abra Visual Studio y agregue un nuevo proyecto de aplicación de consola de Visual Basic.  Haga doble clic en el archivo Module1.vb creado por Visual Basic.  
  
2.  Los ejemplos de este tema usan los tipos `Person` y `Pet`, así como los datos del siguiente ejemplo de código.  Copie este código en el módulo `Module1` predeterminado creado por Visual Basic.  
  
     [!code-vb[VbLINQHowTos#1](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/visualbasic/VbLINQHowTos/Module1.vb#1)]  
    [!code-vb[VbLINQHowTos#2](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/visualbasic/VbLINQHowTos/Module1.vb#2)]  
  
## Realizar una combinación interna mediante la cláusula Join  
 Una combinación INNER JOIN combina los datos de dos colecciones.  Los elementos para los que se incluye la coincidencia de los valores clave especificados.  Se excluye cualquier elemento de cualquier colección que no tenga ningún elemento coincidente en la otra colección.  
  
 En Visual Basic, LINQ proporciona dos opciones para realizar una combinación INNER JOIN: una combinación implícita y una explícita.  
  
 Una combinación implícita especifica las colecciones que se van a combinar en una cláusula `From` e identifica los campos clave coincidentes de una cláusula `Where`.  Visual Basic combina implícitamente las dos colecciones basándose en los campos clave especificados.  
  
 Puede especificar una combinación explícita utilizando la cláusula `Join` cuando desee ser concreto sobre los campos clave que se van a usar en la combinación.  En este caso, una cláusula `Where` se puede seguir usando para filtrar los resultados de la consulta.  
  
#### Para realizar una combinación interna mediante la cláusula Join  
  
1.  Agregue el código siguiente al módulo `Module1` del proyecto para ver ejemplos de una combinación interna tanto implícita como explícita.  
  
     [!code-vb[VbLINQHowTos#4](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/visualbasic/VbLINQHowTos/Module1.vb#4)]  
  
## Realizar una combinación externa izquierda mediante la cláusula Group Join  
 Una combinación LEFT OUTER JOIN incluye todos los elementos de la colección de la izquierda de la combinación y sólo los valores coincidentes de la colección de la derecha de la combinación.  Cualquier elemento de la colección de la derecha de la combinación que no tiene ningún elemento coincidente en la colección de la izquierda se excluye del resultado de la consulta.  
  
 La cláusula `Group Join` realiza, de hecho, una combinación LEFT OUTER JOIN.  La diferencia entre lo que normalmente se conoce como LEFT OUTER JOIN y lo que devuelve la cláusula `Group Join` es que la cláusula `Group Join` agrupa los resultados de la colección de la derecha de la combinación de cada elemento de la colección de la izquierda.  En una base de datos relacional, una combinación LEFT OUTER JOIN devuelve un resultado desagrupado en el que cada elemento del resultado de la consulta contiene los elementos coincidentes de ambas colecciones de la combinación.  En este caso, los elementos de la colección de la izquierda de la combinación se repiten por cada elemento coincidente de la colección de la derecha.  Verá el aspecto cuando complete el procedimiento siguiente.  
  
 Puede recuperar los resultados de una consulta `Group Join` como resultado desagrupado ampliando la consulta para devolver un elemento por cada resultado de la consulta agrupado.  Para ello, debe asegurarse de que realiza la consulta en el método `DefaultIfEmpty` de la colección agrupada.  De esta forma, se asegura de que los elementos de la colección de la izquierda de la combinación siguen estando incluidos en el resultado de la consulta aunque no tengan ningún resultado coincidente en la colección de la derecha.  Puede agregar código a la consulta para proporcionar un valor de resultado predeterminado cuando no haya ningún valor coincidente en la colección de la derecha de la combinación.  
  
#### Para realizar una combinación externa izquierda mediante la cláusula Group Join  
  
1.  Agregue el código siguiente al módulo `Module1` del proyecto para ver ejemplos tanto de una combinación externa izquierda agrupada como de una combinación externa izquierda desagrupada.  
  
     [!code-vb[VbLINQHowTos#3](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/visualbasic/VbLINQHowTos/Module1.vb#3)]  
  
## Realizar una combinación mediante una clave compuesta  
 Puede utilizar la palabra clave `And` en la cláusula `Join` o `Group Join` para identificar varios campos clave que se van a usar cuando se combinen los valores coincidentes de las colecciones.  La palabra clave `And` especifica que todos los campos clave especificados deben coincidir con los elementos que se van a combinar.  
  
#### Para realizar una combinación mediante una clave compuesta  
  
1.  Agregue el código siguiente al módulo `Module1` del proyecto para ver ejemplos de una combinación que usa una clave compuesta.  
  
     [!code-vb[VbLINQHowTos#5](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/visualbasic/VbLINQHowTos/Module1.vb#5)]  
  
## Ejecutar el código  
  
#### Para agregar código con el fin de ejecutar los ejemplos  
  
1.  Reemplace `Sub Main` en el módulo `Module1` del proyecto por el código siguiente para ejecutar los ejemplos de este tema.  
  
     [!code-vb[VbLINQHowTos#6](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/visualbasic/VbLINQHowTos/Module1.vb#6)]  
  
2.  Presione F5 para ejecutar los ejemplos.  
  
## Vea también  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Join \(Cláusula\)](../../../../visual-basic/language-reference/queries/join-clause.md)   
 [Group Join \(Cláusula\)](../../../../visual-basic/language-reference/queries/group-join-clause.md)   
 [From \(Cláusula\)](../../../../visual-basic/language-reference/queries/from-clause.md)   
 [Where \(Cláusula\)](../../../../visual-basic/language-reference/queries/where-clause.md)   
 [Consultas](../../../../visual-basic/language-reference/queries/queries.md)   
 [Transformaciones de datos con LINQ \(C\#\)](../../../../csharp/programming-guide/concepts/linq/data-transformations-with-linq.md)