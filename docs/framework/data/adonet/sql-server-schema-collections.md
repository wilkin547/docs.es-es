---
title: "Colecciones de esquemas SQL Server | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c6403cc3-d78b-4f85-bab1-ada7a3446ec5
caps.latest.revision: 5
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 5
---
# Colecciones de esquemas SQL Server
El proveedor de datos .NET Framework para SQL Server de Microsoft admite colecciones de esquemas adicionales, además de las colecciones de esquemas comunes.  Las colecciones de esquemas varían ligeramente respecto de la versión de SQL Server que está utilizando.  Para determinar la lista de colecciones de esquemas admitidas, llame al método **GetSchema** sin argumentos o con el nombre de colección de esquemas "MetaDataCollections".  Esto devolverá una <xref:System.Data.DataTable> con una lista de colecciones de esquemas admitidas, el número de restricciones que admite cada una y el número de partes de identificador que emplean.  
  
## Bases de datos  
  
|ColumName|DataType|Descripción|  
|---------------|--------------|-----------------|  
|database\_name|String|Nombre de la base de datos.|  
|Dbid|Int16|Id. de la base de datos.|  
|create\_date|DateTime|Fecha de creación de la base de datos.|  
  
## Claves externas  
  
|ColumName|DataType|Descripción|  
|---------------|--------------|-----------------|  
|constraint\_catalog|String|Catálogo al que pertenece la restricción.|  
|constraint\_schema|String|Esquema que contiene la restricción.|  
|constraint\_name|String|Nombre.|  
|table\_catalog|String|Nombre de la tabla de la que forma parte la restricción.|  
|table\_schema|String|Esquema que contiene la tabla.|  
|table\_name|String|Nombre de la tabla|  
|constraint\_type|String|Tipo de restricción.  Sólo se permite "FOREIGN KEY".|  
|is\_deferrable|String|Especifica si la restricción es aplazable.  Devuelve NO.|  
|initially\_deferred|String|Especifica si la restricción es inicialmente aplazable.  Devuelve NO.|  
  
## Índices  
  
|ColumName|DataType|Descripción|  
|---------------|--------------|-----------------|  
|constraint\_catalog|String|Catálogo al que pertenece el índice.|  
|constraint\_schema|String|Esquema que contiene el índice.|  
|constraint\_name|String|Nombre del índice.|  
|table\_catalog|String|Nombre de la tabla con la que está asociado el índice.|  
|table\_schema|String|Esquema que contiene la tabla con la que está asociado el índice.|  
|table\_name|String|Nombre de la tabla.|  
  
### Índices \(SQL Server 2008\)  
 Desde .NET Framework 3.5 Service Pack 1 y SQL Server 2008, se han agregado las columnas siguientes a la colección de esquemas Indexes para admitir nuevas columnas de tipos espaciales, de secuencia de archivos y dispersas.  Estas columnas no se admiten en versiones anteriores de .NET Framework y SQL Server.  
  
|ColumName|DataType|Descripción|  
|---------------|--------------|-----------------|  
|type\_desc|String|El tipo de índice debe ser uno de los valores siguientes:<br /><br /> -   HEAP<br />-   CLUSTERED<br />-   NONCLUSTERED<br />-   XML<br />-   SPATIAL|  
  
## IndexColumns  
  
|ColumName|DataType|Descripción|  
|---------------|--------------|-----------------|  
|constraint\_catalog|String|Catálogo al que pertenece el índice.|  
|constraint\_schema|String|Esquema que contiene el índice.|  
|constraint\_name|String|Nombre del índice.|  
|table\_catalog|String|Nombre de la tabla con la que está asociado el índice.|  
|table\_schema|String|Esquema que contiene la tabla con la que está asociado el índice.|  
|table\_name|String|Nombre de la tabla.|  
|column\_name|String|Nombre de la columna con la que está asociado el índice.|  
|ordinal\_position|Int32|Posición del índice de columna.|  
|KeyType|UInt16|Tipo del objeto.|  
  
## Procedimientos  
  
