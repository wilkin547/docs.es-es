---
title: Controlar valores Null
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: f18b288f-b265-4bbe-957f-c6833c0645ef
caps.latest.revision: "6"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 23a502cc3a286ed5cb47c7bbe21253f312722409
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="handling-null-values"></a><span data-ttu-id="cdc3e-102">Controlar valores Null</span><span class="sxs-lookup"><span data-stu-id="cdc3e-102">Handling Null Values</span></span>
<span data-ttu-id="cdc3e-103">Los valores NULL se utilizan en bases de datos relacionales cuando el valor de una columna se desconoce o falta.</span><span class="sxs-lookup"><span data-stu-id="cdc3e-103">A null value in a relational database is used when the value in a column is unknown or missing.</span></span> <span data-ttu-id="cdc3e-104">Un NULL no es ni una cadena vacía (en los tipos de datos de caracteres o de fecha y hora) ni un valor cero (en los tipos de datos numéricos).</span><span class="sxs-lookup"><span data-stu-id="cdc3e-104">A null is neither an empty string (for character or datetime data types) nor a zero value (for numeric data types).</span></span> <span data-ttu-id="cdc3e-105">La especificación ANSI SQL-92 afirma que un NULL debe ser igual en todos los tipos de datos; por lo tanto, todos los NULL se tratan de forma coherente.</span><span class="sxs-lookup"><span data-stu-id="cdc3e-105">The ANSI SQL-92 specification states that a null must be the same for all data types, so that all nulls are handled consistently.</span></span> <span data-ttu-id="cdc3e-106">El espacio de nombres <xref:System.Data.SqlTypes> proporciona semántica para valores NULL mediante la implementación de la interfaz <xref:System.Data.SqlTypes.INullable>.</span><span class="sxs-lookup"><span data-stu-id="cdc3e-106">The <xref:System.Data.SqlTypes> namespace provides null semantics by implementing the <xref:System.Data.SqlTypes.INullable> interface.</span></span> <span data-ttu-id="cdc3e-107">Cada uno de los tipos de datos de <xref:System.Data.SqlTypes> tiene su propia propiedad  `IsNull` y un valor `Null` que se puede asignar a una instancia de ese tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="cdc3e-107">Each of the data types in <xref:System.Data.SqlTypes> has its own `IsNull` property and a `Null` value that can be assigned to an instance of that data type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cdc3e-108">En la versión 2.0 de .NET Framework se introduce la compatibilidad con tipos que admiten valores NULL, lo que permite a los programadores ampliar un tipo de valor para representar todos los valores del tipo subyacente.</span><span class="sxs-lookup"><span data-stu-id="cdc3e-108">The .NET Framework version 2.0 introduced support for nullable types, which allow programmers to extend a value type to represent all values of the underlying type.</span></span> <span data-ttu-id="cdc3e-109">Estos tipos CLR que admiten valores NULL representan una instancia de la estructura <xref:System.Nullable>.</span><span class="sxs-lookup"><span data-stu-id="cdc3e-109">These CLR nullable types represent an instance of the <xref:System.Nullable> structure.</span></span> <span data-ttu-id="cdc3e-110">Esta capacidad es especialmente útil cuando a los tipos de valor se les ha aplicado la conversión boxing o la conversión unboxing, lo que proporciona una compatibilidad mejorada con tipos de objeto.</span><span class="sxs-lookup"><span data-stu-id="cdc3e-110">This capability is especially useful when value types are boxed and unboxed, providing enhanced compatibility with object types.</span></span> <span data-ttu-id="cdc3e-111">Los tipos CLR que admiten valores NULL no están pensados para el almacenamiento de valores NULL de base de datos porque un valor NULL ANSI SQL no se comporta del mismo modo que una referencia `null` (o `Nothing`, en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="cdc3e-111">CLR nullable types are not intended for storage of database nulls because an ANSI SQL null does not behave the same way as a `null` reference (or `Nothing` in Visual Basic).</span></span> <span data-ttu-id="cdc3e-112">Para trabajar con valores NULL ANSI SQL de base de datos, utilice valores NULL <xref:System.Data.SqlTypes> en lugar de <xref:System.Nullable>.</span><span class="sxs-lookup"><span data-stu-id="cdc3e-112">For working with database ANSI SQL null values, use <xref:System.Data.SqlTypes> nulls rather than <xref:System.Nullable>.</span></span> <span data-ttu-id="cdc3e-113">Para obtener más información sobre cómo trabajar con CLR Vea tipos que aceptan valores NULL en Visual Basic [tipos de valor que aceptan valores NULL](~/docs/visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)y para C#, vea [utilizar tipos que aceptan valores NULL](~/docs/csharp/programming-guide/nullable-types/using-nullable-types.md).</span><span class="sxs-lookup"><span data-stu-id="cdc3e-113">For more information on working with CLR nullable types in Visual Basic see [Nullable Value Types](~/docs/visual-basic/programming-guide/language-features/data-types/nullable-value-types.md), and for C# see [Using Nullable Types](~/docs/csharp/programming-guide/nullable-types/using-nullable-types.md).</span></span>  
  
