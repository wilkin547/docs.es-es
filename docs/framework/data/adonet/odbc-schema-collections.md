---
title: Colecciones de esquemas de ODBC
ms.date: 03/30/2017
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
ms.openlocfilehash: f0240e99d2420b0956d3c144f837b39e094bb78a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794721"
---
# <a name="odbc-schema-collections"></a>Colecciones de esquemas de ODBC

En esta sección se describe la compatibilidad de las colecciones de esquemas con los controladores ODBC de Microsoft SQL Server, Oracle y Microsoft Jet.

## <a name="microsoft-sql-server-odbc-driver"></a>Controlador ODBC para Microsoft SQL Server

El controlador ODBC de Microsoft SQL Server admite las siguientes colecciones de esquemas específicas además de las colecciones de esquemas comunes:

- Tablas

- Índices

- Columnas

- Procedimientos

- ProcedureColumns

- ProcedureParameters

- Vistas

### <a name="tables-and-views"></a>Tablas y vistas

|ColumName|DataType|
|----------------|--------------|
|TABLE_CAT|string|
|TABLE_SCHEM|string|
|TABLE_NAME|string|
|TABLE_TYPE|string|
|REMARKS|string|

### <a name="indexes"></a>Índices

|ColumName|DataType|
|----------------|--------------|
|TABLE_CAT|string|
|TABLE_SCHEM|string|
|TABLE_NAME|string|
|NON_UNIQUE|Int16|
|INDEX_QUALIFIER|string|
|INDEX_NAME|string|
|TYPE|Int16|
|ORDINAL_POSITION|Int16|
|COLUMN_NAME|string|
|ASC_OR_DESC|string|
|CARDINALITY|Int32|
|PAGES|Int32|
|FILTER_CONDITION|string|
|SS_TYPE_SCHEMA|string|
|SS_DATA_TYPE|Byte|

### <a name="columns"></a>Columnas

|ColumName|DataType|
|----------------|--------------|
|TABLE_CAT|string|
|TABLE_SCHEM|string|
|TABLE_NAME|string|
|COLUMN_NAME|string|
|DATA_TYPE|Int16|
|TYPE_NAME|string|
|COLUMN_SIZE|Int32|
|BUFFER_LENGTH|Int32|
|DECIMAL_DIGITS|Int16|
|NUM_PREC_RADIX|Int16|
|NULLABLE|Int16|
|REMARKS|string|
|COLUMN_DEF|string|
|SQL_DATA_TYPE|Int16|
|SQL_DATETIME_SUB|Int16|
|CHAR_OCTET_LENGTH|Int32|
|ORDINAL_POSITION|Int32|
|IS_NULLABLE|string|
|SS_TYPE_CATALOG|string|
|SS_TYPE_SCHEMA|string|
|SS_DATA_TYPE|Byte|

### <a name="procedures"></a>Procedimientos

|ColumName|DataType|
|----------------|--------------|
|PROCEDURE_CAT|string|
|PROCEDURE_SCHEM|string|
|PROCEDURE_NAME|string|
|NUM_INPUT_PARAMS|Int32|
|NUM_OUTPUT_PARAMS|Int32|
|NUM_RESULT_SETS|Int32|
|REMARKS|string|
|PROCEDURE_TYPE|Int16|

### <a name="procedurecolumns"></a>ProcedureColumns

|ColumName|DataType|
|----------------|--------------|
|PROCEDURE_CAT|string|
|PROCEDURE_SCHEM|string|
|PROCEDURE_NAME|string|
|COLUMN_NAME|string|
|COLUMN_TYPE|Int16|
|DATA_TYPE|Int16|
|TYPE_NAME|string|
|COLUMN_SIZE|Int32|
|BUFFER_LENGTH|Int32|
|DECIMAL_DIGITS|Int16|
|NUM_PREC_RADIX|Int16|
|NULLABLE|Int16|
|REMARKS|string|
|COLUMN_DEF|string|
|SQL_DATA_TYPE|Int16|
|SQL_DATETIME_SUB|Int16|
|CHAR_OCTET_LENGTH|Int32|
|ORDINAL_POSITION|Int32|
|IS_NULLABLE|string|
|SS_TYPE_CATALOG|string|
|SS_TYPE_SCHEMA|string|
|SS_DATA_TYPE|Byte|

### <a name="procedureparameters"></a>ProcedureParameters

|ColumName|DataType|
|----------------|--------------|
|PROCEDURE_CAT|string|
|PROCEDURE_SCHEM|string|
|PROCEDURE_NAME|string|
|COLUMN_NAME|string|
|COLUMN_TYPE|Int16|
|DATA_TYPE|Int16|
|TYPE_NAME|string|
|COLUMN_SIZE|Int32|
|BUFFER_LENGTH|Int32|
|DECIMAL_DIGITS|Int16|
|NUM_PREC_RADIX|Int16|
|NULLABLE|Int16|
|REMARKS|string|
|COLUMN_DEF|string|
|SQL_DATA_TYPE|Int16|
|SQL_DATETIME_SUB|Int16|
|CHAR_OCTET_LENGTH|Int32|
|ORDINAL_POSITION|Int32|
|IS_NULLABLE|string|
|SS_TYPE_CATALOG|string|
|SS_TYPE_SCHEMA|string|
|SS_DATA_TYPE|Byte|

