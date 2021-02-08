---
description: 'Más información sobre: discrepancias de tipos de SQL-CLR'
title: Desajustes de tipos entre SQL y CLR
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0a90c33f-7ed7-4501-ad5f-6224c5da8e9b
ms.openlocfilehash: 9a2e1d360fc2a54f401572e46d92654f2b9284db
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803729"
---
# <a name="sql-clr-type-mismatches"></a>Desajustes de tipos entre SQL y CLR

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] automatiza gran parte de la conversión entre el modelo de objetos y SQL Server. No obstante, algunas situaciones impiden la exactitud de la conversión. Estas discordancias clave entre los tipos de Common Language Runtime (CLR) y los de base de datos de SQL Server se resumen en las siguientes secciones. Puede encontrar más detalles sobre las asignaciones de tipos y la traducción de funciones específicas en asignación de tipos [SQL-CLR](sql-clr-type-mapping.md) y [funciones y tipos de datos](data-types-and-functions.md).

## <a name="data-types"></a>Tipo de datos

La conversión entre CLR y SQL Server se produce cuando se envía una consulta a la base de datos y cuando los resultados se devuelven al modelo de objetos. Por ejemplo, la siguiente consulta de Transact-SQL requiere dos conversiones de valores:

```sql
Select DateOfBirth From Customer Where CustomerId = @id
```

Antes de que se pueda ejecutar la consulta en SQL Server, se debe especificar el valor del parámetro de Transact-SQL. En este ejemplo, el valor del parámetro `id` primero se debe convertir de un tipo de elemento <xref:System.Int32?displayProperty=nameWithType> de CLR a un tipo de elemento `INT` de SQL Server para que la base de datos pueda entender el significado del valor. Después, para recuperar los resultados, la columna `DateOfBirth` de SQL Server se debe convertir de un tipo de elemento `DATETIME` de SQL Server a un tipo de elemento <xref:System.DateTime?displayProperty=nameWithType> de CLR para su uso en el modelo de objetos. En este ejemplo, los tipos del modelo de objetos de CLR y la base de datos de SQL Server tienen asignaciones naturales. Pero no siempre es así.

### <a name="missing-counterparts"></a>Ausencia de tipos equivalentes

Los tipos siguientes no tienen equivalencias razonables.

- Discordancias del espacio de nombres <xref:System> de CLR:

  - **Enteros sin signo**. Estos tipos suelen asignarse a sus equivalentes con signo de mayor tamaño para evitar el desbordamiento. Los literales se pueden convertir a un tipo numérico con signo del mismo tamaño o de un tamaño inferior, según su valor.

  - **Booleano**. Estos tipos pueden asignarse a un valor numérico en bits o mayor, o a una cadena. Un literal se puede asignar a una expresión que se evalúe en el mismo valor (por ejemplo, `1=1` en SQL para `True` en CLS).

  - **Intervalo** de tiempo. Este tipo representa la diferencia entre dos valores `DateTime` y no se corresponde con `timestamp` en SQL Server. El elemento <xref:System.TimeSpan?displayProperty=nameWithType> de CLR también se puede asignar al tipo de elemento `TIME` de SQL Server en algunos casos. La única finalidad del tipo de elemento `TIME` de SQL Server era representar valores positivos menores que 24 horas. El ámbito del elemento <xref:System.TimeSpan> de CLR es mucho más amplio.

  > [!NOTE]
  > Los tipos de .NET Framework específicos de SQL Server de <xref:System.Data.SqlTypes> no se incluyen en esta comparación.

- Discordancias de SQL Server:

  - **Tipos de caracteres de longitud fija**. Transact-SQL distingue entre las categorías Unicode y no Unicode, y tiene tres tipos distintos en cada categoría: longitud fija `nchar` / `char` , longitud variable `nvarchar` / `varchar` y mayor tamaño `ntext` / `text` . Los tipos de caracteres de longitud fija podrían asignarse al tipo de elemento <xref:System.Char?displayProperty=nameWithType> de CLR para recuperar los caracteres, pero realmente no se corresponden con el mismo tipo en conversiones y comportamiento.

  - **Bit**. Aunque el dominio `bit` tiene el mismo número de valores que `Nullable<Boolean>`, ambos son tipos diferentes. `Bit`toma valores `1` y `0` en lugar de `true` / `false` y no se puede usar como equivalente a Expresiones booleanas.

  - **Timestamp**. A diferencia del tipo de elemento <xref:System.TimeSpan?displayProperty=nameWithType> de CLR, el tipo de elemento `TIMESTAMP` de SQL Server representa un número de 8 bits generado por la base de datos que es único para cada actualización y no se basa en la diferencia entre los valores de <xref:System.DateTime>.

  - **Money** y **SmallMoney**. Estos tipos pueden asignarse a <xref:System.Decimal>, pero básicamente son tipos diferentes y son tratados como tales en las conversiones y por las funciones basadas en servidor.

