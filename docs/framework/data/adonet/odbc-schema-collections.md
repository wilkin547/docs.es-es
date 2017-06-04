---
title: "Colecciones de esquemas ODBC | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Colecciones de esquemas ODBC
En esta sección se describe la compatibilidad de las colecciones de esquemas con los controladores ODBC de Microsoft SQL Server, Oracle y Microsoft Jet.  
  
## Controlador ODBC para Microsoft SQL Server  
 El controlador ODBC de Microsoft SQL Server admite, además de las colecciones de esquemas comunes, las siguientes colecciones de esquemas específicas:  
  
-   Tablas  
  
-   Índices  
  
-   Columnas  
  
-   Procedimientos  
  
-   ProcedureColumns  
  
-   ProcedureParameters  
  
-   Vistas  
  
### Tablas y vistas  
  
|ColumName|DataType|  
|---------------|--------------|  
|TABLE\_CAT|String|  
|TABLE\_SCHEM|String|  
|TABLE\_NAME|String|  
|TABLE\_TYPE|String|  
|REMARKS|String|  
  
### Índices  
  
|ColumName|DataType|  
|---------------|--------------|  
|TABLE\_CAT|String|  
|TABLE\_SCHEM|String|  
|TABLE\_NAME|String|  
|NON\_UNIQUE|Int16|  
|INDEX\_QUALIFIER|String|  
|INDEX\_NAME|String|  
|TYPE|Int16|  
|ORDINAL\_POSITION|Int16|  
|COLUMN\_NAME|String|  
|ASC\_OR\_DESC|String|  
|CARDINATLITY|Int32|  
|PAGES|Int32|  
|FILTER\_CONDITION|String|  
|SS\_TYPE\_SCHEMA|String|  
|SS\_DATA\_TYPE|Byte|  
  
### Columnas  
  
|ColumName|DataType|  
|---------------|--------------|  
|TABLE\_CAT|String|  
|TABLE\_SCHEM|String|  
|TABLE\_NAME|String|  
|COLUMN\_NAME|String|  
|DATA\_TYPE|Int16|  
|TYPE\_NAME|String|  
|COLUMN\_SIZE|Int32|  
|BUFFER\_LENGTH|Int32|  
|DECIMAL\_DIGITS|Int16|  
|NUM\_PREC\_RADIX|Int16|  
|NULLABLE|Int16|  
|REMARKS|String|  
|COLUMN\_DEF|String|  
|SQL\_DATA\_TYPE|Int16|  
|SQL\_DATETIME\_SUB|Int16|  
|CHAR\_OCTET\_LENGTH|Int32|  
|ORDINAL\_POSITION|Int32|  
|IS\_NULLABLE|String|  
|SS\_TYPE\_CATALOG|String|  
|SS\_TYPE\_SCHEMA|String|  
|SS\_DATA\_TYPE|Byte|  
  
### Procedimientos  
  
|ColumName|DataType|  
|---------------|--------------|  
|PROCEDURE\_CAT|String|  
|PROCEDURE\_SCHEM|String|  
|PROCEDURE\_NAME|String|  
|NUM\_INPUT\_PARAMS|Int32|  
|NUM\_OUTPUT\_PARAMS|Int32|  
|NUM\_RESULT\_SETS|Int32|  
|REMARKS|String|  
|PROCEDURE\_TYPE|Int16|  
  
### ProcedureColumns  
  
|ColumName|DataType|  
|---------------|--------------|  
|PROCEDURE\_CAT|String|  
|PROCEDURE\_SCHEM|String|  
|PROCEDURE\_NAME|String|  
|COLUMN\_NAME|String|  
|COLUMN\_TYPE|Int16|  
|DATA\_TYPE|Int16|  
|TYPE\_NAME|String|  
|COLUMN\_SIZE|Int32|  
|BUFFER\_LENGTH|Int32|  
|DECIMAL\_DIGITS|Int16|  
|NUM\_PREC\_RADIX|Int16|  
|NULLABLE|Int16|  
|REMARKS|String|  
|COLUMN\_DEF|String|  
|SQL\_DATA\_TYPE|Int16|  
|SQL\_DATETIME\_SUB|Int16|  
|CHAR\_OCTET\_LENGTH|Int32|  
|ORDINAL\_POSITION|Int32|  
|IS\_NULLABLE|String|  
|SS\_TYPE\_CATALOG|String|  
|SS\_TYPE\_SCHEMA|String|  
|SS\_DATA\_TYPE|Byte|  
  
### ProcedureParameters  
  
|ColumName|DataType|  
|---------------|--------------|  
|PROCEDURE\_CAT|String|  
|PROCEDURE\_SCHEM|String|  
|PROCEDURE\_NAME|String|  
|COLUMN\_NAME|String|  
|COLUMN\_TYPE|Int16|  
|DATA\_TYPE|Int16|  
|TYPE\_NAME|String|  
|COLUMN\_SIZE|Int32|  
|BUFFER\_LENGTH|Int32|  
|DECIMAL\_DIGITS|Int16|  
|NUM\_PREC\_RADIX|Int16|  
|NULLABLE|Int16|  
|REMARKS|String|  
|COLUMN\_DEF|String|  
|SQL\_DATA\_TYPE|Int16|  
|SQL\_DATETIME\_SUB|Int16|  
|CHAR\_OCTET\_LENGTH|Int32|  
|ORDINAL\_POSITION|Int32|  
|IS\_NULLABLE|String|  
|SS\_TYPE\_CATALOG|String|  
|SS\_TYPE\_SCHEMA|String|  
|SS\_DATA\_TYPE|Byte|  
  
## Controlador ODBC para Oracle de Microsoft  
 El controlador ODBC para Oracle de Microsoft SQL Server admite, además de las colecciones de esquemas comunes, las siguientes colecciones de esquemas específicas:  
  
