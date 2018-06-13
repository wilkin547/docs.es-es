---
title: Aggregate (Cláusula, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryAggregateIn
- vb.QueryAggregate
- vb.QueryAggregateInto
helpviewer_keywords:
- Aggregate clause [Visual Basic]
- Aggregate statement [Visual Basic]
- queries [Visual Basic], Aggregate
ms.assetid: 1315a814-5db6-4077-b34b-b141e11cc0eb
ms.openlocfilehash: 1db4b7fdcf9c8a38c2c49eca9d874eccea90ab1d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604905"
---
# <a name="aggregate-clause-visual-basic"></a>Aggregate (Cláusula, Visual Basic)
Aplica una o más funciones agregadas a una colección.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
Aggregate element [As type] In collection _  
  [, element2 [As type2] In collection2, [...]]  
  [ clause ]  
  Into expressionList  
```  
  
## <a name="parts"></a>Elementos  
  
|Término|Definición|  
|---|---|  
|`element`|Requerido. Variable que se utiliza para recorrer en iteración los elementos de la colección.|  
|`type`|Opcional. Tipo de `element`. Si se especifica ningún tipo, el tipo de `element` se deduce de `collection`.|  
|`collection`|Requerido. Hace referencia a la colección para operar en.|  
|`clause`|Opcional. Uno o más las cláusulas de consulta, como un `Where` cláusula para refinar los resultados de consulta para aplicar las cláusulas para o aggregate (cláusula).|  
|`expressionList`|Requerido. Uno o más delimitada por comas expresiones que identifican una función de agregado para aplicar a la colección. Puede aplicar un alias a una función de agregado para especificar un nombre de miembro para el resultado de la consulta. Si no se proporciona ningún alias, se utiliza el nombre de la función de agregado. Para obtener ejemplos, vea la sección acerca de las funciones de agregado más adelante en este tema.|  
  
## <a name="remarks"></a>Comentarios  
 El `Aggregate` cláusula puede usarse para incluir funciones de agregado en las consultas. Las funciones de agregado realizan comprobaciones y cálculos sobre un conjunto de valores y devuelven un valor único. Puede acceder el valor calculado mediante el uso de un miembro del tipo del resultado de consulta. Las funciones agregadas estándares que puede utilizar son el `All`, `Any`, `Average`, `Count`, `LongCount`, `Max`, `Min`, y `Sum` funciones. Estas funciones son familiares para los programadores que están familiarizados con agregados en SQL. Se describen en la sección siguiente de este tema.  
  
 El resultado de una función de agregado se incluye en el resultado de la consulta como un campo del tipo de resultado de consulta. Puede proporcionar un alias para el resultado de la función de agregado especificar el nombre del miembro del tipo del resultado de consulta que contendrá el valor de agregado. Si no se proporciona ningún alias, se utiliza el nombre de la función de agregado.  
  
 El `Aggregate` cláusula puede iniciar una consulta o se puede incluir como cláusula adicional en una consulta. Si el `Aggregate` cláusula comienza una consulta, el resultado es un valor único que es el resultado de la función de agregado especificada en el `Into` cláusula. Si se especifica más de una función de agregado en la `Into` cláusula, la consulta devuelve un tipo único con una propiedad independiente para hacer referencia al resultado de cada función de agregado en la `Into` cláusula. Si el `Aggregate` cláusula se incluye como una cláusula adicional en una consulta, el tipo devuelto de la colección de consultas tendrá una propiedad independiente para hacer referencia al resultado de cada función de agregado en la `Into` cláusula.  
  
## <a name="aggregate-functions"></a>Funciones de agregado  
 En la lista siguiente describe las funciones de agregado estándares que pueden utilizarse con el `Aggregate` cláusula.  
  
|Función|Descripción|  
|---|---|  
|`All`|Devuelve `true` si todos los elementos de la colección cumplen una condición especificada; en caso contrario, devuelve `false`. A continuación se muestra un ejemplo:<br /><br /> [!code-vb[VbSimpleQuerySamples#5](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_1.vb)]|  
|`Any`|Devuelve `true` si algún elemento de la colección cumple una condición especificada; en caso contrario, devuelve `false`. A continuación se muestra un ejemplo:<br /><br /> [!code-vb[VbSimpleQuerySamples#6](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_2.vb)]|  
|`Average`|Calcula el promedio de todos los elementos de la colección, o calcula la expresión proporcionada para todos los elementos de la colección. A continuación se muestra un ejemplo:<br /><br /> [!code-vb[VbSimpleQuerySamples#7](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_3.vb)]|  
|`Count`|Cuenta el número de elementos de la colección. Puede proporcionar una función opcional `Boolean` expresión para contar sólo el número de elementos de la colección que cumplen una condición. A continuación se muestra un ejemplo:<br /><br /> [!code-vb[VbSimpleQuerySamples#8](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_4.vb)]|  
|`Group`|Hace referencia a los resultados de la consulta que se agrupan como resultado de un `Group By` o `Group Join` cláusula. El `Group` función solo es válida en el `Into` cláusula de una `Group By` o `Group Join` cláusula. Para obtener más información y ejemplos, vea [Group By Clause](../../../visual-basic/language-reference/queries/group-by-clause.md) y [cláusula Join de grupo](../../../visual-basic/language-reference/queries/group-join-clause.md).|  
|`LongCount`|Cuenta el número de elementos de la colección. Puede proporcionar una función opcional `Boolean` expresión para contar sólo el número de elementos de la colección que cumplen una condición. Devuelve el resultado como un `Long`. Para obtener un ejemplo, vea el `Count` función de agregado.|  
|`Max`|Calcula el valor máximo de la colección, o una expresión proporcionada para todos los elementos de la colección. A continuación se muestra un ejemplo:<br /><br /> [!code-vb[VbSimpleQuerySamples#9](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_5.vb)]|  
|`Min`|Calcula el valor mínimo de la colección, o una expresión proporcionada para todos los elementos de la colección. A continuación se muestra un ejemplo:<br /><br /> [!code-vb[VbSimpleQuerySamples#10](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_6.vb)]|  
|`Sum`|Calcula la suma de todos los elementos de la colección, o una expresión proporcionada para todos los elementos de la colección. A continuación se muestra un ejemplo:<br /><br /> [!code-vb[VbSimpleQuerySamples#15](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_7.vb)]|  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se muestra cómo utilizar el `Aggregate` cláusula para aplicar funciones de agregado a un resultado de consulta.  
  
 [!code-vb[VbSimpleQuerySamples#4](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_8.vb)]  
  
## <a name="creating-user-defined-aggregate-functions"></a>Crear funciones de agregado definidas por el usuario  
 Puede incluir sus propias funciones agregados personalizadas en una expresión de consulta agregando métodos de extensión para el <xref:System.Collections.Generic.IEnumerable%601> tipo. El método personalizado, a continuación, puede realizar un cálculo o una operación en la colección enumerable que se hace referencia a la función de agregado. Para obtener más información sobre los métodos de extensión, vea [Extension Methods](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md) (Métodos de extensión).  
  
 Por ejemplo, en el ejemplo de código siguiente se muestra una función agregada personalizada que calcula el valor medio de una colección de números. Hay dos sobrecargas de la `Median` método de extensión. La primera sobrecarga acepta como entrada, una colección de tipo `IEnumerable(Of Double)`. Si el `Median` se llama la función de agregado para un campo de consulta de tipo `Double`, se llamará a este método. La segunda sobrecarga de la `Median` método se puede pasar cualquier tipo genérico. La sobrecarga genérica de la `Median` método toma un segundo parámetro que haga referencia a la `Func(Of T, Double)` una expresión lambda a un valor para un tipo (de una colección) de un proyecto como el valor correspondiente de tipo `Double`. A continuación, delega el cálculo del valor medio a la otra sobrecarga de la `Median` método. Para obtener más información sobre las expresiones lambda, vea [Expresiones lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
 [!code-vb[VbSimpleQuerySamples#18](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_9.vb)]  
  
 El siguiente código en el ejemplo se muestra un ejemplo consultas que llaman a la `Median` función en una colección de tipo de agregado `Integer`y una colección de tipo `Double`. La consulta que llama el `Median` función en la colección de tipo de agregado `Double` llama a la sobrecarga de la `Median` método que acepta como entrada, una colección de tipo `Double`. La consulta que llama el `Median` función en la colección de tipo de agregado `Integer` llama a la sobrecarga genérica de la `Median` método.  
  
 [!code-vb[VbSimpleQuerySamples#19](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_10.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Introducción a LINQ en Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [Consultas](../../../visual-basic/language-reference/queries/queries.md)  
 [Select (cláusula)](../../../visual-basic/language-reference/queries/select-clause.md)  
 [From (cláusula)](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Where (cláusula)](../../../visual-basic/language-reference/queries/where-clause.md)  
 [Group By (cláusula)](../../../visual-basic/language-reference/queries/group-by-clause.md)
