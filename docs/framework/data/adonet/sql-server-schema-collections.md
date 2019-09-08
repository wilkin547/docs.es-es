---
title: Colecciones de esquemas de SQL Server
ms.date: 03/30/2017
ms.assetid: c6403cc3-d78b-4f85-bab1-ada7a3446ec5
ms.openlocfilehash: 0f65bbf2534eb7167baacb1405a8ce6e9769c23f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794336"
---
# <a name="sql-server-schema-collections"></a>Colecciones de esquemas de SQL Server
El proveedor de datos .NET Framework para SQL Server de Microsoft admite colecciones de esquemas adicionales, además de las colecciones de esquemas comunes. Las colecciones de esquemas varían ligeramente respecto de la versión de SQL Server que está utilizando. Para determinar la lista de colecciones de esquemas admitidas, llame al método **GetSchema** sin argumentos o con el nombre de la colección de esquemas "MetaDataCollections". Esto devolverá una <xref:System.Data.DataTable> con una lista de colecciones de esquemas admitidas, el número de restricciones que admite cada una y el número de partes de identificador que emplean.  
  
## <a name="databases"></a>Bases de datos  
  
|ColumName|DataType|DESCRIPCIÓN|  
|----------------|--------------|-----------------|  
|database_name|string|Nombre de la base de datos.|  
|DBID|Int16|Id. de la base de datos.|  
|create_date|DateTime|Fecha de creación de la base de datos.|  
  
## <a name="foreign-keys"></a>Claves externas  
  
|ColumName|DataType|DESCRIPCIÓN|  
|----------------|--------------|-----------------|  
|CONSTRAINT_CATALOG|string|Catálogo al que pertenece la restricción.|  
|CONSTRAINT_SCHEMA|string|Esquema que contiene la restricción.|  
|CONSTRAINT_NAME|string|Nombre.|  
|TABLE_CATALOG|string|Nombre de la tabla de la que forma parte la restricción.|  
|TABLE_SCHEMA|string|Esquema que contiene la tabla.|  
|TABLE_NAME|string|Nombre de la tabla|  
|CONSTRAINT_TYPE|string|Tipo de restricción. Sólo se permite "FOREIGN KEY".|  
|IS_DEFERRABLE|string|Especifica si la restricción es aplazable. Devuelve NO.|  
|INITIALLY_DEFERRED|string|Especifica si la restricción es inicialmente aplazable. Devuelve NO.|  
  
## <a name="indexes"></a>Índices  
  
|ColumName|DataType|DESCRIPCIÓN|  
|----------------|--------------|-----------------|  
|constraint_catalog|string|Catálogo al que pertenece el índice.|  
|constraint_schema|string|Esquema que contiene el índice.|  
|constraint_name|string|Nombre del índice.|  
|table_catalog|string|Nombre de la tabla con la que está asociado el índice.|  
|table_schema|string|Esquema que contiene la tabla con la que está asociado el índice.|  
|table_name|string|Nombre de la tabla.|  
|index_name|string|Nombre del índice.|  
  
### <a name="indexes-sql-server-2008"></a>Índices (SQL Server 2008)  
 Desde .NET Framework 3.5 Service Pack 1 y SQL Server 2008, se han agregado las columnas siguientes a la colección de esquemas Indexes para admitir nuevas columnas de tipos espaciales, de secuencia de archivos y dispersas. Estas columnas no se admiten en versiones anteriores de .NET Framework y SQL Server.  
  
|ColumName|DataType|DESCRIPCIÓN|  
|----------------|--------------|-----------------|  
|type_desc|string|El tipo de índice debe ser uno de los valores siguientes:<br /><br /> -MONTÓN<br />-AGRUPADO<br />-NONCLUSTERED<br />-XML<br />-ESPACIAL|  
  
## <a name="indexcolumns"></a>IndexColumns  
  