|ColumName|DataType|Descripción|  
|---------------|--------------|-----------------|  
|specific\_catalog|String|Nombre específico del catálogo.|  
|specific\_schema|String|Nombre específico del esquema.|  
|specific\_name|String|Nombre específico del catálogo.|  
|routine\_catalog|String|Catálogo al que pertenece el procedimiento almacenado.|  
|routine\_schema|String|Esquema que contiene el procedimiento almacenado.|  
|routine\_name|String|Nombre del procedimiento almacenado.|  
|routine\_type|String|Devuelve PROCEDURE en el caso de los procedimientos almacenados y FUNCTION en el caso de las funciones.|  
|created|DateTime|Hora a la que se creó el procedimiento.|  
|last\_altered|DateTime|La última vez que se modificó el procedimiento.|  
  
## Parámetros de procedimiento  
  
|ColumName|DataType|Descripción|  
|---------------|--------------|-----------------|  
|specific\_catalog|String|Nombre de catálogo del procedimiento del que forma parte este parámetro.|  
|specific\_schema|String|Esquema que contiene el procedimiento del que forma parte este parámetro.|  
|specific\_name|String|Nombre del procedimiento del que forma parte este parámetro.|  
|ordinal\_position|Int16|Posición ordinal del parámetro que empieza por 1.  Para el valor devuelto de un procedimiento, es un 0.|  
|parameter\_mode|String|Devuelve IN si es un parámetro de entrada, OUT si es un parámetro de salida e INOUT si es un parámetro de entrada y salida.|  
|is\_result|String|Devuelve YES si indica que el resultado del procedimiento es una función.  De lo contrario, devuelve NO.|  
|as\_locator|String|Devuelve YES si se declara como localizador.  De lo contrario, devuelve NO.|  
|parameter\_name|String|Nombre del parámetro.  NULL si corresponde al valor devuelto de una función.|  
|data\_type|String|Tipo de datos suministrado por el sistema.|  
|character\_maximum\_length|Int32|Longitud máxima, en caracteres, de los tipos de datos binarios o de caracteres.  De lo contrario, devuelve NULL.|  
|character\_octet\_length|Int32|Longitud máxima, en bytes, de los tipos de datos binarios o de caracteres.  De lo contrario, devuelve NULL.|  
|collation\_catalog|String|Nombre de catálogo de la intercalación del parámetro.  Si no es uno de los tipos de caracteres, devuelve NULL.|  
|collation\_schema|String|Siempre devuelve NULL.|  
|collation\_name|String|Nombre de la intercalación del parámetro.  Si no es uno de los tipos de caracteres, devuelve NULL.|  
|character\_set\_catalog|String|Nombre de catálogo del juego de caracteres del parámetro.  Si no es uno de los tipos de caracteres, devuelve NULL.|  
|character\_set\_schema|String|Siempre devuelve NULL.|  
|character\_set\_name|String|Nombre del juego de caracteres del parámetro.  Si no es uno de los tipos de caracteres, devuelve NULL.|  
|numeric\_precision|Byte|Precisión de datos numéricos aproximados, datos numéricos exactos, datos enteros o datos monetarios.  De lo contrario, devuelve NULL.|  
|numeric\_precision\_radix|Int16|Base de precisión de datos numéricos aproximados, datos numéricos exactos, datos enteros o datos monetarios.  De lo contrario, devuelve NULL.|  
|numeric\_scale|Int32|Escala de datos numéricos aproximados, datos numéricos exactos, datos enteros o datos monetarios.  De lo contrario, devuelve NULL.|  
|datetime\_precision|Int16|Precisión en segundos decimales si el tipo de parámetro es datetime o smalldatetime.  De lo contrario, devuelve NULL.|  
|interval\_type|String|NULL.  Reservado por SQL Server para uso futuro.|  
|interval\_precision|Int16|NULL.  Reservado por SQL Server para uso futuro.|  
  
## Tablas  
  
|ColumName|DataType|Descripción|  
|---------------|--------------|-----------------|  
|table\_catalog|String|Catálogo de la tabla.|  
|table\_schema|String|Esquema que contiene la tabla.|  
|table\_name|String|Nombre de la tabla.|  
|table\_type|String|Tipo de tabla.  Puede ser VIEW o BASE TABLE.|  
  
## Columnas  
  
