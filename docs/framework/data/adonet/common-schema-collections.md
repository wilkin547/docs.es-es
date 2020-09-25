---
title: Colecciones de esquemas comunes
ms.date: 03/30/2017
ms.assetid: 50127ced-2ac8-4d7a-9cd1-5c98c655ff03
ms.openlocfilehash: f822de27e53554aba4011a701f59a8feda847c67
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203818"
---
# <a name="common-schema-collections"></a>Colecciones de esquemas comunes

Las colecciones de esquemas comunes son las colecciones de esquemas que implementa cada uno de los proveedores administrados de .NET Framework. Puede consultar un proveedor administrado de .NET Framework para determinar la lista de colecciones de esquemas admitidas llamando al método **GetSchema** sin argumentos o con el nombre de la colección de esquemas "MetaDataCollections". Esto devolverá una <xref:System.Data.DataTable> con una lista de colecciones de esquemas admitidas, el número de restricciones que admite cada una y el número de partes de identificador que emplean. Estas colecciones describen todas las columnas necesarias. Los proveedores pueden agregar más columnas si lo desean. Por ejemplo, `SqlClient` y `OracleClient` agregan ParameterName a la colección con restricciones.  
  
 Si un proveedor no puede determinar el valor de una columna necesaria, se devolverá NULL.  
  
 Para obtener más información sobre el uso de los métodos **GetSchema** , vea [GetSchema y colecciones de esquemas](getschema-and-schema-collections.md).  
  
## <a name="metadatacollections"></a>MetaDataCollections  

 Esta colección de esquemas expone información acerca de las colecciones de esquemas que admite el proveedor administrado de .NET Framework que se utiliza actualmente para conectarse a la base de datos.  
  
|ColumnName|DataType|Descripción|  
|----------------|--------------|-----------------|  
|CollectionName|string|Nombre de la colección que se va a pasar al método **GetSchema** para devolver la colección.|  
|NumberOfRestrictions|int|El número de restricciones que se pueden especificar para la colección.|  
|NumberOfIdentifierParts|int|El número de partes del identificador compuesto y nombre del objeto de base de datos. Por ejemplo, en SQL Server, sería 3 para las tablas y 4 para las columnas. En Oracle, sería 2 para las tablas y 3 para las columnas.|  
  
## <a name="datasourceinformation"></a>DataSourceInformation  

 Esta colección de esquemas expone información acerca del origen de datos al que actualmente está conectado el proveedor administrado de .NET Framework.  
  