|ColumName|DataType|DESCRIPCIÓN|  
|----------------|--------------|-----------------|  
|constraint_catalog|string|Catálogo al que pertenece el índice.|  
|constraint_schema|string|Esquema que contiene el índice.|  
|constraint_name|string|Nombre del índice.|  
|table_catalog|string|Nombre de la tabla con la que está asociado el índice.|  
|table_schema|string|Esquema que contiene la tabla con la que está asociado el índice.|  
|table_name|string|Nombre de la tabla.|  
|column_name|string|Nombre de la columna con la que está asociado el índice.|  
|ordinal_position|Int32|Posición del índice de columna.|  
|KeyType|Byte|Tipo del objeto.|  
|index_name|string|Nombre del índice.|  
  
## <a name="procedures"></a>Procedimientos  
  
|ColumName|DataType|DESCRIPCIÓN|  
|----------------|--------------|-----------------|  
|SPECIFIC_CATALOG|string|Nombre específico del catálogo.|  
|SPECIFIC_SCHEMA|string|Nombre específico del esquema.|  
|SPECIFIC_NAME|string|Nombre específico del catálogo.|  
|ROUTINE_CATALOG|string|Catálogo al que pertenece el procedimiento almacenado.|  
|ROUTINE_SCHEMA|string|Esquema que contiene el procedimiento almacenado.|  
|ROUTINE_NAME|string|Nombre del procedimiento almacenado.|  
|ROUTINE_TYPE|string|Devuelve PROCEDURE en el caso de los procedimientos almacenados y FUNCTION en el caso de las funciones.|  
|CREATED|DateTime|Hora a la que se creó el procedimiento.|  
|LAST_ALTERED|DateTime|La última vez que se modificó el procedimiento.|  
  
## <a name="procedure-parameters"></a>Parámetros de procedimiento  
  
|ColumName|DataType|DESCRIPCIÓN|  
|----------------|--------------|-----------------|  
|SPECIFIC_CATALOG|string|Nombre de catálogo del procedimiento del que forma parte este parámetro.|  
|SPECIFIC_SCHEMA|string|Esquema que contiene el procedimiento del que forma parte este parámetro.|  
|SPECIFIC_NAME|string|Nombre del procedimiento del que forma parte este parámetro.|  
|ORDINAL_POSITION|Int32|Posición ordinal del parámetro que empieza por 1. Para el valor devuelto de un procedimiento, es un 0.|  
|PARAMETER_MODE|string|Devuelve IN si es un parámetro de entrada, OUT si es un parámetro de salida e INOUT si es un parámetro de entrada y salida.|  
|IS_RESULT|string|Devuelve YES si indica que el resultado del procedimiento es una función. De lo contrario, devuelve NO.|  
|AS_LOCATOR|string|Devuelve YES si se declara como localizador. De lo contrario, devuelve NO.|  
|PARAMETER_NAME|string|Nombre del parámetro. NULL si corresponde al valor devuelto de una función.|  
|DATA_TYPE|string|Tipo de datos suministrado por el sistema.|  
|CHARACTER_MAXIMUM_LENGTH|Int32|Longitud máxima, en caracteres, de los tipos de datos binarios o de caracteres. De lo contrario, devuelve NULL.|  
|CHARACTER_OCTET_LENGTH|Int32|Longitud máxima, en bytes, de los tipos de datos binarios o de caracteres. De lo contrario, devuelve NULL.|  
|COLLATION_CATALOG|string|Nombre de catálogo de la intercalación del parámetro. Si no es uno de los tipos de caracteres, devuelve NULL.|  
|COLLATION_SCHEMA|string|Siempre devuelve NULL.|  
|COLLATION_NAME|string|Nombre de la intercalación del parámetro. Si no es uno de los tipos de caracteres, devuelve NULL.|  
|CHARACTER_SET_CATALOG|string|Nombre de catálogo del juego de caracteres del parámetro. Si no es uno de los tipos de caracteres, devuelve NULL.|  
|CHARACTER_SET_SCHEMA|string|Siempre devuelve NULL.|  
|CHARACTER_SET_NAME|string|Nombre del juego de caracteres del parámetro. Si no es uno de los tipos de caracteres, devuelve NULL.|  
|NUMERIC_PRECISION|Byte|Precisión de datos numéricos aproximados, datos numéricos exactos, datos enteros o datos monetarios. De lo contrario, devuelve NULL.|  
|NUMERIC_PRECISION_RADIX|Int16|Base de precisión de datos numéricos aproximados, datos numéricos exactos, datos enteros o datos monetarios. De lo contrario, devuelve NULL.|  
|NUMERIC_SCALE|Int32|Escala de datos numéricos aproximados, datos numéricos exactos, datos enteros o datos monetarios. De lo contrario, devuelve NULL.|  
|DATETIME_PRECISION|Int16|Precisión en segundos decimales si el tipo de parámetro es datetime o smalldatetime. De lo contrario, devuelve NULL.|  
|INTERVAL_TYPE|string|NULL. Reservado por SQL Server para uso futuro.|  
|INTERVAL_PRECISION|Int16|NULL. Reservado por SQL Server para uso futuro.|  
  
