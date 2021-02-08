---
description: 'Más información acerca de: referencia de Entity SQL'
title: Referencia de Entity SQL
ms.date: 03/30/2017
ms.assetid: 61ce7ee1-ffe2-477d-8a9f-835b0a11d900
ms.openlocfilehash: 89a53d6d365d8cae99e16c52cc159c9d2ff57cfc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786425"
---
# <a name="entity-sql-reference"></a>Referencia de Entity SQL

Esta sección contiene Entity SQL artículos de referencia. En este artículo se resumen y se agrupan los operadores de Entity SQL por categoría.

## <a name="arithmetic-operators"></a>Operadores aritméticos

Los operadores aritméticos realizan operaciones matemáticas con dos expresiones de uno o más tipos de datos numéricos. En la tabla siguiente se enumeran los operadores aritméticos Entity SQL:

|Operator|Uso|
|--------------|---------|
|[+ (Sumar)](add.md)|Suma.|
|[/ (Dividir)](divide-entity-sql.md)|División.|
|[% (Módulo)](modulo-entity-sql.md)|Devuelve el resto de una división.|
|[* (Multiplicar)](multiply-entity-sql.md)|Multiplicación.|
|[- (Negativo)](negative-entity-sql.md)|Negación.|
|[- (Restar)](subtract-entity-sql.md)|Resta.|

## <a name="canonical-functions"></a>Funciones canónicas

Las funciones canónicas son admitidas por todos los proveedores de datos y pueden usarse en todas las tecnologías de creación de consultas. En la tabla siguiente se enumeran las funciones canónicas:

|Función|Tipo|
|--------------|----------|
|[Funciones canónicas de agregado de Entity SQL](aggregate-canonical-functions.md)|Describe las funciones de agregado Entity SQL canónicas.|
|[Funciones canónicas matemáticas](math-canonical-functions.md)|Describe las funciones matemáticas Entity SQL canónicas.|
|[Funciones canónicas de cadena](string-canonical-functions.md)|Describe las funciones canónicas de Entity SQL de cadenas.|
|[Funciones canónicas de fecha y hora](date-and-time-canonical-functions.md)|Describe las funciones canónicas de fecha y hora Entity SQL.|
|[Funciones canónicas bit a bit](bitwise-canonical-functions.md)|Describe las funciones canónicas Entity SQL de bits.|
|[Otras funciones canónicas](other-canonical-functions.md)|Describe las funciones no clasificadas como funciones bit a bit, de fecha y hora, de cadena, matemáticas o de agregado.|

## <a name="comparison-operators"></a>Operadores de comparación

Los operadores de comparación se definen para los tipos siguientes: `Byte`, `Int16`, `Int32`, `Int64`, `Double`, `Single`, `Decimal`, `String`, `DateTime`, `Date`, `Time` y `DateTimeOffset`. La promoción de tipos implícita se produce para los operandos antes de que se aplique el operador de comparación. Los operadores de comparación siempre dan como resultados valores booleanos. Cuando al menos uno de los operandos es `null`, el resultado es `null`.

La igualdad y desigualdad se definen para cualquier tipo de objeto que tenga identidad, como el tipo `Boolean`. Los objetos no primitivos con identidad se consideran iguales si comparten la misma identidad. En la tabla siguiente se enumeran los operadores de comparación Entity SQL:

|Operator|Descripción|
|--------------|-----------------|
|[= (Es igual a)](equals-entity-sql.md)|Compara la igualdad de dos expresiones.|
|[> (Mayor que)](greater-than-entity-sql.md)|Compara dos expresiones para determinar si la expresión de la izquierda tiene un valor mayor que el de la expresión de la derecha.|
|[>= (Mayor o igual a)](greater-than-or-equal-to-entity-sql.md)|Compara dos expresiones para determinar si la expresión de la izquierda tiene un valor igual o mayor que el de la expresión de la derecha.|
|[\[no es \] null](isnull-entity-sql.md)|Determina si una expresión de consulta es nula.|
|[< (Menor que)](less-than-entity-sql.md)|Compara dos expresiones para determinar si la expresión de la izquierda tiene un valor menor que el de la expresión de la derecha.|
|[<= (Menor o igual a)](less-than-or-equal-to-entity-sql.md)|Compara dos expresiones para determinar si la expresión izquierda tiene un valor igual o menor que el de la expresión derecha.|
|[\[NO \] entre](between-entity-sql.md)|Determina si el resultado de una expresión es un valor incluido en un intervalo especificado.|
|[\!= (No es igual a)](not-equal-to-entity-sql.md)|Compara dos expresiones para determinar si la expresión izquierda no es igual que la expresión de la derecha.|
|[\[NO es \] como](like-entity-sql.md)|Determina si una cadena de caracteres específica coincide con un patrón especificado.|