## <a name="nulls-and-three-valued-logic"></a><span data-ttu-id="cdc3e-114">Valores NULL y la lógica de tres valores</span><span class="sxs-lookup"><span data-stu-id="cdc3e-114">Nulls and Three-Valued Logic</span></span>  
 <span data-ttu-id="cdc3e-115">Permitir valores NULL en definiciones de columna introduce la lógica de tres valores en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="cdc3e-115">Allowing null values in column definitions introduces three-valued logic into your application.</span></span> <span data-ttu-id="cdc3e-116">Una comparación puede evaluarse en función de una de tres condiciones:</span><span class="sxs-lookup"><span data-stu-id="cdc3e-116">A comparison can evaluate to one of three conditions:</span></span>  
  
-   <span data-ttu-id="cdc3e-117">True</span><span class="sxs-lookup"><span data-stu-id="cdc3e-117">True</span></span>  
  
-   <span data-ttu-id="cdc3e-118">False</span><span class="sxs-lookup"><span data-stu-id="cdc3e-118">False</span></span>  
  
-   <span data-ttu-id="cdc3e-119">Desconocido</span><span class="sxs-lookup"><span data-stu-id="cdc3e-119">Unknown</span></span>  
  
 <span data-ttu-id="cdc3e-120">Como un valor NULL se considera que es desconocido, dos valores NULL comparados entre sí no se consideran iguales.</span><span class="sxs-lookup"><span data-stu-id="cdc3e-120">Because null is considered to be unknown, two null values compared to each other are not considered to be equal.</span></span> <span data-ttu-id="cdc3e-121">En expresiones que utilizan operadores aritméticos, si alguno de los operandos es nulo, el resultado también es nulo.</span><span class="sxs-lookup"><span data-stu-id="cdc3e-121">In expressions using arithmetic operators, if any of the operands is null, the result is null as well.</span></span>  
  