## <a name="tables"></a>Tablas  
  
|ColumName|DataType|DESCRIPCIÓN|  
|----------------|--------------|-----------------|  
|TABLE_CATALOG|string|Catálogo de la tabla.|  
|TABLE_SCHEMA|string|Esquema que contiene la tabla.|  
|TABLE_NAME|string|Nombre de la tabla.|  
|TABLE_TYPE|string|Tipo de tabla. Puede ser VIEW o BASE TABLE.|  
  
## <a name="columns"></a>Columnas  
  
|ColumName|DataType|DESCRIPCIÓN|  
|----------------|--------------|-----------------|  
|TABLE_CATALOG|string|Catálogo de la tabla.|  
|TABLE_SCHEMA|string|Esquema que contiene la tabla.|  
|TABLE_NAME|string|Nombre de la tabla.|  
|COLUMN_NAME|string|Nombre de columna.|  
|ORDINAL_POSITION|Int32|Número de identificación de la columna.|  
|COLUMN_DEFAULT|string|Valor predeterminado de la columna.|  
|IS_NULLABLE|string|Capacidad de la columna de admitir valores NULL. Si esta columna permite NULL, devuelve YES. De lo contrario, devuelve NO.|  
|DATA_TYPE|string|Tipo de datos suministrado por el sistema.|  
|CHARACTER_MAXIMUM_LENGTH|Int32 – Sql8, Int16 – Sql7|Longitud máxima, en caracteres, de los datos binarios, datos de caracteres o datos de texto e imágenes. De lo contrario, devuelve NULL.|  
|CHARACTER_OCTET_LENGTH|Int32 – SQL8, Int16 – Sql7|Longitud máxima, en bytes, de los datos binarios, datos de caracteres o datos de texto e imágenes. De lo contrario, devuelve NULL.|  
|NUMERIC_PRECISION|Byte sin signo|Precisión de datos numéricos aproximados, datos numéricos exactos, datos enteros o datos monetarios. De lo contrario, devuelve NULL.|  
|NUMERIC_PRECISION_RADIX|Int16|Base de precisión de datos numéricos aproximados, datos numéricos exactos, datos enteros o datos monetarios. De lo contrario, devuelve NULL.|  
|NUMERIC_SCALE|Int32|Escala de datos numéricos aproximados, datos numéricos exactos, datos enteros o datos monetarios. De lo contrario, devuelve NULL.|  
|DATETIME_PRECISION|Int16|Código de subtipo para los tipos de datos datetime y de intervalo SQL-92. Para otros tipos de datos, devuelve NULL.|  
|CHARACTER_SET_CATALOG|string|Devuelve Master, para indicar la base de datos en la que se encuentra el juego de caracteres, si la columna es del tipo de datos de caracteres o de texto. De lo contrario, devuelve NULL.|  
|CHARACTER_SET_SCHEMA|string|Siempre devuelve NULL.|  
|CHARACTER_SET_NAME|string|Devuelve el nombre único del juego de caracteres si esta columna es del tipo de datos de caracteres o de texto. De lo contrario, devuelve NULL.|  
|COLLATION_CATALOG|string|Devuelve Master, para indicar la base de datos en la que se define la intercalación, si la columna es del tipo de datos de caracteres o de texto. De lo contrario, esta columna es NULL.|  
  
