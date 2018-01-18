---
title: "Generar SQL a partir de árboles de comandos: procedimientos recomendados"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 71ef6a24-4c4f-4254-af3a-ffc0d855b0a8
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: d68194ab83a6606337a33668470411ed8b1c6957
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="generating-sql-from-command-trees---best-practices"></a>Generar SQL a partir de árboles de comandos: procedimientos recomendados
Los árboles de comandos de consulta de salida crean modelos muy similares a consultas expresables en SQL. Sin embargo, hay ciertos retos comunes para los programadores de proveedores a la hora de generar SQL a partir de un árbol de comandos de salida. En este tema se describen estos retos. En el tema siguiente, el proveedor de ejemplo muestra cómo actuar ante estos retos.  
  
## <a name="group-dbexpression-nodes-in-a-sql-select-statement"></a>Agrupar nodos DbExpression en una instrucción SELECT de SQL  
 Una instrucción SQL típica tiene una estructura anidada con la siguiente forma:  
  
```  
SELECT …  
FROM …  
WHERE …  
GROUP BY …  
ORDER BY …  
```  
  
 Una o más cláusulas pueden estar vacías.  Una instrucción SELECT anidada puede producirse en cualquiera de las líneas.  
  
 Una posible traducción de un árbol de comandos de consulta en una instrucción SELECT de SQL generaría una subconsulta para cada operador relacional. Sin embargo, esto conduciría a subconsultas anidadas innecesarias que serían difíciles de leer.  En algunos almacenes de datos, esta consulta puede tener un bajo rendimiento.  
  
 Como ejemplo, observe el siguiente árbol de comandos de consulta:  
  
```  
Project (  
a.x,  
   a = Filter(  
      b.y = 5,   
      b = Scan("TableA")  
   )  
)  
```  
  
 Una traducción ineficaz generaría:  
  
```  
SELECT a.x  
FROM (   SELECT *  
         FROM TableA as b  
         WHERE b.y = 5) as a  
```  
  
 Observe que cada nodo de expresión relacional se convierte en una nueva instrucción SELECT de SQL.  
  
 Por tanto, es importante agregar tantos nodos de expresión como sea posible en una única instrucción SELECT de SQL conservando la exactitud.  
  
 El resultado de esta agregación en el ejemplo presentado anteriormente sería:  
  
```  
SELECT b.x   
FROM TableA as b  
WHERE b.y = 5  
```  
  
## <a name="flatten-joins-in-a-sql-select-statement"></a>Reducir combinaciones en una instrucción SELECT de SQL  
 Un caso de agregación de varios nodos en una única instrucción SELECT de SQL consiste en agregar varias expresiones de combinación en una única instrucción SELECT de SQL. DbJoinExpression representa una combinación única entre dos entradas. Sin embargo, como parte de una instrucción SELECT de SQL única, se puede especificar más de una combinación. En este caso, las combinaciones se realizan en el orden especificado.  
  
 Las combinaciones del lateral izquierdo (combinaciones que aparecen como elemento secundario izquierdo de otra combinación) se pueden reducir más fácilmente a una instrucción SELECT de SQL única. Por ejemplo, observe el siguiente árbol de comandos de consulta:  
  
```  
InnerJoin(  
   a = LeftOuterJoin(  
   b = Extent("TableA")  
   c = Extent("TableB")  
   ON b.y = c.x ),  
   d = Extent("TableC")   
   ON a.b.y = d.z  
)  
```  
  
 Esto se puede traducir correctamente en:  
  
```  
SELECT *  
FROM TableA as b  
LEFT OUTER JOIN TableB as c ON b.y = c.x  
INNER JOIN TableC as d ON b.y = d.z  
```  
  
 Sin embargo, las combinaciones no situadas en el lateral izquierdo no se pueden reducir fácilmente y no debe intentar llevar a cabo esta acción. Por ejemplo, las combinaciones del siguiente árbol de comandos de consulta:  
  
```  
InnerJoin(  
   a = Extent("TableA")   
   b = LeftOuterJoin(  
   c = Extent("TableB")  
   d = Extent("TableC")  
   ON c.y = d.x),  
   ON a.z = b.c.y  
)  
```  
  
 Se traducirían a una instrucción SELECT de SQL con una subconsulta.  
  
```  
SELECT *  
FROM TableA as a  
INNER JOIN (SELECT *   
   FROM TableB as c   
   LEFT OUTER JOIN TableC as d  
   ON c.y = d.x) as b  
ON b.y = d.z  
```  
  
