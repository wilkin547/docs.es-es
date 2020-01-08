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
# <a name="metadata"></a>Metadatos

Existen dos API para recuperar los metadatos en ADO.NET. Uno recupera los metadatos sobre los resultados de la consulta. El otro recupera metadatos sobre el esquema de la base de datos.

## <a name="query-result-metadata"></a>Metadatos de resultados de consulta

Puede recuperar metadatos sobre los resultados de una consulta mediante el método <xref:Microsoft.Data.Sqlite.SqliteDataReader.GetSchemaTable%2A> en `SqliteDataReader`. El <xref:System.Data.DataTable> devuelto contiene las columnas siguientes:

| Columna             | Tipo de    | Descripción                                                               |
| ------------------ | ------- | ------------------------------------------------------------------------- |
| `AllowDBNull`      | Booleano | True si la columna de origen puede ser NULL.                                    |
| `BaseCatalogName`  | Cadena  | Nombre de la base de datos de la columna de origen. Siempre es NULL para las expresiones.    |
| `BaseColumnName`   | Cadena  | Nombre sin alias de la columna de origen. Siempre es NULL para las expresiones.    |
| `BaseSchemaName`   | Cadena  | Siempre es NULL. SQLite no admite esquemas.                              |
| `BaseServerName`   | Cadena  | Ruta de acceso al archivo de base de datos especificado en la cadena de conexión.         |
| `BaseTableName`    | Cadena  | Nombre de la tabla de la columna de origen. Siempre es NULL para las expresiones.       |
| `ColumnName`       | Cadena  | Nombre o alias de la columna en el conjunto de resultados.                        |
| `ColumnOrdinal`    | Int32   | El ordinal de la columna en el conjunto de resultados.                              |
| `ColumnSize`       | Int32   | Siempre-1. Esto puede cambiar en versiones futuras de `Microsoft.Data.Sqlite`.   |
| `DataType`         | Tipo de    | El tipo de datos predeterminado de .NET de la columna.                                 |
| `DataTypeName`     | Cadena  | El tipo de datos SQLite de la columna.                                       |
| `IsAliased`        | Booleano | True si el nombre de columna tiene alias en el conjunto de resultados.                     |
| `IsAutoIncrement`  | Booleano | True si la columna de origen se creó con la palabra clave AutoIncrement.     |
| `IsExpression`     | Booleano | True si la columna se origina a partir de una expresión de la consulta.            |
| `IsKey`            | Booleano | True si la columna de origen forma parte de la clave principal.                     |
| `IsUnique`         | Booleano | True si la columna de origen es única.                                      |
| `NumericPrecision` | Int16   | Siempre es NULL. Esto puede cambiar en versiones futuras de `Microsoft.Data.Sqlite`. |
| `NumericScale`     | Int16   | Siempre es NULL. Esto puede cambiar en versiones futuras de `Microsoft.Data.Sqlite`. |

En el ejemplo siguiente se muestra cómo usar `GetSchemaTable` para crear una cadena de depuración que muestra los metadatos de un resultado:

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ResultMetadataSample/Program.cs?name=snippet_ResultMetadata)]

Por ejemplo, esta consulta produciría la siguiente cadena de depuración:

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

## <a name="schema-metadata"></a>Metadatos de esquema

Microsoft. Data. SQLite no implementa el método GetSchema en DbConnection. En su lugar, puede consultar directamente la información del esquema mediante las instrucciones [sqlite_master](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema) Table y pragma, como [table_info](https://www.sqlite.org/pragma.html#pragma_table_info) y [foreign_key_list](https://www.sqlite.org/pragma.html#pragma_foreign_key_list).

Por ejemplo, esta consulta recuperará los metadatos de todas las columnas de la base de datos.

```sql
SELECT t.name AS tbl_name, c.name, c.type, c.notnull, c.dflt_value, c.pk
FROM sqlite_master AS t,
     pragma_table_info(t.name) AS c
WHERE t.type = 'table';
```

## <a name="see-also"></a>Vea también

* [Almacenamiento del esquema de SQL Database](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema)
* [Instrucciones PRAGMA](https://www.sqlite.org/pragma.html)
* [Tipos de datos](types.md)
