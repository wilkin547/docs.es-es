---
title: Metadatos
ms.date: 12/13/2019
description: Obtenga información sobre cómo recuperar metadatos relativos a la base de datos.
ms.openlocfilehash: b2f2704a748627d9943943fa2fa7b1b7e9f3007f
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450433"
---
# <a name="metadata"></a><span data-ttu-id="e20a1-103">Metadatos</span><span class="sxs-lookup"><span data-stu-id="e20a1-103">Metadata</span></span>

<span data-ttu-id="e20a1-104">Existen dos API para recuperar metadatos en ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="e20a1-104">There are two APIs for retrieving metadata in ADO.NET.</span></span> <span data-ttu-id="e20a1-105">Una recupera los metadatos sobre los resultados de consulta</span><span class="sxs-lookup"><span data-stu-id="e20a1-105">One retrieves metadata about query results.</span></span> <span data-ttu-id="e20a1-106">y la otra sobre el esquema de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="e20a1-106">The other retrieves metadata about the database schema.</span></span>

## <a name="query-result-metadata"></a><span data-ttu-id="e20a1-107">Metadatos de resultados de consulta</span><span class="sxs-lookup"><span data-stu-id="e20a1-107">Query result metadata</span></span>

<span data-ttu-id="e20a1-108">Para recuperar metadatos sobre los resultados de una consulta, se usa el método <xref:Microsoft.Data.Sqlite.SqliteDataReader.GetSchemaTable%2A> en `SqliteDataReader`.</span><span class="sxs-lookup"><span data-stu-id="e20a1-108">You can retrieve metadata about the results of a query using the <xref:Microsoft.Data.Sqlite.SqliteDataReader.GetSchemaTable%2A> method on `SqliteDataReader`.</span></span> <span data-ttu-id="e20a1-109">El elemento <xref:System.Data.DataTable> devuelto contiene las siguientes columnas:</span><span class="sxs-lookup"><span data-stu-id="e20a1-109">The returned <xref:System.Data.DataTable> contains the following columns:</span></span>

