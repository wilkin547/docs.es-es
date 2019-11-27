---
title: 'Cómo: combinar datos con LINQ mediante combinaciones'
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], joins
- joins [LINQ in Visual Basic]
- Join clause [LINQ in Visual Basic]
- Group Join clause [Visual Basic]
- joining [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 5b00a478-035b-41c6-8918-be1a97728396
ms.openlocfilehash: 7279908c5d262b65f4c4da9cd9b6c1b4117bc402
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345000"
---
# <a name="how-to-combine-data-with-linq-by-using-joins-visual-basic"></a>Cómo: Combinar datos con LINQ usando cláusulas Join (Visual Basic)
Visual Basic proporciona las cláusulas de consulta `Join` y `Group Join` para que pueda combinar el contenido de varias colecciones en función de los valores comunes entre las colecciones. Estos valores se conocen como valores de *clave* . Los desarrolladores familiarizados con los conceptos de bases de datos relacionales reconocerán la cláusula `Join` como una combinación interna y la cláusula `Group Join` como, efectivamente, una combinación externa izquierda.  
  
 Los ejemplos de este tema muestran algunas maneras de combinar los datos mediante las cláusulas de consulta `Join` y `Group Join`.  
  
## <a name="create-a-project-and-add-sample-data"></a>Crear un proyecto y agregar datos de ejemplo  
  
#### <a name="to-create-a-project-that-contains-sample-data-and-types"></a>Para crear un proyecto que contenga datos y tipos de ejemplo  
  
1. Para ejecutar los ejemplos de este tema, abra Visual Studio y agregue un nuevo proyecto de aplicación de consola de Visual Basic. Haga doble clic en el archivo Module1. VB creado por Visual Basic.  
  
2. Los ejemplos de este tema usan los tipos de `Person` y `Pet` y los datos del ejemplo de código siguiente. Copie este código en el módulo de `Module1` predeterminado creado por Visual Basic.  
  
     [!code-vb[VbLINQHowTos#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#1)]  
    [!code-vb[VbLINQHowTos#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#2)]  
  
## <a name="perform-an-inner-join-by-using-the-join-clause"></a>Realizar una combinación interna mediante la cláusula join  
 Una combinación interna combina datos de dos colecciones. Se incluyen los elementos para los que coinciden los valores de clave especificados. Se excluyen todos los elementos de cualquier colección que no tengan un elemento coincidente en la otra colección.  
  
 En Visual Basic, LINQ proporciona dos opciones para realizar una combinación interna: una combinación implícita y una combinación explícita.  
  
 Una combinación implícita especifica las colecciones que se van a combinar en una cláusula `From` e identifica los campos clave coincidentes en una cláusula `Where`. Visual Basic combina implícitamente las dos colecciones basándose en los campos de clave especificados.  
  
 Puede especificar una combinación explícita mediante la cláusula `Join` cuando quiera ser específica de qué campos clave usar en la combinación. En este caso, todavía se puede usar una cláusula `Where` para filtrar los resultados de la consulta.  
  
#### <a name="to-perform-an-inner-join-by-using-the-join-clause"></a>Para realizar una combinación interna mediante la cláusula join  
  
1. Agregue el siguiente código al módulo `Module1` del proyecto para ver ejemplos de una combinación interna implícita y explícita.  
  
     [!code-vb[VbLINQHowTos#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#4)]  
  
## <a name="perform-a-left-outer-join-by-using-the-group-join-clause"></a>Realizar una combinación externa izquierda mediante la cláusula Group join  
 Una combinación externa izquierda incluye todos los elementos de la colección del lado izquierdo de la combinación y solo los valores coincidentes de la colección del lado derecho de la combinación. Los elementos de la colección del lado derecho de la combinación que no tienen un elemento coincidente en la colección del lado izquierdo se excluyen del resultado de la consulta.  
  
 La cláusula `Group Join` realiza una combinación externa izquierda, en efecto. La diferencia entre lo que se conoce normalmente como una combinación externa izquierda y lo que devuelve la cláusula `Group Join` es que la cláusula `Group Join` agrupa los resultados de la colección del lado derecho de la combinación para cada elemento de la colección del lado izquierdo. En una base de datos relacional, una combinación externa izquierda devuelve un resultado no agrupado en el que cada elemento del resultado de la consulta contiene elementos coincidentes de ambas colecciones en la combinación. En este caso, los elementos de la colección del lado izquierdo de la combinación se repiten para cada elemento coincidente de la colección del lado derecho. Verá el aspecto que tendrá cuando complete el procedimiento siguiente.  
  
 Puede recuperar los resultados de una consulta de `Group Join` como resultado no agrupado extendiendo la consulta para devolver un elemento para cada resultado de la consulta agrupada. Para ello, debe asegurarse de que consulta en el método `DefaultIfEmpty` de la colección agrupada. Esto garantiza que los elementos de la colección del lado izquierdo de la combinación todavía se incluyen en el resultado de la consulta, incluso si no tienen resultados coincidentes de la colección del lado derecho. Puede agregar código a la consulta para proporcionar un valor de resultado predeterminado cuando no haya ningún valor coincidente en la colección del lado derecho de la combinación.  
  
#### <a name="to-perform-a-left-outer-join-by-using-the-group-join-clause"></a>Para realizar una combinación externa izquierda mediante la cláusula Group join  
  
1. Agregue el siguiente código al módulo `Module1` del proyecto para ver ejemplos de una combinación externa izquierda agrupada y una combinación externa izquierda no agrupada.  
  
     [!code-vb[VbLINQHowTos#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#3)]  
  
## <a name="perform-a-join-by-using-a-composite-key"></a>Realizar una combinación mediante una clave compuesta  
 Puede usar la palabra clave `And` en una cláusula `Join` o `Group Join` para identificar varios campos clave que se usarán al buscar valores coincidentes de las colecciones que se están combinando. La palabra clave `And` especifica que todos los campos de clave especificados deben coincidir con los elementos que se van a combinar.  
  
#### <a name="to-perform-a-join-by-using-a-composite-key"></a>Para realizar una combinación mediante una clave compuesta  
  
1. Agregue el siguiente código al módulo `Module1` del proyecto para ver ejemplos de una combinación que usa una clave compuesta.  
  
     [!code-vb[VbLINQHowTos#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#5)]  
  
## <a name="run-the-code"></a>Ejecutar el código  
  
#### <a name="to-add-code-to-run-the-examples"></a>Para agregar código para ejecutar los ejemplos  
  
1. Reemplace el `Sub Main` en el módulo de `Module1` del proyecto por el código siguiente para ejecutar los ejemplos de este tema.  
  
     [!code-vb[VbLINQHowTos#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#6)]  
  
2. Presione F5 para ejecutar los ejemplos.  
  
## <a name="see-also"></a>Vea también

- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Join (cláusula)](../../../../visual-basic/language-reference/queries/join-clause.md)
- [Group Join (cláusula)](../../../../visual-basic/language-reference/queries/group-join-clause.md)
- [From (cláusula)](../../../../visual-basic/language-reference/queries/from-clause.md)
- [Where (cláusula)](../../../../visual-basic/language-reference/queries/where-clause.md)
- [Consultas](../../../../visual-basic/language-reference/queries/index.md)
- [Transformaciones de datos con LINQ (C#)](../../../../csharp/programming-guide/concepts/linq/data-transformations-with-linq.md)
