---
title: Controlar valores Null
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f18b288f-b265-4bbe-957f-c6833c0645ef
ms.openlocfilehash: 0d200ad35d3ab56bf97114b51b4f7fcc898eecdf
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59332149"
---
# <a name="handling-null-values"></a>Controlar valores Null
Los valores NULL se utilizan en bases de datos relacionales cuando el valor de una columna se desconoce o falta. Un NULL no es ni una cadena vacía (en los tipos de datos de caracteres o de fecha y hora) ni un valor cero (en los tipos de datos numéricos). La especificación ANSI SQL-92 afirma que un NULL debe ser igual en todos los tipos de datos; por lo tanto, todos los NULL se tratan de forma coherente. El espacio de nombres <xref:System.Data.SqlTypes> proporciona semántica para valores NULL mediante la implementación de la interfaz <xref:System.Data.SqlTypes.INullable>. Cada uno de los tipos de datos de <xref:System.Data.SqlTypes> tiene su propia propiedad  `IsNull` y un valor `Null` que se puede asignar a una instancia de ese tipo de datos.  
  
> [!NOTE]
>  En la versión 2.0 de .NET Framework se introduce la compatibilidad con tipos que admiten valores NULL, lo que permite a los programadores ampliar un tipo de valor para representar todos los valores del tipo subyacente. Estos tipos CLR que admiten valores NULL representan una instancia de la estructura <xref:System.Nullable>. Esta capacidad es especialmente útil cuando a los tipos de valor se les ha aplicado la conversión boxing o la conversión unboxing, lo que proporciona una compatibilidad mejorada con tipos de objeto. Los tipos CLR que admiten valores NULL no están pensados para el almacenamiento de valores NULL de base de datos porque un valor NULL ANSI SQL no se comporta del mismo modo que una referencia `null` (o `Nothing`, en Visual Basic). Para trabajar con valores NULL ANSI SQL de base de datos, utilice valores NULL <xref:System.Data.SqlTypes> en lugar de <xref:System.Nullable>. Para obtener más información sobre cómo trabajar con CLR Vea tipos que aceptan valores NULL en Visual Basic [los tipos de valor que acepta valores NULL](~/docs/visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)y para C#, vea [utilizar tipos que aceptan valores NULL](~/docs/csharp/programming-guide/nullable-types/using-nullable-types.md).  
  
## <a name="nulls-and-three-valued-logic"></a>Valores NULL y la lógica de tres valores  
 Permitir valores NULL en definiciones de columna introduce la lógica de tres valores en la aplicación. Una comparación puede evaluarse en función de una de tres condiciones:  
  
-   True  
  
-   False  
  
-   Desconocido  
  
 Como un valor NULL se considera que es desconocido, dos valores NULL comparados entre sí no se consideran iguales. En expresiones que utilizan operadores aritméticos, si alguno de los operandos es nulo, el resultado también es nulo.  
  
## <a name="nulls-and-sqlboolean"></a>Valores NULL y SqlBoolean  
 La comparación entre cualquier <xref:System.Data.SqlTypes> devolverá un <xref:System.Data.SqlTypes.SqlBoolean>. La función `IsNull` de cada `SqlType` devuelve un <xref:System.Data.SqlTypes.SqlBoolean> y se puede utilizar para comprobar si hay valores NULL. En las siguientes tablas de tipo truth se muestra cómo funcionan los operadores AND, OR y NOT en presencia de un valor NULL. (T=true, F=false y U=unknown, o NULL.)  
  
 ![Truth Table](../../../../../docs/framework/data/adonet/sql/media/truthtable-bpuedev11.gif "TruthTable_bpuedev11")  
  
