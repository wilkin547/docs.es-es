---
title: "Diferencias entre Entity SQL y Transact-SQL | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: 9c9ee36d-f294-4c8b-a196-f0114c94f559
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Diferencias entre Entity SQL y Transact-SQL
Este tema describe las diferencias entre [!INCLUDE[esql](../../../../../../includes/esql-md.md)] y [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)].  
  
## Compatibilidad con herencia y relaciones  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] trabaja directamente con esquemas de entidades conceptuales y admite características del modelo conceptual tales como herencia y relaciones.  
  
 Cuando se trabaja con la herencia, suele ser útil seleccionar instancias de un subtipo de una colección de instancias de supertipo.  El operador [oftype](../../../../../../docs/framework/data/adonet/ef/language-reference/oftype-entity-sql.md) de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] \(similar a `oftype` de las secuencias de C\#\) proporciona esta capacidad.  
  
## Compatibilidad con colecciones  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] trata las colecciones como entidades de primera clase.  Por ejemplo:  
  
-   Las expresiones de colecciones son válidas en una cláusula `from`.  
  
-   Las subconsultas `in` y `exists` se han generalizado para permitir cualquier tipo de colección.  
  
     Una subconsulta es un tipo de colección.  `e1 in e2` y `exists(e)` son las construcciones de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] que permiten realizar estas operaciones.  
  
-   Las operaciones Set, como `union`, `intersect` y `except`, funcionan ahora en colecciones.  
  
-   Las combinaciones funcionan en colecciones.  
  
## Compatibilidad con expresiones  
 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] tiene subconsultas \(tablas\) y expresiones \(filas y columnas\).  
  
 Para admitir colecciones y colecciones anidadas, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] convierte todo en una expresión.  [!INCLUDE[esql](../../../../../../includes/esql-md.md)] es más ajustable que [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]: todas las expresiones se puede utilizar en cualquier parte.  Las expresiones de consulta siempre producen colecciones de los tipos proyectados y se pueden utilizar en cualquier parte donde se permita una expresión de colección.  Para obtener información sobre las expresiones de [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] que no se admiten en [!INCLUDE[esql](../../../../../../includes/esql-md.md)], vea [Expresiones no admitidas](../../../../../../docs/framework/data/adonet/ef/language-reference/unsupported-expressions-entity-sql.md).  
  
 A continuación se muestran consultas válidas de [!INCLUDE[esql](../../../../../../includes/esql-md.md)]:  
  
```  
1+2 *3  
"abc"  
row(1 as a, 2 as b)  
{ 1, 3, 5}   
e1 union all e2  
set(e1)  
```  
  
## Tratamiento uniforme de subconsultas  
 Dada la importancia de las tablas, [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] realiza una interpretación contextual de las subconsultas.  Por ejemplo, se considera que una subconsulta en la cláusula `from` es un conjunto múltiple \(tabla\).  Pero la misma subconsulta utilizada en la cláusula `select` se considera una subconsulta escalar.  De igual forma, se considera que una subconsulta utilizada en el lado izquierdo de un operador `in` es una subconsulta escalar, mientras se espera que en el lado derecho sea una subconsulta de conjunto múltiple.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] elimina estas diferencias.  Una expresión tiene una interpretación uniforme que no depende del contexto en el que se utiliza.  [!INCLUDE[esql](../../../../../../includes/esql-md.md)] considera que todas las subconsultas son de conjunto múltiple.  Si se desea que la subconsulta tenga un valor escalar, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] proporciona el operador `anyelement` que opera en una colección \(en este caso, la subconsulta\) y extrae el valor singleton de la misma.  
  
### Evitar conversiones implícitas en subconsultas  
 Un efecto secundario relacionado del tratamiento uniforme de las subconsultas es la conversión implícita de las subconsultas en valores escalares.  En concreto, en [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)], un conjunto múltiple de filas \(con un campo único\) se convierte implícitamente en un valor escalar cuyo tipo de datos es el del campo.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] no admite esta conversión implícita.  [!INCLUDE[esql](../../../../../../includes/esql-md.md)] proporciona el operador ANYELEMENT para extraer un valor singleton de una colección y una cláusula `select value` para evitar crear un contenedor de filas durante una expresión de consulta.  
  
