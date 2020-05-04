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
# <a name="metadata"></a>Metadatos

Existen dos API para recuperar metadatos en ADO.NET. Una recupera los metadatos sobre los resultados de consulta y la otra sobre el esquema de la base de datos.

## <a name="query-result-metadata"></a>Metadatos de resultados de consulta

Para recuperar metadatos sobre los resultados de una consulta, se usa el método <xref:Microsoft.Data.Sqlite.SqliteDataReader.GetSchemaTable%2A> en `SqliteDataReader`. El elemento <xref:System.Data.DataTable> devuelto contiene las siguientes columnas:

| Columna             | Tipo    | Descripción                                                               |
| ------------------ | ------- | ------------------------------------------------------------------------- |
| `AllowDBNull`      | Booleano | True si la columna de origen puede ser NULL.                                    |
| `BaseCatalogName`  | String  | Nombre de la base de datos de la columna de origen. Siempre es NULL en las expresiones.    |
| `BaseColumnName`   | String  | Nombre sin alias de la columna de origen. Siempre es NULL en las expresiones.    |
| `BaseSchemaName`   | String  | Siempre es NULL. SQLite no admite esquemas.                              |
| `BaseServerName`   | String  | Ruta de acceso al archivo de base de datos especificado en la cadena de conexión.         |
| `BaseTableName`    | String  | Nombre de la tabla de la columna de origen. Siempre es NULL en las expresiones.       |
| `ColumnName`       | String  | Nombre o alias de la columna en el conjunto de resultados.                        |
| `ColumnOrdinal`    | Int32   | Número ordinal de la columna en el conjunto de resultados.                              |
| `ColumnSize`       | Int32   | Siempre es -1. Esto puede cambiar en versiones futuras de `Microsoft.Data.Sqlite`.   |
| `DataType`         | Tipo    | Tipo de datos predeterminado de .NET de la columna.                                 |
| `DataTypeName`     | String  | Tipo de datos de SQLite de la columna.                                       |
| `IsAliased`        | Booleano | True si el nombre de columna tiene alias en el conjunto de resultados.                     |
| `IsAutoIncrement`  | Booleano | True si la columna de origen se creó con la palabra clave AUTOINCREMENT.     |
| `IsExpression`     | Booleano | True si la columna se origina a partir de una expresión de la consulta.            |
| `IsKey`            | Booleano | True si la columna de origen forma parte de PRIMARY KEY.                     |
| `IsUnique`         | Booleano | True si la columna de origen es UNIQUE.                                      |
| `NumericPrecision` | Int16   | Siempre es NULL. Esto puede cambiar en versiones futuras de `Microsoft.Data.Sqlite`. |
| `NumericScale`     | Int16   | Siempre es NULL. Esto puede cambiar en versiones futuras de `Microsoft.Data.Sqlite`. |

En el siguiente ejemplo se muestra cómo usar `GetSchemaTable` para crear una cadena de depuración que muestre los metadatos de un resultado:

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

Microsoft.Data.Sqlite no implementa el método GetSchema en DbConnection. En su lugar, la información de esquema se puede consultar directamente usando la tabla [sqlite_master](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema), así como instrucciones PRAGMA como [table_info](https://www.sqlite.org/pragma.html#pragma_table_info) y [foreign_key_list](https://www.sqlite.org/pragma.html#pragma_foreign_key_list).

Con esta consulta, por ejemplo, se recuperarán los metadatos de todas las columnas de la base de datos.

```sql
SELECT t.name AS tbl_name, c.name, c.type, c.notnull, c.dflt_value, c.pk
FROM sqlite_master AS t,
     pragma_table_info(t.name) AS c
WHERE t.type = 'table';
```

## <a name="see-also"></a>Vea también

* [Almacenamiento del esquema de base de datos SQL](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema)
* [Instrucciones PRAGMA](https://www.sqlite.org/pragma.html)
* [Tipos de datos](types.md)