### <a name="multiple-mappings"></a>Asignaciones múltiples

Existen muchos tipos de datos de SQL Server que se pueden asignar a uno o más tipos de datos de CLR. Asimismo, existen muchos tipos de datos de CLR que se pueden asignar a uno o más tipos de SQL Server. Aunque LINQ to SQL pueda admitir una asignación, no significa que dos tipos asignados entre CLR y SQL Server tengan una coincidencia perfecta en precisión, ámbito y semántica. Algunas asignaciones pueden incluir diferencias en alguna o todas estas dimensiones. Puede encontrar detalles sobre estas posibles diferencias en las distintas posibilidades de asignación en la [asignación de tipos de SQL-CLR](sql-clr-type-mapping.md).

### <a name="user-defined-types"></a>Tipos definidos por el usuario

Los tipos de CLR definidos por el usuario están diseñados para eliminar las lagunas del sistema de tipos. No obstante, revelan problemas interesantes con el control de versiones de los tipos. Un cambio de versión en el cliente podría no corresponderse con un cambio en el tipo almacenado en el servidor de bases de datos. Esto generaría otra discordancia de tipos según la cual no coincidiría la semántica de tipos y es probable que saltase a la vista la diferencia entre las versiones. Esto se complica todavía más cuando las jerarquías de herencia se refactorizan en sucesivas versiones.

## <a name="expression-semantics"></a>Semántica de expresión

Además de la discordancia en pares entre los tipos de CLR y los tipos de base de datos, las expresiones agregan complejidad. Deben considerarse las discordancias en la semántica de operador, semántica de función, conversión de tipos implícita y reglas de prioridad.

Las subsecciones siguientes muestran la discordancia entre expresiones aparentemente similares. Quizás se puedan generar expresiones SQL semánticamente equivalentes a una expresión CLR dada. Sin embargo, no está claro si las diferencias semánticas entre expresiones aparentemente similares son evidentes para un usuario de CLR y, por tanto, si se han previsto o no los cambios necesarios para la equivalencia semántica. Éste es un problema especialmente crítico cuando una expresión se evalúa para un conjunto de valores. La visibilidad de la diferencia podría depender de los datos y ser difícil de identificar durante la codificación y depuración.

### <a name="null-semantics"></a>Semántica de null

Las expresiones SQL proporcionan lógica de tres valores para las expresiones booleanas. El resultado puede ser True, False o Null. En cambio, CLR especifica un resultado booleano de dos valores para las comparaciones que implican valores de tipo NULL. Tenga en cuenta el código siguiente:

[!code-csharp[DLinqMismatch#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqMismatch/cs/Program.cs#2)]
[!code-vb[DLinqMismatch#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqMismatch/vb/Module1.vb#2)]

```sql
-- Assume col1 and col2 are integer columns with null values.
-- Assume that ANSI null behavior has not been explicitly
--  turned off.
Select …
From …
Where col1 = col2
-- Evaluates to null, not true and the corresponding row is not
--   selected.
-- To obtain matching behavior (i -> col1, j -> col2) change
--   the query to the following:
Select …
From …
Where
    col1 = col2
or (col1 is null and col2 is null)
-- (Visual Basic 'Nothing'.)
```

Un problema similar se da cuando se asumen resultados de dos valores.

[!code-csharp[DLinqMismatch#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqMismatch/cs/Program.cs#3)]
[!code-vb[DLinqMismatch#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqMismatch/vb/Module1.vb#3)]

```sql
-- Assume col1 and col2 are nullable columns.
-- Assume that ANSI null behavior has not been explicitly
--   turned off.
Select …
From …
Where
    col1 = col2
or col1 != col2
-- Visual Basic: col1 <> col2.

-- Excludes the case where the boolean expression evaluates
--   to null. Therefore the where clause does not always
--   evaluate to true.
```

En el caso anterior, puede obtener un comportamiento equivalente para generar SQL, pero la conversión podría no reflejar su intención de manera precisa.

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no impone la `null` `nothing` semántica de comparación de C# o Visual Basic en SQL. Los operadores de comparación se convierten sintácticamente en sus equivalentes SQL. La semántica refleja la semántica de SQL tal como la define la configuración del servidor o de la conexión. Dos valores nulos se consideran distintos según la configuración predeterminada de SQL Server (aunque se puede cambiar la configuración para cambiar la semántica). Sea como fuere, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no considera la configuración del servidor en la conversión de consultas.

Una comparación con el literal `null` (`nothing`) se convierte a la versión de SQL correcta (`is null` o `is not null`).

SQL Server define el valor `null` (`nothing`) en la intercalación; [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no cambia la intercalación.

### <a name="type-conversion-and-promotion"></a>Conversión y promoción de tipos

SQL admite un completo conjunto de conversiones implícitas en las expresiones. Las mismas expresiones en C# requerirían una conversión de tipos explícita. Por ejemplo:

- Los tipos `Nvarchar` y `DateTime` se pueden comparar en SQL sin ninguna conversión de tipos explícita; C# requiere la conversión explícita.

- `Decimal` se convierte implícitamente a `DateTime` en SQL. C# no permite una conversión implícita.

De igual forma, la prioridad de los tipos en Transact-SQL difiere de la prioridad de los tipos en C#, ya que el conjunto de tipos subyacente es diferente. De hecho, no hay una relación clara de subconjuntos/supraconjuntos entre las listas de prioridades. Por ejemplo, al comparar `nvarchar` con `varchar`, se produce la conversión implícita de la expresión `varchar` a `nvarchar`. CLR no proporciona ninguna promoción equivalente.

En casos más sencillos, estas diferencias generan expresiones CLR con conversiones de tipos que van a ser redundantes para la expresión SQL correspondiente. Lo que es más importante, los resultados intermedios de una expresión SQL podrían promoverse implícitamente a un tipo que no tiene ningún homólogo preciso en C#, y lo mismo a la inversa. En general, las pruebas, la depuración y la validación de tales expresiones representan una carga adicional importante para el usuario.

### <a name="collation"></a>Intercalación

Transact-SQL admite las intercalaciones explícitas como anotaciones en tipos de cadena de caracteres. Estas intercalaciones determinan la validez de ciertas comparaciones. Por ejemplo, al comparar dos columnas con intercalaciones explícitas diferentes, se genera un error. Si se utiliza el tipo de cadena CTS, más simplificado, no se producen tales errores. Considere el ejemplo siguiente:

```sql
create table T2 (
    Col1 nvarchar(10),
    Col2      nvarchar(10) collate Latin_general_ci_as
)
```

[!code-csharp[DLinqMismatch#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqMismatch/cs/Program.cs#4)]
[!code-vb[DLinqMismatch#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqMismatch/vb/Module1.vb#4)]

```sql
Select …
From …
Where Col1 = Col2
-- Error, collation conflict.
```

En efecto, la subcláusula collation crea un *tipo restringido* que no se sustituye.

De forma similar, el criterio de ordenación puede ser bastante diferente entre los sistemas de tipos. Esta diferencia afecta a la ordenación de los resultados. <xref:System.Guid> se ordena en los 16 bytes por orden lexicográfico (`IComparable()`), mientras que T-SQL compara los GUID en el orden siguiente: node(10-15), clock-seq(8-9), time-high(6-7), time-mid(4-5), time-low(0-3). Esta ordenación era la habitual en SQL 7.0, cuando los GUID generados por NT tenían este orden de octetos. Este enfoque garantizaba que los GUID generados en el mismo clúster de nodos se obtenían juntos y ordenados secuencialmente, según la marca de tiempo. También era útil para compilar índices (las inserciones se convertían en anexos en lugar de E/S aleatorias). Posteriormente, el orden se codificó en Windows por cuestiones de privacidad, pero SQL debe mantener la compatibilidad. Una solución alternativa es usar en <xref:System.Data.SqlTypes.SqlGuid> lugar de <xref:System.Guid> .

### <a name="operator-and-function-differences"></a>Diferencias entre operadores y funciones

Los operadores y las funciones que son esencialmente comparables presentan una semántica ligeramente diferente. Por ejemplo:

- C# especifica una semántica de cortocircuito basada en el orden léxico de los operandos para los operadores lógicos `&&` y `||`. Por otro lado, SQL está orientado a consultas basadas en conjuntos y, por consiguiente, proporciona más libertad al optimizador para que decida el orden de ejecución. Algunas de las implicaciones se exponen a continuación:

  - La conversión semánticamente equivalente requeriría " `CASE` ... `WHEN` … `THEN`"construir en SQL para evitar la reordenación de la ejecución de operandos.

  - Una traducción dinámica a los `AND` / `OR` operadores podría producir errores inesperados si la expresión de C# se basa en la evaluación del segundo operando que se basa en el resultado de la evaluación del primer operando.

- `Round()` la función tiene una semántica diferente en .NET Framework y en T-SQL.

- El índice de inicio de las cadenas es 0 en CLR, pero 1 en SQL. Por consiguiente, cualquier función que tenga un índice requiere la conversión del índice.

- CLR admite el operador de módulo (‘%’) para los números de punto flotante, pero SQL no.

- El operador `Like` admite eficazmente las sobrecargas automáticas basadas en las conversiones implícitas. Aunque el operador `Like` por definición funciona en tipos de cadena de caracteres, la conversión implícita de tipos numéricos o tipos `DateTime` permite utilizar igualmente tipos que no son de cadena con `Like`. En CTS, no existe una conversión implícita comparable. Por lo tanto, se requieren sobrecargas adicionales.

    > [!NOTE]
    > Este comportamiento del operador `Like` solo se aplica en C#; la palabra clave de Visual Basic `Like` se mantiene invariable.

- Overflow siempre se comprueba en SQL, pero tiene que especificarse explícitamente en C# (no en Visual Basic) para evitar salto. Dadas las columnas de enteros C1, C2 y C3, si C1+C2 se almacena en C3 (Update T Set C3 = C1 + C2):

    ```sql
    create table T3 (
        Col1      integer,
        Col2      integer
    )
    insert into T3 (col1, col2) values (2147483647, 5)
    -- Valid values: max integer value and 5.
    select * from T3 where col1 + col2 < 0
    -- Produces arithmetic overflow error.
    ```

[!code-csharp[DLinqMismatch#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqMismatch/cs/Program.cs#5)]
[!code-vb[DLinqMismatch#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqMismatch/vb/Module1.vb#5)]

- SQL realiza un redondeo aritmético simétrico mientras .NET Framework usa el redondeo bancario. Para obtener información detallada, vea el artículo 196652 de Microsoft Knowledge Base.

- De forma predeterminada, para las configuraciones regionales comunes, en las comparaciones de cadenas de caracteres no se hace distinción entre mayúsculas y minúsculas en SQL. En Visual Basic y en C#, se distingue entre mayúsculas y minúsculas. Por ejemplo, `s == "Food"` ( `s = "Food"` en Visual Basic) y `s == "Food"` puede producir resultados diferentes si `s` es `food` .

    ```sql
    -- Assume default US-English locale (case insensitive).
    create table T4 (
        Col1      nvarchar (256)
    )
    insert into T4 values (‘Food’)
    insert into T4 values (‘FOOD’)
    select * from T4 where Col1 = ‘food’
    -- Both the rows are returned because of case-insensitive matching.
    ```

[!code-csharp[DLinqMismatch#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqMismatch/cs/Program.cs#6)]
[!code-vb[DLinqMismatch#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqMismatch/vb/Module1.vb#6)]

- Los operadores o las funciones aplicados a argumentos de tipo de caracteres de longitud fija en SQL tienen una semántica significativamente diferente a la de las mismas funciones y operadores aplicados a <xref:System.String?displayProperty=nameWithType> de CLR. Esto también podría interpretarse como una implicación más del problema de la ausencia de tipos equivalentes que se describió en la sección relativa a los tipos.

    ```sql
    create table T4 (
        Col1      nchar(4)
    )
    Insert into T5(Col1) values ('21');
    Insert into T5(Col1) values ('1021');
    Select * from T5 where Col1 like '%1'
    -- Only the second row with Col1 = '1021' is returned.
    -- Not the first row!
    ```

     [!code-csharp[DLinqMismatch#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqMismatch/cs/Program.cs#7)]
     [!code-vb[DLinqMismatch#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqMismatch/vb/Module1.vb#7)]

     Un problema similar se produce con la concatenación de cadenas.

    ```sql
    create table T6 (
        Col1      nchar(4)
        Col2       nchar(4)
    )
    Insert into T6 values ('a', 'b');
    Select Col1+Col2 from T6
    -- Returns concatenation of padded strings "a   b   " and not "ab".
    ```

En resumen, podría requerirse una conversión compleja para las expresiones CLR, así como operadores o funciones adicionales para exponer la funcionalidad de SQL.

### <a name="type-casting"></a>Conversión de tipos

En C# y en SQL, los usuarios pueden invalidar la semántica predeterminada de las expresiones utilizando conversiones de tipos explícitas (`Cast` y `Convert`). Sin embargo, exponer esta funcionalidad entre los límites del sistema de tipos puede plantear un dilema. Una conversión de tipos de SQL que proporciona la semántica deseada no se puede convertir con facilidad a la conversión de tipos de C# correspondiente. Por otro lado, una conversión de tipos de C# no se puede convertir directamente en una conversión de tipos de SQL equivalente debido a las discordancias de los tipos, la ausencia de tipos equivalentes y las diferencias en las jerarquías de prioridades de tipos. Es necesario elegir entre exponer la discordancia con el sistema de tipos y perder una importante capacidad de expresión.

En otros casos, puede que la conversión de tipos no sea necesaria para validar una expresión en cualquiera de los dos dominios, pero podría serlo para garantizar que una asignación no predeterminada se aplica correctamente a la expresión.

```sql
-- Example from "Non-default Mapping" section extended
create table T5 (
    Col1      nvarchar(10),
    Col2      nvarchar(10)
)
Insert into T5(col1, col2) values (‘3’, ‘2’);
```

[!code-csharp[DLinqMismatch#8](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqMismatch/cs/Program.cs#8)]
[!code-vb[DLinqMismatch#8](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqMismatch/vb/Module1.vb#8)]

```sql
Select *
From T5
Where Col1 + Col2 > 4
-- "Col1 + Col2" expr evaluates to '32'
```

## <a name="performance-issues"></a>Problemas de rendimiento

La contabilidad de algunas diferencias de tipo SQL Server-CLR puede dar lugar a una disminución del rendimiento al cruzar entre CLR y los sistemas de tipo SQL Server. A continuación se muestran ejemplos de escenarios cuyo rendimiento se ve muy afectado:

- Orden forzado de evaluación de los operadores lógicos AND/OR

- La generación de SQL para aplicar el orden de evaluación del predicado limita la funcionalidad del optimizador de SQL.

- Las conversiones de tipos, ya sean originadas por un compilador de CLR o por una implementación de consulta relacional de objetos, pueden reducir el uso de los índices.

     Por ejemplo,

    ```sql
    -- Table DDL
    create table T5 (
        Col1      varchar(100)
    )
    ```

     [!code-csharp[DLinqMismatch#9](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqMismatch/cs/Program.cs#9)]
     [!code-vb[DLinqMismatch#9](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqMismatch/vb/Module1.vb#9)]

     Considere la conversión de la expresión `(s = SOME_STRING_CONSTANT)`.

    ```sql
    -- Corresponding part of SQL where clause
    Where …
    Col1 = SOME_STRING_CONSTANT
    -- This expression is of the form <varchar> = <nvarchar>.
    -- Hence SQL introduces a conversion from varchar to nvarchar,
    --   resulting in
    Where …
    Convert(nvarchar(100), Col1) = SOME_STRING_CONSTANT
    -- Cannot use the index for column Col1 for some implementations.
    ```

Además de las diferencias semánticas, es importante tener en cuenta el impacto en el rendimiento si se entrecruzan los sistemas de tipos de CLR y SQL Server. Para los conjuntos de datos grandes, estos problemas de rendimiento pueden determinar si una aplicación se puede implementar o no.

## <a name="see-also"></a>Vea también

- [Información general](background-information.md)
