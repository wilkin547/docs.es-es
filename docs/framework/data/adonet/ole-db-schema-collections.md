---
title: Colecciones de esquemas de OLE DB
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: 2d5718c12100ebea49a6b6fab29a3790918c6ad3
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783447"
---
# <a name="ole-db-schema-collections"></a>Colecciones de esquemas de OLE DB
En esta sección se describe la compatibilidad de las colecciones de esquemas con los proveedores OLE DB de Microsoft SQL Server, Oracle y Microsoft Jet.  
  
## <a name="microsoft-sql-server-ole-db-provider"></a>Proveedor OLE DB para Microsoft SQL Server  
 El controlador de OLE DB de Microsoft SQL Server admite las siguientes colecciones de esquemas específicas además de las colecciones de esquemas comunes:  
  
- Tablas  
  
- Columnas  
  
- Procedimientos  
  
- ProcedureParameters  
  
- Catálogo  
  
- Índices  
  
### <a name="tables"></a>Tablas  
  
|ColumName|DataType|  
|----------------|--------------|  
|TABLE_CATALOG|string|  
|TABLE_SCHEMA|string|  
|TABLE_NAME|string|  
|TABLE_TYPE|string|  
|TABLE_GUID|Guid|  
|DESCRIPTION|string|  
|TABLE_PROPID|Int64|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="columns"></a>Columnas  
  
|ColumName|DataType|  
|----------------|--------------|  
|TABLE_CATALOG|string|  
|TABLE_SCHEMA|string|  
|TABLE_NAME|string|  
|COLUMN_NAME|string|  
|COLUMN_GUID|Guid|  
|COLUMN_PROPID|Int64|  
|ORDINAL_POSITION|Int64|  
|COLUMN_HASDEFAULT|Boolean|  
|COLUMN_DEFAULT|string|  
|COLUMN_FLAGS|Int64|  
|IS_NULLABLE|Boolean|  
|DATA_TYPE|Int32|  
|TYPE_GUID|Guid|  
|CHARACTER_MAXIMUM_LENGTH|Int64|  
|CHARACTER_OCTET_LENGTH|Int64|  
|NUMERIC_PRECISION|Int32|  
|NUMERIC_SCALE|Int16|  
|DATETIME_PRECISION|Int64|  
|CHARACTER_SET_CATALOG|string|  
|CHARACTER_SET_SCHEMA|string|  
|CHARACTER_SET_NAME|string|  
|COLLATION_CATALOG|string|  
|COLLATION_SCHEMA|string|  
|COLLATION_NAME|string|  
|DOMAIN_CATALOG|string|  
|DOMAIN_SCHEMA|string|  
|DOMAIN_NAME|string|  
|DESCRIPTION|string|  
|COLUMN_LCID|Int32|  
|COLUMN_COMPFLAGS|Int32|  
|COLUMN_SORTID|Int32|  
|COLUMN_TDSCOLLATION|Byte[]|  
|IS_COMPUTED|Boolean|  
  
### <a name="procedures"></a>Procedimientos  
  
|ColumName|DataType|  
|----------------|--------------|  
|PROCEDURE_CATALOG|string|  
|PROCEDURE_SCHEMA|string|  
|PROCEDURE_NAME|string|  
|PROCEDURE_TYPE|Int16|  
|PROCEDURE_DEFINITION|string|  
|DESCRIPTION|string|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="procedureparameters"></a>ProcedureParameters  
  
|ColumName|DataType|  
|----------------|--------------|  
|PROCEDURE_CATALOG|string|  
|PROCEDURE_SCHEMA|string|  
|PROCEDURE_NAME|string|  
|PARAMETER_NAME|string|  
|ORDINAL_POSITION|Int32|  
|PARAMETER_TYPE|Int32|  
|PARAMETER_HASDEFAULT|Boolean|  
|PARAMETER_DEFAULT|string|  
|IS_NULLABLE|Boolean|  
|DATA_TYPE|Int32|  
|CHARACTER_MAXIMUM_LENGTH|Int64|  
|CHARACTER_OCTET_LENGTH|Int64|  
|NUMERIC_PRECISION|Int32|  
|NUMERIC_SCALE|Int16|  
|DESCRIPTION|string|  
|TYPE_NAME|string|  
|LOCAL_TYPE_NAME|string|  
  
### <a name="catalog"></a>Catálogo  
  
|ColumName|DataType|  
|----------------|--------------|  
|CATALOG_NAME|string|  
|DESCRIPTION|string|  
  
### <a name="indexes"></a>Índices  
  
