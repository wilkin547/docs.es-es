---
description: 'Más información acerca de: colecciones de esquemas de ODBC'
title: Colecciones de esquemas de ODBC
ms.date: 03/30/2017
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
ms.openlocfilehash: ceac67e49914db7010e315a2dfcdb630bea1e29f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786204"
---
# <a name="odbc-schema-collections"></a>Colecciones de esquemas de ODBC

En esta sección se describe la compatibilidad de las colecciones de esquemas con los controladores ODBC de Microsoft SQL Server, Oracle y Microsoft Jet.

## <a name="microsoft-sql-server-odbc-driver"></a>Controlador ODBC para Microsoft SQL Server

El controlador ODBC de Microsoft SQL Server admite, además de las colecciones de esquemas comunes, las siguientes colecciones de esquemas específicas:

- Tablas

- Índices

- Columnas

- Procedimientos

- ProcedureColumns

- ProcedureParameters

- Vistas

### <a name="tables-and-views"></a>Tablas y vistas

|ColumnName|DataType|
|----------------|--------------|
|TABLE_CAT|String|
|TABLE_SCHEM|String|
|TABLE_NAME|String|
|TABLE_TYPE|String|
|COMENTARIOS|String|

### <a name="indexes"></a>Índices

|ColumnName|DataType|
|----------------|--------------|
|TABLE_CAT|String|
|TABLE_SCHEM|String|
|TABLE_NAME|String|
|NON_UNIQUE|Int16|
|INDEX_QUALIFIER|String|
|INDEX_NAME|String|
|TYPE|Int16|
|ORDINAL_POSITION|Int16|
|COLUMN_NAME|String|
|ASC_OR_DESC|String|
|CARDINALITY|Int32|
|PAGES|Int32|
|FILTER_CONDITION|String|
|SS_TYPE_SCHEMA|String|
|SS_DATA_TYPE|Byte|

### <a name="columns"></a>Columnas

|ColumnName|DataType|
|----------------|--------------|
|TABLE_CAT|String|
|TABLE_SCHEM|String|
|TABLE_NAME|String|
|COLUMN_NAME|String|
|DATA_TYPE|Int16|
|TYPE_NAME|String|
|COLUMN_SIZE|Int32|
|BUFFER_LENGTH|Int32|
|DECIMAL_DIGITS|Int16|
|NUM_PREC_RADIX|Int16|
|NULLABLE|Int16|
|COMENTARIOS|String|
|COLUMN_DEF|String|
|SQL_DATA_TYPE|Int16|
|SQL_DATETIME_SUB|Int16|
|CHAR_OCTET_LENGTH|Int32|
|ORDINAL_POSITION|Int32|
|IS_NULLABLE|String|
|SS_TYPE_CATALOG|String|
|SS_TYPE_SCHEMA|String|
|SS_DATA_TYPE|Byte|

### <a name="procedures"></a>Procedimientos

|ColumnName|DataType|
|----------------|--------------|
|PROCEDURE_CAT|String|
|PROCEDURE_SCHEM|String|
|PROCEDURE_NAME|String|
|NUM_INPUT_PARAMS|Int32|
|NUM_OUTPUT_PARAMS|Int32|
|NUM_RESULT_SETS|Int32|
|COMENTARIOS|String|
|PROCEDURE_TYPE|Int16|

### <a name="procedurecolumns"></a>ProcedureColumns

|ColumnName|DataType|
|----------------|--------------|
|PROCEDURE_CAT|String|
|PROCEDURE_SCHEM|String|
|PROCEDURE_NAME|String|
|COLUMN_NAME|String|
|COLUMN_TYPE|Int16|
|DATA_TYPE|Int16|
|TYPE_NAME|String|
|COLUMN_SIZE|Int32|
|BUFFER_LENGTH|Int32|
|DECIMAL_DIGITS|Int16|
|NUM_PREC_RADIX|Int16|
|NULLABLE|Int16|
|COMENTARIOS|String|
|COLUMN_DEF|String|
|SQL_DATA_TYPE|Int16|
|SQL_DATETIME_SUB|Int16|
|CHAR_OCTET_LENGTH|Int32|
|ORDINAL_POSITION|Int32|
|IS_NULLABLE|String|
|SS_TYPE_CATALOG|String|
|SS_TYPE_SCHEMA|String|
|SS_DATA_TYPE|Byte|

### <a name="procedureparameters"></a>ProcedureParameters

|ColumnName|DataType|
|----------------|--------------|
|PROCEDURE_CAT|String|
|PROCEDURE_SCHEM|String|
|PROCEDURE_NAME|String|
|COLUMN_NAME|String|
|COLUMN_TYPE|Int16|
|DATA_TYPE|Int16|
|TYPE_NAME|String|
|COLUMN_SIZE|Int32|
|BUFFER_LENGTH|Int32|
|DECIMAL_DIGITS|Int16|
|NUM_PREC_RADIX|Int16|
|NULLABLE|Int16|
|COMENTARIOS|String|
|COLUMN_DEF|String|
|SQL_DATA_TYPE|Int16|
|SQL_DATETIME_SUB|Int16|
|CHAR_OCTET_LENGTH|Int32|
|ORDINAL_POSITION|Int32|
|IS_NULLABLE|String|
|SS_TYPE_CATALOG|String|
|SS_TYPE_SCHEMA|String|
|SS_DATA_TYPE|Byte|

## <a name="microsoft-oracle-odbc-driver"></a>Controlador ODBC para Oracle de Microsoft

