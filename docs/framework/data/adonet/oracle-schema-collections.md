---
description: 'Más información acerca de: colecciones de esquemas de Oracle'
title: Colecciones de esquemas de Oracle
ms.date: 03/30/2017
ms.assetid: 89a75de8-dee8-45e2-a97f-254d7e62e7e1
ms.openlocfilehash: c3093887c9359cbb170846c0ae425e0f77fc2580
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99672418"
---
# <a name="oracle-schema-collections"></a>Colecciones de esquemas de Oracle

El proveedor de datos Microsoft .NET Framework para Oracle admite, además de las colecciones de esquemas comunes, las siguientes colecciones de esquemas específicas:

- Columnas

- Índices

- IndexColumns

- Procedimientos

- Secuencias

- Sinónimos

- Tablas

- Usuarios

- Vistas

- Functions

- Paquetes

- PackageBodies

- Argumentos

- UniqueKeys

- PrimaryKeys

- ForeignKeys

- ForeignKeyColumns

- ProcedureParameters

## <a name="columns"></a>Columnas

|ColumnName|DataType|Descripción|
|----------------|--------------|-----------------|
|OWNER|String|Propietario de la tabla, vista o clúster.|
|TABLE_NAME|String|Nombre de la tabla, vista o clúster.|
|COLUMN_NAME|String|Nombre de la columna.|
|Id.|Decimal|Número de secuencia de la columna que se crea.|
|DATATYPE|String|Tipo de datos de la columna.|
|LENGTH|Decimal|Longitud de la columna en bytes.|
|PRECISION|Decimal|Precisión decimal del tipo de datos NUMBER; precisión binaria del tipo de datos FLOAT; NULL para todos los demás tipos de datos.|
|SCALE|Decimal|Dígitos a la derecha del separador decimal en un número.|
|NULLABLE|String|Especifica si una columna permite valores NULL. El valor es N si hay una restricción NOT NULL en la columna o si la columna forma parte de una restricción PRIMARY KEY.|

## <a name="indexes"></a>Índices