## <a name="nulls-and-sqlboolean"></a><span data-ttu-id="cdc3e-122">Valores NULL y SqlBoolean</span><span class="sxs-lookup"><span data-stu-id="cdc3e-122">Nulls and SqlBoolean</span></span>  
 <span data-ttu-id="cdc3e-123">La comparación entre cualquier <xref:System.Data.SqlTypes> devolverá un <xref:System.Data.SqlTypes.SqlBoolean>.</span><span class="sxs-lookup"><span data-stu-id="cdc3e-123">Comparison between any <xref:System.Data.SqlTypes> will return a <xref:System.Data.SqlTypes.SqlBoolean>.</span></span> <span data-ttu-id="cdc3e-124">La función `IsNull` de cada `SqlType` devuelve un <xref:System.Data.SqlTypes.SqlBoolean> y se puede utilizar para comprobar si hay valores NULL.</span><span class="sxs-lookup"><span data-stu-id="cdc3e-124">The `IsNull` function for each `SqlType` returns a <xref:System.Data.SqlTypes.SqlBoolean> and can be used to check for null values.</span></span> <span data-ttu-id="cdc3e-125">En las siguientes tablas de tipo truth se muestra cómo funcionan los operadores AND, OR y NOT en presencia de un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="cdc3e-125">The following truth tables show how the AND, OR, and NOT operators function in the presence of a null value.</span></span> <span data-ttu-id="cdc3e-126">(T=true, F=false y U=unknown, o NULL.)</span><span class="sxs-lookup"><span data-stu-id="cdc3e-126">(T=true, F=false, and U=unknown, or null.)</span></span>  
  
 <span data-ttu-id="cdc3e-127">![Tabla Truth](../../../../../docs/framework/data/adonet/sql/media/truthtable-bpuedev11.gif "TruthTable_bpuedev11")</span><span class="sxs-lookup"><span data-stu-id="cdc3e-127">![Truth Table](../../../../../docs/framework/data/adonet/sql/media/truthtable-bpuedev11.gif "TruthTable_bpuedev11")</span></span>  
  
### <a name="understanding-the-ansinulls-option"></a><span data-ttu-id="cdc3e-128">Descripción de la opción ANSI_NULLS</span><span class="sxs-lookup"><span data-stu-id="cdc3e-128">Understanding the ANSI_NULLS Option</span></span>  
 <span data-ttu-id="cdc3e-129"><xref:System.Data.SqlTypes> proporciona la misma semántica que cuando se establece la opción ANSI_NULLS en ON en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cdc3e-129"><xref:System.Data.SqlTypes> provides the same semantics as when the ANSI_NULLS option is set on in SQL Server.</span></span> <span data-ttu-id="cdc3e-130">Todos los operadores aritméticos (+, -, \*, /, %), operadores bit a bit (~ &, &#124;), y la mayoría de las funciones devuelve null si alguno de los operandos o argumentos es nulo, excepto la propiedad `IsNull`.</span><span class="sxs-lookup"><span data-stu-id="cdc3e-130">All arithmetic operators (+, -, \*, /, %), bitwise operators (~, &, &#124;), and most functions return null if any of the operands or arguments is null, except for the property `IsNull`.</span></span>  
  
 <span data-ttu-id="cdc3e-131">No es compatible con el estándar ANSI SQL-92 *columnName* = NULL en una cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="cdc3e-131">The ANSI SQL-92 standard does not support *columnName* = NULL in a WHERE clause.</span></span> <span data-ttu-id="cdc3e-132">En SQL Server, la opción ANSI_NULLS controla la posibilidad de aceptar NULL predeterminada en la base de datos y la evaluación de comparaciones con respecto a valores NULL.</span><span class="sxs-lookup"><span data-stu-id="cdc3e-132">In SQL Server, the ANSI_NULLS option controls both default nullability in the database and evaluation of comparisons against null values.</span></span> <span data-ttu-id="cdc3e-133">Si ANSI_NULLS está activado (el valor predeterminado), al comprobar la existencia de valores NULL se debe utilizar el operador IS NULL en las expresiones.</span><span class="sxs-lookup"><span data-stu-id="cdc3e-133">If ANSI_NULLS is turned on (the default), the IS NULL operator must be used in expressions when testing for null values.</span></span> <span data-ttu-id="cdc3e-134">Por ejemplo, la siguiente comparación siempre produce UNKNOWN cuando ANSI_NULLS está activado:</span><span class="sxs-lookup"><span data-stu-id="cdc3e-134">For example, the following comparison always yields unknown when ANSI_NULLS is on:</span></span>  
  