|ColumName|DataType|Descripción|  
|---------------|--------------|-----------------|  
|table\_catalog|String|Catálogo de la tabla.|  
|table\_schema|String|Esquema que contiene la tabla.|  
|table\_name|String|Nombre de la tabla.|  
|column\_name|String|Nombre de columna.|  
|ordinal\_position|Int16|Número de identificación de la columna.|  
|column\_default|String|Valor predeterminado de la columna.|  
|is\_nullable|String|Capacidad de la columna de admitir valores NULL.  Si esta columna permite NULL, devuelve YES.  De lo contrario, devuelve NO.|  
|data\_type|String|Tipo de datos suministrado por el sistema.|  
|character\_maximum\_length|Int32 – Sql8, Int16 – Sql7|Longitud máxima, en caracteres, de los datos binarios, datos de caracteres o datos de texto e imágenes.  De lo contrario, devuelve NULL.|  
|character\_octet\_length|Int32 – SQL8, Int16 – Sql7|Longitud máxima, en bytes, de los datos binarios, datos de caracteres o datos de texto e imágenes.  De lo contrario, devuelve NULL.|  
|numeric\_precision|Byte sin signo|Precisión de datos numéricos aproximados, datos numéricos exactos, datos enteros o datos monetarios.  De lo contrario, devuelve NULL.|  
|numeric\_precision\_radix|Int16|Base de precisión de datos numéricos aproximados, datos numéricos exactos, datos enteros o datos monetarios.  De lo contrario, devuelve NULL.|  
|numeric\_scale|Int32|Escala de datos numéricos aproximados, datos numéricos exactos, datos enteros o datos monetarios.  De lo contrario, devuelve NULL.|  
|datetime\_precision|Int16|Código de subtipo para los tipos de datos datetime y de intervalo SQL\-92.  Para otros tipos de datos, devuelve NULL.|  
|character\_set\_catalog|String|Devuelve Master, para indicar la base de datos en la que se encuentra el juego de caracteres, si la columna es del tipo de datos de caracteres o de texto.  De lo contrario, devuelve NULL.|  
|character\_set\_schema|String|Siempre devuelve NULL.|  
|character\_set\_name|String|Devuelve el nombre único del juego de caracteres si esta columna es del tipo de datos de caracteres o de texto.  De lo contrario, devuelve NULL.|  
|collation\_catalog|String|Devuelve Master, para indicar la base de datos en la que se define la intercalación, si la columna es del tipo de datos de caracteres o de texto.  De lo contrario, esta columna es NULL.|  
  
### Columns \(SQL Server 2008\)  
 A partir de .NET Framework versión 3.5 Service Pack 1 y SQL Server 2008, se han agregado las columnas siguientes a la colección de esquemas Columns para admitir nuevas columnas de tipos espaciales, de secuencias de archivos y dispersas.  Estas columnas no se admiten en versiones anteriores de .NET Framework y SQL Server.  
  
|ColumName|DataType|Descripción|  
|---------------|--------------|-----------------|  
|IS\_FILESTREAM|String|YES si la columna tiene el atributo FILESTREAM.<br /><br /> NO si la columna no tiene el atributo FILESTREAM.|  
|IS\_SPARSE|String|YES si la columna es una columna dispersa.<br /><br /> NO si la columna no es una columna dispersa.|  
|IS\_COLUMN\_SET|String|YES si la columna es de conjunto de columnas.<br /><br /> NO si la columna no es de conjunto de columnas.|  
  
### AllColumns \(SQL Server 2008\)  
 A partir de .NET Framework versión 3.5 Service Pack 1 y SQL Server 2008, se ha agregado la colección de esquemas AllColumns para admitir columnas dispersas.  AllColumns no se admite en versiones anteriores de .NET Framework y SQL Server.  
  
 AllColumns tiene las mismas restricciones y el mismo esquema DataTable resultante que la colección de esquemas Columns.  La única diferencia es que AllColumns contiene columnas de conjunto de columnas que no se incluyen en la colección de esquemas Columns.  Estas columnas se describen en la siguiente tabla.  
  