## <a name="logical-and-case-expression-operators"></a>Operadores lógicos y de expresión Case

Los operadores lógicos prueban la veracidad de una condición. La expresión CASE evalúa un conjunto de expresiones booleanas para determinar el resultado. En la tabla siguiente se enumeran los operadores lógicos y de expresiones CASE:

|Operator|Descripción|
|--------------|-----------------|
|[&&  (AND lógico)](and-entity-sql.md)|Y lógico.|
|[\! (NOT lógico)](not-entity-sql.md)|NOT lógico.|
|[&#124;&#124;  (OR lógico)](or-entity-sql.md)|O lógico.|
|[CASE](case-entity-sql.md)|Evalúa un conjunto de expresiones booleanas para determinar el resultado.|
|[THEN](then-entity-sql.md)|El resultado de una cláusula [When](/previous-versions/dotnet/netframework-4.0/bb387119(v=vs.100)) cuando se evalúa como true.|

## <a name="query-operators"></a>Operadores de consulta

Los operadores de consulta se usan para definir expresiones de consulta que devuelven datos de la entidad. En la tabla siguiente se enumeran los operadores de consulta:

|Operator|Uso|
|--------------|---------|
|[FROM](from-entity-sql.md)|Especifica la colección que se utiliza en las instrucciones [Select](select-entity-sql.md) .|
|[GROUP BY](group-by-entity-sql.md)|Especifica los grupos en los que se van a colocar los objetos devueltos por una expresión de consulta ([Select](select-entity-sql.md)).|
|[GroupPartition](grouppartition-entity-sql.md)|Devuelve una colección de valores de argumento que se proyecta a partir de la partición de grupo con la que está relacionado el agregado.|
|[HAVING](having-entity-sql.md)|Especifica una condición de búsqueda para un grupo o agregado.|
|[ILIMITADO](limit-entity-sql.md)|Se usa con la cláusula [order by](order-by-entity-sql.md) para realizar la paginación física.|
|[ORDER BY](order-by-entity-sql.md)|Especifica el criterio de ordenación que se usa en los objetos devueltos en una instrucción [Select](select-entity-sql.md) .|
|[SELECT](select-entity-sql.md)|Especifica los elementos de la proyección devueltos por una consulta.|
|[IRÁ](skip-entity-sql.md)|Se usa con la cláusula [order by](order-by-entity-sql.md) para realizar la paginación física.|
|[TOP](top-entity-sql.md)|Especifica que solo se devolverá el primer conjunto de filas del resultado de la consulta.|
|[WHERE](where-entity-sql.md)|Filtra de forma condicional los datos devueltos por una consulta.|

## <a name="reference-operators"></a>Operadores de referencia

Una referencia es un puntero lógico (clave externa) a una entidad concreta en un conjunto de entidades específico. Entity SQL admite los operadores siguientes para construir, deconstruir y navegar por referencias:

|Operator|Uso|
|--------------|---------|
|[CREATEREF](createref-entity-sql.md)|Crea referencias a una entidad en un conjunto de entidades.|
|[DEREF](deref-entity-sql.md)|Desreferencia un valor de referencia y genera el resultado de dicha desreferenciación.|
|[KEY](key-entity-sql.md)|Extrae la clave de una referencia o de una expresión de entidad.|
|[NAVEGAR](navigate-entity-sql.md)|Permite navegar por la relación de un tipo de entidad a otro|
|[CLI](ref-entity-sql.md)|Devuelve una referencia a una instancia de entidad.|

## <a name="set-operators"></a>Operadores de conjuntos

Entity SQL proporciona varias operaciones de conjuntos muy eficaces. Esto incluye operadores de conjuntos similares a los operadores de Transact-SQL como UNION, INTERSECT, Except y EXISTs. Entity SQL también admite operadores para la eliminación de duplicados (SET), la prueba de pertenencia (en) y las combinaciones (JOIN). En la tabla siguiente se enumeran los operadores de conjuntos de Entity SQL:

|Operator|Uso|
|--------------|---------|
|[ANYELEMENT](anyelement-entity-sql.md)|Extrae un elemento de una colección de varios valores.|
|[EXCEPT](except-entity-sql.md)|Devuelve una colección de los valores distintos de la expresión de consulta a la izquierda del operando Except que no se devuelven también desde la expresión de consulta a la derecha del operando except.|
|[\[NO \] existe](exists-entity-sql.md)|Determina si una colección está vacía.|
|[PLANO](flatten-entity-sql.md)|Convierte una colección de colecciones en una colección plana.|
|[\[NO \] en](in-entity-sql.md)|Determina si un valor determinado coincide con algún valor de una colección.|
|[INTERSECT](intersect-entity-sql.md)|Devuelve una colección de los valores distintos que devuelven las expresiones de consulta situadas a los lados izquierdo y derecho del operando INTERSECT.|
|[OVERLAPS](overlaps-entity-sql.md)|Determina si dos colecciones tienen elementos comunes.|
|[SET](set-entity-sql.md)|Convierte una colección de objetos en un conjunto produciendo una colección nueva en la que se han quitado todos los elementos duplicados.|
|[UNION](union-entity-sql.md)|Combina los resultados de dos o más consultas en una sola colección.|

## <a name="type-operators"></a>Operadores de tipo

Entity SQL proporciona operaciones que permiten construir, consultar y manipular el tipo de una expresión (valor). En la tabla siguiente se enumeran los operadores que se usan para trabajar con tipos:

|Operator|Uso|
|--------------|---------|
|[CAST](cast-entity-sql.md)|Convierte una expresión de un tipo de datos a otro.|
|[COLLECTION](collection-entity-sql.md)|Se utiliza en una operación de [función](function-entity-sql.md) para declarar una colección de tipos de entidad o tipos complejos.|
|[\[no es \] de](isof-entity-sql.md)|Determina si el tipo de una expresión es del tipo especificado o uno de sus subtipos.|
|[OFTYPE](oftype-entity-sql.md)|Devuelve una colección de objetos de una expresión de consulta de un tipo específico.|
|[Constructor de tipos con nombre](named-type-constructor-entity-sql.md)|Crea instancias de tipos de entidad o tipos complejos.|
|[MULTISET](multiset-entity-sql.md)|Crea una instancia de un conjunto múltiple a partir de una lista de valores.|
|[ROW](row-entity-sql.md)|Crea registros anónimos con tipos asignados estructuralmente a partir de uno o varios valores.|
|[TREAT](treat-entity-sql.md)|Trata un objeto de un tipo base determinado como un objeto del tipo derivado especificado.|

## <a name="other-operators"></a>Otros operadores

En la tabla siguiente se enumeran otros operadores de Entity SQL:

|Operator|Uso|
|--------------|---------|
|[+ (Concatenación de cadenas)](string-concatenation-entity-sql.md)|Se utiliza para concatenar cadenas en Entity SQL.|
|[. (Acceso a miembros)](member-access-entity-sql.md)|Obtiene acceso al valor de una propiedad o campo de una instancia de un tipo de modelo conceptual estructural.|
|[-- (Comentario)](comment-entity-sql.md)|Incluye comentarios de Entity SQL.|
|[FUNCTION](function-entity-sql.md)|Define una función insertada que se puede ejecutar en una consulta de Entity SQL.|

## <a name="see-also"></a>Vea también

- [Lenguaje Entity SQL](entity-sql-language.md)