### <a name="columns-sql-server-2008"></a>Columns (SQL Server 2008)  
 A partir de .NET Framework versión 3.5 Service Pack 1 y SQL Server 2008, se han agregado las columnas siguientes a la colección de esquemas Columns para admitir nuevas columnas de tipos espaciales, de secuencias de archivos y dispersas. Estas columnas no se admiten en versiones anteriores de .NET Framework y SQL Server.  
  
|ColumName|DataType|DESCRIPCIÓN|  
|----------------|--------------|-----------------|  
|IS_FILESTREAM|string|YES si la columna tiene el atributo FILESTREAM.<br /><br /> NO si la columna no tiene el atributo FILESTREAM.|  
|IS_SPARSE|string|YES si la columna es una columna dispersa.<br /><br /> NO si la columna no es una columna dispersa.|  
|IS_COLUMN_SET|string|YES si la columna es de conjunto de columnas.<br /><br /> NO si la columna no es de conjunto de columnas.|  
  
### <a name="allcolumns-sql-server-2008"></a>AllColumns (SQL Server 2008)  
 A partir de .NET Framework versión 3.5 Service Pack 1 y SQL Server 2008, se ha agregado la colección de esquemas AllColumns para admitir columnas dispersas. AllColumns no se admite en versiones anteriores de .NET Framework y SQL Server.  
  
 AllColumns tiene las mismas restricciones y el mismo esquema DataTable resultante que la colección de esquemas Columns. La única diferencia es que AllColumns contiene columnas de conjunto de columnas que no se incluyen en la colección de esquemas Columns. Estas columnas se describen en la siguiente tabla.  
  
|ColumName|DataType|DESCRIPCIÓN|  
|----------------|--------------|-----------------|  
|TABLE_CATALOG|string|Catálogo de la tabla.|  
|TABLE_SCHEMA|string|Esquema que contiene la tabla.|  
|TABLE_NAME|string|Nombre de la tabla.|  
|COLUMN_NAME|string|Nombre de columna.|  
|ORDINAL_POSITION|Int32|Número de identificación de la columna.|  
|COLUMN_DEFAULT|string|Valor predeterminado de la columna.|  
|IS_NULLABLE|string|Capacidad de la columna de admitir valores NULL. Si esta columna permite NULL, devuelve YES. De lo contrario, devuelve NO.|  
|DATA_TYPE|string|Tipo de datos suministrado por el sistema.|  
|CHARACTER_MAXIMUM_LENGTH|Int32|Longitud máxima, en caracteres, de los datos binarios, datos de caracteres o datos de texto e imágenes. De lo contrario, devuelve NULL.|  
|CHARACTER_OCTET_LENGTH|Int32|Longitud máxima, en bytes, de los datos binarios, datos de caracteres o datos de texto e imágenes. De lo contrario, devuelve NULL.|  
|NUMERIC_PRECISION|Byte sin signo|Precisión de datos numéricos aproximados, datos numéricos exactos, datos enteros o datos monetarios. De lo contrario, devuelve NULL.|  
|NUMERIC_PRECISION_RADIX|Int16|Base de precisión de datos numéricos aproximados, datos numéricos exactos, datos enteros o datos monetarios. De lo contrario, devuelve NULL.|  
|NUMERIC_SCALE|Int32|Escala de datos numéricos aproximados, datos numéricos exactos, datos enteros o datos monetarios. De lo contrario, devuelve NULL.|  
|DATETIME_PRECISION|Int16|Código de subtipo para los tipos de datos datetime y de intervalo SQL-92. Para otros tipos de datos, devuelve NULL.|  
|CHARACTER_SET_CATALOG|string|Devuelve Master, para indicar la base de datos en la que se encuentra el juego de caracteres, si la columna es del tipo de datos de caracteres o de texto. De lo contrario, devuelve NULL.|  
|CHARACTER_SET_SCHEMA|string|Siempre devuelve NULL.|  
|CHARACTER_SET_NAME|string|Devuelve el nombre único del juego de caracteres si esta columna es del tipo de datos de caracteres o de texto. De lo contrario, devuelve NULL.|  
|COLLATION_CATALOG|string|Devuelve Master, para indicar la base de datos en la que se define la intercalación, si la columna es del tipo de datos de caracteres o de texto. De lo contrario, esta columna es NULL.|  
|IS_FILESTREAM|string|YES si la columna tiene el atributo FILESTREAM.<br /><br /> NO si la columna no tiene el atributo FILESTREAM.|  
|IS_SPARSE|string|YES si la columna es una columna dispersa.<br /><br /> NO si la columna no es una columna dispersa.|  
|IS_COLUMN_SET|string|YES si la columna es de conjunto de columnas.<br /><br /> NO si la columna no es de conjunto de columnas.|  
  
