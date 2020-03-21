---
title: Modificación de datos de gran valor (máx.)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8aca5f00-d80e-4320-81b3-016d0466f7ee
ms.openlocfilehash: 00a4ae83270bb74e9703faebfc93e26b5c069478
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174282"
---
# <a name="modifying-large-value-max-data-in-adonet"></a><span data-ttu-id="26872-102">Modificar datos de valores grandes (max) en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="26872-102">Modifying Large-Value (max) Data in ADO.NET</span></span>
<span data-ttu-id="26872-103">Los tipos de datos de objeto grande (LOB) son aquellos que superan el tamaño máximo de fila de 8 kilobytes (KB).</span><span class="sxs-lookup"><span data-stu-id="26872-103">Large object (LOB) data types are those that exceed the maximum row size of 8 kilobytes (KB).</span></span> <span data-ttu-id="26872-104">SQL Server proporciona un especificador `max` para los tipos de datos `varchar`, `nvarchar` y `varbinary` que permite el almacenamiento de valores tan grandes como 2^32 bytes.</span><span class="sxs-lookup"><span data-stu-id="26872-104">SQL Server provides a `max` specifier for `varchar`, `nvarchar`, and `varbinary` data types to allow storage of values as large as 2^32 bytes.</span></span> <span data-ttu-id="26872-105">Las columnas de tabla y las variables de Transact-SQL pueden especificar tipos de datos `varchar(max)`, `nvarchar(max)` o `varbinary(max)`.</span><span class="sxs-lookup"><span data-stu-id="26872-105">Table columns and Transact-SQL variables may specify `varchar(max)`, `nvarchar(max)`, or `varbinary(max)` data types.</span></span> <span data-ttu-id="26872-106">En ADO.NET, los tipos de datos `max` se pueden recuperar mediante `DataReader` y también se pueden especificar como valores de parámetros de entrada y salida sin ningún control especial.</span><span class="sxs-lookup"><span data-stu-id="26872-106">In ADO.NET, the `max` data types can be fetched by a `DataReader`, and can also be specified as both input and output parameter values without any special handling.</span></span> <span data-ttu-id="26872-107">En el caso de los tipos de datos `varchar` grandes, los datos se pueden recuperar y actualizar incrementalmente.</span><span class="sxs-lookup"><span data-stu-id="26872-107">For large `varchar` data types, data can be retrieved and updated incrementally.</span></span>  
  
 <span data-ttu-id="26872-108">Los tipos de datos `max` se pueden usar para comparaciones, como variables de Transact-SQL y para la concatenación.</span><span class="sxs-lookup"><span data-stu-id="26872-108">The `max` data types can be used for comparisons, as Transact-SQL variables, and for concatenation.</span></span> <span data-ttu-id="26872-109">También se pueden usar en las cláusulas DISTINCT, ORDER BY, GROUP BY de una instrucción SELECT, así como en agregados, combinaciones y subconsultas.</span><span class="sxs-lookup"><span data-stu-id="26872-109">They can also be used in the DISTINCT, ORDER BY, GROUP BY clauses of a SELECT statement as well as in aggregates, joins, and subqueries.</span></span>  
  
 <span data-ttu-id="26872-110">La tabla siguiente proporciona vínculos a la documentación de los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="26872-110">The following table provides links to the documentation in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="26872-111">**SQL Server, documentación**</span><span class="sxs-lookup"><span data-stu-id="26872-111">**SQL Server documentation**</span></span>  
  
1. <span data-ttu-id="26872-112">[Usar tipos de datos de valores grandes](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms178158(v=sql.100))</span><span class="sxs-lookup"><span data-stu-id="26872-112">[Using Large-Value Data Types](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms178158(v=sql.100))</span></span>  
  
## <a name="large-value-type-restrictions"></a><span data-ttu-id="26872-113">Restricciones de los tipos de valor grande</span><span class="sxs-lookup"><span data-stu-id="26872-113">Large-Value Type Restrictions</span></span>  
 <span data-ttu-id="26872-114">Las restricciones siguientes se aplican a los tipos de datos `max`, que no existen para tipos de datos más pequeños:</span><span class="sxs-lookup"><span data-stu-id="26872-114">The following restrictions apply to the `max` data types, which do not exist for smaller data types:</span></span>  
  
- <span data-ttu-id="26872-115">Un `sql_variant` no puede contener un tipo de datos `varchar` grande.</span><span class="sxs-lookup"><span data-stu-id="26872-115">A `sql_variant` cannot contain a large `varchar` data type.</span></span>  
  