|ColumnName|DataType|Descripción|  
|----------------|--------------|-----------------|  
|CompositeIdentifierSeparatorPattern|string|La expresión regular que va a hacer corresponder los separadores compuestos en un identificador compuesto. Por ejemplo, "\\". (por SQL Server) o " \@&#124;\\ ". (en Oracle).<br /><br /> Normalmente, un identificador compuesto es lo que se usa para el nombre de un objeto de base de datos, por ejemplo: pubs. DBO. Authors o pubs \@ dbo. authors.<br /><br /> Por SQL Server, utilice la expresión regular " \\ .". Para OracleClient, use " \@&#124;\\ .".<br /><br /> En ODBC, utilice Catalog_name_seperator.<br /><br /> En OLE DB, use DBLITERAL_CATALOG_SEPARATOR o DBLITERAL_SCHEMA_SEPARATOR.|  
|DataSourceProductName|string|El nombre del producto al que tiene acceso el proveedor, por ejemplo, "Oracle" o "SQLServer".|  
|DataSourceProductVersion|string|Indica la versión del producto al que tiene acceso el proveedor, en el formato nativo de los orígenes de datos y no en el formato de Microsoft.<br /><br /> En algunos casos, DataSourceProductVersion y DataSourceProductVersionNormalized tendrán el mismo valor. En el caso de OLE DB y ODBC, serán siempre iguales dado que se asignan a la misma llamada de función en la API nativa subyacente.|  
|DataSourceProductVersionNormalized|string|Una versión normalizada del origen de datos, de forma que se puede comparar con `String.Compare()`. Su formato es coherente con todas las versiones del proveedor para evitar que la versión 10 se clasifique entre la versión 1 y la versión 2.<br /><br /> Por ejemplo, el proveedor de Oracle usa un formato de "NN. NN. NN. NN. NN" para su versión normalizada, lo que hace que un origen de datos Oracle 8i devuelva "08.01.07.04.01". SQL Server usa el formato típico de Microsoft "NN. NN. nnnn".<br /><br /> En algunos casos, DataSourceProductVersion y DataSourceProductVersionNormalized tendrán el mismo valor. En el caso de OLE DB y ODBC, serán siempre iguales dado que se asignan a la misma llamada de función en la API nativa subyacente.|  
|GroupByBehavior|<xref:System.Data.Common.GroupByBehavior>|Especifica la relación entre las columnas de una cláusula GROUP BY y las columnas no agregadas de la lista de selección.|  
|IdentifierPattern|string|Expresión regular que crea una correspondencia con un identificador y con un valor de coincidencia del identificador. Por ejemplo, "[A-Za-z0-9_#$]".|  
|IdentifierCase|<xref:System.Data.Common.IdentifierCase>|Indica si los identificadores que no se incluyen entre comillas se usan con distinción de mayúsculas y minúsculas o no.|  
|OrderByColumnsInSelect|bool|Especifica si las columnas de una cláusula ORDER BY deben estar en la lista de selección. Un valor de true indica que es necesario que estén en la lista de selección; un valor de false indica que no es necesario que estén en la lista de selección.|  
|ParameterMarkerFormat|string|Una cadena de formato que representa cómo dar formato a un parámetro.<br /><br /> Si el origen de datos admite parámetros con nombre, el primer marcador de posición de esta cadena debe estar donde se debe dar formato al nombre del parámetro.<br /><br /> Por ejemplo, si el origen de datos espera que los parámetros tengan un nombre y tienen el prefijo ":", esto sería ": {0} ". Cuando se formatea con un nombre de parámetro de "p1", la cadena resultante es ":p1".<br /><br /> Si el origen de datos espera que los parámetros tengan como prefijo ' \@ ', pero los nombres ya los incluyen, esto sería ' {0} ' y el resultado de dar formato a un parámetro denominado " \@ P1" sería simplemente " \@ P1".<br /><br /> En el caso de los orígenes de datos que no esperan parámetros con nombre y esperan el uso del carácter '? ', la cadena de formato se puede especificar simplemente como '? ', lo que omitiría el nombre del parámetro. Por OLE DB, devolvemos '? '.|  
|ParameterMarkerPattern|string|Una expresión regular que crea una correspondencia con un marcador de parámetro. Tendrá un valor de correspondencia del nombre del parámetro, si lo hay.<br /><br /> Por ejemplo, si se admiten parámetros con nombre con un \@ carácter de cliente ' ' que se incluirá en el nombre del parámetro, esto sería: " \@ ([a-Za-z0-9_ $ #] *)".<br /><br /> Sin embargo, si se admiten parámetros con nombre con ': ' como carácter de inicialización y no forman parte del nombre del parámetro, esto sería: ":([A-Za-z0-9_ $ #] \* )".<br /><br /> Por supuesto, si el origen de datos no admite parámetros con nombre, esto sería simplemente "?".|  
|ParameterNameMaxLength|int|La longitud máxima del nombre del parámetro en caracteres. Visual Studio espera que si se admiten nombres de parámetros, el valor mínimo de la longitud máxima sea 30 caracteres.<br /><br /> Si el origen de datos no admite parámetros con nombre, esta propiedad devuelve cero.|  
|ParameterNamePattern|string|Una expresión regular que crea una correspondencia con los nombres de parámetros válidos. Según el origen de datos, existen diferentes reglas respecto a los caracteres que se pueden utilizar en los nombres de parámetros.<br /><br /> Visual Studio espera que si se admiten nombres de parámetros, los caracteres "\p{Lu}\p{Ll}\p{Lt}\p{Lm}\p{Lo}\p{Nl}\p{Nd}" son el juego mínimo de caracteres admitidos que son válidos en nombres de parámetros.|  
|QuotedIdentifierPattern|string|Una expresión regular que crea una correspondencia con un identificador incluido entre comillas y que tiene un valor de correspondencia del propio identificador sin las comillas. Por ejemplo, si el origen de datos utilizó comillas dobles para identificar identificadores entre comillas, sería: "(([^ \\ "] &#124;\\ " \\ ") *) ".|  
|QuotedIdentifierCase|<xref:System.Data.Common.IdentifierCase>|Indica si los identificadores incluidos entre comillas se tratan o no como con diferenciación entre mayúsculas y minúsculas.|  
|StatementSeparatorPattern|string|Una expresión regular que crea una correspondencia con el separador de instrucciones.|  
|StringLiteralPattern|string|Una expresión regular que crea una correspondencia con un literal de cadena y que tiene un valor de correspondencia del propio literal. Por ejemplo, si el origen de datos utilizó comillas simples para identificar cadenas, sería: "(' ([^ '] &#124; ' ') * ')" '|  
|SupportedJoinOperators|<xref:System.Data.Common.SupportedJoinOperators>|Especifica los tipos de instrucciones de unión SQL que admite el origen de datos.|  
  
