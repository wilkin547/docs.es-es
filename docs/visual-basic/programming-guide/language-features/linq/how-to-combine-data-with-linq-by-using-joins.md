---
title: Filtrar Combinar datos con LINQ usando cláusulas Join (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], joins
- joins [LINQ in Visual Basic]
- Join clause [LINQ in Visual Basic]
- Group Join clause [Visual Basic]
- joining [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 5b00a478-035b-41c6-8918-be1a97728396
ms.openlocfilehash: dde627edfeb1d4473c9d2e01b9ff83c580a0f122
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58822692"
---
# <a name="how-to-combine-data-with-linq-by-using-joins-visual-basic"></a>Filtrar Combinar datos con LINQ usando cláusulas Join (Visual Basic)
Visual Basic proporciona el `Join` y `Group Join` cláusulas que le permite combinar el contenido de varias colecciones basadas en valores comunes entre las colecciones de consulta. Estos valores se conocen como *clave* valores. Reconocerán los desarrolladores familiarizados con conceptos de base de datos relacional el `Join` cláusula como INNER JOIN y `Group Join` cláusula as, de hecho, LEFT OUTER JOIN.  
  
 Los ejemplos de este tema muestran algunos ejemplos de cómo combinar datos mediante el uso de la `Join` y `Group Join` cláusulas de consulta.  
  
## <a name="create-a-project-and-add-sample-data"></a>Cree un proyecto y agregar datos de ejemplo  
  
#### <a name="to-create-a-project-that-contains-sample-data-and-types"></a>Para crear un proyecto que contiene los tipos y datos de ejemplo  
  
1.  Para ejecutar los ejemplos de este tema, abra Visual Studio y agregue un nuevo proyecto de aplicación de consola de Visual Basic. Haga doble clic en el archivo Module1.vb creado por Visual Basic.  
  
2.  Los ejemplos de este tema usan el `Person` y `Pet` tipos y los datos de ejemplo de código siguiente. Copie este código en el valor predeterminado `Module1` módulo creado por Visual Basic.  
  
     [!code-vb[VbLINQHowTos#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#1)]  
    [!code-vb[VbLINQHowTos#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#2)]  
  
## <a name="perform-an-inner-join-by-using-the-join-clause"></a>Realizar una combinación interna mediante la cláusula de combinación  
 INNER JOIN combina los datos de dos colecciones. Se incluyen los elementos que coinciden con los valores de clave especificados. Se excluyen los elementos de cualquier colección que no tiene un elemento coincidente en la otra colección.  
  
 En Visual Basic, LINQ proporciona dos opciones para realizar una combinación interna: una combinación implícita y una combinación explícita.  
  
 Una combinación implícita especifica las colecciones que combinarse una `From` cláusula e identifica los campos clave coincidentes en un `Where` cláusula. Visual Basic combina implícitamente las dos colecciones en función de los campos de clave especificados.  
  
 Puede especificar una combinación explícita mediante la `Join` cláusula cuando desee especificar qué clave campos para utilizar en la combinación. En este caso, un `Where` cláusula aún puede usarse para filtrar los resultados de consulta.  
  
#### <a name="to-perform-an-inner-join-by-using-the-join-clause"></a>Para realizar una combinación interna mediante la cláusula de combinación  
  
1.  Agregue el código siguiente a la `Module1` módulo en el proyecto para ver ejemplos de ambos una implícita y explícita combinación interna.  
  
     [!code-vb[VbLINQHowTos#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#4)]  
  
## <a name="perform-a-left-outer-join-by-using-the-group-join-clause"></a>Realizar una combinación externa izquierda mediante la cláusula Group Join  
 Una combinación externa izquierda incluye todos los elementos de la colección del lado izquierdo de la combinación y sólo los valores de la colección del lado derecho de la combinación coincidentes. Los elementos de la colección del lado derecho de la combinación que no tiene un elemento coincidente en la colección del lado izquierdo se excluirán del resultado de la consulta.  
  
 El `Group Join` cláusula realiza, de hecho, LEFT OUTER JOIN. La diferencia entre lo que normalmente se conoce como una combinación externa izquierda y cuáles las `Group Join` cláusula devuelve es que la `Group Join` los resultados de grupos de cláusula de la colección del lado derecho de la combinación para cada elemento de la colección del lado izquierdo. En una base de datos relacional, una combinación externa izquierda devuelve un resultado sin agrupar en el que dar lugar a cada elemento de la consulta contiene los elementos coincidentes de ambas colecciones en la combinación. En este caso, los elementos de la colección del lado izquierdo de la combinación se repiten para cada elemento coincidente de la colección del lado derecho. Podrá ver qué aspecto cuando se complete el procedimiento siguiente.  
  
 Puede recuperar los resultados de una `Group Join` consulta como un resultado no agrupado mediante la extensión de la consulta para devolver un elemento para cada resultado de consulta agrupada. Para ello, tiene que asegurarse de que consulta en el `DefaultIfEmpty` método de la colección agrupada. Esto garantiza que los elementos de la colección del lado izquierdo de la combinación todavía se incluyen en el resultado de la consulta incluso si tienen que no hay resultados coincidentes de la colección del lado derecho. Puede agregar código a la consulta para proporcionar un valor de resultado de forma predeterminada cuando no hay ningún valor coincidente de la colección del lado derecho de la combinación.  
  
#### <a name="to-perform-a-left-outer-join-by-using-the-group-join-clause"></a>Para llevar a cabo Left Outer Join con la cláusula Group Join  
  
1.  Agregue el código siguiente a la `Module1` módulo en el proyecto para ver ejemplos de una combinación externa izquierda agrupada y una combinación externa izquierda sin agrupar.  
  
     [!code-vb[VbLINQHowTos#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#3)]  
  
## <a name="perform-a-join-by-using-a-composite-key"></a>Realizar una combinación con una clave compuesta  
 Puede usar el `And` palabra clave en un `Join` o `Group Join` cláusula para identificar varios campos de clave para usar al comparar los valores de las colecciones que se están combina. El `And` palabra clave especifica que todos especificado deben coincidir con los campos de clave para que los elementos que se unirán.  
  
#### <a name="to-perform-a-join-by-using-a-composite-key"></a>Para realizar una combinación con una clave compuesta  
  
1.  Agregue el código siguiente a la `Module1` módulo en el proyecto para ver ejemplos de una combinación que utiliza una clave compuesta.  
  
     [!code-vb[VbLINQHowTos#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#5)]  
  
## <a name="run-the-code"></a>Ejecute el código  
  
#### <a name="to-add-code-to-run-the-examples"></a>Para agregar código para ejecutar los ejemplos  
  
1.  Reemplace el `Sub Main` en el `Module1` módulo en el proyecto con el código siguiente para ejecutar los ejemplos de este tema.  
  
     [!code-vb[VbLINQHowTos#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#6)]  
  
2.  Presione F5 para ejecutar los ejemplos.  
  
## <a name="see-also"></a>Vea también

- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Join (cláusula)](../../../../visual-basic/language-reference/queries/join-clause.md)
- [Group Join (cláusula)](../../../../visual-basic/language-reference/queries/group-join-clause.md)
- [From (cláusula)](../../../../visual-basic/language-reference/queries/from-clause.md)
- [Where (cláusula)](../../../../visual-basic/language-reference/queries/where-clause.md)
- [Consultas](../../../../visual-basic/language-reference/queries/index.md)
- [Transformaciones de datos con LINQ (C#)](../../../../csharp/programming-guide/concepts/linq/data-transformations-with-linq.md)