### <a name="columnsetcolumns-sql-server-2008"></a>ColumnSetColumns (SQL Server 2008)  
 A partir de .NET Framework versión 3.5 Service Pack 1 y SQL Server 2008, se ha agregado la colección de esquemas ColumnSetColumns para admitir columnas dispersas. ColumnSetColumns no se admite en versiones anteriores de .NET Framework y SQL Server. La colección de esquemas ColumnSetColumns devuelve el esquema de todas las columnas de un conjunto de columnas. Estas columnas se describen en la siguiente tabla.  
  
|ColumName|DataType|DESCRIPCIÓN|  
|----------------|--------------|-----------------|  
|TABLE_CATALOG|string|Catálogo de la tabla.|  
|TABLE_SCHEMA|string|Esquema que contiene la tabla.|  
|TABLE_NAME|string|Nombre de la tabla.|  
|COLUMN_NAME|string|Nombre de columna.|  
|ORDINAL_POSITION|Int32|Número de identificación de la columna.|  
|COLUMN_DEFAULT|string|Valor predeterminado de la columna.|  
|IS_NULLABLE|string|Capacidad de la columna de admitir valores NULL. Si esta columna permite NULL, devuelve YES. De lo contrario, devuelve NO.|  
|DATA_TYPE|string|Tipo de datos suministrado por el sistema.|  
|CHARACTER_MAXIMUM_LENGTH|Int32|Longitud máxima, en caracteres, de los datos binarios, datos de caracteres o datos de texto e imágenes. De lo contrario, devuelve NULL.|  
|CHARACTER_OCTET_LENGTH|Int32|Longitud máxima, en bytes, de los datos binarios, datos de caracteres o datos de texto e imágenes. De lo contrario, devuelve NULL.|  
|NUMERIC_PRECISION|Byte sin signo|Precisión de datos numéricos aproximados, datos numéricos exactos, datos enteros o datos monetarios. De lo contrario, devuelve NULL.|  
|NUMERIC_PRECISION_RADIX|Int16|Base de precisión de datos numéricos aproximados, datos numéricos exactos, datos enteros o datos monetarios. De lo contrario, devuelve NULL.|  
|NUMERIC_SCALE|Int32|Escala de datos numéricos aproximados, datos numéricos exactos, datos enteros o datos monetarios. De lo contrario, devuelve NULL.|  
|DATETIME_PRECISION|Int16|Código de subtipo para los tipos de datos datetime y de intervalo SQL-92. Para otros tipos de datos, devuelve NULL.|  
|CHARACTER_SET_CATALOG|string|Devuelve Master, para indicar la base de datos en la que se encuentra el juego de caracteres, si la columna es del tipo de datos de caracteres o de texto. De lo contrario, devuelve NULL.|  
|CHARACTER_SET_SCHEMA|string|Siempre devuelve NULL.|  
|CHARACTER_SET_NAME|string|Devuelve el nombre único del juego de caracteres si esta columna es del tipo de datos de caracteres o de texto. De lo contrario, devuelve NULL.|  
|COLLATION_CATALOG|string|Devuelve Master, para indicar la base de datos en la que se define la intercalación, si la columna es del tipo de datos de caracteres o de texto. De lo contrario, esta columna es NULL.|  
|IS_FILESTREAM|string|YES si la columna tiene el atributo FILESTREAM.<br /><br /> NO si la columna no tiene el atributo FILESTREAM.|  
|IS_SPARSE|string|YES si la columna es una columna dispersa.<br /><br /> NO si la columna no es una columna dispersa.|  
|IS_COLUMN_SET|string|YES si la columna es de conjunto de columnas.<br /><br /> NO si la columna no es de conjunto de columnas.|  
  
