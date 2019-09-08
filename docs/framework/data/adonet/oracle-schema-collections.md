---
title: Colecciones de esquemas de Oracle
ms.date: 03/30/2017
ms.assetid: 89a75de8-dee8-45e2-a97f-254d7e62e7e1
ms.openlocfilehash: cb91a90ae7323283556954caa401646a2063a37e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783296"
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

- Funciones

- Paquetes

- PackageBodies

- Argumentos

- UniqueKeys

- PrimaryKeys

- ForeignKeys

- ForeignKeyColumns

- ProcedureParameters

## <a name="columns"></a>Columnas

|ColumName|DataType|DESCRIPCIÓN|
|----------------|--------------|-----------------|
|OWNER|string|Propietario de la tabla, vista o clúster.|
|TABLE_NAME|string|Nombre de la tabla, vista o clúster.|
|COLUMN_NAME|string|Nombre de columna.|
|ID|Decimal|Número de secuencia de la columna que se crea.|
|DATATYPE|string|Tipo de datos de la columna.|
|LENGTH|Decimal|Longitud de la columna en bytes.|
|PRECISION|Decimal|Precisión decimal del tipo de datos NUMBER; precisión binaria del tipo de datos FLOAT; NULL para todos los demás tipos de datos.|
|SCALE|Decimal|Dígitos a la derecha del separador decimal en un número.|
|NULLABLE|string|Especifica si una columna permite valores NULL. El valor es N si hay una restricción NOT NULL en la columna o si la columna forma parte de una restricción PRIMARY KEY.|

## <a name="indexes"></a>Índices

|ColumName|DataType|DESCRIPCIÓN|
|----------------|--------------|-----------------|
|OWNER|string|Propietario del índice|
|INDEX_NAME|string|Nombre del índice.|
|INDEX_TYPE|string|Tipo de índice (NORMAL, BITMAP, FUNCTION-BASED NORMAL, FUNCTION-BASED BITMAP o DOMAIN).|
|TABLE_OWNER|string|Propietario del objeto indizado.|
|TABLE_NAME|string|Nombre del objeto indizado.|
|TABLE_TYPE|string|Tipo del objeto indizado (por ejemplo, TABLE, CLUSTER).|
|UNIQUENESS|string|Si el índice es UNIQUE o NONUNIQUE.|
|COMPRESSION|string|Si el índice está ENABLED o DISABLED.|
|PREFIX_LENGTH|Decimal|Número de columnas en el prefijo de la clave de compresión.|
|TABLESPACE_NAME|string|Nombre del espacio de tabla que contiene el índice.|
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
|LOGGING|string|Información de registro.|
|BLEVEL|Decimal|Nivel de b*-Tree: profundidad del índice desde su bloque raíz a sus bloques hoja. Una profundidad de 0 indica que el bloque raíz y el bloque hoja son iguales.|
|LEAF_BLOCKS|Decimal|Número de bloques hoja del índice|
|DISTINCT_KEYS|Decimal|Número de valores indizados distintos. En el caso de los índices que exigen las restricciones UNIQUE y PRIMARY KEY, este valor es igual al número de filas de la tabla (USER_TABLES.NUM_ROWS).|
|AVG_LEAF_BLOCKS_PER_KEY|Decimal|Número medio de bloques hoja en el que cada valor distinto en el índice aparece redondeado al entero más próximo. En los índices que exigen restricciones UNIQUE y PRIMARY KEY, este valor es siempre 1.|
|AVG_DATA_BLOCKS_PER_KEY|Decimal|Número medio de bloques de datos en la tabla a los que apunta un valor distinto en el índice redondeado al entero más cercano. Esta estadística es el número medio de bloques de datos que contienen filas con un valor determinado para las columnas indizadas.|
|CLUSTERING_FACTOR|Decimal|Indica la cantidad de orden de las filas de la tabla según los valores del índice.|
|STATUS|string|Si un índice no particionado es VALID o UNUSABLE.|
|NUM_ROWS|Decimal|Número de filas en el índice.|
|SAMPLE_SIZE|Decimal|Tamaño de la muestra utilizada para analizar el índice.|
|LAST_ANALYZED|DateTime|Fecha de análisis más reciente de este índice.|
|DEGREE|string|Número de subprocesos por instancia para examinar el índice.|
|INSTANCES|string|Número de instancias a través de las que se van a examinar los índices.|
|PARTITIONED|string|Indica si este índice tiene particiones ( &#124; sí no).|
|TEMPORARY|string|Si el índice se encuentra en una tabla temporal.|
|GENERATED|string|Indica si el nombre del índice es generado por el sistema&#124;(Y N).|
|SECONDARY|string|Si el índice es un objeto secundario creado por el método ODCIIndexCreate del cartucho de datos Oracle9i (Y&#124;N).|
|BUFFER_POOL|string|Nombre del grupo de búferes predeterminado que se va a utilizar en los bloques de índice.|
|USER_STATS|string|Si el usuario introdujo directamente las estadísticas.|
|DURATION|string|Indica la duración de una tabla temporal. 1) SYS $ SESSION: las filas se conservan mientras dure la sesión, 2) SYS $ TRANSACTION: las filas se eliminan después de COMMIT, 3) null para la tabla permanente.|
|PCT_DIRECT_ACCESS|Decimal|En un índice secundario de una tabla organizada por índice, el porcentaje de filas con estimación VALID|
|ITYP_OWNER|string|En un índice de dominio, el propietario del tipo de índice.|
|ITYP_NAME|string|En un índice de dominio, el nombre del tipo de índice.|
|PARAMETERS|string|En un índice de dominio, la cadena de parámetros.|
|GLOBAL_STATS|string|En índices particionados, indica si se recopilaron las estadísticas mediante el análisis del índice como un todo (YES) o si se estimaron a partir de las estadísticas de las particiones y subparticiones del índice subyacente (NO).|
|DOMIDX_STATUS|string|Refleja el estado del índice de dominio. NULL: el índice especificado no es un índice de dominio. VALID: el índice es un índice de dominio válido. IDXTYP_INVLD: el tipo de índice de este índice de dominio no es válido.|
|DOMIDX_OPSTATUS|string|Refleja el estado de una operación que se realizó en un índice de dominio: NULL: el índice especificado no es un índice de dominio. VALID: la operación transcurrió sin errores. FAILED: la operación produjo un error.|
|FUNCIDX_STATUS|string|Indica el estado de un índice basado en función: NULL: este no es un índice basado en función, ENABLED: el índice basado en función está habilitado, Disabled: el índice basado en función está deshabilitado.|
|JOIN_INDEX|string|Indica si es o no un índice de combinación.|