```  
colname > NULL  
```  
  
 <span data-ttu-id="cdc3e-135">La comparación con una variable que contiene un valor NULL también produce UNKNOWN: </span><span class="sxs-lookup"><span data-stu-id="cdc3e-135">Comparison to a variable containing a null value also yields unknown:</span></span>  
  
```  
colname > @MyVariable  
```  
  
 <span data-ttu-id="cdc3e-136">Utilice el predicado IS NULL o IS NOT NULL para comprobar si un valor es NULL.</span><span class="sxs-lookup"><span data-stu-id="cdc3e-136">Use the IS NULL or IS NOT NULL predicate to test for a null value.</span></span> <span data-ttu-id="cdc3e-137">Esto puede agregar complejidad a la cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="cdc3e-137">This can add complexity to the WHERE clause.</span></span> <span data-ttu-id="cdc3e-138">Por ejemplo, la columna TerritoryID de la tabla Customer de AdventureWorks permite valores NULL.</span><span class="sxs-lookup"><span data-stu-id="cdc3e-138">For example, the TerritoryID column in the AdventureWorks Customer table allows null values.</span></span> <span data-ttu-id="cdc3e-139">Si se utiliza una instrucción SELECT para comprobar si hay valores NULL además de otros, debe incluir un predicado IS NULL:</span><span class="sxs-lookup"><span data-stu-id="cdc3e-139">If a SELECT statement is to test for null values in addition to others, it must include an IS NULL predicate:</span></span>  
  
```  
SELECT CustomerID, AccountNumber, TerritoryID  
FROM AdventureWorks.Sales.Customer  
WHERE TerritoryID IN (1, 2, 3)  
   OR TerritoryID IS NULL  
```  
  
 <span data-ttu-id="cdc3e-140">Si establece ANSI_NULLS en OFF en SQL Server, puede crear expresiones que utilicen el operador de igualdad para comparar con NULL.</span><span class="sxs-lookup"><span data-stu-id="cdc3e-140">If you set ANSI_NULLS off in SQL Server, you can create expressions that use the equality operator to compare to null.</span></span> <span data-ttu-id="cdc3e-141">Sin embargo, no puede evitar que diferentes conexiones establezcan opciones nulas para esa conexión.</span><span class="sxs-lookup"><span data-stu-id="cdc3e-141">However, you can't prevent different connections from setting null options for that connection.</span></span> <span data-ttu-id="cdc3e-142">El uso de IS NULL para probar si los valores son NULL siempre funciona, con independencia de la configuración de ANSI_NULLS en una conexión.</span><span class="sxs-lookup"><span data-stu-id="cdc3e-142">Using IS NULL to test for null values always works, regardless of the ANSI_NULLS settings for a connection.</span></span>  
  
 <span data-ttu-id="cdc3e-143">No se admite el establecimiento de ANSI_NULLS en OFF en un `DataSet`, ya que siempre sigue el estándar ANSI SQL-92 para el tratamiento de valores NULL en <xref:System.Data.SqlTypes>.</span><span class="sxs-lookup"><span data-stu-id="cdc3e-143">Setting ANSI_NULLS off is not supported in a `DataSet`, which always follows the ANSI SQL-92 standard for handling null values in <xref:System.Data.SqlTypes>.</span></span>  
  