|ColumName|DataType|  
|----------------|--------------|  
|TABLE_CATALOG|string|  
|TABLE_SCHEMA|string|  
|TABLE_NAME|string|  
|INDEX_CATALOG|string|  
|INDEX_SCHEMA|string|  
|INDEX_NAME|string|  
|PRIMARY_KEY|Boolean|  
|UNIQUE|Boolean|  
|CLUSTERED|Boolean|  
|TYPE|Int32|  
|FILL_FACTOR|Int32|  
|INITIAL_SIZE|Int32|  
|NULLS|Int32|  
|SORT_BOOKMARKS|Boolean|  
|AUTO_UPDATE|Boolean|  
|NULL_COLLATION|Int32|  
|ORDINAL_POSITION|Int64|  
|COLUMN_NAME|string|  
|COLUMN_GUID|Guid|  
|COLUMN_PROPID|Int64|  
|COLLATION|Int16|  
|CARDINALITY|Decimal|  
|PAGES|Int32|  
|FILTER_CONDITION|string|  
|INTEGRATED|Boolean|  
  
## <a name="microsoft-oracle-ole-db-provider"></a>Proveedor OLE DB de Microsoft para Oracle  
 El controlador OLE DB de Microsoft para Oracle admite, además de las colecciones de esquemas comunes, las siguientes colecciones de esquemas específicas:  
  
- Tablas  
  
- Columnas  
  
- Procedimientos  
  
- ProcedureColumns  
  
- ProcedureParameters  
  
- Vistas  
  
- Índices  
  
### <a name="tables"></a>Tablas  
  
|ColumName|DataType|  
|----------------|--------------|  
|TABLE_CATALOG|string|  
|TABLE_SCHEMA|string|  
|TABLE_NAME|string|  
|TABLE_TYPE|string|  
|TABLE_GUID|Guid|  
|DESCRIPTION|string|  
|TABLE_PROPID|Int64|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="columns"></a>Columnas  
  
|ColumName|DataType|  
|----------------|--------------|  
|TABLE_CATALOG|string|  
|TABLE_SCHEMA|string|  
|TABLE_NAME|string|  
|COLUMN_NAME|string|  
|COLUMN_GUID|Guid|  
|COLUMN_PROPID|Int64|  
|ORDINAL_POSITION|Int64|  
|COLUMN_HASDEFAULT|Boolean|  
|COLUMN_DEFAULT|string|  
|COLUMN_FLAGS|Int64|  
|IS_NULLABLE|Boolean|  
|DATA_TYPE|Int32|  
|TYPE_GUID|Guid|  
|CHARACTER_MAXIMUM_LENGTH|Int64|  
|CHARACTER_OCTET_LENGTH|Int64|  
|NUMERIC_PRECISION|Int32|  
|NUMERIC_SCALE|Int16|  
|DATETIME_PRECISION|Int64|  
|CHARACTER_SET_CATALOG|string|  
|CHARACTER_SET_SCHEMA|string|  
|CHARACTER_SET_NAME|string|  
|COLLATION_CATALOG|string|  
|COLLATION_SCHEMA|string|  
|COLLATION_NAME|string|  
|DOMAIN_CATALOG|string|  
|DOMAIN_SCHEMA|string|  
|DOMAIN_NAME|string|  
|DESCRIPTION|string|  
  
### <a name="procedures"></a>Procedimientos  
  
|ColumName|DataType|  
|----------------|--------------|  
|PROCEDURE_CATALOG|string|  
|PROCEDURE_SCHEMA|string|  
|PROCEDURE_NAME|string|  
|PROCEDURE_TYPE|Int16|  
|PROCEDURE_DEFINITION|string|  
|DESCRIPTION|string|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="procedurecolumns"></a>ProcedureColumns  
  
|ColumName|DataType|  
|----------------|--------------|  
|PROCEDURE_CATALOG|string|  
|PROCEDURE_SCHEMA|string|  
|PROCEDURE_NAME|string|  
|COLUMN_NAME|string|  
|COLUMN_GUID|Guid|  
|COLUMN_PROPID|Int64|  
|ROWSET_NUMBER|Int64|  
|ORDINAL_POSITION|Int64|  
|IS_NULLABLE|Boolean|  
|DATA_TYPE|Int32|  
|TYPE_GUID|Guid|  
|CHARACTER_MAXIMUM_LENGTH|Int64|  
|CHARACTER_OCTET_LENGTH|Int64|  
|NUMERIC_PRECISION|Int32|  
|NUMERIC_SCALE|Int16|  
|DESCRIPTION|string|  
|OVERLOAD|Int16|  
  
### <a name="views"></a>Vistas  
  
|ColumName|DataType|  
|----------------|--------------|  
|TABLE_CATALOG|string|  
|TABLE_SCHEMA|string|  
|TABLE_NAME|string|  
|VIEW_DEFINITION|string|  
|CHECK_OPTION|Boolean|  
|IS_UPDATABLE|Boolean|  
|DESCRIPTION|string|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="indexes"></a>Índices  
  
