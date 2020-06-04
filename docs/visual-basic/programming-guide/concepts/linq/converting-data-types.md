---
title: Conversión de tipos de datos
ms.date: 07/20/2015
ms.assetid: 9b0cf1ab-de48-4c6e-9f00-05b40fade46e
ms.openlocfilehash: 1394f53923ba850ae11fbc326a25c279589c3be1
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410856"
---
# <a name="converting-data-types-visual-basic"></a>Convertir tipos de datos (Visual Basic)

Los métodos de conversión cambian el tipo de los objetos de entrada.

 Las operaciones de conversión en las consultas LINQ son útiles en una serie de aplicaciones. A continuación se muestran algunos ejemplos.

- El método <xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType> puede usarse para ocultar una implementación personalizada de tipo de un operador de consulta estándar.

- El método <xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType> puede usarse para permitir colecciones no parametrizadas para las consultas LINQ.

- Los métodos <xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> y <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType> pueden usarse para aplicar la ejecución de consultas inmediata en lugar de aplazarla hasta que se enumere la consulta.

## <a name="methods"></a>Métodos

En la siguiente tabla se muestran los métodos de operadores de consulta estándar que efectúan conversiones de tipo de datos.

Los métodos de conversión de esta tabla cuyos nombres comienzan por "As" cambian el tipo estático de la colección de origen, pero no lo enumeran. Los métodos cuyos nombres empiezan por "To" enumeran la colección de origen y colocan los elementos en el tipo de colección correspondiente.

|Nombre de método|Descripción|Visual Basic sintaxis de expresiones de consulta|Más información|
|-----------------|-----------------|------------------------------------------|----------------------|
|AsEnumerable|Devuelve la entrada con tipo como <xref:System.Collections.Generic.IEnumerable%601>.|No aplicable.|<xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType>|
|AsQueryable|Convierte un <xref:System.Collections.IEnumerable> (genérico) en un <xref:System.Linq.IQueryable> (genérico).|No aplicable.|<xref:System.Linq.Queryable.AsQueryable%2A?displayProperty=nameWithType>|
|Conversión|Convierte los elementos de una colección en un tipo especificado.|`From … As …`|<xref:System.Linq.Enumerable.Cast%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Cast%2A?displayProperty=nameWithType>|
|OfType|Filtra valores en función de su capacidad para convertirse en un tipo especificado.|No aplicable.|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|
|ToArray|Convierte una colección en una matriz. Este método fuerza la ejecución de la consulta.|No aplicable.|<xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>|
|ToDictionary|Coloca elementos en <xref:System.Collections.Generic.Dictionary%602> basándose en una función de selector de claves. Este método fuerza la ejecución de la consulta.|No aplicable.|<xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>|
|ToList|Convierte una colección en <xref:System.Collections.Generic.List%601>. Este método fuerza la ejecución de la consulta.|No aplicable.|<xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>|
|ToLookup|Coloca elementos en una <xref:System.Linq.Lookup%602> (un diccionario uno a varios) basándose en una función de selector de claves. Este método fuerza la ejecución de la consulta.|No aplicable.|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|

## <a name="query-expression-syntax-example"></a>Ejemplo de sintaxis de expresiones de consulta

En el ejemplo de código siguiente `From As` se usa la cláusula para convertir un tipo en un subtipo antes de tener acceso a un miembro que solo está disponible en el subtipo.

```vb
Class Plant
    Public Property Name As String
End Class

Class CarnivorousPlant
    Inherits Plant
    Public Property TrapType As String
End Class

Sub Cast()

    Dim plants() As Plant = {
        New CarnivorousPlant With {.Name = "Venus Fly Trap", .TrapType = "Snap Trap"},
        New CarnivorousPlant With {.Name = "Pitcher Plant", .TrapType = "Pitfall Trap"},
        New CarnivorousPlant With {.Name = "Sundew", .TrapType = "Flypaper Trap"},
        New CarnivorousPlant With {.Name = "Waterwheel Plant", .TrapType = "Snap Trap"}}

    Dim query = From plant As CarnivorousPlant In plants
                Where plant.TrapType = "Snap Trap"
                Select plant

    Dim sb As New System.Text.StringBuilder()
    For Each plant In query
        sb.AppendLine(plant.Name)
    Next

    ' Display the results.
    MsgBox(sb.ToString())

    ' This code produces the following output:

    ' Venus Fly Trap
    ' Waterwheel Plant

End Sub
```

## <a name="see-also"></a>Consulte también

- <xref:System.Linq>
- [Información general sobre operadores de consulta estándar (Visual Basic)](standard-query-operators-overview.md)
- [Cláusula FROM](../../../language-reference/queries/from-clause.md)
- [Cómo: consultar una ArrayList con LINQ (Visual Basic)](how-to-query-an-arraylist-with-linq.md)