## <a name="assigning-null-values"></a><span data-ttu-id="cdc3e-144">Asignación de valores NULL</span><span class="sxs-lookup"><span data-stu-id="cdc3e-144">Assigning Null Values</span></span>  
 <span data-ttu-id="cdc3e-145">Los valores NULL son especiales y su semántica de almacenamiento y asignación varía según los diversos sistemas de tipos y sistemas de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="cdc3e-145">Null values are special, and their storage and assignment semantics differ across different type systems and storage systems.</span></span> <span data-ttu-id="cdc3e-146">Un `Dataset` se ha diseñado para su uso con diferentes sistemas de tipos y de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="cdc3e-146">A `Dataset` is designed to be used with different type and storage systems.</span></span>  
  
 <span data-ttu-id="cdc3e-147">En esta sección se describe la semántica de valores NULL para la asignación de dichos valores a una <xref:System.Data.DataColumn> de una <xref:System.Data.DataRow> entre sistemas de tipos diferentes.</span><span class="sxs-lookup"><span data-stu-id="cdc3e-147">This section describes the null semantics for assigning null values to a <xref:System.Data.DataColumn> in a <xref:System.Data.DataRow> across the different type systems.</span></span>  
  
 `DBNull.Value`  
 <span data-ttu-id="cdc3e-148">Esta asignación es válida para una `DataColumn` de cualquier tipo.</span><span class="sxs-lookup"><span data-stu-id="cdc3e-148">This assignment is valid for a `DataColumn` of any type.</span></span> <span data-ttu-id="cdc3e-149">Si el tipo implementa `INullable`, `DBNull.Value` se convierte en el valor NULL adecuado fuertemente tipado.</span><span class="sxs-lookup"><span data-stu-id="cdc3e-149">If the type implements `INullable`, `DBNull.Value` is coerced into the appropriate strongly typed Null value.</span></span>  
  
 `SqlType.Null`  
 <span data-ttu-id="cdc3e-150">Todos los tipos de datos <xref:System.Data.SqlTypes> implementan `INullable`.</span><span class="sxs-lookup"><span data-stu-id="cdc3e-150">All <xref:System.Data.SqlTypes> data types implement `INullable`.</span></span> <span data-ttu-id="cdc3e-151">Si el valor NULL fuertemente tipado se puede convertir en el tipo de datos de la columna mediante operadores de conversión implícitos, la asignación debería realizarse.</span><span class="sxs-lookup"><span data-stu-id="cdc3e-151">If the strongly typed null value can be converted into the column's data type using implicit cast operators, the assignment should go through.</span></span> <span data-ttu-id="cdc3e-152">De lo contrario, se produce una excepción de conversión no válida.</span><span class="sxs-lookup"><span data-stu-id="cdc3e-152">Otherwise an invalid cast exception is thrown.</span></span>  
  
 `null`  
 <span data-ttu-id="cdc3e-153">Si 'null' es un valor válido para el tipo de datos `DataColumn` dado, se convierte en el `DbNull.Value` o `Null` asociado con el tipo `INullable` (`SqlType.Null`)</span><span class="sxs-lookup"><span data-stu-id="cdc3e-153">If 'null' is a legal value for the given `DataColumn` data type, it is coerced into the appropriate `DbNull.Value` or `Null` associated with the `INullable` type (`SqlType.Null`)</span></span>  
  
 `derivedUdt.Null`  
 <span data-ttu-id="cdc3e-154">En columnas de tipos definidos por el usuario, los valores NULL se almacenan siempre en el tipo asociado con la `DataColumn`.</span><span class="sxs-lookup"><span data-stu-id="cdc3e-154">For UDT columns, nulls are always stored based on the type associated with the `DataColumn`.</span></span> <span data-ttu-id="cdc3e-155">Considere el caso de un tipo definido por el usuario asociado con una `DataColumn` que no implementa `INullable`, mientras su subclase sí lo hace.</span><span class="sxs-lookup"><span data-stu-id="cdc3e-155">Consider the case of a UDT associated with a `DataColumn` that does not implement `INullable` while its sub-class does.</span></span> <span data-ttu-id="cdc3e-156">En este caso, si se asigna un valor NULL fuertemente tipado asociado a la clase derivada, se almacenará como `DbNull.Value` sin tipo, porque el almacenamiento de valores NULL es siempre coherente con el tipo de datos de DataColumn.</span><span class="sxs-lookup"><span data-stu-id="cdc3e-156">In this case, if a strongly typed null value associated with the derived class is assigned, it is stored as an untyped `DbNull.Value`, because null storage is always consistent with the DataColumn's data type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cdc3e-157">La estructura `Nullable<T>` o <xref:System.Nullable> no se admite actualmente en `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="cdc3e-157">The `Nullable<T>` or <xref:System.Nullable> structure is not currently supported in the `DataSet`.</span></span>  
  