|ColumName|DataType|Descripción|  
|---------------|--------------|-----------------|  
|table\_catalog|String|Catálogo de la tabla.|  
|table\_schema|String|Esquema que contiene la tabla.|  
|table\_name|String|Nombre de la tabla.|  
|column\_name|String|Nombre de columna.|  
|ordinal\_position|Int16|Número de identificación de la columna.|  
|column\_default|String|Valor predeterminado de la columna.|  
|is\_nullable|String|Capacidad de la columna de admitir valores NULL.  Si esta columna permite NULL, devuelve YES.  De lo contrario, devuelve NO.|  
|data\_type|String|Tipo de datos suministrado por el sistema.|  
|character\_maximum\_length|Int32|Longitud máxima, en caracteres, de los datos binarios, datos de caracteres o datos de texto e imágenes.  De lo contrario, devuelve NULL.|  
|character\_octet\_length|Int32|Longitud máxima, en bytes, de los datos binarios, datos de caracteres o datos de texto e imágenes.  De lo contrario, devuelve NULL.|  
|numeric\_precision|Byte sin signo|Precisión de datos numéricos aproximados, datos numéricos exactos, datos enteros o datos monetarios.  De lo contrario, devuelve NULL.|  
|numeric\_precision\_radix|Int16|Base de precisión de datos numéricos aproximados, datos numéricos exactos, datos enteros o datos monetarios.  De lo contrario, devuelve NULL.|  
|numeric\_scale|Int32|Escala de datos numéricos aproximados, datos numéricos exactos, datos enteros o datos monetarios.  De lo contrario, devuelve NULL.|  
|datetime\_precision|Int16|Código de subtipo para los tipos de datos datetime y de intervalo SQL\-92.  Para otros tipos de datos, devuelve NULL.|  
|character\_set\_catalog|String|Devuelve Master, para indicar la base de datos en la que se encuentra el juego de caracteres, si la columna es del tipo de datos de caracteres o de texto.  De lo contrario, devuelve NULL.|  
|character\_set\_schema|String|Siempre devuelve NULL.|  
|character\_set\_name|String|Devuelve el nombre único del juego de caracteres si esta columna es del tipo de datos de caracteres o de texto.  De lo contrario, devuelve NULL.|  
|collation\_catalog|String|Devuelve Master, para indicar la base de datos en la que se define la intercalación, si la columna es del tipo de datos de caracteres o de texto.  De lo contrario, esta columna es NULL.|  
|IS\_FILESTREAM|String|YES si la columna tiene el atributo FILESTREAM.<br /><br /> NO si la columna no tiene el atributo FILESTREAM.|  
|IS\_SPARSE|String|YES si la columna es una columna dispersa.<br /><br /> NO si la columna no es una columna dispersa.|  
|IS\_COLUMN\_SET|String|YES si la columna es de conjunto de columnas.<br /><br /> NO si la columna no es de conjunto de columnas.|  
  
### ColumnSetColumns \(SQL Server 2008\)  
 A partir de .NET Framework versión 3.5 Service Pack 1 y SQL Server 2008, se ha agregado la colección de esquemas ColumnSetColumns para admitir columnas dispersas.  ColumnSetColumns no se admite en versiones anteriores de .NET Framework y SQL Server.  La colección de esquemas ColumnSetColumns devuelve el esquema de todas las columnas de un conjunto de columnas.  Estas columnas se describen en la siguiente tabla.  
  