-   Tablas  
  
-   Columnas  
  
-   Procedimientos  
  
-   ProcedureColumns  
  
-   ProcedureParameters  
  
-   Vistas  
  
-   Índices  
  
### Tablas y vistas  
  
|ColumName|DataType|  
|---------------|--------------|  
|TABLE\_QUALIFIER|String|  
|TABLE\_OWNER|String|  
|TABLE\_NAME|String|  
|TABLE\_TYPE|String|  
|REMARKS|String|  
  
### Columnas  
  
|ColumName|DataType|  
|---------------|--------------|  
|TABLE\_QUALIFIER|String|  
|TABLE\_OWNER|String|  
|TABLE\_NAME|String|  
|COLUMN\_NAME|String|  
|DATA\_TYPE|Int16|  
|TYPE\_NAME|String|  
|PRECISION|Int32|  
|LENGTH|Int32|  
|SCALE|Int16|  
|RADIX|Int16|  
|NULLABLE|Int16|  
|REMARKS|String|  
|ORDINAL\_POSITION|Int32|  
  
### Procedimientos  
  
|ColumName|DataType|  
|---------------|--------------|  
|PROCEDURE\_QUALIFIER|String|  
|PROCEDURE\_OWNER|String|  
|PROCEDURE\_NAME|String|  
|NUM\_INPUT\_PARAMS|Int16|  
|NUM\_OUTPUT\_PARAMS|Int16|  
|NUM\_RESULT\_SETS|Int16|  
|REMARKS|String|  
|PROCEDURE\_TYPE|Int16|  
  
### ProcedureColumns  
  
|ColumName|DataType|  
|---------------|--------------|  
|PROCEDURE\_QUALIFIER|String|  
|PROCEDURE\_OWNER|String|  
|PROCEDURE\_NAME|String|  
|COLUMN\_NAME|String|  
|COLUMN\_TYPE|Int16|  
|DATA\_TYPE|Int16|  
|TYPE\_NAME|String|  
|PRECISION|Int32|  
|LENGTH|Int32|  
|SCALE|Int16|  
|RADIX|Int16|  
|NULLABLE|Int16|  
|REMARKS|String|  
|OVERLOAD|Int32|  
|ORDINAL\_POSITION|Int32|  
  
## Controlador ODBC de Microsoft para Jet  
 El controlador ODBC de Microsoft para Jet admite, además de las colecciones de esquemas comunes, las siguientes colecciones de esquemas específicas:  
  
-   Tablas  
  
-   Índices  
  
-   Columnas  
  
-   Procedimientos  
  
-   ProcedureColumns  
  
-   ProcedureParameters  
  
-   Vistas  
  
### Tablas y vistas  
  
|ColumName|DataType|  
|---------------|--------------|  
|TABLE\_QUALIFIER|String|  
|TABLE\_OWNER|String|  
|TABLE\_NAME|String|  
|TABLE\_TYPE|String|  
|REMARKS|String|  
  
### Columnas  
  
|ColumName|DataType|  
|---------------|--------------|  
|TABLE\_QUALIFIER|String|  
|TABLE\_OWNER|String|  
|TABLE\_NAME|String|  
|COLUMN\_NAME|String|  
|DATA\_TYPE|Int16|  
|TYPE\_NAME|String|  
|PRECISION|Int32|  
|LENGTH|Int32|  
|SCALE|Int16|  
|RADIX|Int16|  
|NULLABLE|Int16|  
|REMARKS|String|  
|ORDINAL\_POSITION|Int32|  
  
### Procedimientos  
  
|ColumName|DataType|  
|---------------|--------------|  
|PROCEDURE\_QUALIFIER|String|  
|PROCEDURE\_OWNER|String|  
|PROCEDURE\_NAME|String|  
|NUM\_INPUT\_PARAMS|Int16|  
|NUM\_OUTPUT\_PARAMS|Int16|  
|NUM\_RESULT\_SETS|Int16|  
|REMARKS|String|  
|PROCEDURE\_TYPE|Int16|  
  
### ProcedureColumns  
  
|ColumName|DataType|  
|---------------|--------------|  
|PROCEDURE\_QUALIFIER|String|  
|PROCEDURE\_OWNER|String|  
|PROCEDURE\_NAME|String|  
|COLUMN\_NAME|String|  
|COLUMN\_TYPE|Int16|  
|DATA\_TYPE|Int16|  
|TYPE\_NAME|String|  
|PRECISION|Int32|  
|LENGTH|Int32|  
|SCALE|Int16|  
|RADIX|Int16|  
|NULLABLE|Int16|  
|REMARKS|String|  
|OVERLOAD|Int32|  
|ORDINAL\_POSITION|Int32|  
  
### ProcedureParameters  
  
|ColumName|DataType|  
|---------------|--------------|  
|PROCEDURE\_CAT|String|  
|PROCEDURE\_SCHEM|String|  
|PROCEDURE\_NAME|String|  
|COLUMN\_NAME|String|  
|COLUMN\_TYPE|Int16|  
|DATA\_TYPE|Int16|  
|TYPE\_NAME|String|  
|COLUMN\_SIZE|Int32|  
|BUFFER\_LENGTH|Int32|  
|DECIMAL\_DIGITS|Int16|  
|NUM\_PREC\_RADIX|Int16|  
|NULLABLE|Int16|  
|REMARKS|String|  
|COLUMN\_DEF|String|  
|SQL\_DATA\_TYPE|Int16|  
|SQL\_DATETIME\_SUB|Int16|  
|CHAR\_OCTET\_LENGTH|Int32|  
|ORDINAL\_POSITION|Int32|  
|IS\_NULLABLE|String|  
  
## Vea también  
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)