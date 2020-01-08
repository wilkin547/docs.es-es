---
title: Metadatos
ms.date: 12/13/2019
description: Obtenga información sobre cómo recuperar metadatos sobre la base de datos.
ms.openlocfilehash: b2f2704a748627d9943943fa2fa7b1b7e9f3007f
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450433"
---
# <a name="metadata"></a><span data-ttu-id="f4f42-103">Metadatos</span><span class="sxs-lookup"><span data-stu-id="f4f42-103">Metadata</span></span>

<span data-ttu-id="f4f42-104">Existen dos API para recuperar los metadatos en ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="f4f42-104">There are two APIs for retrieving metadata in ADO.NET.</span></span> <span data-ttu-id="f4f42-105">Uno recupera los metadatos sobre los resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="f4f42-105">One retrieves metadata about query results.</span></span> <span data-ttu-id="f4f42-106">El otro recupera metadatos sobre el esquema de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="f4f42-106">The other retrieves metadata about the database schema.</span></span>

## <a name="query-result-metadata"></a><span data-ttu-id="f4f42-107">Metadatos de resultados de consulta</span><span class="sxs-lookup"><span data-stu-id="f4f42-107">Query result metadata</span></span>

<span data-ttu-id="f4f42-108">Puede recuperar metadatos sobre los resultados de una consulta mediante el método <xref:Microsoft.Data.Sqlite.SqliteDataReader.GetSchemaTable%2A> en `SqliteDataReader`.</span><span class="sxs-lookup"><span data-stu-id="f4f42-108">You can retrieve metadata about the results of a query using the <xref:Microsoft.Data.Sqlite.SqliteDataReader.GetSchemaTable%2A> method on `SqliteDataReader`.</span></span> <span data-ttu-id="f4f42-109">El <xref:System.Data.DataTable> devuelto contiene las columnas siguientes:</span><span class="sxs-lookup"><span data-stu-id="f4f42-109">The returned <xref:System.Data.DataTable> contains the following columns:</span></span>