| <span data-ttu-id="e20a1-110">Columna</span><span class="sxs-lookup"><span data-stu-id="e20a1-110">Column</span></span>             | <span data-ttu-id="e20a1-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="e20a1-111">Type</span></span>    | <span data-ttu-id="e20a1-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="e20a1-112">Description</span></span>                                                               |
| ------------------ | ------- | ------------------------------------------------------------------------- |
| `AllowDBNull`      | <span data-ttu-id="e20a1-113">Booleano</span><span class="sxs-lookup"><span data-stu-id="e20a1-113">Boolean</span></span> | <span data-ttu-id="e20a1-114">True si la columna de origen puede ser NULL.</span><span class="sxs-lookup"><span data-stu-id="e20a1-114">True if the origin column may be NULL.</span></span>                                    |
| `BaseCatalogName`  | <span data-ttu-id="e20a1-115">String</span><span class="sxs-lookup"><span data-stu-id="e20a1-115">String</span></span>  | <span data-ttu-id="e20a1-116">Nombre de la base de datos de la columna de origen.</span><span class="sxs-lookup"><span data-stu-id="e20a1-116">The name of the origin column's database.</span></span> <span data-ttu-id="e20a1-117">Siempre es NULL en las expresiones.</span><span class="sxs-lookup"><span data-stu-id="e20a1-117">Always NULL for expressions.</span></span>    |
| `BaseColumnName`   | <span data-ttu-id="e20a1-118">String</span><span class="sxs-lookup"><span data-stu-id="e20a1-118">String</span></span>  | <span data-ttu-id="e20a1-119">Nombre sin alias de la columna de origen.</span><span class="sxs-lookup"><span data-stu-id="e20a1-119">The unaliased name of the origin column.</span></span> <span data-ttu-id="e20a1-120">Siempre es NULL en las expresiones.</span><span class="sxs-lookup"><span data-stu-id="e20a1-120">Always NULL for expressions.</span></span>    |
| `BaseSchemaName`   | <span data-ttu-id="e20a1-121">String</span><span class="sxs-lookup"><span data-stu-id="e20a1-121">String</span></span>  | <span data-ttu-id="e20a1-122">Siempre es NULL.</span><span class="sxs-lookup"><span data-stu-id="e20a1-122">Always NULL.</span></span> <span data-ttu-id="e20a1-123">SQLite no admite esquemas.</span><span class="sxs-lookup"><span data-stu-id="e20a1-123">SQLite doesn't support schemas.</span></span>                              |
| `BaseServerName`   | <span data-ttu-id="e20a1-124">String</span><span class="sxs-lookup"><span data-stu-id="e20a1-124">String</span></span>  | <span data-ttu-id="e20a1-125">Ruta de acceso al archivo de base de datos especificado en la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="e20a1-125">The path to the database file specified in the connection string.</span></span>         |
| `BaseTableName`    | <span data-ttu-id="e20a1-126">String</span><span class="sxs-lookup"><span data-stu-id="e20a1-126">String</span></span>  | <span data-ttu-id="e20a1-127">Nombre de la tabla de la columna de origen.</span><span class="sxs-lookup"><span data-stu-id="e20a1-127">The name of the origin column's table.</span></span> <span data-ttu-id="e20a1-128">Siempre es NULL en las expresiones.</span><span class="sxs-lookup"><span data-stu-id="e20a1-128">Always NULL for expressions.</span></span>       |
| `ColumnName`       | <span data-ttu-id="e20a1-129">String</span><span class="sxs-lookup"><span data-stu-id="e20a1-129">String</span></span>  | <span data-ttu-id="e20a1-130">Nombre o alias de la columna en el conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="e20a1-130">The name or alias of the column in the result set.</span></span>                        |
| `ColumnOrdinal`    | <span data-ttu-id="e20a1-131">Int32</span><span class="sxs-lookup"><span data-stu-id="e20a1-131">Int32</span></span>   | <span data-ttu-id="e20a1-132">Número ordinal de la columna en el conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="e20a1-132">The ordinal of the column in the result set.</span></span>                              |
| `ColumnSize`       | <span data-ttu-id="e20a1-133">Int32</span><span class="sxs-lookup"><span data-stu-id="e20a1-133">Int32</span></span>   | <span data-ttu-id="e20a1-134">Siempre es -1.</span><span class="sxs-lookup"><span data-stu-id="e20a1-134">Always -1.</span></span> <span data-ttu-id="e20a1-135">Esto puede cambiar en versiones futuras de `Microsoft.Data.Sqlite`.</span><span class="sxs-lookup"><span data-stu-id="e20a1-135">This may change in future versions of `Microsoft.Data.Sqlite`.</span></span>   |
| `DataType`         | <span data-ttu-id="e20a1-136">Tipo</span><span class="sxs-lookup"><span data-stu-id="e20a1-136">Type</span></span>    | <span data-ttu-id="e20a1-137">Tipo de datos predeterminado de .NET de la columna.</span><span class="sxs-lookup"><span data-stu-id="e20a1-137">The default .NET data type of the column.</span></span>                                 |
| `DataTypeName`     | <span data-ttu-id="e20a1-138">String</span><span class="sxs-lookup"><span data-stu-id="e20a1-138">String</span></span>  | <span data-ttu-id="e20a1-139">Tipo de datos de SQLite de la columna.</span><span class="sxs-lookup"><span data-stu-id="e20a1-139">The SQLite data type of the column.</span></span>                                       |
| `IsAliased`        | <span data-ttu-id="e20a1-140">Booleano</span><span class="sxs-lookup"><span data-stu-id="e20a1-140">Boolean</span></span> | <span data-ttu-id="e20a1-141">True si el nombre de columna tiene alias en el conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="e20a1-141">True if the column name is aliased in the result set.</span></span>                     |
| `IsAutoIncrement`  | <span data-ttu-id="e20a1-142">Booleano</span><span class="sxs-lookup"><span data-stu-id="e20a1-142">Boolean</span></span> | <span data-ttu-id="e20a1-143">True si la columna de origen se creó con la palabra clave AUTOINCREMENT.</span><span class="sxs-lookup"><span data-stu-id="e20a1-143">True if the origin column was created with the AUTOINCREMENT keyword.</span></span>     |
| `IsExpression`     | <span data-ttu-id="e20a1-144">Booleano</span><span class="sxs-lookup"><span data-stu-id="e20a1-144">Boolean</span></span> | <span data-ttu-id="e20a1-145">True si la columna se origina a partir de una expresión de la consulta.</span><span class="sxs-lookup"><span data-stu-id="e20a1-145">True if the column originates from an expression in the query.</span></span>            |
| `IsKey`            | <span data-ttu-id="e20a1-146">Booleano</span><span class="sxs-lookup"><span data-stu-id="e20a1-146">Boolean</span></span> | <span data-ttu-id="e20a1-147">True si la columna de origen forma parte de PRIMARY KEY.</span><span class="sxs-lookup"><span data-stu-id="e20a1-147">True if the origin column is part of the PRIMARY KEY.</span></span>                     |
| `IsUnique`         | <span data-ttu-id="e20a1-148">Booleano</span><span class="sxs-lookup"><span data-stu-id="e20a1-148">Boolean</span></span> | <span data-ttu-id="e20a1-149">True si la columna de origen es UNIQUE.</span><span class="sxs-lookup"><span data-stu-id="e20a1-149">True if the origin column is UNIQUE.</span></span>                                      |
| `NumericPrecision` | <span data-ttu-id="e20a1-150">Int16</span><span class="sxs-lookup"><span data-stu-id="e20a1-150">Int16</span></span>   | <span data-ttu-id="e20a1-151">Siempre es NULL.</span><span class="sxs-lookup"><span data-stu-id="e20a1-151">Always NULL.</span></span> <span data-ttu-id="e20a1-152">Esto puede cambiar en versiones futuras de `Microsoft.Data.Sqlite`.</span><span class="sxs-lookup"><span data-stu-id="e20a1-152">This may change in future versions of `Microsoft.Data.Sqlite`.</span></span> |
| `NumericScale`     | <span data-ttu-id="e20a1-153">Int16</span><span class="sxs-lookup"><span data-stu-id="e20a1-153">Int16</span></span>   | <span data-ttu-id="e20a1-154">Siempre es NULL.</span><span class="sxs-lookup"><span data-stu-id="e20a1-154">Always NULL.</span></span> <span data-ttu-id="e20a1-155">Esto puede cambiar en versiones futuras de `Microsoft.Data.Sqlite`.</span><span class="sxs-lookup"><span data-stu-id="e20a1-155">This may change in future versions of `Microsoft.Data.Sqlite`.</span></span> |