## <a name="input-alias-redirecting"></a>Redirección de alias de entrada  
 Para explicar la redirección de alias de entrada, considere la estructura de las expresiones relacionales, como DbFilterExpression, DbProjectExpression, DbCrossJoinExpression, DbJoinExpression, DbSortExpression, DbGroupByExpression, DbApplyExpression y DbSkipExpression.  
  
 Cada uno de estos tipos tiene una o más propiedades Input que describen una colección de entradas, y se usa una variable de enlace correspondiente a cada entrada para representar cada elemento de dicha entrada durante un recorrido de la colección. La variable de enlace se usa al hacer referencia al elemento de entrada, por ejemplo en la propiedad Predicate de DbFilterExpression o en la propiedad Projection de DbProjectExpression.  
  
 Al agregar más nodos de expresión relacional en una única instrucción SELECT de SQL y evaluar una expresión que forma parte de una expresión relacional (por ejemplo parte de la propiedad Projection de DbProjectExpression), es posible que la variable de enlace que utiliza no sea igual que el alias de la entrada, ya que se redirigen varios enlaces de expresión a una única extensión.  Este problema se denomina cambio de nombre de alias.  
  
 Considere el primer ejemplo de este tema. Si se realiza una traducción básica y se traduce Projection a.x (DbPropertyExpression (a, x)), es correcto traducirlo como `a.x`, ya que hemos definido la entrada con el alias "a" para coincidir con la variable de enlace.  Sin embargo, al agregar ambos nodos en una instrucción SELECT de SQL única, debe traducir el mismo elemento DbPropertyExpression a `b.x`, ya que la entrada se ha definido con el alias "b".  
  
## <a name="join-alias-flattening"></a>Eliminación de la información de estructura jerárquica de los alias de combinación  
 A diferencia de cualquier otra expresión relacional en un árbol de comandos de salida, DbJoinExpression genera un tipo de resultado que es una fila compuesta de dos columnas, cada una de las cuales corresponde a una de las entradas. Cuando se crea un elemento DbPropertyExpresssion para tener acceso a una propiedad escalar que procede de una combinación, se sitúa por encima de otro elemento DbPropertyExpresssion.  
  
 En los ejemplos se incluye "a.b.y" en el ejemplo 2 y "b.c.y" en el ejemplo 3. Sin embargo, en las instrucciones SQL correspondientes se hace referencia a ellos como "b.y". Este nuevo uso de alias se denomina reducción de alias de combinación.  
  
## <a name="column-name-and-extent-alias-renaming"></a>Cambio de nombre de una columna y de un alias de extensión  
 Si una consulta SELECT de SQL que tiene una combinación se debe completar con una proyección, al enumerar todas las columnas que participan de las entradas, se puede producir un conflicto de nombres, ya que varias entradas pueden tener el mismo nombre de columna. Utilice un nombre diferente en la columna para evitar el conflicto.  
  
 También, al reducir las combinaciones, las tablas (o subconsultas) que participan pueden usar alias en conflicto, en cuyo caso será necesario cambiar su nombre.  
  
## <a name="avoid-select-"></a>Evitar SELECT *  
 No utilice `SELECT *` para seleccionar en las tablas bases. El modelo de almacenamiento en un [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] aplicación solo puede contener un subconjunto de las columnas que se encuentran en la tabla de base de datos. En este caso, `SELECT *` puede generar un resultado incorrecto. En su lugar, debe especificar todas las columnas que participan utilizando los nombres de columna del tipo de resultado de las expresiones que participan.  
  
## <a name="reuse-of-expressions"></a>Reutilizar expresiones  
 Las expresiones se pueden reutilizar en el árbol de comandos de consulta pasado por [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]. No suponga que cada expresión aparece una sola vez en el árbol de comandos de consulta.  
  
## <a name="mapping-primitive-types"></a>Asignar tipos primitivos  
 Al asignar tipos conceptuales (EDM) a los tipos de proveedor, debe asignar al tipo más ancho (Int32) para que quepan todos los valores posibles. Evite además la asignación a los tipos que no se pueden utilizar para muchas operaciones, como los tipos BLOB (por ejemplo, `ntext` en [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]).  
  
## <a name="see-also"></a>Vea también  
 [Generación de SQL](../../../../../docs/framework/data/adonet/ef/sql-generation.md)