| <span data-ttu-id="f4f42-110">Columna</span><span class="sxs-lookup"><span data-stu-id="f4f42-110">Column</span></span>             | <span data-ttu-id="f4f42-111">Tipo de</span><span class="sxs-lookup"><span data-stu-id="f4f42-111">Type</span></span>    | <span data-ttu-id="f4f42-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="f4f42-112">Description</span></span>                                                               |
| ------------------ | ------- | ------------------------------------------------------------------------- |
| `AllowDBNull`      | <span data-ttu-id="f4f42-113">Booleano</span><span class="sxs-lookup"><span data-stu-id="f4f42-113">Boolean</span></span> | <span data-ttu-id="f4f42-114">True si la columna de origen puede ser NULL.</span><span class="sxs-lookup"><span data-stu-id="f4f42-114">True if the origin column may be NULL.</span></span>                                    |
| `BaseCatalogName`  | <span data-ttu-id="f4f42-115">Cadena</span><span class="sxs-lookup"><span data-stu-id="f4f42-115">String</span></span>  | <span data-ttu-id="f4f42-116">Nombre de la base de datos de la columna de origen.</span><span class="sxs-lookup"><span data-stu-id="f4f42-116">The name of the origin column's database.</span></span> <span data-ttu-id="f4f42-117">Siempre es NULL para las expresiones.</span><span class="sxs-lookup"><span data-stu-id="f4f42-117">Always NULL for expressions.</span></span>    |
| `BaseColumnName`   | <span data-ttu-id="f4f42-118">Cadena</span><span class="sxs-lookup"><span data-stu-id="f4f42-118">String</span></span>  | <span data-ttu-id="f4f42-119">Nombre sin alias de la columna de origen.</span><span class="sxs-lookup"><span data-stu-id="f4f42-119">The unaliased name of the origin column.</span></span> <span data-ttu-id="f4f42-120">Siempre es NULL para las expresiones.</span><span class="sxs-lookup"><span data-stu-id="f4f42-120">Always NULL for expressions.</span></span>    |
| `BaseSchemaName`   | <span data-ttu-id="f4f42-121">Cadena</span><span class="sxs-lookup"><span data-stu-id="f4f42-121">String</span></span>  | <span data-ttu-id="f4f42-122">Siempre es NULL.</span><span class="sxs-lookup"><span data-stu-id="f4f42-122">Always NULL.</span></span> <span data-ttu-id="f4f42-123">SQLite no admite esquemas.</span><span class="sxs-lookup"><span data-stu-id="f4f42-123">SQLite doesn't support schemas.</span></span>                              |
| `BaseServerName`   | <span data-ttu-id="f4f42-124">Cadena</span><span class="sxs-lookup"><span data-stu-id="f4f42-124">String</span></span>  | <span data-ttu-id="f4f42-125">Ruta de acceso al archivo de base de datos especificado en la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="f4f42-125">The path to the database file specified in the connection string.</span></span>         |
| `BaseTableName`    | <span data-ttu-id="f4f42-126">Cadena</span><span class="sxs-lookup"><span data-stu-id="f4f42-126">String</span></span>  | <span data-ttu-id="f4f42-127">Nombre de la tabla de la columna de origen.</span><span class="sxs-lookup"><span data-stu-id="f4f42-127">The name of the origin column's table.</span></span> <span data-ttu-id="f4f42-128">Siempre es NULL para las expresiones.</span><span class="sxs-lookup"><span data-stu-id="f4f42-128">Always NULL for expressions.</span></span>       |
| `ColumnName`       | <span data-ttu-id="f4f42-129">Cadena</span><span class="sxs-lookup"><span data-stu-id="f4f42-129">String</span></span>  | <span data-ttu-id="f4f42-130">Nombre o alias de la columna en el conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="f4f42-130">The name or alias of the column in the result set.</span></span>                        |
| `ColumnOrdinal`    | <span data-ttu-id="f4f42-131">Int32</span><span class="sxs-lookup"><span data-stu-id="f4f42-131">Int32</span></span>   | <span data-ttu-id="f4f42-132">El ordinal de la columna en el conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="f4f42-132">The ordinal of the column in the result set.</span></span>                              |
| `ColumnSize`       | <span data-ttu-id="f4f42-133">Int32</span><span class="sxs-lookup"><span data-stu-id="f4f42-133">Int32</span></span>   | <span data-ttu-id="f4f42-134">Siempre-1.</span><span class="sxs-lookup"><span data-stu-id="f4f42-134">Always -1.</span></span> <span data-ttu-id="f4f42-135">Esto puede cambiar en versiones futuras de `Microsoft.Data.Sqlite`.</span><span class="sxs-lookup"><span data-stu-id="f4f42-135">This may change in future versions of `Microsoft.Data.Sqlite`.</span></span>   |
| `DataType`         | <span data-ttu-id="f4f42-136">Tipo de</span><span class="sxs-lookup"><span data-stu-id="f4f42-136">Type</span></span>    | <span data-ttu-id="f4f42-137">El tipo de datos predeterminado de .NET de la columna.</span><span class="sxs-lookup"><span data-stu-id="f4f42-137">The default .NET data type of the column.</span></span>                                 |
| `DataTypeName`     | <span data-ttu-id="f4f42-138">Cadena</span><span class="sxs-lookup"><span data-stu-id="f4f42-138">String</span></span>  | <span data-ttu-id="f4f42-139">El tipo de datos SQLite de la columna.</span><span class="sxs-lookup"><span data-stu-id="f4f42-139">The SQLite data type of the column.</span></span>                                       |
| `IsAliased`        | <span data-ttu-id="f4f42-140">Booleano</span><span class="sxs-lookup"><span data-stu-id="f4f42-140">Boolean</span></span> | <span data-ttu-id="f4f42-141">True si el nombre de columna tiene alias en el conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="f4f42-141">True if the column name is aliased in the result set.</span></span>                     |
| `IsAutoIncrement`  | <span data-ttu-id="f4f42-142">Booleano</span><span class="sxs-lookup"><span data-stu-id="f4f42-142">Boolean</span></span> | <span data-ttu-id="f4f42-143">True si la columna de origen se creó con la palabra clave AutoIncrement.</span><span class="sxs-lookup"><span data-stu-id="f4f42-143">True if the origin column was created with the AUTOINCREMENT keyword.</span></span>     |
| `IsExpression`     | <span data-ttu-id="f4f42-144">Booleano</span><span class="sxs-lookup"><span data-stu-id="f4f42-144">Boolean</span></span> | <span data-ttu-id="f4f42-145">True si la columna se origina a partir de una expresión de la consulta.</span><span class="sxs-lookup"><span data-stu-id="f4f42-145">True if the column originates from an expression in the query.</span></span>            |
| `IsKey`            | <span data-ttu-id="f4f42-146">Booleano</span><span class="sxs-lookup"><span data-stu-id="f4f42-146">Boolean</span></span> | <span data-ttu-id="f4f42-147">True si la columna de origen forma parte de la clave principal.</span><span class="sxs-lookup"><span data-stu-id="f4f42-147">True if the origin column is part of the PRIMARY KEY.</span></span>                     |
| `IsUnique`         | <span data-ttu-id="f4f42-148">Booleano</span><span class="sxs-lookup"><span data-stu-id="f4f42-148">Boolean</span></span> | <span data-ttu-id="f4f42-149">True si la columna de origen es única.</span><span class="sxs-lookup"><span data-stu-id="f4f42-149">True if the origin column is UNIQUE.</span></span>                                      |
| `NumericPrecision` | <span data-ttu-id="f4f42-150">Int16</span><span class="sxs-lookup"><span data-stu-id="f4f42-150">Int16</span></span>   | <span data-ttu-id="f4f42-151">Siempre es NULL.</span><span class="sxs-lookup"><span data-stu-id="f4f42-151">Always NULL.</span></span> <span data-ttu-id="f4f42-152">Esto puede cambiar en versiones futuras de `Microsoft.Data.Sqlite`.</span><span class="sxs-lookup"><span data-stu-id="f4f42-152">This may change in future versions of `Microsoft.Data.Sqlite`.</span></span> |
| `NumericScale`     | <span data-ttu-id="f4f42-153">Int16</span><span class="sxs-lookup"><span data-stu-id="f4f42-153">Int16</span></span>   | <span data-ttu-id="f4f42-154">Siempre es NULL.</span><span class="sxs-lookup"><span data-stu-id="f4f42-154">Always NULL.</span></span> <span data-ttu-id="f4f42-155">Esto puede cambiar en versiones futuras de `Microsoft.Data.Sqlite`.</span><span class="sxs-lookup"><span data-stu-id="f4f42-155">This may change in future versions of `Microsoft.Data.Sqlite`.</span></span> |