## <a name="microsoft-oracle-odbc-driver"></a>Controlador ODBC para Oracle de Microsoft

El controlador ODBC de Oracle Microsoft SQL Server admite las siguientes colecciones de esquemas específicas además de las colecciones de esquemas comunes:

- Tablas

- Columnas

- Procedimientos

- ProcedureColumns

- ProcedureParameters

- Vistas

- Índices

### <a name="tables-and-views"></a>Tablas y vistas

|ColumName|DataType|
|----------------|--------------|
|TABLE_QUALIFIER|string|
|TABLE_OWNER|string|
|TABLE_NAME|string|
|TABLE_TYPE|string|
|REMARKS|string|

### <a name="columns"></a>Columnas

|ColumName|DataType|
|----------------|--------------|
|TABLE_QUALIFIER|string|
|TABLE_OWNER|string|
|TABLE_NAME|string|
|COLUMN_NAME|string|
|DATA_TYPE|Int16|
|TYPE_NAME|string|
|PRECISION|Int32|
|LENGTH|Int32|
|SCALE|Int16|
|RADIX|Int16|
|NULLABLE|Int16|
|REMARKS|string|
|ORDINAL_POSITION|Int32|

### <a name="procedures"></a>Procedimientos

|ColumName|DataType|
|----------------|--------------|
|PROCEDURE_QUALIFIER|string|
|PROCEDURE_OWNER|string|
|PROCEDURE_NAME|string|
|NUM_INPUT_PARAMS|Int16|
|NUM_OUTPUT_PARAMS|Int16|
|NUM_RESULT_SETS|Int16|
|REMARKS|string|
|PROCEDURE_TYPE|Int16|

### <a name="procedurecolumns"></a>ProcedureColumns

|ColumName|DataType|
|----------------|--------------|
|PROCEDURE_QUALIFIER|string|
|PROCEDURE_OWNER|string|
|PROCEDURE_NAME|string|
|COLUMN_NAME|string|
|COLUMN_TYPE|Int16|
|DATA_TYPE|Int16|
|TYPE_NAME|string|
|PRECISION|Int32|
|LENGTH|Int32|
|SCALE|Int16|
|RADIX|Int16|
|NULLABLE|Int16|
|REMARKS|string|
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

|ColumName|DataType|
|----------------|--------------|
|TABLE_QUALIFIER|string|
|TABLE_OWNER|string|
|TABLE_NAME|string|
|TABLE_TYPE|string|
|REMARKS|string|

### <a name="columns"></a>Columnas

|ColumName|DataType|
|----------------|--------------|
|TABLE_QUALIFIER|string|
|TABLE_OWNER|string|
|TABLE_NAME|string|
|COLUMN_NAME|string|
|DATA_TYPE|Int16|
|TYPE_NAME|string|
|PRECISION|Int32|
|LENGTH|Int32|
|SCALE|Int16|
|RADIX|Int16|
|NULLABLE|Int16|
|REMARKS|string|
|ORDINAL_POSITION|Int32|

### <a name="procedures"></a>Procedimientos

|ColumName|DataType|
|----------------|--------------|
|PROCEDURE_QUALIFIER|string|
|PROCEDURE_OWNER|string|
|PROCEDURE_NAME|string|
|NUM_INPUT_PARAMS|Int16|
|NUM_OUTPUT_PARAMS|Int16|
|NUM_RESULT_SETS|Int16|
|REMARKS|string|
|PROCEDURE_TYPE|Int16|

### <a name="procedurecolumns"></a>ProcedureColumns

|ColumName|DataType|
|----------------|--------------|
|PROCEDURE_QUALIFIER|string|
|PROCEDURE_OWNER|string|
|PROCEDURE_NAME|string|
|COLUMN_NAME|string|
|COLUMN_TYPE|Int16|
|DATA_TYPE|Int16|
|TYPE_NAME|string|
|PRECISION|Int32|
|LENGTH|Int32|
|SCALE|Int16|
|RADIX|Int16|
|NULLABLE|Int16|
|REMARKS|string|
|OVERLOAD|Int32|
|ORDINAL_POSITION|Int32|

### <a name="procedureparameters"></a>ProcedureParameters

|ColumName|DataType|
|----------------|--------------|
|PROCEDURE_CAT|string|
|PROCEDURE_SCHEM|string|
|PROCEDURE_NAME|string|
|COLUMN_NAME|string|
|COLUMN_TYPE|Int16|
|DATA_TYPE|Int16|
|TYPE_NAME|string|
|COLUMN_SIZE|Int32|
|BUFFER_LENGTH|Int32|
|DECIMAL_DIGITS|Int16|
|NUM_PREC_RADIX|Int16|
|NULLABLE|Int16|
|REMARKS|string|
|COLUMN_DEF|string|
|SQL_DATA_TYPE|Int16|
|SQL_DATETIME_SUB|Int16|
|CHAR_OCTET_LENGTH|Int32|
|ORDINAL_POSITION|Int32|
|IS_NULLABLE|string|

## <a name="see-also"></a>Vea también

- [Información general sobre ADO.NET](ado-net-overview.md)