|ColumName|DataType|  
|----------------|--------------|  
|TABLE_CATALOG|string|  
|TABLE_SCHEMA|string|  
|TABLE_NAME|string|  
|INDEX_CATALOG|string|  
|INDEX_SCHEMA|string|  
|INDEX_NAME|string|  
|PRIMARY_KEY|Boolean|  
|UNIQUE|Boolean|  
|CLUSTERED|Boolean|  
|TYPE|Int32|  
|FILL_FACTOR|Int32|  
|INITIAL_SIZE|Int32|  
|NULLS|Int32|  
|SORT_BOOKMARKS|Boolean|  
|AUTO_UPDATE|Boolean|  
|NULL_COLLATION|Int32|  
|ORDINAL_POSITION|Int64|  
|COLUMN_NAME|string|  
|COLUMN_GUID|Guid|  
|COLUMN_PROPID|Int64|  
|COLLATION|Int16|  
|CARDINALITY|Decimal|  
|PAGES|Int32|  
|FILTER_CONDITION|string|  
|INTEGRATED|Boolean|  
  
## <a name="microsoft-jet-ole-db-provider"></a>Proveedor OLE DB de Microsoft para Jet  
 El controlador OLE DB de Microsoft para Jet admite, además de las colecciones de esquemas comunes, las siguientes colecciones de esquemas específicas:  
  
- Tablas  
  
- Columnas  
  
- Procedimientos  
  
- Vistas  
  
- Índices  
  
### <a name="tables"></a>Tablas  
  
|ColumName|DataType|  
|----------------|--------------|  
|TABLE_CATALOG|string|  
|TABLE_SCHEMA|string|  
|TABLE_NAME|string|  
|TABLE_TYPE|string|  
|TABLE_GUID|Guid|  
|DESCRIPTION|string|  
|TABLE_PROPID|Int64|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="columns"></a>Columnas  
  
|ColumName|DataType|  
|----------------|--------------|  
|TABLE_CATALOG|string|  
|TABLE_SCHEMA|string|  
|TABLE_NAME|string|  
|COLUMN_NAME|string|  
|COLUMN_GUID|Guid|  
|COLUMN_PROPID|Int64|  
|ORDINAL_POSITION|Int64|  
|COLUMN_HASDEFAULT|Boolean|  
|COLUMN_DEFAULT|string|  
|COLUMN_FLAGS|Int64|  
|IS_NULLABLE|Boolean|  
|DATA_TYPE|Int32|  
|TYPE_GUID|Guid|  
|CHARACTER_MAXIMUM_LENGTH|Int64|  
|CHARACTER_OCTET_LENGTH|Int64|  
|NUMERIC_PRECISION|Int32|  
|NUMERIC_SCALE|Int16|  
|DATETIME_PRECISION|Int64|  
|CHARACTER_SET_CATALOG|string|  
|CHARACTER_SET_SCHEMA|string|  
|CHARACTER_SET_NAME|string|  
|COLLATION_CATALOG|string|  
|COLLATION_SCHEMA|string|  
|COLLATION_NAME|string|  
|DOMAIN_CATALOG|string|  
|DOMAIN_SCHEMA|string|  
|DOMAIN_NAME|string|  
|DESCRIPTION|string|  
  
### <a name="procedures"></a>Procedimientos  
  
|ColumName|DataType|  
|----------------|--------------|  
|PROCEDURE_CATALOG|string|  
|PROCEDURE_SCHEMA|string|  
|PROCEDURE_NAME|string|  
|PROCEDURE_TYPE|Int16|  
|PROCEDURE_DEFINITION|string|  
|DESCRIPTION|string|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="views"></a>Vistas  
  
|ColumName|DataType|  
|----------------|--------------|  
|TABLE_CATALOG|string|  
|TABLE_SCHEMA|string|  
|TABLE_NAME|string|  
|VIEW_DEFINITION|string|  
|CHECK_OPTION|Boolean|  
|IS_UPDATABLE|Boolean|  
|DESCRIPTION|string|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="indexes"></a>Índices  
  
|ColumName|DataType|  
|----------------|--------------|  
|TABLE_CATALOG|string|  
|TABLE_SCHEMA|string|  
|TABLE_NAME|string|  
|INDEX_CATALOG|string|  
|INDEX_SCHEMA|string|  
|INDEX_NAME|string|  
|PRIMARY_KEY|Boolean|  
|UNIQUE|Boolean|  
|CLUSTERED|Boolean|  
|TYPE|Int32|  
|FILL_FACTOR|Int32|  
|INITIAL_SIZE|Int32|  
|NULLS|Int32|  
|SORT_BOOKMARKS|Boolean|  
|AUTO_UPDATE|Boolean|  
|NULL_COLLATION|Int32|  
|ORDINAL_POSITION|Int64|  
|COLUMN_NAME|string|  
|COLUMN_GUID|Guid|  
|COLUMN_PROPID|Int64|  
|COLLATION|Int16|  
|CARDINALITY|Decimal|  
|PAGES|Int32|  
|FILTER_CONDITION|string|  
|INTEGRATED|Boolean|  
  
## <a name="see-also"></a>Vea también

- [Información general sobre ADO.NET](ado-net-overview.md)