<span data-ttu-id="f4f42-156">En el ejemplo siguiente se muestra cómo usar `GetSchemaTable` para crear una cadena de depuración que muestra los metadatos de un resultado:</span><span class="sxs-lookup"><span data-stu-id="f4f42-156">The following example shows how to use `GetSchemaTable` to create a debug string that shows metadata about a result:</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ResultMetadataSample/Program.cs?name=snippet_ResultMetadata)]

<span data-ttu-id="f4f42-157">Por ejemplo, esta consulta produciría la siguiente cadena de depuración:</span><span class="sxs-lookup"><span data-stu-id="f4f42-157">For example, this query would produce the following debug string:</span></span>

```sql
SELECT id AS post_id,
       title,
       body,
       random() AS random
FROM post
```

```output
post.id AS post_id INTEGER PRIMARY KEY AUTOINCREMENT
post.title TEXT NOT NULL UNIQUE
post.body TEXT
(expression) AS random BLOB
```

## <a name="schema-metadata"></a><span data-ttu-id="f4f42-158">Metadatos de esquema</span><span class="sxs-lookup"><span data-stu-id="f4f42-158">Schema metadata</span></span>

<span data-ttu-id="f4f42-159">Microsoft. Data. SQLite no implementa el método GetSchema en DbConnection.</span><span class="sxs-lookup"><span data-stu-id="f4f42-159">Microsoft.Data.Sqlite doesn't implement the GetSchema method on DbConnection.</span></span> <span data-ttu-id="f4f42-160">En su lugar, puede consultar directamente la información del esquema mediante las instrucciones [sqlite_master](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema) Table y pragma, como [table_info](https://www.sqlite.org/pragma.html#pragma_table_info) y [foreign_key_list](https://www.sqlite.org/pragma.html#pragma_foreign_key_list).</span><span class="sxs-lookup"><span data-stu-id="f4f42-160">Instead, you can query directly for schema information using the [sqlite_master](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema) table and PRAGMA statements like [table_info](https://www.sqlite.org/pragma.html#pragma_table_info) and [foreign_key_list](https://www.sqlite.org/pragma.html#pragma_foreign_key_list).</span></span>

<span data-ttu-id="f4f42-161">Por ejemplo, esta consulta recuperará los metadatos de todas las columnas de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="f4f42-161">For example, this query will retrieve metadata about all the columns in the database.</span></span>

```sql
SELECT t.name AS tbl_name, c.name, c.type, c.notnull, c.dflt_value, c.pk
FROM sqlite_master AS t,
     pragma_table_info(t.name) AS c
WHERE t.type = 'table';
```

## <a name="see-also"></a><span data-ttu-id="f4f42-162">Vea también</span><span class="sxs-lookup"><span data-stu-id="f4f42-162">See also</span></span>

* [<span data-ttu-id="f4f42-163">Almacenamiento del esquema de SQL Database</span><span class="sxs-lookup"><span data-stu-id="f4f42-163">Storage of the SQL Database Schema</span></span>](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema)
* [<span data-ttu-id="f4f42-164">Instrucciones PRAGMA</span><span class="sxs-lookup"><span data-stu-id="f4f42-164">PRAGMA Statements</span></span>](https://www.sqlite.org/pragma.html)
* [<span data-ttu-id="f4f42-165">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="f4f42-165">Data types</span></span>](types.md)
