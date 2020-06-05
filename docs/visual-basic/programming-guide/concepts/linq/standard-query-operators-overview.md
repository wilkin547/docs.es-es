---
title: Información general sobre operadores de consulta estándar
ms.date: 07/20/2015
ms.assetid: 302bd39e-2ec1-495b-94bf-37d370d6f05f
ms.openlocfilehash: 7c229a576f6695282473352d6253d2c699c76604
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406786"
---
# <a name="standard-query-operators-overview-visual-basic"></a>Información general sobre operadores de consulta estándar (Visual Basic)

Los *operadores de consulta estándar* son los métodos que constituyen el modelo LINQ. La mayoría de estos métodos funciona en secuencias; donde una secuencia es un objeto cuyo tipo implementa la interfaz <xref:System.Collections.Generic.IEnumerable%601> o la interfaz <xref:System.Linq.IQueryable%601>. Los operadores de consulta estándar ofrecen funcionalidades de consulta, como las funciones de filtrado, proyección, agregación y ordenación, entre otras.

Hay dos conjuntos de operadores de consulta estándar de LINQ, uno que actúa sobre objetos de tipo <xref:System.Collections.Generic.IEnumerable%601> y otro que actúa en objetos de tipo <xref:System.Linq.IQueryable%601>. Los métodos que forman cada conjunto son miembros estáticos de las clases <xref:System.Linq.Enumerable> y <xref:System.Linq.Queryable>, respectivamente. Se definen como *métodos de extensión* del tipo en el que actúan. Esto significa que se pueden llamar mediante sintaxis de método estático o sintaxis de método de instancia.

Además, varios métodos de operador de consulta estándar funcionan en tipos distintos de los que se basan en <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Linq.IQueryable%601>. El tipo <xref:System.Linq.Enumerable> define dos métodos que funcionan en objetos de tipo <xref:System.Collections.IEnumerable>. Estos métodos, <xref:System.Linq.Enumerable.Cast%60%601%28System.Collections.IEnumerable%29> y <xref:System.Linq.Enumerable.OfType%60%601%28System.Collections.IEnumerable%29>, le permiten habilitar una colección no genérica o no parametrizada para consultarse en el patrón LINQ. Para ello, se crea una colección de objetos fuertemente tipados. La clase <xref:System.Linq.Queryable> define dos métodos similares, <xref:System.Linq.Queryable.Cast%60%601%28System.Linq.IQueryable%29> y <xref:System.Linq.Queryable.OfType%60%601%28System.Linq.IQueryable%29>, que funcionan en objetos de tipo <xref:System.Linq.Queryable>.

Los operadores de consulta estándar difieren en sus intervalos de ejecución, dependiendo de que devuelvan un valor singleton o una secuencia de valores. Esos métodos que devuelven un valor singleton (por ejemplo, <xref:System.Linq.Enumerable.Average%2A> y <xref:System.Linq.Enumerable.Sum%2A>) se ejecutan inmediatamente. Los métodos que devuelven una secuencia aplazan la ejecución de la consulta y devuelven un objeto enumerable.

En el caso de los métodos que actúan en colecciones en memoria, es decir, los métodos que extienden <xref:System.Collections.Generic.IEnumerable%601>, el objeto enumerable devuelto captura los argumentos que se han pasado al método. Cuando se enumera ese objeto, se emplea la lógica del operador de consulta y se devuelven los resultados de la consulta.

En cambio, los métodos que extienden <xref:System.Linq.IQueryable%601> no implementan ningún comportamiento de consulta, pero crean un árbol de la expresión que representa la consulta que se va a realizar. El procesamiento de consultas se controla mediante el objeto <xref:System.Linq.IQueryable%601> de origen.

Las llamadas a métodos de consulta se pueden encadenar juntas en una consulta, lo que permite que las consultas se conviertan en complejas de forma arbitraria.

En el ejemplo de código siguiente se muestra el uso de los operadores de consulta estándar para obtener información sobre una secuencia.

```vb
Dim sentence = "the quick brown fox jumps over the lazy dog"
' Split the string into individual words to create a collection.
Dim words = sentence.Split(" "c)

Dim query = From word In words
            Group word.ToUpper() By word.Length Into gr = Group
            Order By Length _
            Select Length, GroupedWords = gr

Dim output As New System.Text.StringBuilder
For Each obj In query
    output.AppendLine(String.Format("Words of length {0}:", obj.Length))
    For Each word As String In obj.GroupedWords
        output.AppendLine(word)
    Next
Next

'Display the output
MsgBox(output.ToString())

' This code example produces the following output:
'
' Words of length 3:
' THE
' FOX
' THE
' DOG
' Words of length 4:
' OVER
' LAZY
' Words of length 5:
' QUICK
' BROWN
' JUMPS
```

## <a name="query-expression-syntax"></a>Sintaxis de expresiones de consulta

Algunos de los operadores de consulta estándar que se usan con más frecuencia tienen una sintaxis especial de palabras clave dedicadas de lenguaje C# y Visual Basic para que se puedan invocar como parte de una *expresión* *de consulta*. Para obtener más información sobre los operadores de consulta estándar que tienen palabras clave dedicadas y sus sintaxis correspondientes, vea [Sintaxis de expresiones de consulta para operadores de consulta estándar (Visual Basic)](query-expression-syntax-for-standard-query-operators.md).

## <a name="extending-the-standard-query-operators"></a>Extender los operadores de consulta estándar

Puede aumentar el conjunto de operadores de consulta estándar creando métodos específicos de dominio que sean adecuados para su tecnología o dominio de destino. También puede reemplazar los operadores de consulta estándar con sus propias implementaciones que proporcionen otros servicios tales como evaluación remota, traducción de consultas y optimización. Vea <xref:System.Linq.Enumerable.AsEnumerable%2A> para obtener un ejemplo.

## <a name="related-sections"></a>Secciones relacionadas

Los vínculos siguientes le llevan a temas que ofrecen información adicional sobre los distintos operadores de consulta estándar según la funcionalidad.

- [Ordenación de datos](sorting-data.md)

- [Operaciones Set (Visual Basic)](set-operations.md)

- [Filtrar datos (Visual Basic)](filtering-data.md)

- [Operaciones cuantificadoras (Visual Basic)](quantifier-operations.md)

- [Operaciones de proyección (Visual Basic)](projection-operations.md)

- [Creación de particiones de datos (Visual Basic)](partitioning-data.md)

- [Operaciones de combinación (Visual Basic)](join-operations.md)

- [Agrupar datos (Visual Basic)](grouping-data.md)

- [Operaciones de generación (Visual Basic)](generation-operations.md)

- [Operaciones de igualdad (Visual Basic)](equality-operations.md)

- [Operaciones de elementos (Visual Basic)](element-operations.md)

- [Convertir tipos de datos (Visual Basic)](converting-data-types.md)

- [Operaciones de concatenación (Visual Basic)](concatenation-operations.md)

- [Operaciones de agregación (Visual Basic)](aggregation-operations.md)

## <a name="see-also"></a>Vea también

- <xref:System.Linq.Enumerable>
- <xref:System.Linq.Queryable>
- [Introducción a LINQ (Visual Basic)](introduction-to-linq.md)
- [Sintaxis de expresiones de consulta para operadores de consulta estándar (Visual Basic)](query-expression-syntax-for-standard-query-operators.md)
- [Clasificación de operadores de consulta estándar por modo de ejecución (Visual Basic)](classification-of-standard-query-operators-by-manner-of-execution.md)
- [Métodos de extensión](../../language-features/procedures/extension-methods.md)