## Seleccionar el valor: evitar el contenedor de filas implícitas  
 La cláusula select de una subconsulta de [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] crea implícitamente un contenedor de filas en torno a los elementos de la cláusula.  Esto implica que no podemos crear colecciones de valores escalares o de objetos.  [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] permite una conversión implícita entre un tipo de fila con un campo y un valor singleton del mismo tipo de datos.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] proporciona la cláusula `select value` para omitir la creación de filas implícitas.  Solo se puede especificar un elemento en una cláusula `select value`.  Cuando se utiliza este tipo de cláusula, no se crea ningún contenedor de filas en torno a los elementos de la cláusula `select` y se puede generar una colección de la forma deseada, por ejemplo: `select value a`.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] también proporciona el constructor de filas para crear filas arbitrarias.  La cláusula `select` toma uno o más elementos en la proyección y devuelve un registro de datos con campos, de la siguiente forma:  
  
 `select a, b, c`  
  
## Correlación izquierda y uso de alias  
 En [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)], las expresiones de un ámbito determinado \(una cláusula única como `select` o `from`\) no pueden hacer referencia a expresiones definidas anteriormente en el mismo ámbito.  Algunos dialectos de SQL \(incluido [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]\) admiten formas limitadas de estas en la cláusula `from`.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] generaliza las correlaciones izquierdas de la cláusula `from` y las trata uniformemente.  Las expresiones de la cláusula `from` pueden hacer referencia a definiciones anteriores \(a la izquierda\) en la misma cláusula sin necesidad de una sintaxis adicional.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] también impone restricciones adicionales en consultas que afectan a cláusulas `group by`.  Las expresiones de las cláusulas `select` y `having` de dichas consultas solo pueden hacer referencia a las claves `group by` a través de sus alias.  La construcción siguiente es válida en [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] pero no lo es en [!INCLUDE[esql](../../../../../../includes/esql-md.md)]:  
  
```  
select t.x + t.y from T as t group by t.x + t.y  
```  
  
 Para hacer esto en [!INCLUDE[esql](../../../../../../includes/esql-md.md)]:  
  
```  
select k from T as t group by (t.x + t.y) as k  
```  
  
## Hacer referencia a columnas \(propiedades\) de tablas \(colecciones\)  
 Todas las referencias de columna de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] se deben calificar con el alias de la tabla.  La construcción siguiente \(suponiendo que `a` es una columna válida de la tabla `T`\) es válida en [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] pero no lo es en [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
```  
select a from T  
```  
  
 El formato de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] es:  
  
```  
select t.a as A from T as t  
```  
  
 Los alias de tabla son opcionales en la cláusula `from`.  El nombre de la tabla se utiliza como alias implícito.  [!INCLUDE[esql](../../../../../../includes/esql-md.md)] también permite el formato siguiente:  
  
```  
select Tab.a from Tab  
```  
  
## Navegación a través de objetos  
 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] usa la notación "." para hacer referencia a las columnas de \(una fila de\) una tabla.  [!INCLUDE[esql](../../../../../../includes/esql-md.md)] amplía esta notación \(que toma prestada de los lenguajes de programación\) para admitir la navegación a través de las propiedades de un objeto.  
  
 Por ejemplo, si `p` es una expresión de tipo Persona, lo siguiente es la sintaxis de [!INCLUDE[esql](../../../../../../includes/esql-md.md)] para hacer referencia a la ciudad de la dirección de esta persona.  
  
```  
p.Address.City   
```  
  
## No hay compatibilidad con \*  
 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] admite la sintaxis \* sin calificar como alias de la fila completa y la sintaxis \* calificada \(t.\*\) como acceso directo para los campos de esa tabla.  Además, [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] contempla un agregado count\(\*\) especial, que incluye valores NULL.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] no admite la construcción \*.  Las consultas [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] con el formato `select * from T` y `select T1.* from T1, T2...` se pueden expresar en [!INCLUDE[esql](../../../../../../includes/esql-md.md)] como `select value t from T as t` y `select value t1 from T1 as t1, T2 as t2...`, respectivamente.  Además, estas construcciones administran la herencia \(capacidad de sustitución de valores\), mientras que las variantes de `select *` se restringen a las propiedades de nivel superior del tipo declarado.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] no admite el agregado `count(*)`.  Utilice `count(0)` en su lugar.  
  
## Cambios de Group By  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] admite el uso de alias de las claves `group by`.  Las expresiones de la cláusula `select` y de la cláusula `having` deben hacer referencia a las claves `group by` a través de estos alias. Por ejemplo, esta sintaxis de [!INCLUDE[esql](../../../../../../includes/esql-md.md)]:  
  