<span data-ttu-id="e20a1-156">En el siguiente ejemplo se muestra cómo usar `GetSchemaTable` para crear una cadena de depuración que muestre los metadatos de un resultado:</span><span class="sxs-lookup"><span data-stu-id="e20a1-156">The following example shows how to use `GetSchemaTable` to create a debug string that shows metadata about a result:</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ResultMetadataSample/Program.cs?name=snippet_ResultMetadata)]

<span data-ttu-id="e20a1-157">Por ejemplo, esta consulta produciría la siguiente cadena de depuración:</span><span class="sxs-lookup"><span data-stu-id="e20a1-157">For example, this query would produce the following debug string:</span></span>

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

## <a name="schema-metadata"></a><span data-ttu-id="e20a1-158">Metadatos de esquema</span><span class="sxs-lookup"><span data-stu-id="e20a1-158">Schema metadata</span></span>

<span data-ttu-id="e20a1-159">Microsoft.Data.Sqlite no implementa el método GetSchema en DbConnection.</span><span class="sxs-lookup"><span data-stu-id="e20a1-159">Microsoft.Data.Sqlite doesn't implement the GetSchema method on DbConnection.</span></span> <span data-ttu-id="e20a1-160">En su lugar, la información de esquema se puede consultar directamente usando la tabla [sqlite_master](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema), así como instrucciones PRAGMA como [table_info](https://www.sqlite.org/pragma.html#pragma_table_info) y [foreign_key_list](https://www.sqlite.org/pragma.html#pragma_foreign_key_list).</span><span class="sxs-lookup"><span data-stu-id="e20a1-160">Instead, you can query directly for schema information using the [sqlite_master](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema) table and PRAGMA statements like [table_info](https://www.sqlite.org/pragma.html#pragma_table_info) and [foreign_key_list](https://www.sqlite.org/pragma.html#pragma_foreign_key_list).</span></span>

<span data-ttu-id="e20a1-161">Con esta consulta, por ejemplo, se recuperarán los metadatos de todas las columnas de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="e20a1-161">For example, this query will retrieve metadata about all the columns in the database.</span></span>

```sql
SELECT t.name AS tbl_name, c.name, c.type, c.notnull, c.dflt_value, c.pk
FROM sqlite_master AS t,
     pragma_table_info(t.name) AS c
WHERE t.type = 'table';
```

## <a name="see-also"></a><span data-ttu-id="e20a1-162">Vea también</span><span class="sxs-lookup"><span data-stu-id="e20a1-162">See also</span></span>

* [<span data-ttu-id="e20a1-163">Almacenamiento del esquema de base de datos SQL</span><span class="sxs-lookup"><span data-stu-id="e20a1-163">Storage of the SQL Database Schema</span></span>](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema)
* [<span data-ttu-id="e20a1-164">Instrucciones PRAGMA</span><span class="sxs-lookup"><span data-stu-id="e20a1-164">PRAGMA Statements</span></span>](https://www.sqlite.org/pragma.html)
* [<span data-ttu-id="e20a1-165">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="e20a1-165">Data types</span></span>](types.md)