- <span data-ttu-id="26872-116">No se pueden especificar columnas de `varchar` grandes como columna de clave en un índice.</span><span class="sxs-lookup"><span data-stu-id="26872-116">Large `varchar` columns cannot be specified as a key column in an index.</span></span> <span data-ttu-id="26872-117">Se permiten en una columna incluida en un índice no agrupado.</span><span class="sxs-lookup"><span data-stu-id="26872-117">They are allowed in an included column in a non-clustered index.</span></span>  
  
- <span data-ttu-id="26872-118">Las columnas de `varchar` grandes no se pueden usar como columnas de clave de partición.</span><span class="sxs-lookup"><span data-stu-id="26872-118">Large `varchar` columns cannot be used as partitioning key columns.</span></span>  
  
## <a name="working-with-large-value-types-in-transact-sql"></a><span data-ttu-id="26872-119">Trabajar con tipos de valor grande en Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="26872-119">Working with Large-Value Types in Transact-SQL</span></span>  
 <span data-ttu-id="26872-120">La función `OPENROWSET` de Transact-SQL es un método único de conexión y acceso a los datos remotos.</span><span class="sxs-lookup"><span data-stu-id="26872-120">The Transact-SQL `OPENROWSET` function is a one-time method of connecting and accessing remote data.</span></span> <span data-ttu-id="26872-121">Incluye toda la información de conexión necesaria para tener acceso a datos remotos desde un origen de datos OLE DB.</span><span class="sxs-lookup"><span data-stu-id="26872-121">It includes all of the connection information necessary to access remote data from an OLE DB data source.</span></span> <span data-ttu-id="26872-122">Se puede hacer referencia a `OPENROWSET` en la cláusula FROM de una consulta como si fuera un nombre de tabla.</span><span class="sxs-lookup"><span data-stu-id="26872-122">`OPENROWSET` can be referenced in the FROM clause of a query as though it were a table name.</span></span> <span data-ttu-id="26872-123">y como si fuera la tabla de destino de una instrucción INSERT, UPDATE o DELETE, sujeta a las capacidades del proveedor OLE DB.</span><span class="sxs-lookup"><span data-stu-id="26872-123">It can also be referenced as the target table of an INSERT, UPDATE, or DELETE statement, subject to the capabilities of the OLE DB provider.</span></span>  
  
 <span data-ttu-id="26872-124">La función `OPENROWSET` incluye el proveedor de conjuntos de filas `BULK`, que permite leer los datos directamente de un archivo sin tener que cargarlos en una tabla de destino.</span><span class="sxs-lookup"><span data-stu-id="26872-124">The `OPENROWSET` function includes the `BULK` rowset provider, which allows you to read data directly from a file without loading the data into a target table.</span></span> <span data-ttu-id="26872-125">Esto permite usar `OPENROWSET` en una instrucción INSERT SELECT simple.</span><span class="sxs-lookup"><span data-stu-id="26872-125">This enables you to use `OPENROWSET` in a simple INSERT SELECT statement.</span></span>  
  
 <span data-ttu-id="26872-126">Los argumentos de la opción `OPENROWSET BULK` ofrecen un control significativo sobre dónde comienza y termina la lectura de datos, cómo tratar los errores y cómo interpretar los datos.</span><span class="sxs-lookup"><span data-stu-id="26872-126">The `OPENROWSET BULK` option arguments provide significant control over where to begin and end reading data, how to deal with errors, and how data is interpreted.</span></span> <span data-ttu-id="26872-127">Por ejemplo, puede especificar que el archivo de datos se lea como un conjunto de filas de una sola fila y una sola columna de tipo `varbinary`, `varchar` o `nvarchar`.</span><span class="sxs-lookup"><span data-stu-id="26872-127">For example, you can specify that the data file be read as a single-row, single-column rowset of type `varbinary`, `varchar`, or `nvarchar`.</span></span> <span data-ttu-id="26872-128">Para obtener la sintaxis y las opciones completas, vea Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="26872-128">For the complete syntax and options, see SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="26872-129">En el ejemplo siguiente se inserta una foto en la tabla ProductPhoto de la base de datos de ejemplo de AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="26872-129">The following example inserts a photo into the ProductPhoto table in the AdventureWorks sample database.</span></span> <span data-ttu-id="26872-130">Si usa el proveedor `BULK OPENROWSET`, debe proporcionar la lista con nombre de columnas, incluso aunque no inserte valores en todas las columnas.</span><span class="sxs-lookup"><span data-stu-id="26872-130">When using the `BULK OPENROWSET` provider, you must supply the named list of columns even if you aren't inserting values into every column.</span></span> <span data-ttu-id="26872-131">En este caso, la clave principal se define como una columna de identidad y se puede omitir en la lista de columnas.</span><span class="sxs-lookup"><span data-stu-id="26872-131">The primary key in this case is defined as an identity column, and may be omitted from the column list.</span></span> <span data-ttu-id="26872-132">Tenga en cuenta que también debe proporcionar un nombre de correlación al final de la instrucción `OPENROWSET`, que en este caso es ThumbnailPhoto.</span><span class="sxs-lookup"><span data-stu-id="26872-132">Note that you must also supply a correlation name at the end of the `OPENROWSET` statement, which in this case is ThumbnailPhoto.</span></span> <span data-ttu-id="26872-133">Esto se correlaciona con la columna de la tabla `ProductPhoto` en la que se carga el archivo.</span><span class="sxs-lookup"><span data-stu-id="26872-133">This correlates with the column in the `ProductPhoto` table into which the file is being loaded.</span></span>  
  