```  
select k1, count(t.a), sum(t.a)  
from T as t  
group by t.b + t.c as k1  
```  
  
 ...es equivalente al código siguiente de [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]:  
  
```  
select b + c, count(*), sum(a)   
from T  
group by b + c  
```  
  
## Agregados basados en colecciones  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] admite dos tipos de agregados.  
  
 Los agregados basados en colecciones operan en colecciones y generan el resultado agregado.  Estos pueden aparecer en cualquier parte de la consulta y no requieren una cláusula `group by`.  Por ejemplo:  
  
```  
select t.a as a, count({1,2,3}) as b from T as t     
```  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] también admite agregados del estilo de SQL.  Por ejemplo:  
  
```  
select a, sum(t.b) from T as t group by t.a as a  
```  
  
## Uso de la cláusula ORDER BY  
 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] permite especificar cláusulas ORDER BY solo en el bloque SELECT .. FROM ..  WHERE de nivel superior.  En [!INCLUDE[esql](../../../../../../includes/esql-md.md)], puede utilizar una expresión ORDER BY anidada que se puede colocar en cualquier parte de la consulta, pero la ordenación en una consulta anidada no se conserva.  
  
```  
-- The following query will order the results by the last name  
SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName  
```  
  
```  
-- In the following query ordering of the nested query is ignored.  
SELECT C2.FirstName, C2.LastName  
    FROM (SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName) as C2  
```  
  
## Identificadores  
 En [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)], la comparación del identificador está basada en la intercalación de la base de datos actual.  En [!INCLUDE[esql](../../../../../../includes/esql-md.md)], los identificadores nunca distinguen mayúsculas de minúsculas, pero sí distinguen acentos \(es decir, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] distingue entre los caracteres acentuados y los caracteres sin acentuar; por ejemplo, 'a' no es igual que 'ấ'\). [!INCLUDE[esql](../../../../../../includes/esql-md.md)] trata las versiones de las letras que parecen la misma pero son de páginas de código diferentes como caracteres distintos.  Para obtener más información, consulta [Juego de caracteres de entrada](../../../../../../docs/framework/data/adonet/ef/language-reference/input-character-set-entity-sql.md).  
  
## Funcionalidad de Transact\-SQL no disponible en Entity SQL  
 La funcionalidad de [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] siguiente no está disponible en [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
 DML  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] no proporciona actualmente compatibilidad con las instrucciones DML \(inserción, actualización, eliminación\).  
  
 DDL  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] no proporciona compatibilidad con DDL en la versión actual.  
  
 Programación imperativa  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] no proporciona compatibilidad con la programación imperativa, a diferencia de [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)].  Utilice un lenguaje de programación en su lugar.  
  
 Funciones de agrupamiento  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] no proporciona aún compatibilidad con las funciones de agrupamiento \(por ejemplo, CUBE, ROLLUP y GROUPING\_SET\).  
  
 Funciones analíticas  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] no proporciona aún compatibilidad con las funciones analíticas.  
  
 Funciones y operadores integrados  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] admite un subconjunto de funciones y operadores integrados de [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)].  Es probable que estos operadores y funciones sean admitidos por los principales proveedores de almacenamiento.  [!INCLUDE[esql](../../../../../../includes/esql-md.md)] utiliza las funciones específicas del almacén declaradas en un manifiesto del proveedor.  Además, [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] permite declarar funciones de almacenamiento existentes integradas y definidas por el usuario, para usarlas en [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
 Sugerencias  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] no proporciona mecanismos para sugerencias de consulta.  
  
 Resultados de un consulta por lotes  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] no admite resultados de una consulta por lotes.  Por ejemplo, el siguiente código es [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] válido \(cuando se envía como un lote\):  
  
```  
select * from products;  
select * from catagories;  
```  
  
 Sin embargo, no se admite el código [!INCLUDE[esql](../../../../../../includes/esql-md.md)] equivalente:  
  
```  
Select value p from Products as p;  
Select value c from Categories as c;  
```  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] admite únicamente una instrucción de consulta que genera un solo resultado por comando.  
  
## Vea también  
 [Información general de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)   
 [Expresiones no admitidas](../../../../../../docs/framework/data/adonet/ef/language-reference/unsupported-expressions-entity-sql.md)