### <a name="multiple-column-row-assignment"></a><span data-ttu-id="cdc3e-158">Asignación de varias columnas (filas)</span><span class="sxs-lookup"><span data-stu-id="cdc3e-158">Multiple Column (Row) Assignment</span></span>  
 <span data-ttu-id="cdc3e-159">`DataTable.Add`, `DataTable.LoadDataRow` u otras API que aceptan <xref:System.Data.DataRow.ItemArray%2A> que se asigna a una fila, asignan 'null' al valor predeterminado de DataColumn.</span><span class="sxs-lookup"><span data-stu-id="cdc3e-159">`DataTable.Add`, `DataTable.LoadDataRow`, or other APIs that accept an <xref:System.Data.DataRow.ItemArray%2A> that gets mapped to a row, map 'null' to the DataColumn's default value.</span></span> <span data-ttu-id="cdc3e-160">Si un objeto de la matriz contiene `DbNull.Value` o su equivalente fuertemente tipado, se aplican las mismas reglas que se han descrito anteriormente.</span><span class="sxs-lookup"><span data-stu-id="cdc3e-160">If an object in the array contains `DbNull.Value` or its strongly typed counterpart, the same rules as described above are applied.</span></span>  
  
 <span data-ttu-id="cdc3e-161">Además, las siguientes reglas se aplican para una instancia de asignaciones de NULL de `DataRow.["columnName"]`:</span><span class="sxs-lookup"><span data-stu-id="cdc3e-161">In addition, the following rules apply for an instance of `DataRow.["columnName"]` null assignments:</span></span>  
  
1.  <span data-ttu-id="cdc3e-162">El valor predeterminado *predeterminado* valor es `DbNull.Value` para todas excepto las columnas null fuertemente tipadas que resulta adecuado fuertemente tipados valor null.</span><span class="sxs-lookup"><span data-stu-id="cdc3e-162">The default *default* value is `DbNull.Value` for all except the strongly typed null columns where it is the appropriate strongly typed null value.</span></span>  
  
2.  <span data-ttu-id="cdc3e-163">Los valores NULL nunca se escriben durante la serialización a archivos XML (como en "xsi:nil").</span><span class="sxs-lookup"><span data-stu-id="cdc3e-163">Null values are never written out during serialization to XML files (as in "xsi:nil").</span></span>  
  
3.  <span data-ttu-id="cdc3e-164">Todos los valores que no son NULL, incluidos los predeterminados, siempre se escriben durante la serialización a XML.</span><span class="sxs-lookup"><span data-stu-id="cdc3e-164">All non-null values, including defaults, are always written out while serializing to XML.</span></span> <span data-ttu-id="cdc3e-165">Esto no es característico de la semántica de XSD/XML en la que un valor NULL (xsi:nil) es explícito y el valor predeterminado es implícito (si no está presente en XML, un analizador de validación puede obtenerlo de un esquema XSD asociado).</span><span class="sxs-lookup"><span data-stu-id="cdc3e-165">This is unlike XSD/XML semantics where a null value (xsi:nil) is explicit and the default value is implicit (if not present in XML, a validating parser can get it from an associated XSD schema).</span></span> <span data-ttu-id="cdc3e-166">Lo contrario se cumple para `DataTable`: un valor NULL es implícito y el valor predeterminado es explícito.</span><span class="sxs-lookup"><span data-stu-id="cdc3e-166">The opposite is true for a `DataTable`: a null value is implicit and the default value is explicit.</span></span>  
  