|ColumnName|DataType|Descripción|
|----------------|--------------|-----------------|
|OWNER|String|Propietario del índice|
|INDEX_NAME|String|Nombre del índice.|
|INDEX_TYPE|String|Tipo de índice (NORMAL, BITMAP, FUNCTION-BASED NORMAL, FUNCTION-BASED BITMAP o DOMAIN).|
|TABLE_OWNER|String|Propietario del objeto indizado.|
|TABLE_NAME|String|Nombre del objeto indizado.|
|TABLE_TYPE|String|Tipo del objeto indizado (por ejemplo, TABLE, CLUSTER).|
|UNIQUENESS|String|Si el índice es UNIQUE o NONUNIQUE.|
|COMPRESSION|String|Si el índice está ENABLED o DISABLED.|
|PREFIX_LENGTH|Decimal|Número de columnas en el prefijo de la clave de compresión.|
|TABLESPACE_NAME|String|Nombre del espacio de tabla que contiene el índice.|
|INI_TRANS|Decimal|Número inicial de transacciones.|
|MAX_TRANS|Decimal|Número máximo de transacciones.|
|INITIAL_EXTENT|Decimal|Tamaño de la extensión inicial.|
|NEXT_EXTENT|Decimal|Tamaño de las extensiones secundarias.|
|MIN_EXTENTS|Decimal|Número mínimo de extensiones permitidas en el segmento.|
|MAX_EXTENTS|Decimal|Número máximo de extensiones permitidas en el segmento.|
|PCT_INCREASE|Decimal|Porcentaje de aumento en el tamaño de la extensión.|
|PCT_THRESHOLD|Decimal|Porcentaje de umbral del espacio de bloque permitido por cada entrada de índice.|
|INCLUDE_COLUMN|Decimal|Id. de columna de la última columna que se incluirá en el índice de clave principal (sin desbordamiento) de la tabla organizada por índice. Esta columna corresponde a la columna COLUMN_ID de las vistas de diccionario de datos *_TAB_COLUMNS.|
|FREELISTS|Decimal|Número de listas de liberaciones de procesos asignadas a este segmento.|
|FREELIST_GROUPS|Decimal|Número de grupos de lista de liberaciones asignados a este segmento.|
|PCT_FREE|Decimal|Porcentaje mínimo de espacio disponible en un bloque.|
|LOGGING|String|Información de registro.|
|BLEVEL|Decimal|Nivel de b*-Tree: profundidad del índice desde su bloque raíz a sus bloques hoja. Una profundidad de 0 indica que el bloque raíz y el bloque hoja son iguales.|
|LEAF_BLOCKS|Decimal|Número de bloques hoja del índice|
|DISTINCT_KEYS|Decimal|Número de valores indizados distintos. En el caso de los índices que exigen las restricciones UNIQUE y PRIMARY KEY, este valor es igual al número de filas de la tabla (USER_TABLES.NUM_ROWS).|
|AVG_LEAF_BLOCKS_PER_KEY|Decimal|Número medio de bloques hoja en el que cada valor distinto en el índice aparece redondeado al entero más próximo. En los índices que exigen restricciones UNIQUE y PRIMARY KEY, este valor es siempre 1.|
|AVG_DATA_BLOCKS_PER_KEY|Decimal|Número medio de bloques de datos en la tabla a los que apunta un valor distinto en el índice redondeado al entero más cercano. Esta estadística es el número medio de bloques de datos que contienen filas con un valor determinado para las columnas indizadas.|
|CLUSTERING_FACTOR|Decimal|Indica la cantidad de orden de las filas de la tabla según los valores del índice.|
|STATUS|String|Si un índice no particionado es VALID o UNUSABLE.|
|NUM_ROWS|Decimal|Número de filas del índice.|
|SAMPLE_SIZE|Decimal|Tamaño de la muestra utilizada para analizar el índice.|
|LAST_ANALYZED|DateTime|Fecha de análisis más reciente de este índice.|
|DEGREE|String|Número de subprocesos por instancia para examinar el índice.|
|INSTANCES|String|Número de instancias a través de las que se van a examinar los índices.|
|PARTITIONED|String|Indica si este índice tiene particiones (sí &#124; NO).|
|TEMPORARY|String|Si el índice se encuentra en una tabla temporal.|
|GENERATED|String|Si el nombre del índice es generado por el sistema (Y&#124;N).|
|SECONDARY|String|Si el índice es un objeto secundario creado por el método ODCIIndexCreate del cartucho de datos Oracle9i (Y&#124;N).|
|BUFFER_POOL|String|Nombre del grupo de búferes predeterminado que se va a utilizar en los bloques de índice.|
|USER_STATS|String|Si el usuario introdujo directamente las estadísticas.|
|DURATION|String|Indica la duración de una tabla temporal: 1)SYS$SESSION: las filas se conservan el tiempo que dura la sesión, 2) SYS$TRANSACTION: las filas se eliminan después de COMMIT, 3) NULL para la Tabla permanente.|
|PCT_DIRECT_ACCESS|Decimal|En un índice secundario de una tabla organizada por índice, el porcentaje de filas con estimación VALID |
|ITYP_OWNER|String|En un índice de dominio, el propietario del tipo de índice.|
|ITYP_NAME|String|En un índice de dominio, el nombre del tipo de índice.|
|PARAMETERS|String|En un índice de dominio, la cadena de parámetros.|
|GLOBAL_STATS|String|En índices particionados, indica si se recopilaron las estadísticas mediante el análisis del índice como un todo (YES) o si se estimaron a partir de las estadísticas de las particiones y subparticiones del índice subyacente (NO).|
|DOMIDX_STATUS|String|Refleja el estado del índice de dominio. NULL: el índice especificado no es un índice de dominio. VALID: el índice es un índice de dominio válido. IDXTYP_INVLD: el tipo de índice de este índice de dominio no es válido.|
|DOMIDX_OPSTATUS|String|Refleja el estado de una operación que se ha realizado en un índice de dominio: NULL: el índice especificado no es un índice de dominio. VALID: la operación transcurrió sin errores. FAILED: la operación produjo un error.|
|FUNCIDX_STATUS|String|Indica el estado de un índice basado en funciones: NULL: no se trata de un índice basado en funciones, ENABLED: está habilitado el índice basado en funciones, DISABLED: está deshabilitado el índice basado en funciones.|
|JOIN_INDEX|String|Indica si es o no un índice de combinación.|