## <a name="users"></a>Usuarios  
  
|ColumName|DataType|DESCRIPCIÓN|  
|----------------|--------------|-----------------|  
|uid|Int16|Id. de usuario, único en esta base de datos. 1 es el propietario de la base de datos.|  
|user_name|string|Nombre de usuario o nombre del grupo, único en esta base de datos.|  
|createdate|DateTime|Fecha en que se agregó la cuenta.|  
|updatedate|DateTime|Fecha en que se modificó la cuenta por última vez.|  
  
## <a name="views"></a>Vistas  
  
|ColumName|DataType|DESCRIPCIÓN|  
|----------------|--------------|-----------------|  
|TABLE_CATALOG|string|Catálogo de la vista.|  
|TABLE_SCHEMA|string|Esquema que contiene la vista.|  
|TABLE_NAME|string|Nombre de la vista.|  
|CHECK_OPTION|string|Tipo de WITH CHECK OPTION. Es CASCADE si la vista original se creó mediante WITH CHECK OPTION. De lo contrario, se devuelve NONE.|  
|IS_UPDATABLE|string|Especifica si la vista se puede actualizar. Siempre devuelve NO.|  
  
## <a name="viewcolumns"></a>ViewColumns  
  
|ColumName|DataType|DESCRIPCIÓN|  
|----------------|--------------|-----------------|  
|VIEW_CATALOG|string|Catálogo de la vista.|  
|VIEW_SCHEMA|string|Esquema que contiene la vista.|  
|VIEW_NAME|string|Nombre de la vista.|  
|TABLE_CATALOG|string|Catálogo de la tabla asociada con esta vista.|  
|TABLE_SCHEMA|string|Esquema que contiene la tabla asociada con esta vista.|  
|TABLE_NAME|string|Nombre de la tabla asociada con esta vista. Tabla base.|  
|COLUMN_NAME|string|Nombre de columna.|  
  
## <a name="userdefinedtypes"></a>UserDefinedTypes  
  
|ColumName|DataType|DESCRIPCIÓN|  
|----------------|--------------|-----------------|  
|assembly_name|string|Nombre de archivo del ensamblado.|  
|udt_name|string|Nombre de clase del ensamblado.|  
|version_major|Object|Número de versión principal.|  
|version_minor|Object|Número de versión secundaria.|  
|version_build|Object|Número de compilación.|  
|version_revision|Object|Número de revisión.|  
|culture_info|Object|La referencia cultural asociada con este tipo definido por el usuario.|  
|public_key|Object|La clave pública que utiliza este ensamblado.|  
|is_fixed_length|Boolean|Especifica si la longitud del tipo es siempre igual que max_length.|  
|max_length|Int16|Longitud máxima del tipo en bytes.|  
|Create_Date|DateTime|Fecha en que se creó o registró el ensamblado.|  
|Permission_set_desc|string|Nombre descriptivo del conjunto de permisos y nivel de seguridad del ensamblado.|  
  
## <a name="see-also"></a>Vea también

- [Recuperación de información del esquema de la base de datos](retrieving-database-schema-information.md)
- [Información general sobre ADO.NET](ado-net-overview.md)