```sql  
INSERT Production.ProductPhoto (  
    ThumbnailPhoto,
    ThumbnailPhotoFilePath,
    LargePhoto,
    LargePhotoFilePath)  
SELECT ThumbnailPhoto.*, null, null, N'tricycle_pink.gif'  
FROM OPENROWSET
    (BULK 'c:\images\tricycle.jpg', SINGLE_BLOB) ThumbnailPhoto  
```  
  
## <a name="updating-data-using-update-write"></a><span data-ttu-id="26872-134">Actualizar datos mediante UPDATE .WRITE</span><span class="sxs-lookup"><span data-stu-id="26872-134">Updating Data Using UPDATE .WRITE</span></span>  
 <span data-ttu-id="26872-135">La instrucción UPDATE de Transact-SQL tiene una nueva sintaxis WRITE para modificar el contenido de las columnas `varchar(max)`, `nvarchar(max)` o `varbinary(max)`.</span><span class="sxs-lookup"><span data-stu-id="26872-135">The Transact-SQL UPDATE statement has new WRITE syntax for modifying the contents of `varchar(max)`, `nvarchar(max)`, or `varbinary(max)` columns.</span></span> <span data-ttu-id="26872-136">Esto le permite realizar actualizaciones parciales de los datos.</span><span class="sxs-lookup"><span data-stu-id="26872-136">This allows you to perform partial updates of the data.</span></span> <span data-ttu-id="26872-137">La sintaxis de UPDATE.WRITE se muestra aquí de forma abreviada:</span><span class="sxs-lookup"><span data-stu-id="26872-137">The UPDATE .WRITE syntax is shown here in abbreviated form:</span></span>  
  
 <span data-ttu-id="26872-138">UPDATE</span><span class="sxs-lookup"><span data-stu-id="26872-138">UPDATE</span></span>  
  
 <span data-ttu-id="26872-139">• objeto>de \* \<objetos\* ?</span><span class="sxs-lookup"><span data-stu-id="26872-139">{ *\<object>* }</span></span>  
  
 <span data-ttu-id="26872-140">SET</span><span class="sxs-lookup"><span data-stu-id="26872-140">SET</span></span>  
  
 <span data-ttu-id="26872-141">• *column_name* . ESCRIBIR *expression* ( @Offset expresión @Length , , ) ?</span><span class="sxs-lookup"><span data-stu-id="26872-141">{ *column_name* = { .WRITE ( *expression* , @Offset , @Length ) }</span></span>  
  
 <span data-ttu-id="26872-142">El método WRITE especifica que se va a modificar una sección del valor de *column_name*.</span><span class="sxs-lookup"><span data-stu-id="26872-142">The WRITE method specifies that a section of the value of the *column_name* will be modified.</span></span> <span data-ttu-id="26872-143">La expresión es el valor que se va a copiar en *column_name*, mientras que `@Offset` es el punto inicial en el que se va a escribir la expresión y, por su parte, el argumento `@Length` es la longitud de la sección en la columna.</span><span class="sxs-lookup"><span data-stu-id="26872-143">The expression is the value that will be copied to the *column_name*, the `@Offset` is the beginning point at which the expression will be written, and the `@Length` argument is the length of the section in the column.</span></span>  
  
|<span data-ttu-id="26872-144">Si</span><span class="sxs-lookup"><span data-stu-id="26872-144">If</span></span>|<span data-ttu-id="26872-145">Entonces</span><span class="sxs-lookup"><span data-stu-id="26872-145">Then</span></span>|  
|--------|----------|  
|<span data-ttu-id="26872-146">La expresión se configura en NULL.</span><span class="sxs-lookup"><span data-stu-id="26872-146">The expression is set to NULL</span></span>|<span data-ttu-id="26872-147">`@Length` se omite y el valor de *column_name* se trunca en el elemento `@Offset` especificado.</span><span class="sxs-lookup"><span data-stu-id="26872-147">`@Length` is ignored and the value in *column_name* is truncated at the specified `@Offset`.</span></span>|  
|<span data-ttu-id="26872-148">`@Offset` es NULL</span><span class="sxs-lookup"><span data-stu-id="26872-148">`@Offset` is NULL</span></span>|<span data-ttu-id="26872-149">La operación de actualización anexa la expresión al final del valor de *column_name* existente y se omite `@Length`.</span><span class="sxs-lookup"><span data-stu-id="26872-149">The update operation appends the expression at the end of the existing *column_name* value and `@Length` is ignored.</span></span>|  
|<span data-ttu-id="26872-150">`@Offset` es mayor que la longitud del valor column_name.</span><span class="sxs-lookup"><span data-stu-id="26872-150">`@Offset` is greater than the length of the column_name value</span></span>|<span data-ttu-id="26872-151">SQL Server devuelve un error.</span><span class="sxs-lookup"><span data-stu-id="26872-151">SQL Server returns an error.</span></span>|  
|<span data-ttu-id="26872-152">`@Length` es NULL</span><span class="sxs-lookup"><span data-stu-id="26872-152">`@Length` is NULL</span></span>|<span data-ttu-id="26872-153">La operación de actualización quita todos los datos de `@Offset` hasta el final del valor de `column_name`.</span><span class="sxs-lookup"><span data-stu-id="26872-153">The update operation removes all data from `@Offset` to the end of the `column_name` value.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="26872-154">`@Offset` ni `@Length` pueden ser un número negativo.</span><span class="sxs-lookup"><span data-stu-id="26872-154">Neither `@Offset` nor `@Length` can be a negative number.</span></span>  
  
## <a name="example"></a><span data-ttu-id="26872-155">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="26872-155">Example</span></span>  
 <span data-ttu-id="26872-156">En este ejemplo de Transact-SQL se actualiza un valor parcial en DocumentSummary, una columna `nvarchar(max)` de la tabla Document de la base de datos AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="26872-156">This Transact-SQL example updates a partial value in DocumentSummary, an `nvarchar(max)` column in the Document table in the AdventureWorks database.</span></span> <span data-ttu-id="26872-157">La palabra "components" se sustituye por la palabra "features" al especificar la palabra sustituta, la ubicación inicial (desplazamiento) de la palabra que se va a sustituir en los datos existentes y el número de caracteres que se va a sustituir (longitud).</span><span class="sxs-lookup"><span data-stu-id="26872-157">The word 'components' is replaced by the word 'features' by specifying the replacement word, the beginning location (offset) of the word to be replaced in the existing data, and the number of characters to be replaced (length).</span></span> <span data-ttu-id="26872-158">En el ejemplo se incluyen instrucciones SELECT antes y después de la instrucción UPDATE para comparar los resultados.</span><span class="sxs-lookup"><span data-stu-id="26872-158">The example includes SELECT statements before and after the UPDATE statement to compare results.</span></span>  
  
```sql
USE AdventureWorks;  
GO  
--View the existing value.  
SELECT DocumentSummary  
FROM Production.Document  
WHERE DocumentID = 3;  
GO  
-- The first sentence of the results will be:  
-- Reflectors are vital safety components of your bicycle.  
  
--Modify a single word in the DocumentSummary column  
UPDATE Production.Document  
SET DocumentSummary .WRITE (N'features',28,10)  
WHERE DocumentID = 3 ;  
GO
--View the modified value.  
SELECT DocumentSummary  
FROM Production.Document  
WHERE DocumentID = 3;  
GO  
-- The first sentence of the results will be:  
-- Reflectors are vital safety features of your bicycle.  
```  
  
## <a name="working-with-large-value-types-in-adonet"></a><span data-ttu-id="26872-159">Trabajar con tipos de valor grandes en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="26872-159">Working with Large-Value Types in ADO.NET</span></span>  
 <span data-ttu-id="26872-160">Puede trabajar con tipos de valor grande en ADO.NET si los especifica como objetos <xref:System.Data.SqlClient.SqlParameter> en <xref:System.Data.SqlClient.SqlDataReader> para que devuelvan un conjunto de resultados o mediante el uso de <xref:System.Data.SqlClient.SqlDataAdapter> para rellenar `DataSet`/`DataTable`.</span><span class="sxs-lookup"><span data-stu-id="26872-160">You can work with large value types in ADO.NET by specifying large value types as <xref:System.Data.SqlClient.SqlParameter> objects in a <xref:System.Data.SqlClient.SqlDataReader> to return a result set, or by using a <xref:System.Data.SqlClient.SqlDataAdapter> to fill a `DataSet`/`DataTable`.</span></span> <span data-ttu-id="26872-161">No hay ninguna diferencia entre la forma de trabajar con un tipo de valor grande y su tipo de datos de valor más pequeño relacionado.</span><span class="sxs-lookup"><span data-stu-id="26872-161">There is no difference between the way you work with a large value type and its related, smaller value data type.</span></span>  
  
### <a name="using-getsqlbytes-to-retrieve-data"></a><span data-ttu-id="26872-162">Uso de GetSqlBytes para recuperar datos</span><span class="sxs-lookup"><span data-stu-id="26872-162">Using GetSqlBytes to Retrieve Data</span></span>  
 <span data-ttu-id="26872-163">El método `GetSqlBytes` de <xref:System.Data.SqlClient.SqlDataReader> se puede utilizar para recuperar el contenido de una columna `varbinary(max)`.</span><span class="sxs-lookup"><span data-stu-id="26872-163">The `GetSqlBytes` method of the <xref:System.Data.SqlClient.SqlDataReader> can be used to retrieve the contents of a `varbinary(max)` column.</span></span> <span data-ttu-id="26872-164">El siguiente fragmento de código asume un objeto <xref:System.Data.SqlClient.SqlCommand> denominado `cmd` que selecciona datos `varbinary(max)` de una tabla y un objeto <xref:System.Data.SqlClient.SqlDataReader> denominado `reader` que recupera los datos como <xref:System.Data.SqlTypes.SqlBytes>.</span><span class="sxs-lookup"><span data-stu-id="26872-164">The following code fragment assumes a <xref:System.Data.SqlClient.SqlCommand> object named `cmd` that selects `varbinary(max)` data from a table and a <xref:System.Data.SqlClient.SqlDataReader> object named `reader` that retrieves the data as <xref:System.Data.SqlTypes.SqlBytes>.</span></span>  
  
```vb  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection)  
While reader.Read()  
    Dim bytes As SqlBytes = reader.GetSqlBytes(0)  
End While  
```  
  
```csharp  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection);  
while (reader.Read())  
    {  
        SqlBytes bytes = reader.GetSqlBytes(0);  
    }  
```  
  
### <a name="using-getsqlchars-to-retrieve-data"></a><span data-ttu-id="26872-165">Uso de GetSqlChars para recuperar datos</span><span class="sxs-lookup"><span data-stu-id="26872-165">Using GetSqlChars to Retrieve Data</span></span>  
 <span data-ttu-id="26872-166">El método `GetSqlChars` de <xref:System.Data.SqlClient.SqlDataReader> se puede utilizar para recuperar el contenido de una columna `varchar(max)` o `nvarchar(max)`.</span><span class="sxs-lookup"><span data-stu-id="26872-166">The `GetSqlChars` method of the <xref:System.Data.SqlClient.SqlDataReader> can be used to retrieve the contents of a `varchar(max)` or `nvarchar(max)` column.</span></span> <span data-ttu-id="26872-167">El siguiente fragmento de código asume un objeto <xref:System.Data.SqlClient.SqlCommand> denominado `cmd` que selecciona datos `nvarchar(max)` de una tabla y un objeto <xref:System.Data.SqlClient.SqlDataReader> denominado `reader` que recupera los datos.</span><span class="sxs-lookup"><span data-stu-id="26872-167">The following code fragment assumes a <xref:System.Data.SqlClient.SqlCommand> object named `cmd` that selects `nvarchar(max)` data from a table and a <xref:System.Data.SqlClient.SqlDataReader> object named `reader` that retrieves the data.</span></span>  
  
```vb  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection)  
While reader.Read()  
    Dim buffer As SqlChars = reader.GetSqlChars(0)  
End While  
```  
  
```csharp  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection);  
while (reader.Read())  
{  
    SqlChars buffer = reader.GetSqlChars(0);  
}  
```  
  
### <a name="using-getsqlbinary-to-retrieve-data"></a><span data-ttu-id="26872-168">Uso de GetSqlBinary para recuperar datos</span><span class="sxs-lookup"><span data-stu-id="26872-168">Using GetSqlBinary to Retrieve Data</span></span>  
 <span data-ttu-id="26872-169">El método `GetSqlBinary` de <xref:System.Data.SqlClient.SqlDataReader> se puede utilizar para recuperar el contenido de una columna `varbinary(max)`.</span><span class="sxs-lookup"><span data-stu-id="26872-169">The `GetSqlBinary` method of a <xref:System.Data.SqlClient.SqlDataReader> can be used to retrieve the contents of a `varbinary(max)` column.</span></span> <span data-ttu-id="26872-170">El siguiente fragmento de código asume un objeto <xref:System.Data.SqlClient.SqlCommand> denominado `cmd` que selecciona datos `varbinary(max)` de una tabla y un objeto <xref:System.Data.SqlClient.SqlDataReader> denominado `reader` que recupera los datos como un flujo <xref:System.Data.SqlTypes.SqlBinary>.</span><span class="sxs-lookup"><span data-stu-id="26872-170">The following code fragment assumes a <xref:System.Data.SqlClient.SqlCommand> object named `cmd` that selects `varbinary(max)` data from a table and a <xref:System.Data.SqlClient.SqlDataReader> object named `reader` that retrieves the data as a <xref:System.Data.SqlTypes.SqlBinary> stream.</span></span>  
  
```vb  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection)  
While reader.Read()  
    Dim binaryStream As SqlBinary = reader.GetSqlBinary(0)  
End While  
```  
  
```csharp  
reader = cmd.ExecuteReader(CommandBehavior.CloseConnection);  
while (reader.Read())  
    {  
        SqlBinary binaryStream = reader.GetSqlBinary(0);  
    }  
```  
  
### <a name="using-getbytes-to-retrieve-data"></a><span data-ttu-id="26872-171">Uso de GetBytes para recuperar datos</span><span class="sxs-lookup"><span data-stu-id="26872-171">Using GetBytes to Retrieve Data</span></span>  
 <span data-ttu-id="26872-172">El método `GetBytes` de <xref:System.Data.SqlClient.SqlDataReader> lee un flujo de bytes a partir del desplazamiento de la columna especificada en una matriz de bytes, comenzando en el desplazamiento de la matriz especificado.</span><span class="sxs-lookup"><span data-stu-id="26872-172">The `GetBytes` method of a <xref:System.Data.SqlClient.SqlDataReader> reads a stream of bytes from the specified column offset into a byte array starting at the specified array offset.</span></span> <span data-ttu-id="26872-173">El siguiente fragmento de código asume un objeto <xref:System.Data.SqlClient.SqlDataReader> denominado `reader` que recupera bytes en una matriz de bytes.</span><span class="sxs-lookup"><span data-stu-id="26872-173">The following code fragment assumes a <xref:System.Data.SqlClient.SqlDataReader> object named `reader` that retrieves bytes into a byte array.</span></span> <span data-ttu-id="26872-174">Tenga en cuenta que, a diferencia de `GetSqlBytes`, `GetBytes` requiere un tamaño para el búfer de la matriz.</span><span class="sxs-lookup"><span data-stu-id="26872-174">Note that, unlike `GetSqlBytes`, `GetBytes` requires a size for the array buffer.</span></span>  
  
```vb  
While reader.Read()  
    Dim buffer(4000) As Byte  
    Dim byteCount As Integer = _  
    CInt(reader.GetBytes(1, 0, buffer, 0, 4000))  
End While  
```  
  
```csharp  
while (reader.Read())  
{  
    byte[] buffer = new byte[4000];  
    long byteCount = reader.GetBytes(1, 0, buffer, 0, 4000);  
}  
```  
  
### <a name="using-getvalue-to-retrieve-data"></a><span data-ttu-id="26872-175">Uso de GetValue para recuperar datos</span><span class="sxs-lookup"><span data-stu-id="26872-175">Using GetValue to Retrieve Data</span></span>  
 <span data-ttu-id="26872-176">El método `GetValue` de <xref:System.Data.SqlClient.SqlDataReader> lee el valor del desplazamiento de columna especificado en una matriz.</span><span class="sxs-lookup"><span data-stu-id="26872-176">The `GetValue` method of a <xref:System.Data.SqlClient.SqlDataReader> reads the value from the specified column offset into an array.</span></span> <span data-ttu-id="26872-177">El siguiente fragmento de código asume un objeto <xref:System.Data.SqlClient.SqlDataReader> denominado `reader` que recupera los datos binarios del desplazamiento de la primera columna y, a continuación, los datos de cadena del desplazamiento de la segunda columna.</span><span class="sxs-lookup"><span data-stu-id="26872-177">The following code fragment assumes a <xref:System.Data.SqlClient.SqlDataReader> object named `reader` that retrieves binary data from the first column offset, and then string data from the second column offset.</span></span>  
  
```vb  
While reader.Read()  
    ' Read the data from varbinary(max) column  
    Dim binaryData() As Byte = CByte(reader.GetValue(0))  
  
    ' Read the data from varchar(max) or nvarchar(max) column  
    Dim stringData() As String = Cstr((reader.GetValue(1))  
End While  
```  
  
```csharp  
while (reader.Read())  
{  
    // Read the data from varbinary(max) column  
    byte[] binaryData = (byte[])reader.GetValue(0);  
  
    // Read the data from varchar(max) or nvarchar(max) column  
    String stringData = (String)reader.GetValue(1);  
}  
```  
  
## <a name="converting-from-large-value-types-to-clr-types"></a><span data-ttu-id="26872-178">Conversión de tipos de valor grandes a tipos CLR</span><span class="sxs-lookup"><span data-stu-id="26872-178">Converting from Large Value Types to CLR Types</span></span>  
 <span data-ttu-id="26872-179">Puede convertir el contenido de una columna `varchar(max)` o `nvarchar(max)` mediante cualquiera de los métodos de conversión de cadenas, como `ToString`.</span><span class="sxs-lookup"><span data-stu-id="26872-179">You can convert the contents of a `varchar(max)` or `nvarchar(max)` column using any of the string conversion methods, such as `ToString`.</span></span> <span data-ttu-id="26872-180">El siguiente fragmento de código asume un objeto <xref:System.Data.SqlClient.SqlDataReader> denominado `reader` que recupera los datos.</span><span class="sxs-lookup"><span data-stu-id="26872-180">The following code fragment assumes a <xref:System.Data.SqlClient.SqlDataReader> object named `reader` that retrieves the data.</span></span>  
  
```vb  
While reader.Read()  
    Dim str as String = reader(0).ToString()  
    Console.WriteLine(str)  
End While  
```  
  
```csharp  
while (reader.Read())  
{  
     string str = reader[0].ToString();  
     Console.WriteLine(str);  
}  
```  
  
### <a name="example"></a><span data-ttu-id="26872-181">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="26872-181">Example</span></span>  
 <span data-ttu-id="26872-182">El código siguiente recupera el nombre y el objeto `LargePhoto` de la tabla `ProductPhoto` de la base de datos `AdventureWorks` y los guarda en un archivo.</span><span class="sxs-lookup"><span data-stu-id="26872-182">The following code retrieves the name and the `LargePhoto` object from the `ProductPhoto` table in the `AdventureWorks` database and saves it to a file.</span></span> <span data-ttu-id="26872-183">El ensamblado debe compilarse con una referencia al espacio de nombres <xref:System.Drawing>.</span><span class="sxs-lookup"><span data-stu-id="26872-183">The assembly needs to be compiled with a reference to the <xref:System.Drawing> namespace.</span></span>  <span data-ttu-id="26872-184">El método <xref:System.Data.SqlClient.SqlDataReader.GetSqlBytes%2A> de <xref:System.Data.SqlClient.SqlDataReader> devuelve un objeto <xref:System.Data.SqlTypes.SqlBytes> que expone una propiedad `Stream`.</span><span class="sxs-lookup"><span data-stu-id="26872-184">The <xref:System.Data.SqlClient.SqlDataReader.GetSqlBytes%2A> method of the <xref:System.Data.SqlClient.SqlDataReader> returns a <xref:System.Data.SqlTypes.SqlBytes> object that exposes a `Stream` property.</span></span> <span data-ttu-id="26872-185">El código lo usa para crear un nuevo objeto `Bitmap` y, luego, lo guarda en el Gif `ImageFormat`.</span><span class="sxs-lookup"><span data-stu-id="26872-185">The code uses this to create a new `Bitmap` object, and then saves it in the Gif `ImageFormat`.</span></span>  
  
 [!code-csharp[DataWorks LargeValueType.Photo#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks LargeValueType.Photo/CS/source.cs#1)]
 [!code-vb[DataWorks LargeValueType.Photo#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks LargeValueType.Photo/VB/source.vb#1)]  
  
## <a name="using-large-value-type-parameters"></a><span data-ttu-id="26872-186">Usar parámetros de tipos de valor grande</span><span class="sxs-lookup"><span data-stu-id="26872-186">Using Large Value Type Parameters</span></span>  
 <span data-ttu-id="26872-187">Los tipos de valores grandes se pueden usar en objetos <xref:System.Data.SqlClient.SqlParameter> de la misma manera en que se usan los tipos de valores más pequeños en objetos <xref:System.Data.SqlClient.SqlParameter>.</span><span class="sxs-lookup"><span data-stu-id="26872-187">Large value types can be used in <xref:System.Data.SqlClient.SqlParameter> objects the same way you use smaller value types in <xref:System.Data.SqlClient.SqlParameter> objects.</span></span> <span data-ttu-id="26872-188">Puede recuperar tipos de valor grande como valores <xref:System.Data.SqlClient.SqlParameter>, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="26872-188">You can retrieve large value types as <xref:System.Data.SqlClient.SqlParameter> values, as shown in the following example.</span></span> <span data-ttu-id="26872-189">En el código se supone que existe el siguiente procedimiento almacenado GetDocumentSummary en la base de datos de ejemplo AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="26872-189">The code assumes that the following GetDocumentSummary stored procedure exists in the AdventureWorks sample database.</span></span> <span data-ttu-id="26872-190">El procedimiento almacenado toma un parámetro de entrada denominado @DocumentID y devuelve el contenido de la columna DocumentSummary en el parámetro de salida @DocumentSummary.</span><span class="sxs-lookup"><span data-stu-id="26872-190">The stored procedure takes an input parameter named @DocumentID and returns the contents of the DocumentSummary column in the @DocumentSummary output parameter.</span></span>  
  
```sql
CREATE PROCEDURE GetDocumentSummary
(  
    @DocumentID int,  
    @DocumentSummary nvarchar(MAX) OUTPUT  
)  
AS  
SET NOCOUNT ON  
SELECT  @DocumentSummary=Convert(nvarchar(MAX), DocumentSummary)  
FROM    Production.Document  
WHERE   DocumentID=@DocumentID  
```  
  
### <a name="example"></a><span data-ttu-id="26872-191">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="26872-191">Example</span></span>  
 <span data-ttu-id="26872-192">El código ADO.NET crea objetos <xref:System.Data.SqlClient.SqlConnection> y <xref:System.Data.SqlClient.SqlCommand> para ejecutar el procedimiento almacenado GetDocumentSummary y recuperar el resumen del documento, que se almacena como un tipo de valores grandes.</span><span class="sxs-lookup"><span data-stu-id="26872-192">The ADO.NET code creates <xref:System.Data.SqlClient.SqlConnection> and <xref:System.Data.SqlClient.SqlCommand> objects to execute the GetDocumentSummary stored procedure and retrieve the document summary, which is stored as a large value type.</span></span> <span data-ttu-id="26872-193">El código pasa un valor para el parámetro de entrada @DocumentID y muestra los resultados que se han vuelto a pasar en el parámetro de salida @DocumentSummary de la ventana Consola.</span><span class="sxs-lookup"><span data-stu-id="26872-193">The code passes a value for the @DocumentID input parameter, and displays the results passed back in the @DocumentSummary output parameter in the Console window.</span></span>  
  
 [!code-csharp[DataWorks LargeValueType.Param#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks LargeValueType.Param/CS/source.cs#1)]
 [!code-vb[DataWorks LargeValueType.Param#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks LargeValueType.Param/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="26872-194">Consulte también</span><span class="sxs-lookup"><span data-stu-id="26872-194">See also</span></span>

- [<span data-ttu-id="26872-195">DATOS binarios y de gran valor de SQL Server</span><span class="sxs-lookup"><span data-stu-id="26872-195">SQL Server Binary and Large-Value Data</span></span>](sql-server-binary-and-large-value-data.md)
- [<span data-ttu-id="26872-196">Asignaciones de tipos de datos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="26872-196">SQL Server Data Type Mappings</span></span>](../sql-server-data-type-mappings.md)
- [<span data-ttu-id="26872-197">Operaciones de datos de SQL Server en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="26872-197">SQL Server Data Operations in ADO.NET</span></span>](sql-server-data-operations.md)
- [<span data-ttu-id="26872-198">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="26872-198">ADO.NET Overview</span></span>](../ado-net-overview.md)