El controlador ODBC para Oracle de Microsoft SQL Server admite, además de las colecciones de esquemas comunes, las siguientes colecciones de esquemas específicas:

- Tablas

- Columnas

- Procedimientos

- ProcedureColumns

- ProcedureParameters

- Vistas

- Índices

### <a name="tables-and-views"></a>Tablas y vistas

|ColumnName|DataType|
|----------------|--------------|
|TABLE_QUALIFIER|String|
|TABLE_OWNER|String|
|TABLE_NAME|String|
|TABLE_TYPE|String|
|COMENTARIOS|String|

### <a name="columns"></a>Columnas

|ColumnName|DataType|
|----------------|--------------|
|TABLE_QUALIFIER|String|
|TABLE_OWNER|String|
|TABLE_NAME|String|
|COLUMN_NAME|String|
|DATA_TYPE|Int16|
|TYPE_NAME|String|
|PRECISION|Int32|
|LENGTH|Int32|
|SCALE|Int16|
|RADIX|Int16|
|NULLABLE|Int16|
|COMENTARIOS|String|
|ORDINAL_POSITION|Int32|

### <a name="procedures"></a>Procedimientos

|ColumnName|DataType|
|----------------|--------------|
|PROCEDURE_QUALIFIER|String|
|PROCEDURE_OWNER|String|
|PROCEDURE_NAME|String|
|NUM_INPUT_PARAMS|Int16|
|NUM_OUTPUT_PARAMS|Int16|
|NUM_RESULT_SETS|Int16|
|COMENTARIOS|String|
|PROCEDURE_TYPE|Int16|

### <a name="procedurecolumns"></a>ProcedureColumns

|ColumnName|DataType|
|----------------|--------------|
|PROCEDURE_QUALIFIER|String|
|PROCEDURE_OWNER|String|
|PROCEDURE_NAME|String|
|COLUMN_NAME|String|
|COLUMN_TYPE|Int16|
|DATA_TYPE|Int16|
|TYPE_NAME|String|
|PRECISION|Int32|
|LENGTH|Int32|
|SCALE|Int16|
|RADIX|Int16|
|NULLABLE|Int16|
|COMENTARIOS|String|
|OVERLOAD|Int32|
|ORDINAL_POSITION|Int32|

## <a name="microsoft-jet-odbc-driver"></a>Controlador ODBC de Microsoft para Jet

El controlador ODBC de Microsoft para Jet admite, además de las colecciones de esquemas comunes, las siguientes colecciones de esquemas específicas:

- Tablas

- Índices

- Columnas

- Procedimientos

- ProcedureColumns

- ProcedureParameters

- Vistas

### <a name="tables-and-views"></a>Tablas y vistas

|ColumnName|DataType|
|----------------|--------------|
|TABLE_QUALIFIER|String|
|TABLE_OWNER|String|
|TABLE_NAME|String|
|TABLE_TYPE|String|
|COMENTARIOS|String|

### <a name="columns"></a>Columnas

|ColumnName|DataType|
|----------------|--------------|
|TABLE_QUALIFIER|String|
|TABLE_OWNER|String|
|TABLE_NAME|String|
|COLUMN_NAME|String|
|DATA_TYPE|Int16|
|TYPE_NAME|String|
|PRECISION|Int32|
|LENGTH|Int32|
|SCALE|Int16|
|RADIX|Int16|
|NULLABLE|Int16|
|COMENTARIOS|String|
|ORDINAL_POSITION|Int32|

### <a name="procedures"></a>Procedimientos

|ColumnName|DataType|
|----------------|--------------|
|PROCEDURE_QUALIFIER|String|
|PROCEDURE_OWNER|String|
|PROCEDURE_NAME|String|
|NUM_INPUT_PARAMS|Int16|
|NUM_OUTPUT_PARAMS|Int16|
|NUM_RESULT_SETS|Int16|
|COMENTARIOS|String|
|PROCEDURE_TYPE|Int16|

### <a name="procedurecolumns"></a>ProcedureColumns

|ColumnName|DataType|
|----------------|--------------|
|PROCEDURE_QUALIFIER|String|
|PROCEDURE_OWNER|String|
|PROCEDURE_NAME|String|
|COLUMN_NAME|String|
|COLUMN_TYPE|Int16|
|DATA_TYPE|Int16|
|TYPE_NAME|String|
|PRECISION|Int32|
|LENGTH|Int32|
|SCALE|Int16|
|RADIX|Int16|
|NULLABLE|Int16|
|COMENTARIOS|String|
|OVERLOAD|Int32|
|ORDINAL_POSITION|Int32|

### <a name="procedureparameters"></a>ProcedureParameters

|ColumnName|DataType|
|----------------|--------------|
|PROCEDURE_CAT|String|
|PROCEDURE_SCHEM|String|
|PROCEDURE_NAME|String|
|COLUMN_NAME|String|
|COLUMN_TYPE|Int16|
|DATA_TYPE|Int16|
|TYPE_NAME|String|
|COLUMN_SIZE|Int32|
|BUFFER_LENGTH|Int32|
|DECIMAL_DIGITS|Int16|
|NUM_PREC_RADIX|Int16|
|NULLABLE|Int16|
|COMENTARIOS|String|
|COLUMN_DEF|String|
|SQL_DATA_TYPE|Int16|
|SQL_DATETIME_SUB|Int16|
|CHAR_OCTET_LENGTH|Int32|
|ORDINAL_POSITION|Int32|
|IS_NULLABLE|String|

## <a name="see-also"></a>Vea también

- [Información general de ADO.NET](ado-net-overview.md)
