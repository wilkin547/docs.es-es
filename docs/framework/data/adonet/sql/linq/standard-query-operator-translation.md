---
description: 'Más información acerca de: traducción de operadores de consulta estándar'
title: Traslación del operador de consulta estándar
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a60c30fa-1e68-45fe-b984-f6abb9ede40e
ms.openlocfilehash: e7e45e8f27f1e7d3c572f00ea014b4edb288b2b0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99681531"
---
# <a name="standard-query-operator-translation"></a>Traslación del operador de consulta estándar

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] convierte los operadores de consulta estándar en comandos SQL. El procesador de consultas de la base de datos determina la semántica de ejecución de la conversión a SQL.

Los operadores de consulta estándar se definen en *secuencias*. Una secuencia se *ordena* y se basa en la identidad de referencia para cada elemento de la secuencia. Para obtener más información, vea información general sobre [operadores de consulta estándar (C#)](../../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) o [información general sobre operadores de consulta estándar (Visual Basic)](../../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).

SQL trata principalmente con *conjuntos de valores desordenados*. La ordenación es normalmente una operación de procesamiento posterior declarada de forma explícita que se aplica al resultado final de una consulta en lugar de a los resultados intermedios. La identidad se define con valores. Por esta razón, las consultas SQL se entienden para tratar con conjuntos (*bolsas*) en lugar de *conjuntos*.

En los párrafos siguientes se describen las diferencias entre los operadores de consulta estándar y su conversión a SQL para el proveedor de SQL Server de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].

## <a name="operator-support"></a>Compatibilidad de los operadores

### <a name="concat"></a>Concat

El método <xref:System.Linq.Enumerable.Concat%2A> se define para los conjuntos múltiples ordenados cuando el orden del receptor y el orden del argumento son iguales. <xref:System.Linq.Enumerable.Concat%2A> funciona como `UNION ALL` sobre los conjuntos múltiples después del orden común.

El último paso es ordenar en SQL antes de que se generen los resultados. <xref:System.Linq.Enumerable.Concat%2A> no conserva el orden de sus argumentos. Para garantizar una ordenación correcta, debe ordenar explícitamente los resultados de <xref:System.Linq.Enumerable.Concat%2A>.

### <a name="intersect-except-union"></a>Intersect, Except, Union

Los métodos <xref:System.Linq.Enumerable.Intersect%2A> y <xref:System.Linq.Enumerable.Except%2A> se definen bien solo en los conjuntos. La semántica de conjuntos múltiples no está definida.

El método <xref:System.Linq.Enumerable.Union%2A> se define para los conjuntos múltiples como la concatenación no ordenada de los conjuntos múltiples (de hecho, el resultado de la cláusula UNION ALL en SQL).

### <a name="take-skip"></a>Take, Skip

<xref:System.Linq.Enumerable.Take%2A><xref:System.Linq.Enumerable.Skip%2A>los métodos y están bien definidos solo en *conjuntos ordenados*. La semántica para los conjuntos no ordenados o conjuntos múltiples no está definida.

> [!NOTE]
> <xref:System.Linq.Enumerable.Take%2A> y <xref:System.Linq.Enumerable.Skip%2A> tienen ciertas limitaciones cuando se utilizan en consultas en SQL Server 2000. Para obtener más información, vea la entrada sobre cómo omitir y tomar excepciones en SQL Server 2000 "en [solución de problemas](troubleshooting.md).

Debido a las limitaciones de la ordenación en SQL, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] intenta trasladar la ordenación del argumento de estos métodos al resultado del método. Por ejemplo, considere la siguiente consulta [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]:

[!code-csharp[DLinqSQOTranslation#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSQOTranslation/cs/Program.cs#1)]
[!code-vb[DLinqSQOTranslation#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSQOTranslation/vb/Module1.vb#1)]

El SQL generado para este código traslada la ordenación al final, como se observa a continuación:

```sql
SELECT TOP 1 [t0].[CustomerID], [t0].[CompanyName],
FROM [Customers] AS [t0]
WHERE (NOT (EXISTS(
    SELECT NULL AS [EMPTY]
    FROM (
        SELECT TOP 1 [t1].[CustomerID]
        FROM [Customers] AS [t1]
        WHERE [t1].[City] = @p0
        ORDER BY [t1].[CustomerID]
        ) AS [t2]
    WHERE [t0].[CustomerID] = [t2].[CustomerID]
    ))) AND ([t0].[City] = @p1)
ORDER BY [t0].[CustomerID]
```

Parece obvio que toda la ordenación especificada debe ser coherente cuando se encadenan <xref:System.Linq.Enumerable.Take%2A> y <xref:System.Linq.Enumerable.Skip%2A>. De lo contrario, los resultados no están definidos.

Tanto <xref:System.Linq.Enumerable.Take%2A> como <xref:System.Linq.Enumerable.Skip%2A> están bien definidos para los argumentos integrales de constante no negativos basados en la especificación de operadores de consulta estándar.

### <a name="operators-with-no-translation"></a>Operadores sin conversión

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no convierte los métodos siguientes. La razón más común es la diferencia entre los conjuntos múltiples no ordenados y las secuencias.

|Operadores|Análisis razonado|
|---------------|---------------|
|<xref:System.Linq.Enumerable.TakeWhile%2A>, <xref:System.Linq.Enumerable.SkipWhile%2A>|Las consultas SQL funcionan con conjuntos múltiples, no con secuencias. `ORDER BY` debe ser la última cláusula aplicada a los resultados. Por esta razón, no hay ninguna conversión general para estos dos métodos.|
|<xref:System.Linq.Enumerable.Reverse%2A>|La conversión de este método es posible para un conjunto ordenado pero [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no la realiza actualmente.|
|<xref:System.Linq.Enumerable.Last%2A>, <xref:System.Linq.Enumerable.LastOrDefault%2A>|La conversión de estos métodos es posible para un conjunto ordenado pero [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no la realiza actualmente.|
|<xref:System.Linq.Enumerable.ElementAt%2A>, <xref:System.Linq.Enumerable.ElementAtOrDefault%2A>|Las consultas SQL funcionan en conjuntos múltiples, no en secuencias indizables.|
|<xref:System.Linq.Enumerable.DefaultIfEmpty%2A> (sobrecarga con argumento predeterminado)|En general, no se puede especificar un valor predeterminado para una tupla arbitraria. Los valores nulos para las tuplas son posibles en algunos casos a través de combinaciones externas.|

## <a name="expression-translation"></a>Conversión de expresiones

### <a name="null-semantics"></a>Semántica de valores null

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no impone las semántica de comparación de valores null en SQL. Los operadores de comparación se convierten sintácticamente en sus equivalentes SQL. Por esta razón, la semántica refleja la semántica de SQL definida según la configuración del servidor o la conexión. Dos valores nulos se consideran distintos según la configuración predeterminada de SQL Server (aunque se puede cambiar la configuración para cambiar la semántica). [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no tiene en cuenta la configuración del servidor cuando convierte las consultas.

Una comparación con el literal null se convierte a la versión de SQL correcta (`is null` o `is not null`).

SQL Server define el valor `null` en la intercalación. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no cambia la intercalación.

### <a name="aggregates"></a>Agregados

El método de agregado del operador de consulta estándar <xref:System.Linq.Enumerable.Sum%2A> se evalúa como cero para una secuencia vacía o para una secuencia que solo contiene valores nulos. En [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] , la semántica de SQL se deja sin cambios y se <xref:System.Linq.Enumerable.Sum%2A> evalúa como en `null` lugar de cero para una secuencia vacía o para una secuencia que solo contiene valores NULL.

En [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] se aplican las restricciones de SQL para los agregados en los resultados intermedios. <xref:System.Linq.Enumerable.Sum%2A> para cantidades enteras de 32 bits no se calcula utilizando los resultados de 64 bits. Puede producirse un desbordamiento en la conversión de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] que realiza <xref:System.Linq.Enumerable.Sum%2A> aun cuando la implementación del operador de consulta estándar no produce un desbordamiento para la secuencia en memoria correspondiente.

De igual forma, la conversión que realiza [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] de <xref:System.Linq.Enumerable.Average%2A> de valores enteros se calcula como `integer`, no como `double`.

### <a name="entity-arguments"></a>Argumentos de entidad

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] permite usar tipos de entidad en los <xref:System.Linq.Enumerable.GroupBy%2A> métodos y <xref:System.Linq.Enumerable.OrderBy%2A> . En la conversión de estos operadores, el uso de un argumento de un tipo se considera equivalente a especificar todos los miembros de ese tipo. Por ejemplo, el código siguiente es equivalente:

[!code-csharp[DLinqSQOTranslation#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSQOTranslation/cs/Program.cs#2)]
[!code-vb[DLinqSQOTranslation#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSQOTranslation/vb/Module1.vb#2)]

### <a name="equatable--comparable-arguments"></a>Argumentos equivalentes o comparables

La igualdad de los argumentos se requiere en la implementación de los métodos siguientes:

- <xref:System.Linq.Enumerable.Contains%2A>

- <xref:System.Linq.Enumerable.Skip%2A>

- <xref:System.Linq.Enumerable.Union%2A>

- <xref:System.Linq.Enumerable.Intersect%2A>

- <xref:System.Linq.Enumerable.Except%2A>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] admite la igualdad y comparación para los argumentos *planos* , pero no para los argumentos que son o contienen secuencias. Un argumento plano es un tipo que asignarse a una fila de SQL. Una proyección de uno o más tipos de entidad que se pueden determinar estáticamente que no contiene una secuencia se considera un argumento plano.

A continuación se muestran ejemplos de argumentos planos:

[!code-csharp[DLinqSQOTranslation#3](~/samples/snippets/csharp/VS_Snippets_Data/DLinqSQOTranslation/cs/Program.cs#3)]
[!code-vb[DLinqSQOTranslation#3](~/samples/snippets/visualbasic/VS_Snippets_Data/DLinqSQOTranslation/vb/Module1.vb#3)]

A continuación se muestran ejemplos de argumentos no planos (jerárquicos):

[!code-csharp[DLinqSQOTranslation#4](~/samples/snippets/csharp/VS_Snippets_Data/DLinqSQOTranslation/cs/Program.cs#4)]
[!code-vb[DLinqSQOTranslation#4](~/samples/snippets/visualbasic/VS_Snippets_Data/DLinqSQOTranslation/vb/Module1.vb#4)]

### <a name="visual-basic-function-translation"></a>Conversión de funciones de Visual Basic

Las siguientes funciones del asistente que utiliza el compilador de Visual Basic se convierten a las funciones y operadores de SQL correspondientes:

- `CompareString`

- `DateTime.Compare`

- `Decimal.Compare`

- `IIf (in Microsoft.VisualBasic.Interaction)`

Métodos de conversión:

|||||
|-|-|-|-|
|ToBoolean|ToSByte|ToByte|ToChar|
|ToCharArrayRankOne|ToDate|ToDecimal|ToDouble|
|ToInteger|ToUInteger|ToLong|ToULong|
|ToShort|ToUShort|ToSingle|ToString|

## <a name="inheritance-support"></a>Compatibilidad de herencia

### <a name="inheritance-mapping-restrictions"></a>Restricciones de la asignación de herencia

Para obtener más información, vea [Cómo: asignar jerarquías de herencia](how-to-map-inheritance-hierarchies.md).

### <a name="inheritance-in-queries"></a>Herencia en consultas

Las conversión de tipos de C# solo se admite en la proyección. Las conversiones de tipos que se utilizan en otra parte no se convierten y se omiten. Además de los nombres de función de SQL, SQL realmente solo realiza la operación equivalente a <xref:System.Convert> de Common Language Runtime (CLR). Es decir, SQL puede cambiar el valor de un tipo a otro. No hay ningún equivalente de conversión de tipos de CLR porque no existe el concepto de reinterpretar los mismos bits que los de otro tipo. Por esa razón una conversión de tipos de C# solo funciona localmente. No es remota.

Los operadores, `is` y `as`, y el método `GetType` no están limitados al operador `Select`. También se pueden utilizar en otros operadores de consulta.

## <a name="sql-server-2008-support"></a>Compatibilidad con SQL Server 2008

A partir de .NET Framework 3.5 Service Pack 1, LINQ to SQL admite la asignación a tipos nuevos de fecha y hora incorporados con SQL Server 2008. Pero, hay algunas limitaciones en los operadores de consulta de LINQ to SQL que puede usar al operar con valores asignados a estos tipos nuevos.

### <a name="unsupported-query-operators"></a>Operadores de consulta no admitidos

Los operadores de consulta siguientes no se admiten en valores asignados a los nuevos tipos de fecha y hora de SQL Server: `DATETIME2`, `DATE`, `TIME` y `DATETIMEOFFSET`.

- `Aggregate`

- `Average`

- `LastOrDefault`

- `OfType`

- `Sum`

Para obtener más información sobre la asignación a estos SQL Server tipos de fecha y hora, vea [asignación de tipos de SQL-CLR](sql-clr-type-mapping.md).

## <a name="sql-server-2005-support"></a>Compatibilidad con SQL Server 2005

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no admite las características de SQL Server 2005 siguientes:

- Procedimientos almacenados escritos para SQL CLR.

- Tipo definido por el usuario.

- Características de consulta XML.

## <a name="sql-server-2000-support"></a>Compatibilidad con SQL Server 2000

Las siguientes limitaciones SQL Server 2000 (en comparación con Microsoft SQL Server 2005) afectan al [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] soporte técnico.

### <a name="cross-apply-and-outer-apply-operators"></a>Operadores Cross Apply y Outer Apply

Estos operadores no están disponibles en SQL Server 2000. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] intenta una serie de operaciones de reescritura para sustituirlos por las combinaciones adecuadas.

`Cross Apply` y `Outer Apply` se generan para la navegación de relaciones. El conjunto de consultas para el que son posibles tales operaciones de reescritura no está bien definido. Por esta razón, el conjunto mínimo de consultas que se admite para SQL Server 2000 es el conjunto que no implica la navegación por la relación.

### <a name="text--ntext"></a>text / ntext

No se `text`  /  `ntext` pueden usar tipos de datos en determinadas operaciones de consulta en `varchar(max)`  /  `nvarchar(max)` , que son compatibles con Microsoft SQL Server 2005.

Esta limitación no tiene ninguna resolución. Concretamente, no puede utilizar `Distinct()` en ningún resultado que contenga miembros que se asignen a columnas `text` o `ntext`.

### <a name="behavior-triggered-by-nested-queries"></a>Comportamiento desencadenado por las consultas anidadas

SQL Server 2000 (a SP4) el enlazador tiene algunas idiosincrasias que se desencadenan mediante consultas anidadas. El conjunto de consultas SQL que las desencadenan no está bien definido. Por esta razón, no se puede definir el conjunto de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] consultas que pueden provocar excepciones SQL Server.

### <a name="skip-and-take-operators"></a>Operadores Skip y Take

<xref:System.Linq.Enumerable.Take%2A> y <xref:System.Linq.Enumerable.Skip%2A> tienen ciertas limitaciones cuando se utilizan en consultas en SQL Server 2000. Para obtener más información, vea la entrada sobre cómo omitir y tomar excepciones en SQL Server 2000 "en [solución de problemas](troubleshooting.md).

## <a name="object-materialization"></a>Materialización de objetos

La materialización crea objetos CLR a partir de las filas devueltas por una o más consultas SQL.

- Las llamadas siguientes se *ejecutan localmente* como parte de la materialización:

  - Constructores

  - Métodos `ToString` en las proyecciones

  - Conversiones de tipos en las proyecciones

- Los métodos que siguen al <xref:System.Linq.Enumerable.AsEnumerable%2A> método se *ejecutan localmente*. Este método no produce la ejecución inmediata.

- Puede utilizar `struct` como tipo de valor devuelto en el resultado de una consulta o como un miembro del tipo de resultado. Las entidades deben ser clases. Los tipos anónimos se materializan como instancias de clase, pero los structs con nombre (no entidades) se pueden utilizar en la proyección.

- Un miembro del tipo de valor devuelto en el resultado de una consulta puede ser de tipo <xref:System.Linq.IQueryable%601>. Se materializa como una colección local.

- Los métodos siguientes provocan la *materialización inmediata* de la secuencia a la que se aplican los métodos:

  - <xref:System.Linq.Enumerable.ToList%2A>

  - <xref:System.Linq.Enumerable.ToDictionary%2A>

  - <xref:System.Linq.Enumerable.ToArray%2A>

## <a name="see-also"></a>Vea también

- [Referencia](reference.md)
- [Devolver u omitir elementos de una secuencia](return-or-skip-elements-in-a-sequence.md)
- [Concatenar dos secuencias](concatenate-two-sequences.md)
- [Devolver la diferencia de conjuntos entre dos secuencias](return-the-set-difference-between-two-sequences.md)
- [Devolver la intersección de conjuntos de dos secuencias](return-the-set-intersection-of-two-sequences.md)
- [Devolver la unión de conjuntos de dos secuencias](return-the-set-union-of-two-sequences.md)
