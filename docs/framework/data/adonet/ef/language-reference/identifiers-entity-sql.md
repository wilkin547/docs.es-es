---
title: Identificadores (Entity SQL)
ms.date: 03/30/2017
ms.assetid: d58a5edd-7b5c-48e1-b5d7-a326ff426aa4
ms.openlocfilehash: 7e9b12ca351b021fab62988969cb98310cb55cc2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203701"
---
# <a name="identifiers-entity-sql"></a>Identificadores (Entity SQL)

En [!INCLUDE[esql](../../../../../../includes/esql-md.md)] se utilizan identificadores como representación de los alias de expresiones de consulta, referencias de variables, propiedades de objetos, funciones, etc. [!INCLUDE[esql](../../../../../../includes/esql-md.md)] proporciona dos tipos de identificadores: identificadores simples e identificadores entre comillas.  
  
## <a name="simple-identifiers"></a>Identificadores simples  

 Un identificador simple en [!INCLUDE[esql](../../../../../../includes/esql-md.md)] es una secuencia de caracteres alfanuméricos y de subrayado. El primer carácter del identificador debe ser alfabético (a-z o A-Z).  
  
## <a name="quoted-identifiers"></a>Identificadores entre comillas  

 Un identificador entre comillas es cualquier secuencia de caracteres incluida entre corchetes ([]). Los identificadores entre comillas le permiten especificar identificadores con caracteres que no son válidos. Todos los caracteres entre corchetes se convierten en parte del identificador, incluidos todos los espacios en blanco.  
  
 Un identificador entre comillas no puede incluir los caracteres siguientes:  
  
- Nueva línea.  
  
- Retorno de carro.  
  
- Tabulaciones.  
  
- Retroceso.  
  
- Corchetes adicionales (es decir, corchetes dentro de los corchetes que delinean el identificador).  
  
 Un identificador entre comillas puede incluir caracteres Unicode.  
  
 Los identificadores entre comillas le permiten crear caracteres de nombres de propiedad que no son válidos en identificadores, como se muestra en el ejemplo siguiente:  
  
 `SELECT c.ContactName AS [Contact Name] FROM customers AS c`  
  
 También puede utilizar los identificadores entre comillas para especificar un identificador que sea una palabra clave reservada de [!INCLUDE[esql](../../../../../../includes/esql-md.md)]. Por ejemplo, si el tipo `Email` tiene una propiedad denominada "From", puede eliminar la ambigüedad de la palabra clave reservada FROM utilizando corchetes, como sigue:  
  
 `SELECT e.[From] FROM emails AS e`  
  
 Puede utilizar un identificador entre comillas en el lado derecho de un operador de punto (.).  
  
 `SELECT t FROM ts as t WHERE t.[property] == 2`  
  
 Para utilizar el corchete en un identificador, agregue un corchete adicional. El ejemplo siguiente, "`abc]`" es el identificador:  
  
 `SELECT t from ts as t WHERE t.[abc]]] == 2`  
  
 Para la semántica de comparación de identificadores entre comillas, consulte [juego de caracteres de entrada](input-character-set-entity-sql.md).  
  
## <a name="aliasing-rules"></a>Reglas de alias  

 Se recomienda especificar los alias en [!INCLUDE[esql](../../../../../../includes/esql-md.md)] las consultas siempre que sea necesario, incluidas las siguientes [!INCLUDE[esql](../../../../../../includes/esql-md.md)] construcciones:  
  
- Campos de un constructor de fila.  
  
- Elementos de la cláusula FROM de una expresión de consulta.  
  
- Elementos de la cláusula SELECT de una expresión de consulta.  
  
- Elementos de la cláusula GROUP BY de una expresión de consulta.  
  
### <a name="valid-aliases"></a>Alias válidos  

 Los alias válidos en [!INCLUDE[esql](../../../../../../includes/esql-md.md)] son cualquier identificador simple o identificador entre comillas.  
  
### <a name="alias-generation"></a>Generación de alias  

 Si no se especifica ningún alias en una [!INCLUDE[esql](../../../../../../includes/esql-md.md)] expresión de consulta, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] intenta generar un alias basado en las siguientes reglas simples:  
  
- Si la expresión de consulta (para la que el alias está sin especificar) es un identificador simple o entre comillas, ese identificador se utiliza como alias. Por ejemplo, `ROW(a, [b])` se convierte en `ROW(a AS a, [b] AS [b])`.  
  
- Si la expresión de consulta es más compleja, pero el último componente es un identificador simple, ese identificador se utiliza como alias. Por ejemplo, `ROW(a.a1, b.[b1])` se convierte en `ROW(a.a1 AS a1, b.[b1] AS [b1])`.  
  
 Recomendamos que no utilice el alias implícito si desea utilizar el nombre del alias después. Cuando aparezca un conflicto en los alias (implícito o explícito) o se repitan en el mismo ámbito, habrá un error de compilación. Un alias implícito pasará la compilación aun cuando sea un alias explícito o implícito del mismo nombre.  
  
 Los alias implícitos se generan automáticamente según los datos que proporcione el usuario. Por ejemplo, la línea de código siguiente generará NAME como un alias para ambas columnas y, por consiguiente, estará en conflicto.  
  
```sql  
SELECT product.NAME, person.NAME  
```  
  
 También se producirá un error en la línea de código siguiente, que utiliza alias explícitos. Sin embargo, el error será más aparente al leer el código.  
  
```sql  
SELECT 1 AS X, 2 AS X …  
```  
  
