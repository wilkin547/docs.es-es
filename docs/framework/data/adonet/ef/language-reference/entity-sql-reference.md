---
title: Referencia de Entity SQL
ms.date: 03/30/2017
ms.assetid: 61ce7ee1-ffe2-477d-8a9f-835b0a11d900
ms.openlocfilehash: d6b40d0c1662e18ed83c58bfdde7b6dac65220dd
ms.sourcegitcommit: f6343b070f3c66877338a05c8bfb0be9985255e2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "39221054"
---
# <a name="entity-sql-reference"></a>Referencia de Entity SQL

Esta sección contiene artículos de referencia de Entity SQL. En este artículo se resume y agrupa los operadores de Entity SQL por categoría.

## <a name="arithmetic-operators"></a>Operadores aritméticos

Los operadores aritméticos realizan operaciones matemáticas con dos expresiones de uno o más tipos de datos numéricos. En la tabla siguiente se enumera los operadores aritméticos de Entity SQL:

|Operador|Usar|
|--------------|---------|
|[+ (Agregar)](add.md)|Adición.|
|[/ (Dividir)](divide-entity-sql.md)|División.|
|[% (Módulo)](modulo-entity-sql.md)|Devuelve el resto de una división.|
|[* (Multiplicar)](multiply-entity-sql.md)|Multiplicación.|
|[- (Negativo)](negative-entity-sql.md)|Negativo.|
|[- (Restar)](subtract-entity-sql.md)|Resta.|

## <a name="canonical-functions"></a>Funciones canónicas

Las funciones canónicas son admitidas por todos los proveedores de datos y pueden usarse en todas las tecnologías de creación de consultas. En la tabla siguiente se enumera las funciones canónicas:

|Función|Tipo|
|--------------|----------|
|[Funciones canónicas de agregado de Entity SQL](aggregate-canonical-functions.md)|Describe las funciones canónicas de agregado Entity SQL.|
|[Funciones canónicas matemáticas](math-canonical-functions.md)|Describe las funciones canónicas de Entity SQL matemáticas.|
|[Funciones canónicas de cadena](string-canonical-functions.md)|Describe las funciones canónicas de cadena Entity SQL.|
|[Funciones canónicas de fecha y hora](date-and-time-canonical-functions.md)|Describe las funciones canónicas de Entity SQL fecha y hora.|
|[Funciones canónicas bit a bit](bitwise-canonical-functions.md)|Describe las funciones canónicas bit a bit de Entity SQL.|
|[Otras funciones canónicas](other-canonical-functions.md)|Describe las funciones no clasificadas como funciones bit a bit, de fecha y hora, de cadena, matemáticas o de agregado.|

## <a name="comparison-operators"></a>Operadores de comparación

Los operadores de comparación se definen para los tipos siguientes: `Byte`, `Int16`, `Int32`, `Int64`, `Double`, `Single`, `Decimal`, `String`, `DateTime`, `Date`, `Time` y `DateTimeOffset`. La promoción de tipos implícita se produce para los operandos antes de que se aplique el operador de comparación. Los operadores de comparación siempre dan como resultados valores booleanos. Cuando al menos uno de los operandos es `null`, el resultado es `null`.

La igualdad y desigualdad se definen para cualquier tipo de objeto que tenga identidad, como el tipo `Boolean`. Los objetos no primitivos con identidad se consideran iguales si comparten la misma identidad. En la tabla siguiente se enumera los operadores de comparación de Entity SQL:

|Operador|Descripción|
|--------------|-----------------|
|[= (Igual que)](equals-entity-sql.md)|Compara la igualdad de dos expresiones.|
|[> (Mayor que)](greater-than-entity-sql.md)|Compara dos expresiones para determinar si la expresión de la izquierda tiene un valor mayor que el de la expresión de la derecha.|
|[>= (Mayor o igual que)](greater-than-or-equal-to-entity-sql.md)|Compara dos expresiones para determinar si la expresión de la izquierda tiene un valor igual o mayor que el de la expresión de la derecha.|
|[ES \[NO\] NULL](isnull-entity-sql.md)|Determina si una expresión de consulta es nula.|
|[< (Menor que)](less-than-entity-sql.md)|Compara dos expresiones para determinar si la expresión de la izquierda tiene un valor menor que el de la expresión de la derecha.|
|[<= (Menor o igual que)](less-than-or-equal-to-entity-sql.md)|Compara dos expresiones para determinar si la expresión izquierda tiene un valor igual o menor que el de la expresión derecha.|
|[\[NO\] BETWEEN](between-entity-sql.md)|Determina si el resultado de una expresión es un valor incluido en un intervalo especificado.|
|[\!= (No igual a)](not-equal-to-entity-sql.md)|Compara dos expresiones para determinar si la expresión izquierda no es igual a la expresión derecha.|
|[\[NO\] COMO](like-entity-sql.md)|Determina si una cadena de caracteres específica coincide con un patrón especificado.|

## <a name="logical-and-case-expression-operators"></a>Operadores lógicos y de expresión case

Los operadores lógicos prueban la veracidad de una condición. La expresión CASE evalúa un conjunto de expresiones booleanas para determinar el resultado. En la tabla siguiente se enumera los operadores lógicos y de expresión CASE:

|Operador|Descripción|
|--------------|-----------------|
|[& & (AND lógico)](and-entity-sql.md)|AND lógico.|
|[\! (NOT lógico)](not-entity-sql.md)|NOT lógico.|
|[&#124;&#124;(OR lógico)](or-entity-sql.md)|OR lógico.|
|[CASE](case-entity-sql.md)|Evalúa un conjunto de expresiones booleanas para determinar el resultado.|
|[THEN](then-entity-sql.md)|El resultado de una [cuando](http://msdn.microsoft.com/library/6233fe9f-00b0-460e-8372-64e138a5f998) cláusula cuando se evalúa como true.|

## <a name="query-operators"></a>Operadores de consulta

Los operadores de consulta se usan para definir expresiones de consulta que devuelven datos de la entidad. En la tabla siguiente se enumera los operadores de consulta:

|Operador|Usar|
|--------------|---------|
|[FROM](from-entity-sql.md)|Especifica la colección que se usa en [seleccione](select-entity-sql.md) instrucciones.|
|[GROUP BY](group-by-entity-sql.md)|Especifica los grupos en los objetos devueltos por una consulta ([seleccione](select-entity-sql.md)) expresión que se van a colocarse.|
|[GroupPartition](grouppartition-entity-sql.md)|Devuelve una colección de valores de argumento que se proyecta a partir de la partición de grupo con la que está relacionado el agregado.|
|[HAVING](having-entity-sql.md)|Especifica una condición de búsqueda para un grupo o agregado.|
|[LIMIT](limit-entity-sql.md)|Puede usar con el [ORDER BY](order-by-entity-sql.md) cláusula para realizar la paginación física.|
|[ORDER BY](order-by-entity-sql.md)|Especifica el criterio de ordenación que se usa en los objetos devueltos en una [seleccione](select-entity-sql.md) instrucción.|
|[SELECT](select-entity-sql.md)|Especifica los elementos de la proyección devueltos por una consulta.|
|[SKIP](skip-entity-sql.md)|Puede usar con el [ORDER BY](order-by-entity-sql.md) cláusula para realizar la paginación física.|
|[TOP](top-entity-sql.md)|Especifica que solo se devolverá el primer conjunto de filas del resultado de la consulta.|
|[WHERE](where-entity-sql.md)|Filtra de forma condicional los datos devueltos por una consulta.|

## <a name="reference-operators"></a>Operadores de referencia

Una referencia es un puntero lógico (clave externa) a una entidad concreta en un conjunto de entidades específico. Entity SQL admite los operadores siguientes para construir, anular la construcción y navegar a través de referencias:

|Operador|Usar|
|--------------|---------|
|[CREATEREF](createref-entity-sql.md)|Crea referencias a una entidad en un conjunto de entidades.|
|[DEREF](deref-entity-sql.md)|Desreferencia un valor de referencia y genera el resultado de dicha desreferenciación.|
|[KEY](key-entity-sql.md)|Extrae la clave de una referencia o de una expresión de entidad.|
|[NAVIGATE](navigate-entity-sql.md)|Permite navegar por la relación de un tipo de entidad a otro|
|[REF](ref-entity-sql.md)|Devuelve una referencia a una instancia de entidad.|

## <a name="set-operators"></a>Operadores de conjuntos

Entity SQL proporciona varias operaciones de conjunto eficaces. Esto incluye operadores de conjuntos similares a los operadores de Transact-SQL como UNION, INTERSECT, EXCEPT y EXISTS. Entity SQL también admite los operadores para la eliminación de duplicados (SET), la pertenencia de las pruebas (IN) y combinaciones (JOIN). En la tabla siguiente se enumera los operadores de conjuntos de Entity SQL:

|Operador|Usar|
|--------------|---------|
|[ANYELEMENT](anyelement-entity-sql.md)|Extrae un elemento de una colección de varios valores.|
|[EXCEPT](except-entity-sql.md)|Devuelve una colección de los valores distintos de la expresión de consulta a la izquierda del operando EXCEPT que no se devuelven desde la expresión de consulta a la derecha del operando EXCEPT.|
|[\[NO\] EXISTS](exists-entity-sql.md)|Determina si una colección está vacía.|
|[FLATTEN](flatten-entity-sql.md)|Convierte una colección de colecciones en una colección plana.|
|[\[NO\] IN](in-entity-sql.md)|Determina si un valor determinado coincide con algún valor de una colección.|
|[INTERSECT](intersect-entity-sql.md)|Devuelve una colección de los valores distintos que devuelven las expresiones de consulta situadas a los lados izquierdo y derecho del operando INTERSECT.|
|[OVERLAPS](overlaps-entity-sql.md)|Determina si dos colecciones tienen elementos comunes.|
|[SET](set-entity-sql.md)|Convierte una colección de objetos en un conjunto produciendo una colección nueva en la que se han quitado todos los elementos duplicados.|
|[UNION](union-entity-sql.md)|Combina los resultados de dos o más consultas en una sola colección.|

## <a name="type-operators"></a>Operadores de tipo

Entity SQL proporciona operaciones que permiten al tipo de una expresión (valor) para construir, consultar y manipular. En la tabla siguiente se enumera los operadores que se usan para trabajar con tipos:

|Operador|Usar|
|--------------|---------|
|[CAST](cast-entity-sql.md)|Convierte una expresión de un tipo de datos a otro.|
|[COLLECTION](collection-entity-sql.md)|Utilizado en un [función](function-entity-sql.md) operación para declarar una colección de tipos de entidad o tipos complejos.|
|[ES \[NO\] OF](isof-entity-sql.md)|Determina si el tipo de una expresión es del tipo especificado o uno de sus subtipos.|
|[OFTYPE](oftype-entity-sql.md)|Devuelve una colección de objetos de una expresión de consulta de un tipo específico.|
|[Constructor de tipos con nombre](named-type-constructor-entity-sql.md)|Crea instancias de tipos de entidad o tipos complejos.|
|[MULTISET](multiset-entity-sql.md)|Crea una instancia de un conjunto múltiple a partir de una lista de valores.|
|[ROW](row-entity-sql.md)|Crea registros anónimos con tipos asignados estructuralmente a partir de uno o varios valores.|
|[TREAT](treat-entity-sql.md)|Trata un objeto de un tipo base determinado como un objeto del tipo derivado especificado.|

## <a name="other-operators"></a>Operadores adicionales

En la tabla siguiente se enumera otros operadores de Entity SQL:

|Operador|Usar|
|--------------|---------|
|[+ (Concatenación de cadenas)](string-concatenation-entity-sql.md)|Se utiliza para concatenar cadenas en Entity SQL.|
|[. (Acceso a miembros)](member-access-entity-sql.md)|Obtiene acceso al valor de una propiedad o campo de una instancia de un tipo de modelo conceptual estructural.|
|[-- (Comentario)](comment-entity-sql.md)|Incluir comentarios de Entity SQL.|
|[FUNCTION](function-entity-sql.md)|Define una función insertada que se puede ejecutar en una consulta de Entity SQL.|

## <a name="see-also"></a>Vea también

[Lenguaje Entity SQL](entity-sql-language.md)