### <a name="understanding-the-ansinulls-option"></a>Descripción de la opción ANSI_NULLS  
 <xref:System.Data.SqlTypes> proporciona la misma semántica que cuando la opción ANSI_NULLS está activada en SQL Server. Todos los operadores aritméticos (+, -, *, /, %), operadores bit a bit (~ &, &#124;), y la mayoría de las funciones devuelve null si alguno de los operandos o argumentos es null, excepto la propiedad `IsNull`.  
  
 No se admite el estándar ANSI SQL-92 *columnName* = NULL en una cláusula WHERE. En SQL Server, la opción ANSI_NULLS controla la posibilidad de aceptar NULL predeterminada en la base de datos y la evaluación de comparaciones con respecto a valores NULL. Si ANSI_NULLS está activado (el valor predeterminado), al comprobar la existencia de valores NULL se debe utilizar el operador IS NULL en las expresiones. Por ejemplo, la siguiente comparación siempre produce UNKNOWN cuando ANSI_NULLS está activado:  
  
```  
colname > NULL  
```  
  
 La comparación con una variable que contiene un valor NULL también produce UNKNOWN:   
  
```  
colname > @MyVariable  
```  
  
 Utilice el predicado IS NULL o IS NOT NULL para comprobar si un valor es NULL. Esto puede agregar complejidad a la cláusula WHERE. Por ejemplo, la columna TerritoryID de la tabla Customer de AdventureWorks permite valores NULL. Si se utiliza una instrucción SELECT para comprobar si hay valores NULL además de otros, debe incluir un predicado IS NULL:  
  
```  
SELECT CustomerID, AccountNumber, TerritoryID  
FROM AdventureWorks.Sales.Customer  
WHERE TerritoryID IN (1, 2, 3)  
   OR TerritoryID IS NULL  
```  
  
 Si establece ANSI_NULLS en OFF en SQL Server, puede crear expresiones que utilicen el operador de igualdad para comparar con NULL. Sin embargo, no puede evitar que diferentes conexiones establezcan opciones nulas para esa conexión. El uso de IS NULL para probar si los valores son NULL siempre funciona, con independencia de la configuración de ANSI_NULLS en una conexión.  
  
 No se admite el establecimiento de ANSI_NULLS en OFF en un `DataSet`, ya que siempre sigue el estándar ANSI SQL-92 para el tratamiento de valores NULL en <xref:System.Data.SqlTypes>.  
  
## <a name="assigning-null-values"></a>Asignación de valores NULL  
 Los valores NULL son especiales y su semántica de almacenamiento y asignación varía según los diversos sistemas de tipos y sistemas de almacenamiento. Un `Dataset` se ha diseñado para su uso con diferentes sistemas de tipos y de almacenamiento.  
  
 En esta sección se describe la semántica de valores NULL para la asignación de dichos valores a una <xref:System.Data.DataColumn> de una <xref:System.Data.DataRow> entre sistemas de tipos diferentes.  
  
 `DBNull.Value`  
 Esta asignación es válida para una `DataColumn` de cualquier tipo. Si el tipo implementa `INullable`, `DBNull.Value` se convierte en el valor NULL adecuado fuertemente tipado.  
  
 `SqlType.Null`  
 Todos los tipos de datos <xref:System.Data.SqlTypes> implementan `INullable`. Si el valor NULL fuertemente tipado se puede convertir en el tipo de datos de la columna mediante operadores de conversión implícitos, la asignación debería realizarse. De lo contrario, se produce una excepción de conversión no válida.  
  
 `null`  
 Si 'null' es un valor válido para el tipo de datos `DataColumn` dado, se convierte en el `DbNull.Value` o `Null` asociado con el tipo `INullable` (`SqlType.Null`)  
  
 `derivedUdt.Null`  
 En columnas de tipos definidos por el usuario, los valores NULL se almacenan siempre en el tipo asociado con la `DataColumn`. Considere el caso de un tipo definido por el usuario asociado con una `DataColumn` que no implementa `INullable`, mientras su subclase sí lo hace. En este caso, si se asigna un valor NULL fuertemente tipado asociado a la clase derivada, se almacenará como `DbNull.Value` sin tipo, porque el almacenamiento de valores NULL es siempre coherente con el tipo de datos de DataColumn.  
  
> [!NOTE]
>  La estructura `Nullable<T>` o <xref:System.Nullable> no se admite actualmente en `DataSet`.  
  
### <a name="multiple-column-row-assignment"></a>Asignación de varias columnas (filas)  
 `DataTable.Add`, `DataTable.LoadDataRow`, u otras API que aceptan un <xref:System.Data.DataRow.ItemArray%2A> que se asigna a una fila, asignan 'null' al valor predeterminado de DataColumn. Si un objeto de la matriz contiene `DbNull.Value` o su equivalente fuertemente tipado, se aplican las mismas reglas que se han descrito anteriormente.  
  
 Además, las siguientes reglas se aplican para una instancia de asignaciones de NULL de `DataRow.["columnName"]`:  
  
1. El valor predeterminado *predeterminada* es el valor `DbNull.Value` para todo excepto las columnas null fuertemente tipadas que encuentra el fuertemente tipado valor null.  
  
2. Los valores NULL nunca se escriben durante la serialización a archivos XML (como en "xsi:nil").  
  
3. Todos los valores que no son NULL, incluidos los predeterminados, siempre se escriben durante la serialización a XML. Esto no es característico de la semántica de XSD/XML en la que un valor NULL (xsi:nil) es explícito y el valor predeterminado es implícito (si no está presente en XML, un analizador de validación puede obtenerlo de un esquema XSD asociado). Lo contrario se cumple para `DataTable`: un valor NULL es implícito y el valor predeterminado es explícito.  
  
4. A todos los valores de columna que faltan en las filas leídas de la información XML introducida se les asigna NULL. A las filas creadas mediante <xref:System.Data.DataTable.NewRow%2A> o métodos similares se les asigna el valor predeterminado de DataColumn.  
  
5. El método <xref:System.Data.DataRow.IsNull%2A> devuelve `true` para `DbNull.Value` y `INullable.Null`.  
  
## <a name="assigning-null-values"></a>Asignación de valores NULL  
 El valor predeterminado de cualquier instancia de <xref:System.Data.SqlTypes> es NULL.  
  
 Los valores NULL de <xref:System.Data.SqlTypes> son específicos del tipo y no se pueden representar con un único valor, como `DbNull`. Utilice la propiedad `IsNull` para comprobar si hay valores NULL.  
  
 Es posible asignar valores NULL a una <xref:System.Data.DataColumn>, como se muestra en el siguiente código de ejemplo. Puede asignar directamente valores NULL a variables `SqlTypes` sin desencadenar una excepción.  
  
### <a name="example"></a>Ejemplo  
 El siguiente código de ejemplo crea una <xref:System.Data.DataTable> con dos columnas definidas como <xref:System.Data.SqlTypes.SqlInt32> y <xref:System.Data.SqlTypes.SqlString>. El código agrega una fila de valores conocidos, una fila de valores NULL y, luego, establece una iteración en la <xref:System.Data.DataTable>, de modo que los valores se asignan a variables y el resultado se muestra en la ventana de la consola.  
  
 [!code-csharp[DataWorks SqlTypes.IsNull#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlTypes.IsNull/CS/source.cs#1)]
 [!code-vb[DataWorks SqlTypes.IsNull#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlTypes.IsNull/VB/source.vb#1)]  
  
 Este ejemplo muestra el siguiente resultado:  
  
```  
isColumnNull=False, ID=123, Description=Side Mirror  
isColumnNull=True, ID=Null, Description=Null  
```  
  
## <a name="comparing-null-values-with-sqltypes-and-clr-types"></a>Comparación de valores NULL con SqlTypes y tipos CLR  
 Al comparar valores NULL, es importante comprender la diferencia entre la forma en que el método `Equals` evalúa los valores NULL en <xref:System.Data.SqlTypes> por contraposición a cómo funciona con tipos CLR. Todos los <xref:System.Data.SqlTypes>`Equals` métodos utilizan la semántica de base de datos para evaluar valores null: si uno o ambos de los valores es null, la comparación produce null. Por otra parte, el uso del método `Equals` de CLR en dos <xref:System.Data.SqlTypes> producirá TRUE si ambos son NULL. Esto refleja la diferencia entre el uso de un método de instancia como el método `String.Equals` de CLR y el uso del método estático o compartido `SqlString.Equals`.  
  
 En el siguiente ejemplo se muestra la diferencia entre los resultados del método `SqlString.Equals` y del método `String.Equals` cuando se pasa a cada uno un par de valores NULL y, a continuación, un par de cadenas vacías.  
  
 [!code-csharp[DataWorks SqlTypes.CompareNulls#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlTypes.CompareNulls/CS/source.cs#1)]
 [!code-vb[DataWorks SqlTypes.CompareNulls#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlTypes.CompareNulls/VB/source.vb#1)]  
  
 El código produce el siguiente resultado:  
  
```  
SqlString.Equals shared/static method:  
  Two nulls=Null  
  
String.Equals instance method:  
  Two nulls=True  
  
SqlString.Equals shared/static method:  
  Two empty strings=True  
  
String.Equals instance method:  
  Two empty strings=True   
```  
  
## <a name="see-also"></a>Vea también

- [Tipos de datos de SQL Server y ADO.NET](../../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)
- [Proveedores administrados de ADO.NET y centro de desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
