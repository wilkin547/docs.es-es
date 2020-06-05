---
title: Aggregate Clause
ms.date: 08/28/2018
f1_keywords:
- vb.QueryAggregateIn
- vb.QueryAggregate
- vb.QueryAggregateInto
helpviewer_keywords:
- Aggregate clause [Visual Basic]
- Aggregate statement [Visual Basic]
- queries [Visual Basic], Aggregate
ms.assetid: 1315a814-5db6-4077-b34b-b141e11cc0eb
ms.openlocfilehash: 326c3306368ceca2122e912556efd84e4bfef1f1
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84413006"
---
# <a name="aggregate-clause-visual-basic"></a>Aggregate (Cláusula, Visual Basic)
Aplica una o más funciones de agregado a una colección.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
Aggregate element [As type] In collection _  
  [, element2 [As type2] In collection2, [...]]  
  [ clause ]  
  Into expressionList  
```  
  
## <a name="parts"></a>Partes  
  
|Término|Definición|  
|---|---|  
|`element`|Obligatorio. Variable usada para recorrer en iteración los elementos de la colección.|  
|`type`|Opcional. Tipo de `element`. Si no se especifica ningún tipo, el tipo de `element` se deduce de `collection` .|  
|`collection`|Necesario. Hace referencia a la colección en la que se va a operar.|  
|`clause`|Opcional. Una o varias cláusulas de consulta, como una `Where` cláusula, para refinar el resultado de la consulta a fin de aplicar la cláusula o cláusulas de agregado a.|  
|`expressionList`|Necesario. Una o más expresiones delimitadas por comas que identifican una función de agregado que se va a aplicar a la colección. Puede aplicar un alias a una función de agregado para especificar un nombre de miembro para el resultado de la consulta. Si no se proporciona ningún alias, se utiliza el nombre de la función de agregado. Para obtener ejemplos, vea la sección acerca de las funciones de agregado más adelante en este tema.|  
  
## <a name="remarks"></a>Observaciones  
 La `Aggregate` cláusula se puede utilizar para incluir funciones de agregado en las consultas. Las funciones de agregado realizan comprobaciones y cálculos sobre un conjunto de valores y devuelven un valor único. Puede tener acceso al valor calculado mediante el uso de un miembro del tipo de resultado de la consulta. Las funciones de agregado estándar que se pueden usar son las `All` funciones,,,,,, `Any` `Average` `Count` `LongCount` `Max` `Min` y `Sum` . Estas funciones resultan familiares a los desarrolladores que están familiarizados con los agregados de SQL. Se describen en la sección siguiente de este tema.  
  
 El resultado de una función de agregado se incluye en el resultado de la consulta como un campo del tipo de resultado de la consulta. Puede proporcionar un alias para que el resultado de la función de agregado especifique el nombre del miembro del tipo de resultado de la consulta que contendrá el valor agregado. Si no se proporciona ningún alias, se utiliza el nombre de la función de agregado.  
  
 La `Aggregate` cláusula puede comenzar una consulta o se puede incluir como una cláusula adicional en una consulta. Si la `Aggregate` cláusula comienza una consulta, el resultado es un valor único que es el resultado de la función de agregado especificada en la `Into` cláusula. Si se especifica más de una función de agregado en la `Into` cláusula, la consulta devuelve un tipo único con una propiedad independiente para hacer referencia al resultado de cada función de agregado en la `Into` cláusula. Si la `Aggregate` cláusula se incluye como una cláusula adicional en una consulta, el tipo devuelto en la colección de consultas tendrá una propiedad independiente para hacer referencia al resultado de cada función de agregado en la `Into` cláusula.  
  
## <a name="aggregate-functions"></a>Funciones de agregado

A continuación se enumeran las funciones de agregado estándar que se pueden usar con la `Aggregate` cláusula.  
  
### <a name="all"></a>All

Devuelve `true` si todos los elementos de la colección satisfacen una condición especificada; de lo contrario, devuelve `false` . Este es un ejemplo:

 [!code-vb[VbSimpleQuerySamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#5)]

### <a name="any"></a>Any

Devuelve `true` si algún elemento de la colección satisface una condición especificada; de lo contrario, devuelve `false` . Este es un ejemplo:

 [!code-vb[VbSimpleQuerySamples#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#6)]

### <a name="average"></a>Average

Calcula el promedio de todos los elementos de la colección o calcula una expresión proporcionada para todos los elementos de la colección. Este es un ejemplo:

 [!code-vb[VbSimpleQuerySamples#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#7)]

### <a name="count"></a>Count

Cuenta el número de elementos de la colección. Puede proporcionar una expresión opcional `Boolean` para contar solo el número de elementos de la colección que satisfacen una condición. Este es un ejemplo:

 [!code-vb[VbSimpleQuerySamples#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#8)]

### <a name="group"></a>Grupo

Hace referencia a los resultados de la consulta agrupados como resultado de `Group By` una `Group Join` cláusula o. La `Group` función solo es válida en la `Into` cláusula de una `Group By` `Group Join` cláusula o. Para obtener más información y ejemplos, vea cláusula [Group by](group-by-clause.md) y Group [join](group-join-clause.md).

### <a name="longcount"></a>LongCount

Cuenta el número de elementos de la colección. Puede proporcionar una expresión opcional `Boolean` para contar solo el número de elementos de la colección que satisfacen una condición. Devuelve el resultado como `Long` . Para obtener un ejemplo, vea la `Count` función de agregado.

### <a name="max"></a>Max

Calcula el valor máximo de la colección o calcula una expresión proporcionada para todos los elementos de la colección. Este es un ejemplo:

 [!code-vb[VbSimpleQuerySamples#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#9)]

### <a name="min"></a>Min

Calcula el valor mínimo de la colección o calcula una expresión proporcionada para todos los elementos de la colección. Este es un ejemplo:

 [!code-vb[VbSimpleQuerySamples#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#10)]

### <a name="sum"></a>Sum

Calcula la suma de todos los elementos de la colección o calcula una expresión proporcionada para todos los elementos de la colección. Este es un ejemplo:

 [!code-vb[VbSimpleQuerySamples#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#15)]

## <a name="example"></a>Ejemplo  

En el ejemplo siguiente se muestra cómo utilizar la `Aggregate` cláusula para aplicar funciones de agregado al resultado de una consulta.  
  
 [!code-vb[VbSimpleQuerySamples#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#4)]  
  
## <a name="creating-user-defined-aggregate-functions"></a>Crear funciones de agregado definidas por el usuario

 Puede incluir sus propias funciones de agregado personalizadas en una expresión de consulta agregando métodos de extensión al <xref:System.Collections.Generic.IEnumerable%601> tipo. Después, el método personalizado puede realizar un cálculo o una operación en la colección Enumerable que ha hecho referencia a la función de agregado. Para obtener más información sobre los métodos de extensión, vea [Métodos de extensión](../../programming-guide/language-features/procedures/extension-methods.md).  
  
 Por ejemplo, en el ejemplo siguiente se muestra una función de agregado personalizada que calcula el valor medio de una colección de números. Hay dos sobrecargas del método de `Median` extensión. La primera sobrecarga acepta, como entrada, una colección de tipo `IEnumerable(Of Double)` . Si `Median` se llama a la función de agregado para un campo de consulta de tipo `Double` , se llamará a este método. A la segunda sobrecarga del `Median` método se le puede pasar cualquier tipo genérico. La sobrecarga genérica del `Median` método toma un segundo parámetro que hace referencia `Func(Of T, Double)` a la expresión lambda para proyectar un valor para un tipo (de una colección) como el valor correspondiente de tipo `Double` . A continuación, delega el cálculo del valor medio en la otra sobrecarga del `Median` método. Para obtener más información sobre las expresiones lambda, vea [expresiones lambda](../../programming-guide/language-features/procedures/lambda-expressions.md).  
  
 [!code-vb[VbSimpleQuerySamples#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/UserDefinedAggregates.vb#18)]  
  
 En el ejemplo siguiente se muestran consultas de ejemplo que llaman a la `Median` función de agregado en una colección de tipo `Integer` y una colección de tipo `Double` . La consulta que llama a la `Median` función de agregado en la colección de tipo `Double` llama a la sobrecarga del `Median` método que acepta, como entrada, una colección de tipo `Double` . La consulta que llama a la `Median` función de agregado en la colección de tipo `Integer` llama a la sobrecarga genérica del `Median` método.  
  
 [!code-vb[VbSimpleQuerySamples#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/UserDefinedAggregates.vb#19)]  
  
## <a name="see-also"></a>Consulte también

- [Introducción a LINQ en Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [Consultas](index.md)
- [Select (cláusula)](select-clause.md)
- [Cláusula FROM](from-clause.md)
- [Cláusula WHERE](where-clause.md)
- [Group by (cláusula)](group-by-clause.md)