4.  <span data-ttu-id="cdc3e-167">A todos los valores de columna que faltan en las filas leídas de la información XML introducida se les asigna NULL.</span><span class="sxs-lookup"><span data-stu-id="cdc3e-167">All missing column values for rows read from XML input are assigned NULL.</span></span> <span data-ttu-id="cdc3e-168">A las filas creadas mediante <xref:System.Data.DataTable.NewRow%2A> o métodos similares se les asigna el valor predeterminado de DataColumn.</span><span class="sxs-lookup"><span data-stu-id="cdc3e-168">Rows created using <xref:System.Data.DataTable.NewRow%2A> or similar methods are assigned the DataColumn's default value.</span></span>  
  
5.  <span data-ttu-id="cdc3e-169">El método <xref:System.Data.DataRow.IsNull%2A> devuelve `true` para `DbNull.Value` y `INullable.Null`.</span><span class="sxs-lookup"><span data-stu-id="cdc3e-169">The <xref:System.Data.DataRow.IsNull%2A> method returns `true` for both `DbNull.Value` and `INullable.Null`.</span></span>  
  
## <a name="assigning-null-values"></a><span data-ttu-id="cdc3e-170">Asignación de valores NULL</span><span class="sxs-lookup"><span data-stu-id="cdc3e-170">Assigning Null Values</span></span>  
 <span data-ttu-id="cdc3e-171">El valor predeterminado de cualquier instancia de <xref:System.Data.SqlTypes> es NULL.</span><span class="sxs-lookup"><span data-stu-id="cdc3e-171">The default value for any <xref:System.Data.SqlTypes> instance is null.</span></span>  
  
 <span data-ttu-id="cdc3e-172">Los valores NULL de <xref:System.Data.SqlTypes> son específicos del tipo y no se pueden representar con un único valor, como `DbNull`.</span><span class="sxs-lookup"><span data-stu-id="cdc3e-172">Nulls in <xref:System.Data.SqlTypes> are type-specific and cannot be represented by a single value, such as `DbNull`.</span></span> <span data-ttu-id="cdc3e-173">Utilice la propiedad `IsNull` para comprobar si hay valores NULL.</span><span class="sxs-lookup"><span data-stu-id="cdc3e-173">Use the `IsNull` property to check for nulls.</span></span>  
  
 <span data-ttu-id="cdc3e-174">Es posible asignar valores NULL a una <xref:System.Data.DataColumn>, como se muestra en el siguiente código de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="cdc3e-174">Null values can be assigned to a <xref:System.Data.DataColumn> as shown in the following code example.</span></span> <span data-ttu-id="cdc3e-175">Puede asignar directamente valores NULL a variables `SqlTypes` sin desencadenar una excepción.</span><span class="sxs-lookup"><span data-stu-id="cdc3e-175">You can directly assign null values to `SqlTypes` variables without triggering an exception.</span></span>  
  