|ColumName|DataType|Descripción|  
|---------------|--------------|-----------------|  
|table\_catalog|String|Catálogo de la tabla.|  
|table\_schema|String|Esquema que contiene la tabla.|  
|table\_name|String|Nombre de la tabla.|  
|column\_name|String|Nombre de columna.|  
|ordinal\_position|Int16|Número de identificación de la columna.|  
|column\_default|String|Valor predeterminado de la columna.|  
|is\_nullable|String|Capacidad de la columna de admitir valores NULL.  Si esta columna permite NULL, devuelve YES.  De lo contrario, devuelve NO.|  
|data\_type|String|Tipo de datos suministrado por el sistema.|  
|character\_maximum\_length|Int32|Longitud máxima, en caracteres, de los datos binarios, datos de caracteres o datos de texto e imágenes.  De lo contrario, devuelve NULL.|  
|character\_octet\_length|Int32|Longitud máxima, en bytes, de los datos binarios, datos de caracteres o datos de texto e imágenes.  De lo contrario, devuelve NULL.|  
|numeric\_precision|Byte sin signo|Precisión de datos numéricos aproximados, datos numéricos exactos, datos enteros o datos monetarios.  De lo contrario, devuelve NULL.|  
|numeric\_precision\_radix|Int16|Base de precisión de datos numéricos aproximados, datos numéricos exactos, datos enteros o datos monetarios.  De lo contrario, devuelve NULL.|  
|numeric\_scale|Int32|Escala de datos numéricos aproximados, datos numéricos exactos, datos enteros o datos monetarios.  De lo contrario, devuelve NULL.|  
|datetime\_precision|Int16|Código de subtipo para los tipos de datos datetime y de intervalo SQL\-92.  Para otros tipos de datos, devuelve NULL.|  
|character\_set\_catalog|String|Devuelve Master, para indicar la base de datos en la que se encuentra el juego de caracteres, si la columna es del tipo de datos de caracteres o de texto.  De lo contrario, devuelve NULL.|  
|character\_set\_schema|String|Siempre devuelve NULL.|  
|character\_set\_name|String|Devuelve el nombre único del juego de caracteres si esta columna es del tipo de datos de caracteres o de texto.  De lo contrario, devuelve NULL.|  
|collation\_catalog|String|Devuelve Master, para indicar la base de datos en la que se define la intercalación, si la columna es del tipo de datos de caracteres o de texto.  De lo contrario, esta columna es NULL.|  
|IS\_FILESTREAM|String|YES si la columna tiene el atributo FILESTREAM.<br /><br /> NO si la columna no tiene el atributo FILESTREAM.|  
|IS\_SPARSE|String|YES si la columna es una columna dispersa.<br /><br /> NO si la columna no es una columna dispersa.|  
|IS\_COLUMN\_SET|String|YES si la columna es de conjunto de columnas.<br /><br /> NO si la columna no es de conjunto de columnas.|  
  
## Usuarios  
  
|ColumName|DataType|Descripción|  
|---------------|--------------|-----------------|  
|uid|Int16|Id. de usuario, único en esta base de datos.  1 es el propietario de la base de datos.|  
|name|String|Nombre de usuario o nombre del grupo, único en esta base de datos.|  
|createdate|DateTime|Fecha en que se agregó la cuenta.|  
|updatedate|DateTime|Fecha en que se modificó la cuenta por última vez.|  
  
## Vistas  
  
|ColumName|DataType|Descripción|  
|---------------|--------------|-----------------|  
|table\_catalog|String|Catálogo de la vista.|  
|table\_schema|String|Esquema que contiene la vista.|  
|table\_name|String|Nombre de la vista.|  
|check\_option|String|Tipo de WITH CHECK OPTION.  Es CASCADE si la vista original se creó mediante WITH CHECK OPTION.  De lo contrario, se devuelve NONE.|  
|is\_updatable|String|Especifica si la vista se puede actualizar.  Siempre devuelve NO.|  
  
## ViewColumns  
  
|ColumName|DataType|Descripción|  
|---------------|--------------|-----------------|  
|view\_catalog|String|Catálogo de la vista.|  
|view\_schema|String|Esquema que contiene la vista.|  
|view\_name|String|Nombre de la vista.|  
|table\_catalog|String|Catálogo de la tabla asociada con esta vista.|  
|table\_schema|String|Esquema que contiene la tabla asociada con esta vista.|  
|table\_name|String|Nombre de la tabla asociada con esta vista.  Tabla base.|  
|column\_name|String|Nombre de columna.|  
  
## UserDefinedTypes  
  
|ColumName|DataType|Descripción|  
|---------------|--------------|-----------------|  
|assembly\_name|String|Nombre de archivo del ensamblado.|  
|UDT\_name|String|Nombre de clase del ensamblado.|  
|version\_major|Objeto|Número de versión principal.|  
|version\_minor|Objeto|Número de versión secundaria.|  
|version\_build|Objeto|Número de compilación.|  
|version\_revision|Objeto|Número de revisión.|  
|Culture\_info|Objeto|La referencia cultural asociada con este tipo definido por el usuario.|  
|Public\_key|Objeto|La clave pública que utiliza este ensamblado.|  
|Is\_fixed\_length|Boolean|Especifica si la longitud del tipo es siempre igual que max\_length.|  
|max\_length|Int16|Longitud máxima del tipo en bytes.|  
|permission\_set\_desc|String|Nombre descriptivo del conjunto de permisos y nivel de seguridad del ensamblado.|  
|create\_date|DateTime|Fecha en que se creó o registró el ensamblado.|  
  
## Vea también  
 [Recuperar información de esquema de la base de datos](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)