## <a name="scoping-rules"></a>Reglas de ámbito  

 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] define reglas de ámbito que determinan cuándo se ven determinadas variables en el lenguaje de consulta. Algunas expresiones o instrucciones incluyen nombres nuevos. Las reglas de ámbito determinan dónde se pueden utilizar esos nombres y cuándo o dónde una declaración nueva con el mismo nombre que otra puede ocultar a su predecesora.  
  
 Cuando los nombres se definen en una [!INCLUDE[esql](../../../../../../includes/esql-md.md)] consulta, se dice que están definidos dentro de un ámbito. Un ámbito cubre una región completa de la consulta. Todas las expresiones o las referencias de nombre dentro de un cierto ámbito pueden ver los nombres que están definidos dentro de ese ámbito. Antes de que un ámbito comience y después de que finalice, no se puede hacer referencia a los nombres que se definen dentro del ámbito.  
  
 Los ámbitos se pueden anidar. Las partes de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] presentan nuevos ámbitos que cubren regiones completas, y estas regiones pueden contener otras [!INCLUDE[esql](../../../../../../includes/esql-md.md)] expresiones que también presentan ámbitos. Cuando los ámbitos están anidados, se pueden realizar referencias a los nombres que se definen en el ámbito más interno, que contiene la referencia. Las referencias también se pueden realizar a cualquier nombre que se defina en algún ámbito externo. Dos ámbitos cualesquiera definidos dentro del mismo ámbito se consideran del mismo nivel. No se pueden realizar referencias a nombres que están definidos dentro de ámbitos del mismo nivel.  
  
 Si un nombre declarado en un ámbito interno coincide con un nombre declarado en un ámbito externo, las referencias dentro del ámbito interno o de los ámbitos declarados dentro de ese ámbito solo hacen referencia al nombre recién declarado. El nombre en el ámbito externo se oculta.  
  
 Incluso dentro del mismo ámbito, no se puede hacer referencia a los nombres antes de que se definan.  
  
 Los nombres globales pueden existir como parte del entorno de ejecución. Se pueden los nombres de las variables de entorno o colecciones persistentes. Para que un nombre sea global, se debe declarar en el ámbito más externo.  
  
 Los parámetros no están en un ámbito. Dado que las referencias a los parámetros incluyen una sintaxis especial, los nombres de los parámetros nunca colisionarán con los otros nombres en la consulta.  
  
### <a name="query-expressions"></a>Expresiones de consulta  

 Una [!INCLUDE[esql](../../../../../../includes/esql-md.md)] expresión de consulta introduce un nuevo ámbito. Los nombres que se definen en la cláusula FROM se incluyen en el ámbito de FROM en orden de aparición, de izquierda a derecha. En la lista de uniones, las expresiones pueden hacer referencia a los nombres que se definieron en la lista anteriormente. Las propiedades públicas (campos, etc.) de los elementos identificados en la cláusula FROM no se agregan al ámbito de FROM. El nombre certificado con el alias siempre debe hacer referencia a estas propiedades. Normalmente, todas las partes de la expresión SELECT se consideran dentro del ámbito de FROM.  
  
 La cláusula GROUP BY también incluye un nuevo ámbito de elementos del mismo nivel. Cada grupo puede tener un nombre que haga referencia a la colección de elementos del grupo. Cada expresión de agrupación también incluirá un nombre nuevo en el ámbito de GROUP. Además, el agregado de anidación (o el grupo con nombre) también se agrega al ámbito. Las propias expresiones de agrupación están dentro del ámbito de FROM. Sin embargo, cuando se utiliza una cláusula GROUP BY, se considera que la lista de selección (proyección), la cláusula HAVING y la cláusula ORDER BY están dentro del ámbito de GROUP y no del ámbito de FROM. Los agregados reciben un tratamiento especial, según se describe en la lista con viñetas siguiente.  
  
 Las siguientes son notas adicionales sobre los ámbitos:  
  
- La lista de selección puede incluir nombres nuevos en el ámbito, en orden. Las expresiones de proyección a la derecha podrían hacer referencia a los nombres proyectados en la izquierda.  
  
- La cláusula ORDER BY puede hacer referencia a los nombres (alias) especificados en la lista de selección.  
  
- El orden de evaluación de las cláusulas dentro de la expresión SELECT determina el orden en que los nombres se incluyen en el ámbito. La cláusula FROM se evalúa primero y a continuación se evalúan las cláusulas WHERE, GROUP BY, HAVING, SELECT y, finalmente, ORDER BY.  
  
### <a name="aggregate-handling"></a>Control de los agregados  

 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] admite dos formas de agregados: los agregados basados en colección y los agregados basados en grupos. Los agregados basados en la colección son la construcción preferida en [!INCLUDE[esql](../../../../../../includes/esql-md.md)] y los agregados basados en el grupo se admiten por compatibilidad con SQL.  
  
 Al resolver un agregado, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] primero intenta tratarlo como un agregado basado en una colección. Si se produce un error, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] transforma la entrada del agregado en una referencia al agregado anidado e intenta resolver esta nueva expresión, tal como se muestra en el ejemplo siguiente.  
  
 `AVG(t.c) becomes AVG(group..(t.c))`  
  
## <a name="see-also"></a>Consulte también

- [Referencia de Entity SQL](entity-sql-reference.md)
- [Información general sobre Entity SQL](entity-sql-overview.md)
- [Juego de caracteres de entrada](input-character-set-entity-sql.md)