### <a name="example"></a><span data-ttu-id="cdc3e-176">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cdc3e-176">Example</span></span>  
 <span data-ttu-id="cdc3e-177">El siguiente código de ejemplo crea una <xref:System.Data.DataTable> con dos columnas definidas como <xref:System.Data.SqlTypes.SqlInt32> y <xref:System.Data.SqlTypes.SqlString>.</span><span class="sxs-lookup"><span data-stu-id="cdc3e-177">The following code example creates a <xref:System.Data.DataTable> with two columns defined as <xref:System.Data.SqlTypes.SqlInt32> and <xref:System.Data.SqlTypes.SqlString>.</span></span> <span data-ttu-id="cdc3e-178">El código agrega una fila de valores conocidos, una fila de valores NULL y, luego, establece una iteración en la <xref:System.Data.DataTable>, de modo que los valores se asignan a variables y el resultado se muestra en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="cdc3e-178">The code adds one row of known values, one row of null values and then iterates through the <xref:System.Data.DataTable>, assigning the values to variables and displaying the output in the console window.</span></span>  
  
 [!code-csharp[DataWorks SqlTypes.IsNull#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlTypes.IsNull/CS/source.cs#1)]
 [!code-vb[DataWorks SqlTypes.IsNull#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlTypes.IsNull/VB/source.vb#1)]  
  
 <span data-ttu-id="cdc3e-179">Este ejemplo muestra el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="cdc3e-179">This example displays the following results:</span></span>  
  
```  
isColumnNull=False, ID=123, Description=Side Mirror  
isColumnNull=True, ID=Null, Description=Null  
```  
  
## <a name="comparing-null-values-with-sqltypes-and-clr-types"></a><span data-ttu-id="cdc3e-180">Comparación de valores NULL con SqlTypes y tipos CLR</span><span class="sxs-lookup"><span data-stu-id="cdc3e-180">Comparing Null Values with SqlTypes and CLR Types</span></span>  
 <span data-ttu-id="cdc3e-181">Al comparar valores NULL, es importante comprender la diferencia entre la forma en que el método `Equals` evalúa los valores NULL en <xref:System.Data.SqlTypes> por contraposición a cómo funciona con tipos CLR.</span><span class="sxs-lookup"><span data-stu-id="cdc3e-181">When comparing null values, it is important to understand the difference between the way the `Equals` method evaluates null values in <xref:System.Data.SqlTypes> as compared with the way it works with CLR types.</span></span> <span data-ttu-id="cdc3e-182">Todos los <xref:System.Data.SqlTypes> `Equals` métodos utilizan la semántica de base de datos para evaluar valores null: si uno o ambos de los valores es null, la comparación produce null.</span><span class="sxs-lookup"><span data-stu-id="cdc3e-182">All of the <xref:System.Data.SqlTypes>`Equals` methods use database semantics for evaluating null values: if either or both of the values is null, the comparison yields null.</span></span> <span data-ttu-id="cdc3e-183">Por otra parte, el uso del método `Equals` de CLR en dos <xref:System.Data.SqlTypes> producirá TRUE si ambos son NULL.</span><span class="sxs-lookup"><span data-stu-id="cdc3e-183">On the other hand, using the CLR `Equals` method on two <xref:System.Data.SqlTypes> will yield true if both are null.</span></span> <span data-ttu-id="cdc3e-184">Esto refleja la diferencia entre el uso de un método de instancia como el método `String.Equals` de CLR y el uso del método estático o compartido `SqlString.Equals`.</span><span class="sxs-lookup"><span data-stu-id="cdc3e-184">This reflects the difference between using an instance method such as the CLR `String.Equals` method, and using the static/shared method, `SqlString.Equals`.</span></span>  
  
 <span data-ttu-id="cdc3e-185">En el siguiente ejemplo se muestra la diferencia entre los resultados del método `SqlString.Equals` y del método `String.Equals` cuando se pasa a cada uno un par de valores NULL y, a continuación, un par de cadenas vacías.</span><span class="sxs-lookup"><span data-stu-id="cdc3e-185">The following example demonstrates the difference in results between the `SqlString.Equals` method and the `String.Equals` method when each is passed a pair of null values and then a pair of empty strings.</span></span>  
  
 [!code-csharp[DataWorks SqlTypes.CompareNulls#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlTypes.CompareNulls/CS/source.cs#1)]
 [!code-vb[DataWorks SqlTypes.CompareNulls#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlTypes.CompareNulls/VB/source.vb#1)]  
  
 <span data-ttu-id="cdc3e-186">El código produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="cdc3e-186">The code produces the following output:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="cdc3e-187">Vea también</span><span class="sxs-lookup"><span data-stu-id="cdc3e-187">See Also</span></span>  
 [<span data-ttu-id="cdc3e-188">Tipos de datos de SQL Server y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="cdc3e-188">SQL Server Data Types and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)  
 [<span data-ttu-id="cdc3e-189">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="cdc3e-189">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