## <a name="datatypes"></a>DataTypes  

 Esta colección de esquemas expone información acerca de los tipos de datos que admite la base de datos a la que está conectado actualmente el proveedor de datos de .NET Framework.  
  
|ColumnName|DataType|Descripción|  
|----------------|--------------|-----------------|  
|TypeName|string|El nombre del tipo de datos específico del proveedor.|  
|ProviderDbType|int|Valor de tipo específico del proveedor que se debe usar al especificar el tipo de un parámetro. Por ejemplo, SqlDbType.Money u OracleType.Blob.|  
|ColumnSize|long|La longitud de una columna o parámetro no numérico hace referencia a la longitud máxima o a la longitud que ha definido el proveedor para este tipo.<br /><br /> En datos de caracteres, es la longitud máxima o definida en unidades por el origen de datos. Oracle tiene el concepto de especificar una longitud y, a continuación, el tamaño de almacenamiento real en algunos tipos de datos de caracteres. Esto solo define la longitud en unidades en Oracle.<br /><br /> En los tipos de datos de fecha y hora, es la longitud de la representación de cadena (suponiendo la precisión máxima permitida del componente de segundos decimales).<br /><br /> Si el tipo de datos es numérico, se corresponde al límite superior de la precisión máxima del tipo de datos.|  
|CreateFormat|string|La cadena de formato que representa cómo agregar esta columna a una instrucción de definición de datos, como CREATE TABLE. Cada elemento de la matriz CreateParameter se debe representar con un "marcador de parámetro" en la cadena de formato.<br /><br /> Por ejemplo, el tipo de datos SQL DECIMAL necesita una precisión y una escala. En este caso, la cadena de formato sería "DECIMAL ( {0} , {1} )".|  
|CreateParameters|string|Los parámetros de creación que se deben especificar al crear una columna de este tipo de datos. Cada parámetro de creación se muestra en la cadena, separado por una coma en el orden en que se suministran.<br /><br /> Por ejemplo, el tipo de datos SQL DECIMAL necesita una precisión y una escala. En este caso, los parámetros de creación deben contener la cadena "precisión, escala".<br /><br /> En un comando de texto para crear una columna DECIMAL con una precisión de 10 y una escala de 2, el valor de la columna CreateFormat podría ser DECIMAL ( {0} , {1} ) "y la especificación de tipo completa sería decimal (10, 2).|  
|DataType|string|El nombre del tipo de datos de .NET Framework.|  
|IsAutoincrementable|bool|true: los valores de este tipo de datos pueden ser de incremento automático.<br /><br /> false: los valores de este tipo de datos podrían no ser de incremento automático.<br /><br /> Tenga en cuenta que esto simplemente indica si una columna de este tipo de datos podría ser de incremento automático, no que todas las columnas de este tipo lo sean.|  
|IsBestMatch|bool|true: el tipo de datos es la mejor coincidencia entre todos los tipos de datos del almacén de datos y el tipo de datos de .NET Framework que indica el valor de la columna DataType.<br /><br /> false: el tipo de datos no es la mejor coincidencia.<br /><br /> En cada conjunto de filas en las que el valor de la columna DataType sea el mismo, la columna IsBestMatch solo se establece en true en una fila.|  
|IsCaseSensitive|bool|true: el tipo de datos es de tipo carácter y distingue entre mayúsculas y minúsculas.<br /><br /> false: el tipo de datos no es de tipo carácter y no distingue entre mayúsculas y minúsculas.|  
|IsFixedLength|bool|true: las columnas de este tipo de datos creadas con el lenguaje de definición de datos (DDL) serán de longitud fija.<br /><br /> false: las columnas de este tipo de datos creadas con la DDL serán de longitud variable.<br /><br /> DBNull.Value: no se sabe si el proveedor asignará este campo con una columna de longitud fija o variable.|  
|IsFixedPrecisionScale|bool|true: el tipo de datos tiene una precisión y escala fijas.<br /><br /> false: el tipo de datos no tiene una precisión y escala fijas.|  
|IsLong|bool|true: el tipo de datos contiene datos muy largos; la definición de datos muy largos es específica del proveedor.<br /><br /> false: el tipo de datos no contiene datos muy largos.|  
|IsNullable|bool|true: el tipo de datos acepta valores NULL.<br /><br /> false: el tipo de datos no acepta valores NULL.<br /><br /> DBNull.Value: no se sabe si el tipo de datos acepta valores NULL.|  
|IsSearchable|bool|true: el tipo de datos se puede utilizar en una cláusula WHERE con cualquier operador, excepto con el predicado LIKE.<br /><br /> false: el tipo de datos no se puede utilizar en una cláusula WHERE con ningún operador, excepto con el predicado LIKE.|  
|IsSearchableWithLike|bool|true: el tipo de datos se puede utilizar con el predicado LIKE<br /><br /> false: el tipo de datos no se puede utilizar con el predicado LIKE.|  
|IsUnsigned|bool|true: el tipo de datos es sin signo.<br /><br /> false: el tipo de datos es con signo.<br /><br /> DBNull.Value: no es aplicable al tipo de datos.|  
|MaximumScale|short|Si el indicador de tipos es un tipo numérico, es el número máximo de dígitos permitidos a la derecha del separador decimal. De lo contrario, es DBNull.Value.|  
|MinimumScale|short|Si el indicador de tipos es un tipo numérico, es el número mínimo de dígitos permitidos a la derecha del separador decimal. De lo contrario, es DBNull.Value.|  
|IsConcurrencyType|bool|true: la base de datos actualiza el tipo de datos cada vez que cambia la fila y el valor de la columna es diferente de todos los valores anteriores.<br /><br /> false: la base de datos no actualiza el tipo de datos cada vez que cambia la fila.<br /><br /> DBNull.Value: la base de datos no admite este tipo de datos.|  
|IsLiteralSupported|bool|true: el tipo de datos se puede expresar como un literal.<br /><br /> false: el tipo de datos no se puede expresar como un literal.|  
|LiteralPrefix|string|El prefijo aplicado a un literal dado.|  
|LiteralSuffix|string|El sufijo aplicado a un literal dado.|  
|NativeDataType|String|NativeDataType es una columna específica de OLE DB para la exposición del tipo de datos de OLE DB.|  
  
## <a name="restrictions"></a>Restricciones  

 Esta colección de esquemas expone información acerca de las restricciones que admite el proveedor administrado de .NET Framework que está actualmente conectado a la base de datos.  
  
|ColumnName|DataType|Descripción|  
|----------------|--------------|-----------------|  
|CollectionName|string|El nombre de la colección a la que se aplican estas restricciones.|  
|RestrictionName|string|El nombre de la restricción en la colección.|  
|RestrictionDefault|string|ignorado.|  
|RestrictionNumber|int|La ubicación real de las restricciones de colecciones en la que se encuentra esta restricción en particular.|  
  
## <a name="reservedwords"></a>ReservedWords  

 Esta colección de esquemas expone información sobre las palabras que reserva la base de datos a la que está conectado actualmente el proveedor de datos de .NET Framework.  
  
|ColumnName|DataType|Descripción|  
|----------------|--------------|-----------------|  
|ReservedWord|string|Palabra reservada específica del proveedor.|  
  
## <a name="see-also"></a>Consulte también

- [Recuperar información del esquema de la base de datos](retrieving-database-schema-information.md)
- [GetSchema y colecciones de esquema](getschema-and-schema-collections.md)
- [Información general de ADO.NET](ado-net-overview.md)