## <a name="indexcolumns"></a>IndexColumns

|ColumName|DataType|DESCRIPCIÓN|
|----------------|--------------|-----------------|
|INDEX_OWNER|string|Propietario del índice.|
|INDEX_NAME|string|Nombre del índice.|
|TABLE_OWNER|string|Propietario de la tabla o clúster.|
|TABLE_NAME|string|Nombre de la tabla o clúster.|
|COLUMN_NAME|string|Nombre o atributo de columna de la columna de tipo de objeto.|
|COLUMN_POSITION|Decimal|Posición de la columna o atributo en el índice.|
|COLUMN_LENGTH|Decimal|Longitud indizada de la columna.|
|CHAR_LENGTH|Decimal|Longitud máxima del punto de código de la columna.|
|DESCEND|string|Si la columna se ha clasificado en orden descendente.|

## <a name="procedures"></a>Procedimientos

|ColumName|DataType|DESCRIPCIÓN|
|----------------|--------------|-----------------|
|OWNER|string|Propietario del objeto.|
|OBJECT_NAME|string|Nombre del objeto.|
|SUBOBJECT_NAME|string|Nombre del subobjeto (por ejemplo, partición).|
|OBJECT_ID|Decimal|Número del objeto de diccionario del objeto.|
|DATA_OBJECT_ID|Decimal|Número del objeto de diccionario del segmento que contiene el objeto.|
|LAST_DDL_TIME|DateTime|Marca de tiempo de la última modificación del objeto resultante de un comando DDL (incluye concesiones y revocaciones).|
|TIMESTAMP|string|Marca de tiempo de la especificación del objeto (datos de caracteres).|
|STATUS|string|Estado del objeto (VALID, INVALID o N/A).|
|TEMPORARY|string|Si el objeto es temporal (la sesión actual solo podrá ver los datos colocados en el objeto en sí).|
|GENERATED|string|¿El nombre de este objeto fue generado por el sistema? (Y &#124; N).|
|SECONDARY|string|Indica si se trata de un objeto secundario creado por el método ODCIIndexCreate del cartucho de datos Oracle9i &#124; (Y N).|
|CREATED|DateTime|Fecha en que se creó el objeto.|

## <a name="sequences"></a>Secuencias

|ColumName|DataType|DESCRIPCIÓN|
|----------------|--------------|-----------------|
|SEQUENCE_OWNER|string|Nombre del propietario de la secuencia.|
|SEQUENCE_NAME|string|Nombre de la secuencia.|
|MIN_VALUE|Decimal|Valor mínimo de la secuencia.|
|MAX_VALUE|Decimal|Valor máximo de la secuencia.|
|INCREMENT_BY|Decimal|Valor en el que se incrementa la secuencia.|
|CYCLE_FLAG|string|¿Salta la secuencia al alcanzar el límite?|
|ORDER_FLAG|string|¿Los números de secuencia se generan en orden?|
|CACHE_SIZE|Decimal|Número de números de secuencia para almacenar en caché.|
|LAST_NUMBER|Decimal|Último número de secuencia escrito en el disco. Si una secuencia utiliza el almacenamiento en caché, el número escrito en el disco es el último número colocado en la caché de secuencias. Este número es probable que sea mayor que el último número de secuencia que se ha utilizado.|

## <a name="synonyms"></a>Sinónimos

|ColumName|DataType|DESCRIPCIÓN|
|----------------|--------------|-----------------|
|OWNER|string|Propietario del sinónimo.|
|SYNONYM_NAME|string|Nombre del sinónimo.|
|TABLE_OWNER|string|Propietario del objeto al que hace referencia el sinónimo.|
|TABLE_NAME|string|Nombre del objeto al que hace referencia el sinónimo.|
|DB_LINK|string|Nombre del vínculo de base de datos al que se hace referencia, si lo hay.|

## <a name="tables"></a>Tablas

|ColumName|DataType|DESCRIPCIÓN|
|----------------|--------------|-----------------|
|OWNER|string|Propietario de la tabla.|
|TABLE_NAME|string|Nombre de la tabla.|
|TYPE|string|Tipo de tabla.|

## <a name="users"></a>Usuarios

|ColumName|DataType|DESCRIPCIÓN|
|----------------|--------------|-----------------|
|NAME|string|Nombre del usuario.|
|ID|Decimal|Número de id. del usuario.|
|CREATEDATE|DateTime|Fecha de creación del usuario.|

## <a name="views"></a>Vistas

|ColumName|DataType|DESCRIPCIÓN|
|----------------|--------------|-----------------|
|OWNER|string|Propietario de la vista.|
|VIEW_NAME|string|Nombre de la vista.|
|TEXT_LENGTH|Decimal|Longitud del texto de la vista.|
|TEXT|string|Texto de la vista.|
|TYPE_TEXT_LENGTH|Decimal|Longitud de la cláusula de tipo de la vista con establecimiento de tipos.|
|TYPE_TEXT|string|Cláusula de tipo de la vista con establecimiento de tipos.|
|OID_TEXT_LENGTH|Decimal|Longitud de la cláusula WITH OID de la vista con establecimiento de tipos.|
|OID_TEXT|string|Cláusula WITH OID de la vista con establecimiento de tipos.|
|VIEW_TYPE_OWNER|string|Propietario del tipo de la vista si ésta es una vista con establecimiento de tipos.|
|VIEW_TYPE|string|Tipo de la vista si esta es una vista con establecimiento de tipos.|
|SUPERVIEW_NAME|string|Nombre de la supervista.|

## <a name="functions"></a>Funciones

|ColumName|DataType|DESCRIPCIÓN|
|----------------|--------------|-----------------|
|OWNER|string|Propietario del objeto.|
|OBJECT_NAME|string|Nombre del objeto.|
|SUBOBJECT_NAME|string|Nombre del subobjeto (por ejemplo, partición).|
|OBJECT_ID|Decimal|Número del objeto de diccionario del objeto.|
|DATA_OBJECT_ID|Decimal|Número del objeto de diccionario del segmento que contiene el objeto.|
|OBJECT_TYPE|string|Tipo del objeto.|
|CREATED|DateTime|Fecha en que se creó el objeto.|
|LAST_DDL_TIME|DateTime|Marca de tiempo de la última modificación del objeto resultante de un comando DDL (incluye concesiones y revocaciones).|
|TIMESTAMP|string|Marca de tiempo de la especificación del objeto (datos de caracteres).|
|STATUS|string|Estado del objeto (VALID, INVALID o N/A).|
|TEMPORARY|string|Si el objeto es temporal (la sesión actual solo podrá ver los datos colocados en el objeto en sí).|
|GENERATED|string|¿El nombre de este objeto fue generado por el sistema? (Y &#124; N).|
|SECONDARY|string|Indica si se trata de un objeto secundario creado por el método ODCIIndexCreate del cartucho de datos Oracle9i &#124; (Y N).|

## <a name="packages"></a>Paquetes

|ColumName|DataType|DESCRIPCIÓN|
|----------------|--------------|-----------------|
|OWNER|string|Propietario del objeto.|
|OBJECT_NAME|string|Nombre del objeto.|
|SUBOBJECT_NAME|string|Nombre del subobjeto (por ejemplo, partición).|
|OBJECT_ID|Decimal|Número del objeto de diccionario del objeto.|
|DATA_OBJECT_ID|Decimal|Número del objeto de diccionario del segmento que contiene el objeto.|
|LAST_DDL_TIME|DateTime|Marca de tiempo de la última modificación del objeto resultante de un comando DDL (incluye concesiones y revocaciones).|
|TIMESTAMP|string|Marca de tiempo de la especificación del objeto (datos de caracteres).|
|STATUS|string|Estado del objeto (VALID, INVALID o N/A).|
|TEMPORARY|string|Si el objeto es temporal (la sesión actual solo podrá ver los datos colocados en el objeto en sí).|
|GENERATED|string|¿El nombre de este objeto fue generado por el sistema? (Y &#124; N).|
|SECONDARY|string|Indica si se trata de un objeto secundario creado por el método ODCIIndexCreate del cartucho de datos Oracle9i &#124; (Y N).|
|CREATED|DateTime|Fecha en que se creó el objeto.|

## <a name="packagebodies"></a>PackageBodies

|ColumName|DataType|DESCRIPCIÓN|
|----------------|--------------|-----------------|
|OWNER|string|Propietario del objeto.|
|OBJECT_NAME|string|Nombre del objeto.|
|SUBOBJECT_NAME|string|Nombre del subobjeto (por ejemplo, partición).|
|OBJECT_ID|Decimal|Número del objeto de diccionario del objeto.|
|DATA_OBJECT_ID|Decimal|Número del objeto de diccionario del segmento que contiene el objeto.|
|LAST_DDL_TIME|DateTime|Marca de tiempo de la última modificación del objeto resultante de un comando DDL (incluye concesiones y revocaciones).|
|TIMESTAMP|string|Marca de tiempo de la especificación del objeto (datos de caracteres).|
|STATUS|string|Estado del objeto (VALID, INVALID o N/A).|
|TEMPORARY|string|Si el objeto es temporal (la sesión actual solo podrá ver los datos colocados en el objeto en sí).|
|GENERATED|string|¿El nombre de este objeto fue generado por el sistema? (Y &#124; N).|
|SECONDARY|string|Indica si se trata de un objeto secundario creado por el método ODCIIndexCreate del cartucho de datos Oracle9i &#124; (Y N).|
|CREATED|DateTime|Fecha en que se creó el objeto.|

## <a name="arguments"></a>Argumentos

|ColumName|DataType|DESCRIPCIÓN|
|----------------|--------------|-----------------|
|OWNER|string|Nombre del propietario del objeto.|
|PACKAGE_NAME|string|Nombre del paquete.|
|OBJECT_NAME|string|Nombre del procedimiento o función.|
|ARGUMENT_NAME|string|Nombre del argumento.|
|POSITION|Decimal|Posición en la lista de argumentos, o NULL para el valor devuelto de la función.|
|SEQUENCE|Decimal|Secuencia de argumentos, incluidos todos los niveles de anidamiento.|
|DEFAULT_VALUE|string|Valor predeterminado del argumento.|
|DEFAULT_LENGTH|Decimal|Longitud del valor predeterminado del argumento.|
|IN_OUT|string|Dirección del argumento (IN, OUT o IN/OUT).|
|DATA_LENGTH|Decimal|Longitud de la columna en bytes.|
|DATA_PRECISION|Decimal|Longitud en dígitos decimales (NUMBER) o dígitos binarios (FLOAT).|
|DATA_SCALE|Decimal|Dígitos a la derecha del separador decimal en un número.|
|DATA_TYPE|string|Tipo de datos del argumento.|

## <a name="uniquekeys"></a>UniqueKeys

|ColumName|DataType|DESCRIPCIÓN|
|----------------|--------------|-----------------|
|OWNER|string|Propietario de la definición de restricción.|
|CONSTRAINT_NAME|string|Nombre de la definición de restricción.|
|TABLE_NAME|string|Nombre asociado con la tabla (o vista) con la definición de restricción.|
|SEARCH_CONDITION|string|Texto de la condición de búsqueda de una restricción de comprobación.|
|R_OWNER|string|Propietario de la tabla a la que se hace referencia en una restricción referencial.|
|R_CONSTRAINT_NAME|string|Nombre de la definición de restricción única de la tabla a la que se hace referencia.|
|DELETE_RULE|string|Regla de eliminación de una restricción referencial (CASCADE o NO ACTION).|
|STATUS|string|Estado de aplicación de la restricción (ENABLED o DISABLED).|
|DEFERRABLE|string|Si la restricción es aplazable.|
|VALIDATED|string|Si todos los datos respetan la restricción (VALIDATED o NOT VALIDATED).|
|GENERATED|string|Si el nombre de la restricción es un nombre generado por el sistema o por el usuario.|
|BAD|string|Un valor YES indica que esta restricción especifica un siglo de manera ambigua. Para evitar los errores derivados de esta ambigüedad, vuelva a escribir la restricción mediante la función TO_DATE con un año de cuatro cifras.|
|RELY|string|Si una restricción habilitada se exige o no se exige.|
|LAST_CHANGE|DateTime|La última vez que se habilitó o deshabilitó la restricción.|
|INDEX_OWNER|string|Nombre del usuario propietario del índice.|
|INDEX_NAME|string|Nombre del índice|

## <a name="primarykeys"></a>PrimaryKeys

|ColumName|DataType|DESCRIPCIÓN|
|----------------|--------------|-----------------|
|OWNER|string|Propietario de la definición de restricción.|
|CONSTRAINT_NAME|string|Nombre de la definición de restricción.|
|TABLE_NAME|string|Nombre asociado con la tabla (o vista) con la definición de restricción.|
|SEARCH_CONDITION|string|Texto de la condición de búsqueda de una restricción de comprobación.|
|R_OWNER|string|Propietario de la tabla a la que se hace referencia en una restricción referencial.|
|R_CONSTRAINT_NAME|string|Nombre de la definición de restricción única de la tabla a la que se hace referencia.|
|DELETE_RULE|string|Regla de eliminación de una restricción referencial (CASCADE o NO ACTION).|
|STATUS|string|Estado de aplicación de la restricción (ENABLED o DISABLED).|
|DEFERRABLE|string|Si la restricción es aplazable.|
|VALIDATED|string|Si todos los datos respetan la restricción (VALIDATED o NOT VALIDATED).|
|GENERATED|string|Si el nombre de la restricción es un nombre generado por el sistema o por el usuario.|
|BAD|string|Un valor YES indica que esta restricción especifica un siglo de manera ambigua. Para evitar los errores derivados de esta ambigüedad, vuelva a escribir la restricción mediante la función TO_DATE con un año de cuatro cifras.|
|RELY|string|Si una restricción habilitada se exige o no se exige.|
|LAST_CHANGE|DateTime|La última vez que se habilitó o deshabilitó la restricción.|
|INDEX_OWNER|string|Nombre del usuario propietario del índice.|
|INDEX_NAME|string|Nombre del índice.|

## <a name="foreignkeys"></a>ForeignKeys

|ColumName|DataType|DESCRIPCIÓN|
|----------------|--------------|-----------------|
|PRIMARY_KEY_CONSTRAINT_NAME|string|Nombre de la definición de restricción.|
|PRIMARY_KEY_OWNER|string|Propietario de la definición de restricción.|
|PRIMARY_KEY_TABLE_NAME|string|Nombre asociado con la tabla (o vista) con la definición de restricción.|
|FOREIGN_KEY_OWNER|string|Propietario de la definición de restricción.|
|FOREIGN_KEY_CONSTRAINT_NAME|string|Nombre de la definición de restricción.|
|FOREIGN_KEY_TABLE_NAME|string|Nombre asociado con la tabla (o vista) con la definición de restricción.|
|SEARCH_CONDITION|string|Texto de la condición de búsqueda de una restricción de comprobación.|
|R_OWNER|string|Propietario de la tabla a la que se hace referencia en una restricción referencial.|
|R_CONSTRAINT_NAME|string|Nombre de la definición de restricción única de la tabla a la que se hace referencia.|
|DELETE_RULE|string|Regla de eliminación de una restricción referencial (CASCADE o NO ACTION).|
|STATUS|string|Estado de aplicación de la restricción (ENABLED o DISABLED).|
|VALIDATED|string|Si todos los datos respetan la restricción (VALIDATED o NOT VALIDATED).|
|GENERATED|string|Si el nombre de la restricción es un nombre generado por el sistema o por el usuario.|
|RELY|string|Si una restricción habilitada se exige o no se exige.|
|LAST_CHANGE|DateTime|La última vez que se habilitó o deshabilitó la restricción.|
|INDEX_OWNER|string|Nombre del usuario propietario del índice.|
|INDEX_NAME|string|Nombre del índice.|

## <a name="foreignkeycolumns"></a>ForeignKeyColumns

|ColumName|DataType|DESCRIPCIÓN|
|----------------|--------------|-----------------|
|OWNER|string|Propietario de la definición de restricción.|
|CONSTRAINT_NAME|string|Nombre de la definición de restricción.|
|TABLE_NAME|string|Nombre de la tabla con la definición de restricción.|
|COLUMN_NAME|string|Nombre de la columna o atributo de la columna de tipo de objeto especificada en la definición de restricción.|
|POSITION|Decimal|Posición original de la columna o atributo en la definición del objeto.|

## <a name="procedureparameters"></a>ProcedureParameters

|ColumName|DataType|DESCRIPCIÓN|
|----------------|--------------|-----------------|
|OWNER|string|Propietario del objeto.|
|OBJECT_NAME|string|Nombre del procedimiento o función.|
|PACKAGE_NAME|string|Nombre del procedimiento o función.|
|OBJECT_ID|Decimal|Número de objeto del objeto.|
|OVERLOAD|string|Identificador único de sobrecarga.|
|ARGUMENT_NAME|string|Nombre del argumento.|
|POSITION|Decimal|Posición en la lista de argumentos, o NULL para un valor devuelto de la función.|
|SEQUENCE|Decimal|Secuencia de argumentos, incluidos todos los niveles de anidamiento.|
|DATA_LEVEL|Decimal|Profundidad de anidamiento del argumento en los tipos compuestos|
|DATA_TYPE|string|Tipo de datos del argumento.|
|DEFAULT_VALUE|string|Valor predeterminado del argumento.|
|DEFAULT_LENGTH|Decimal|Longitud del valor predeterminado del argumento.|
|IN_OUT|string|Dirección del argumento (IN, OUT o IN/OUT).|
|DATA_LENGTH|Decimal|Longitud de la columna (en bytes).|
|DATA_PRECISION|Decimal|Longitud en dígitos decimales (NUMBER) o dígitos binarios (FLOAT).|
|DATA_SCALE|Decimal|Dígitos a la derecha del separador decimal en un número.|
|RADIX|Decimal|Base de argumento de un número.|
|CHARACTER_SET_NAME|string|Nombre del juego de caracteres del argumento.|
|TYPE_OWNER|string|Propietario del tipo del argumento.|
|TYPE_NAME|string|Nombre del tipo del argumento. Si el tipo es un tipo local de paquete (es decir, se declara en una especificación de paquete), entonces esta columna muestra el nombre del paquete.|
|TYPE_SUBNAME|string|Solo es relevante para los tipos locales de paquete. Muestra el nombre del tipo declarado en el paquete identificado en la columna TYPE_NAME.|
|TYPE_LINK|string|Solo es relevante para los tipos locales de paquete cuando el paquete identificado en la columna TYPE_NAME es un paquete remoto. Esta columna muestra el vínculo de base de datos utilizado para hacer referencia al paquete remoto.|
|PLS_TYPE|string|En argumentos numéricos, el nombre del tipo PL/SQL del argumento. De lo contrario, es NULL.|
|CHAR_LENGTH|Decimal|Límite de caracteres de los tipos de datos de cadena.|
|CHAR_USED|string|Indica si el límite de bytes (B) o el límite de caracteres (C) es oficial para la cadena.|

## <a name="see-also"></a>Vea también

- [Información general sobre ADO.NET](ado-net-overview.md)