## <a name="indexcolumns"></a>IndexColumns

|ColumnName|DataType|Descripción|
|----------------|--------------|-----------------|
|INDEX_OWNER|String|Propietario del índice.|
|INDEX_NAME|String|Nombre del índice.|
|TABLE_OWNER|String|Propietario de la tabla o clúster.|
|TABLE_NAME|String|Nombre de la tabla o clúster.|
|COLUMN_NAME|String|Nombre o atributo de columna de la columna de tipo de objeto.|
|COLUMN_POSITION|Decimal|Posición de la columna o atributo en el índice.|
|COLUMN_LENGTH|Decimal|Longitud indizada de la columna.|
|CHAR_LENGTH|Decimal|Longitud máxima del punto de código de la columna.|
|DESCEND|String|Si la columna se ha clasificado en orden descendente.|

## <a name="procedures"></a>Procedimientos

|ColumnName|DataType|Descripción|
|----------------|--------------|-----------------|
|OWNER|String|Propietario del objeto.|
|OBJECT_NAME|String|Nombre del objeto.|
|SUBOBJECT_NAME|String|Nombre del subobjeto (por ejemplo, partición).|
|OBJECT_ID|Decimal|Número del objeto de diccionario del objeto.|
|DATA_OBJECT_ID|Decimal|Número del objeto de diccionario del segmento que contiene el objeto.|
|LAST_DDL_TIME|DateTime|Marca de tiempo de la última modificación del objeto resultante de un comando DDL (incluye concesiones y revocaciones).|
|timestamp|String|Marca de tiempo de la especificación del objeto (datos de caracteres).|
|STATUS|String|Estado del objeto (VALID, INVALID o N/A).|
|TEMPORARY|String|Si el objeto es temporal (la sesión actual solo podrá ver los datos colocados en el objeto en sí).|
|GENERATED|String|¿El nombre de este objeto fue generado por el sistema? (Y &#124; N).|
|SECONDARY|String|Si se trata de un objeto secundario creado por el método ODCIIndexCreate del cartucho de datos Oracle9i (Y &#124; N).|
|CREATED|DateTime|Fecha en que se creó el objeto.|

## <a name="sequences"></a>Secuencias

|ColumnName|DataType|Descripción|
|----------------|--------------|-----------------|
|SEQUENCE_OWNER|String|Nombre del propietario de la secuencia.|
|SEQUENCE_NAME|String|Nombre de la secuencia.|
|MIN_VALUE|Decimal|Valor mínimo de la secuencia.|
|MAX_VALUE|Decimal|Valor máximo de la secuencia.|
|INCREMENT_BY|Decimal|Valor en el que se incrementa la secuencia.|
|CYCLE_FLAG|String|¿Salta la secuencia al alcanzar el límite?|
|ORDER_FLAG|String|¿Los números de secuencia se generan en orden?|
|CACHE_SIZE|Decimal|Número de números de secuencia para almacenar en caché.|
|LAST_NUMBER|Decimal|Último número de secuencia escrito en el disco. Si una secuencia utiliza el almacenamiento en caché, el número escrito en el disco es el último número colocado en la caché de secuencias. Este número es probable que sea mayor que el último número de secuencia que se ha utilizado.|

## <a name="synonyms"></a>Sinónimos

|ColumnName|DataType|Descripción|
|----------------|--------------|-----------------|
|OWNER|String|Propietario del sinónimo.|
|SYNONYM_NAME|String|Nombre del sinónimo.|
|TABLE_OWNER|String|Propietario del objeto al que hace referencia el sinónimo.|
|TABLE_NAME|String|Nombre del objeto al que hace referencia el sinónimo.|
|DB_LINK|String|Nombre del vínculo de base de datos al que se hace referencia, si lo hay.|

## <a name="tables"></a>Tablas

|ColumnName|DataType|Descripción|
|----------------|--------------|-----------------|
|OWNER|String|Propietario de la tabla.|
|TABLE_NAME|String|Nombre de la tabla.|
|TYPE|String|Tipo de tabla.|

## <a name="users"></a>Usuarios

|ColumnName|DataType|Descripción|
|----------------|--------------|-----------------|
|NAME|String|Nombre del usuario.|
|Id.|Decimal|Número de id. del usuario.|
|CREATEDATE|DateTime|Fecha de creación del usuario.|

## <a name="views"></a>Vistas

|ColumnName|DataType|Descripción|
|----------------|--------------|-----------------|
|OWNER|String|Propietario de la vista.|
|VIEW_NAME|String|Nombre de la vista.|
|TEXT_LENGTH|Decimal|Longitud del texto de la vista.|
|TEXT|String|Texto de la vista.|
|TYPE_TEXT_LENGTH|Decimal|Longitud de la cláusula de tipo de la vista con establecimiento de tipos.|
|TYPE_TEXT|String|Cláusula de tipo de la vista con establecimiento de tipos.|
|OID_TEXT_LENGTH|Decimal|Longitud de la cláusula WITH OID de la vista con establecimiento de tipos.|
|OID_TEXT|String|Cláusula WITH OID de la vista con establecimiento de tipos.|
|VIEW_TYPE_OWNER|String|Propietario del tipo de la vista si ésta es una vista con establecimiento de tipos.|
|VIEW_TYPE|String|Tipo de la vista si esta es una vista con establecimiento de tipos.|
|SUPERVIEW_NAME|String|Nombre de la supervista.|

## <a name="functions"></a>Functions

|ColumnName|DataType|Descripción|
|----------------|--------------|-----------------|
|OWNER|String|Propietario del objeto.|
|OBJECT_NAME|String|Nombre del objeto.|
|SUBOBJECT_NAME|String|Nombre del subobjeto (por ejemplo, partición).|
|OBJECT_ID|Decimal|Número del objeto de diccionario del objeto.|
|DATA_OBJECT_ID|Decimal|Número del objeto de diccionario del segmento que contiene el objeto.|
|Object_Type|String|Tipo del objeto.|
|CREATED|DateTime|Fecha en que se creó el objeto.|
|LAST_DDL_TIME|DateTime|Marca de tiempo de la última modificación del objeto resultante de un comando DDL (incluye concesiones y revocaciones).|
|timestamp|String|Marca de tiempo de la especificación del objeto (datos de caracteres).|
|STATUS|String|Estado del objeto (VALID, INVALID o N/A).|
|TEMPORARY|String|Si el objeto es temporal (la sesión actual solo podrá ver los datos colocados en el objeto en sí).|
|GENERATED|String|¿El nombre de este objeto fue generado por el sistema? (Y &#124; N).|
|SECONDARY|String|Si se trata de un objeto secundario creado por el método ODCIIndexCreate del cartucho de datos Oracle9i (Y &#124; N).|

## <a name="packages"></a>Paquetes

|ColumnName|DataType|Descripción|
|----------------|--------------|-----------------|
|OWNER|String|Propietario del objeto.|
|OBJECT_NAME|String|Nombre del objeto.|
|SUBOBJECT_NAME|String|Nombre del subobjeto (por ejemplo, partición).|
|OBJECT_ID|Decimal|Número del objeto de diccionario del objeto.|
|DATA_OBJECT_ID|Decimal|Número del objeto de diccionario del segmento que contiene el objeto.|
|LAST_DDL_TIME|DateTime|Marca de tiempo de la última modificación del objeto resultante de un comando DDL (incluye concesiones y revocaciones).|
|timestamp|String|Marca de tiempo de la especificación del objeto (datos de caracteres).|
|STATUS|String|Estado del objeto (VALID, INVALID o N/A).|
|TEMPORARY|String|Si el objeto es temporal (la sesión actual solo podrá ver los datos colocados en el objeto en sí).|
|GENERATED|String|¿El nombre de este objeto fue generado por el sistema? (Y &#124; N).|
|SECONDARY|String|Si se trata de un objeto secundario creado por el método ODCIIndexCreate del cartucho de datos Oracle9i (Y &#124; N).|
|CREATED|DateTime|Fecha en que se creó el objeto.|

## <a name="packagebodies"></a>PackageBodies

|ColumnName|DataType|Descripción|
|----------------|--------------|-----------------|
|OWNER|String|Propietario del objeto.|
|OBJECT_NAME|String|Nombre del objeto.|
|SUBOBJECT_NAME|String|Nombre del subobjeto (por ejemplo, partición).|
|OBJECT_ID|Decimal|Número del objeto de diccionario del objeto.|
|DATA_OBJECT_ID|Decimal|Número del objeto de diccionario del segmento que contiene el objeto.|
|LAST_DDL_TIME|DateTime|Marca de tiempo de la última modificación del objeto resultante de un comando DDL (incluye concesiones y revocaciones).|
|timestamp|String|Marca de tiempo de la especificación del objeto (datos de caracteres).|
|STATUS|String|Estado del objeto (VALID, INVALID o N/A).|
|TEMPORARY|String|Si el objeto es temporal (la sesión actual solo podrá ver los datos colocados en el objeto en sí).|
|GENERATED|String|¿El nombre de este objeto fue generado por el sistema? (Y &#124; N).|
|SECONDARY|String|Si se trata de un objeto secundario creado por el método ODCIIndexCreate del cartucho de datos Oracle9i (Y &#124; N).|
|CREATED|DateTime|Fecha en que se creó el objeto.|

## <a name="arguments"></a>Argumentos

|ColumnName|DataType|Descripción|
|----------------|--------------|-----------------|
|OWNER|String|Nombre del propietario del objeto.|
|PACKAGE_NAME|String|Nombre del paquete.|
|OBJECT_NAME|String|Nombre del procedimiento o función.|
|ARGUMENT_NAME|String|Nombre del argumento.|
|POSITION|Decimal|Posición en la lista de argumentos, o NULL para el valor devuelto de la función.|
|SEQUENCE|Decimal|Secuencia de argumentos, incluidos todos los niveles de anidamiento.|
|DEFAULT_VALUE|String|Valor predeterminado del argumento.|
|DEFAULT_LENGTH|Decimal|Longitud del valor predeterminado del argumento.|
|IN_OUT|String|Dirección del argumento (IN, OUT o IN/OUT).|
|DATA_LENGTH|Decimal|Longitud de la columna en bytes.|
|DATA_PRECISION|Decimal|Longitud en dígitos decimales (NUMBER) o dígitos binarios (FLOAT).|
|DATA_SCALE|Decimal|Dígitos a la derecha del separador decimal en un número.|
|DATA_TYPE|String|Tipo de datos del argumento.|

## <a name="uniquekeys"></a>UniqueKeys

|ColumnName|DataType|Descripción|
|----------------|--------------|-----------------|
|OWNER|String|Propietario de la definición de restricción.|
|CONSTRAINT_NAME|String|Nombre de la definición de restricción.|
|TABLE_NAME|String|Nombre asociado con la tabla (o vista) con la definición de restricción.|
|SEARCH_CONDITION|String|Texto de la condición de búsqueda de una restricción de comprobación.|
|R_OWNER|String|Propietario de la tabla a la que se hace referencia en una restricción referencial.|
|R_CONSTRAINT_NAME|String|Nombre de la definición de restricción única de la tabla a la que se hace referencia.|
|DELETE_RULE|String|Regla de eliminación de una restricción referencial (CASCADE o NO ACTION).|
|STATUS|String|Estado de aplicación de la restricción (ENABLED o DISABLED).|
|DEFERRABLE|String|Si la restricción es aplazable.|
|VALIDATED|String|Si todos los datos respetan la restricción (VALIDATED o NOT VALIDATED).|
|GENERATED|String|Si el nombre de la restricción es un nombre generado por el sistema o por el usuario.|
|BAD|String|Un valor YES indica que esta restricción especifica un siglo de manera ambigua. Para evitar los errores derivados de esta ambigüedad, vuelva a escribir la restricción mediante la función TO_DATE con un año de cuatro cifras.|
|RELY|String|Si una restricción habilitada se exige o no se exige.|
|LAST_CHANGE|DateTime|La última vez que se habilitó o deshabilitó la restricción.|
|INDEX_OWNER|String|Nombre del usuario propietario del índice.|
|INDEX_NAME|String|Nombre del índice|

## <a name="primarykeys"></a>PrimaryKeys

|ColumnName|DataType|Descripción|
|----------------|--------------|-----------------|
|OWNER|String|Propietario de la definición de restricción.|
|CONSTRAINT_NAME|String|Nombre de la definición de restricción.|
|TABLE_NAME|String|Nombre asociado con la tabla (o vista) con la definición de restricción.|
|SEARCH_CONDITION|String|Texto de la condición de búsqueda de una restricción de comprobación.|
|R_OWNER|String|Propietario de la tabla a la que se hace referencia en una restricción referencial.|
|R_CONSTRAINT_NAME|String|Nombre de la definición de restricción única de la tabla a la que se hace referencia.|
|DELETE_RULE|String|Regla de eliminación de una restricción referencial (CASCADE o NO ACTION).|
|STATUS|String|Estado de aplicación de la restricción (ENABLED o DISABLED).|
|DEFERRABLE|String|Si la restricción es aplazable.|
|VALIDATED|String|Si todos los datos respetan la restricción (VALIDATED o NOT VALIDATED).|
|GENERATED|String|Si el nombre de la restricción es un nombre generado por el sistema o por el usuario.|
|BAD|String|Un valor YES indica que esta restricción especifica un siglo de manera ambigua. Para evitar los errores derivados de esta ambigüedad, vuelva a escribir la restricción mediante la función TO_DATE con un año de cuatro cifras.|
|RELY|String|Si una restricción habilitada se exige o no se exige.|
|LAST_CHANGE|DateTime|La última vez que se habilitó o deshabilitó la restricción.|
|INDEX_OWNER|String|Nombre del usuario propietario del índice.|
|INDEX_NAME|String|Nombre del índice.|

## <a name="foreignkeys"></a>ForeignKeys

|ColumnName|DataType|Descripción|
|----------------|--------------|-----------------|
|PRIMARY_KEY_CONSTRAINT_NAME|String|Nombre de la definición de restricción.|
|PRIMARY_KEY_OWNER|String|Propietario de la definición de restricción.|
|PRIMARY_KEY_TABLE_NAME|String|Nombre asociado con la tabla (o vista) con la definición de restricción.|
|FOREIGN_KEY_OWNER|String|Propietario de la definición de restricción.|
|FOREIGN_KEY_CONSTRAINT_NAME|String|Nombre de la definición de restricción.|
|FOREIGN_KEY_TABLE_NAME|String|Nombre asociado con la tabla (o vista) con la definición de restricción.|
|SEARCH_CONDITION|String|Texto de la condición de búsqueda de una restricción de comprobación.|
|R_OWNER|String|Propietario de la tabla a la que se hace referencia en una restricción referencial.|
|R_CONSTRAINT_NAME|String|Nombre de la definición de restricción única de la tabla a la que se hace referencia.|
|DELETE_RULE|String|Regla de eliminación de una restricción referencial (CASCADE o NO ACTION).|
|STATUS|String|Estado de aplicación de la restricción (ENABLED o DISABLED).|
|VALIDATED|String|Si todos los datos respetan la restricción (VALIDATED o NOT VALIDATED).|
|GENERATED|String|Si el nombre de la restricción es un nombre generado por el sistema o por el usuario.|
|RELY|String|Si una restricción habilitada se exige o no se exige.|
|LAST_CHANGE|DateTime|La última vez que se habilitó o deshabilitó la restricción.|
|INDEX_OWNER|String|Nombre del usuario propietario del índice.|
|INDEX_NAME|String|Nombre del índice.|

## <a name="foreignkeycolumns"></a>ForeignKeyColumns

|ColumnName|DataType|Descripción|
|----------------|--------------|-----------------|
|OWNER|String|Propietario de la definición de restricción.|
|CONSTRAINT_NAME|String|Nombre de la definición de restricción.|
|TABLE_NAME|String|Nombre de la tabla con la definición de restricción.|
|COLUMN_NAME|String|Nombre de la columna o atributo de la columna de tipo de objeto especificada en la definición de restricción.|
|POSITION|Decimal|Posición original de la columna o atributo en la definición del objeto.|

## <a name="procedureparameters"></a>ProcedureParameters

|ColumnName|DataType|Descripción|
|----------------|--------------|-----------------|
|OWNER|String|Propietario del objeto.|
|OBJECT_NAME|String|Nombre del procedimiento o función.|
|PACKAGE_NAME|String|Nombre del procedimiento o función.|
|OBJECT_ID|Decimal|Número de objeto del objeto.|
|OVERLOAD|String|Identificador único de sobrecarga.|
|ARGUMENT_NAME|String|Nombre del argumento.|
|POSITION|Decimal|Posición en la lista de argumentos, o NULL para un valor devuelto de la función.|
|SEQUENCE|Decimal|Secuencia de argumentos, incluidos todos los niveles de anidamiento.|
|DATA_LEVEL|Decimal|Profundidad de anidamiento del argumento en los tipos compuestos|
|DATA_TYPE|String|Tipo de datos del argumento.|
|DEFAULT_VALUE|String|Valor predeterminado del argumento.|
|DEFAULT_LENGTH|Decimal|Longitud del valor predeterminado del argumento.|
|IN_OUT|String|Dirección del argumento (IN, OUT o IN/OUT).|
|DATA_LENGTH|Decimal|Longitud de la columna (en bytes).|
|DATA_PRECISION|Decimal|Longitud en dígitos decimales (NUMBER) o dígitos binarios (FLOAT).|
|DATA_SCALE|Decimal|Dígitos a la derecha del separador decimal en un número.|
|RADIX|Decimal|Base de argumento de un número.|
|CHARACTER_SET_NAME|String|Nombre del juego de caracteres del argumento.|
|TYPE_OWNER|String|Propietario del tipo del argumento.|
|TYPE_NAME|String|Nombre del tipo del argumento. Si el tipo es un tipo local de paquete (es decir, se declara en una especificación de paquete), entonces esta columna muestra el nombre del paquete.|
|TYPE_SUBNAME|String|Solo es relevante para los tipos locales de paquete. Muestra el nombre del tipo declarado en el paquete identificado en la columna TYPE_NAME.|
|TYPE_LINK|String|Solo es relevante para los tipos locales de paquete cuando el paquete identificado en la columna TYPE_NAME es un paquete remoto. Esta columna muestra el vínculo de base de datos utilizado para hacer referencia al paquete remoto.|
|PLS_TYPE|String|En argumentos numéricos, el nombre del tipo PL/SQL del argumento. De lo contrario, es NULL.|
|CHAR_LENGTH|Decimal|Límite de caracteres de los tipos de datos de cadena.|
|CHAR_USED|String|Indica si el límite de bytes (B) o el límite de caracteres (C) es oficial para la cadena.|

## <a name="see-also"></a>Vea también

- [Información general de ADO.NET](ado-net-overview.md)
