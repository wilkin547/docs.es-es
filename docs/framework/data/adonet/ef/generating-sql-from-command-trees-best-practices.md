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
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: d94090eadaa634d1cc2912bf60c987c47c1b6a5f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="generating-sql-from-command-trees---best-practices"></a><span data-ttu-id="e0065-102">Generar SQL a partir de árboles de comandos: procedimientos recomendados</span><span class="sxs-lookup"><span data-stu-id="e0065-102">Generating SQL from Command Trees - Best Practices</span></span>
<span data-ttu-id="e0065-103">Los árboles de comandos de consulta de salida crean modelos muy similares a consultas expresables en SQL.</span><span class="sxs-lookup"><span data-stu-id="e0065-103">Output query command trees closely model queries expressible in SQL.</span></span> <span data-ttu-id="e0065-104">Sin embargo, hay ciertos retos comunes para los programadores de proveedores a la hora de generar SQL a partir de un árbol de comandos de salida.</span><span class="sxs-lookup"><span data-stu-id="e0065-104">However, there are certain common challenges for provider writers when generating SQL from an output command tree.</span></span> <span data-ttu-id="e0065-105">En este tema se describen estos retos.</span><span class="sxs-lookup"><span data-stu-id="e0065-105">This topic discusses these challenges.</span></span> <span data-ttu-id="e0065-106">En el tema siguiente, el proveedor de ejemplo muestra cómo actuar ante estos retos.</span><span class="sxs-lookup"><span data-stu-id="e0065-106">In the next topic, the sample provider shows how to address these challenges.</span></span>  
  
## <a name="group-dbexpression-nodes-in-a-sql-select-statement"></a><span data-ttu-id="e0065-107">Agrupar nodos DbExpression en una instrucción SELECT de SQL</span><span class="sxs-lookup"><span data-stu-id="e0065-107">Group DbExpression Nodes in a SQL SELECT Statement</span></span>  
 <span data-ttu-id="e0065-108">Una instrucción SQL típica tiene una estructura anidada con la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="e0065-108">A typical SQL statement has a nested structure of the following shape:</span></span>  
  
```  
SELECT …  
FROM …  
WHERE …  
GROUP BY …  
ORDER BY …  
```  
  
 <span data-ttu-id="e0065-109">Una o más cláusulas pueden estar vacías.</span><span class="sxs-lookup"><span data-stu-id="e0065-109">One or more clauses may be empty.</span></span>  <span data-ttu-id="e0065-110">Una instrucción SELECT anidada puede producirse en cualquiera de las líneas.</span><span class="sxs-lookup"><span data-stu-id="e0065-110">A nested SELECT statement could occur in any of the lines.</span></span>  
  
 <span data-ttu-id="e0065-111">Una posible traducción de un árbol de comandos de consulta en una instrucción SELECT de SQL generaría una subconsulta para cada operador relacional.</span><span class="sxs-lookup"><span data-stu-id="e0065-111">A possible translation of a query command tree into a SQL SELECT statement would produce one subquery for every relational operator.</span></span> <span data-ttu-id="e0065-112">Sin embargo, esto conduciría a subconsultas anidadas innecesarias que serían difíciles de leer.</span><span class="sxs-lookup"><span data-stu-id="e0065-112">However, that would lead to unnecessary nested subqueries that would be difficult to read.</span></span>  <span data-ttu-id="e0065-113">En algunos almacenes de datos, esta consulta puede tener un bajo rendimiento.</span><span class="sxs-lookup"><span data-stu-id="e0065-113">On some data stores, the query may perform poorly.</span></span>  
  
 <span data-ttu-id="e0065-114">Como ejemplo, observe el siguiente árbol de comandos de consulta:</span><span class="sxs-lookup"><span data-stu-id="e0065-114">As an example, consider the following query command tree</span></span>  
  
```  
Project (  
a.x,  
   a = Filter(  
      b.y = 5,   
      b = Scan("TableA")  
   )  
)  
```  
  
 <span data-ttu-id="e0065-115">Una traducción ineficaz generaría:</span><span class="sxs-lookup"><span data-stu-id="e0065-115">An inefficient translation would produce:</span></span>  
  
```  
SELECT a.x  
FROM (   SELECT *  
         FROM TableA as b  
         WHERE b.y = 5) as a  
```  
  
 <span data-ttu-id="e0065-116">Observe que cada nodo de expresión relacional se convierte en una nueva instrucción SELECT de SQL.</span><span class="sxs-lookup"><span data-stu-id="e0065-116">Note that every relational expression node becomes a new SQL SELECT statement.</span></span>  
  
 <span data-ttu-id="e0065-117">Por tanto, es importante agregar tantos nodos de expresión como sea posible en una única instrucción SELECT de SQL conservando la exactitud.</span><span class="sxs-lookup"><span data-stu-id="e0065-117">Therefore, it is important to aggregate as many expression nodes as possible into a single SQL SELECT statement while preserving correctness.</span></span>  
  
 <span data-ttu-id="e0065-118">El resultado de esta agregación en el ejemplo presentado anteriormente sería:</span><span class="sxs-lookup"><span data-stu-id="e0065-118">The result of such aggregation for the example presented above would be:</span></span>  
  
```  
SELECT b.x   
FROM TableA as b  
WHERE b.y = 5  
```  
  
## <a name="flatten-joins-in-a-sql-select-statement"></a><span data-ttu-id="e0065-119">Reducir combinaciones en una instrucción SELECT de SQL</span><span class="sxs-lookup"><span data-stu-id="e0065-119">Flatten Joins in a SQL SELECT Statement</span></span>  
 <span data-ttu-id="e0065-120">Un caso de agregación de varios nodos en una única instrucción SELECT de SQL consiste en agregar varias expresiones de combinación en una única instrucción SELECT de SQL.</span><span class="sxs-lookup"><span data-stu-id="e0065-120">One case of aggregating multiple nodes into a single SQL SELECT statement is aggregating multiple join expressions into a single SQL SELECT statement.</span></span> <span data-ttu-id="e0065-121">DbJoinExpression representa una combinación única entre dos entradas.</span><span class="sxs-lookup"><span data-stu-id="e0065-121">DbJoinExpression represents a single join between two inputs.</span></span> <span data-ttu-id="e0065-122">Sin embargo, como parte de una instrucción SELECT de SQL única, se puede especificar más de una combinación.</span><span class="sxs-lookup"><span data-stu-id="e0065-122">However, as part of a single SQL SELECT statement, more than one join can be specified.</span></span> <span data-ttu-id="e0065-123">En este caso, las combinaciones se realizan en el orden especificado.</span><span class="sxs-lookup"><span data-stu-id="e0065-123">In that case the joins are performed in the order specified.</span></span>  
  
 <span data-ttu-id="e0065-124">Las combinaciones del lateral izquierdo (combinaciones que aparecen como elemento secundario izquierdo de otra combinación) se pueden reducir más fácilmente a una instrucción SELECT de SQL única.</span><span class="sxs-lookup"><span data-stu-id="e0065-124">Left spine joins, (joins that appear as a left child of another join) can be more easily flattened into a single SQL SELECT statement.</span></span> <span data-ttu-id="e0065-125">Por ejemplo, observe el siguiente árbol de comandos de consulta:</span><span class="sxs-lookup"><span data-stu-id="e0065-125">For example, consider the following query command tree:</span></span>  
  
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
  
 <span data-ttu-id="e0065-126">Esto se puede traducir correctamente en:</span><span class="sxs-lookup"><span data-stu-id="e0065-126">This can be correctly translated into:</span></span>  
  
```  
SELECT *  
FROM TableA as b  
LEFT OUTER JOIN TableB as c ON b.y = c.x  
INNER JOIN TableC as d ON b.y = d.z  
```  
  
 <span data-ttu-id="e0065-127">Sin embargo, las combinaciones no situadas en el lateral izquierdo no se pueden reducir fácilmente y no debe intentar llevar a cabo esta acción.</span><span class="sxs-lookup"><span data-stu-id="e0065-127">However, non-left spine joins cannot easily be flattened, and you should not try to flatten them.</span></span> <span data-ttu-id="e0065-128">Por ejemplo, las combinaciones del siguiente árbol de comandos de consulta:</span><span class="sxs-lookup"><span data-stu-id="e0065-128">For example, the joins in the following query command tree:</span></span>  
  
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
  
 <span data-ttu-id="e0065-129">Se traducirían a una instrucción SELECT de SQL con una subconsulta.</span><span class="sxs-lookup"><span data-stu-id="e0065-129">Would be translated to a SQL SELECT statement with a sub-query.</span></span>  
  
```  
SELECT *  
FROM TableA as a  
INNER JOIN (SELECT *   
   FROM TableB as c   
   LEFT OUTER JOIN TableC as d  
   ON c.y = d.x) as b  
ON b.y = d.z  
```  
  
## <a name="input-alias-redirecting"></a><span data-ttu-id="e0065-130">Redirección de alias de entrada</span><span class="sxs-lookup"><span data-stu-id="e0065-130">Input Alias Redirecting</span></span>  
 <span data-ttu-id="e0065-131">Para explicar la redirección de alias de entrada, considere la estructura de las expresiones relacionales, como DbFilterExpression, DbProjectExpression, DbCrossJoinExpression, DbJoinExpression, DbSortExpression, DbGroupByExpression, DbApplyExpression y DbSkipExpression.</span><span class="sxs-lookup"><span data-stu-id="e0065-131">To explain input alias redirecting, consider the structure of the relational expressions, such as DbFilterExpression, DbProjectExpression, DbCrossJoinExpression, DbJoinExpression, DbSortExpression, DbGroupByExpression, DbApplyExpression, and DbSkipExpression.</span></span>  
  
 <span data-ttu-id="e0065-132">Cada uno de estos tipos tiene una o más propiedades Input que describen una colección de entradas, y se usa una variable de enlace correspondiente a cada entrada para representar cada elemento de dicha entrada durante un recorrido de la colección.</span><span class="sxs-lookup"><span data-stu-id="e0065-132">Each of these types has one or more Input properties that describe an input collection, and a binding variable corresponding to each input is used to represent each element of that input during a collection traversal.</span></span> <span data-ttu-id="e0065-133">La variable de enlace se usa al hacer referencia al elemento de entrada, por ejemplo en la propiedad Predicate de DbFilterExpression o en la propiedad Projection de DbProjectExpression.</span><span class="sxs-lookup"><span data-stu-id="e0065-133">The binding variable is used when referring to the input element, for example in the Predicate property of a DbFilterExpression or the Projection property of a DbProjectExpression.</span></span>  
  
 <span data-ttu-id="e0065-134">Al agregar más nodos de expresión relacional en una única instrucción SELECT de SQL y evaluar una expresión que forma parte de una expresión relacional (por ejemplo parte de la propiedad Projection de DbProjectExpression), es posible que la variable de enlace que utiliza no sea igual que el alias de la entrada, ya que se redirigen varios enlaces de expresión a una única extensión.</span><span class="sxs-lookup"><span data-stu-id="e0065-134">When aggregating more relational expression nodes into a single SQL SELECT statement, and evaluating an expression that is part of a relational expression (for example part of the Projection property of a DbProjectExpression) the binding variable that it uses may not be the same as the alias of the input, as multiple expression bindings would have to be redirected to a single extent.</span></span>  <span data-ttu-id="e0065-135">Este problema se denomina cambio de nombre de alias.</span><span class="sxs-lookup"><span data-stu-id="e0065-135">This problem is called alias renaming.</span></span>  
  
 <span data-ttu-id="e0065-136">Considere el primer ejemplo de este tema.</span><span class="sxs-lookup"><span data-stu-id="e0065-136">Consider the first example in this topic.</span></span> <span data-ttu-id="e0065-137">Si se realiza una traducción básica y se traduce Projection a.x (DbPropertyExpression (a, x)), es correcto traducirlo como `a.x`, ya que hemos definido la entrada con el alias "a" para coincidir con la variable de enlace.</span><span class="sxs-lookup"><span data-stu-id="e0065-137">If doing the naïve translation and translating the Projection a.x (DbPropertyExpression(a, x)), it is correct to translate it into `a.x` because we have aliased the input as "a" to match the binding variable.</span></span>  <span data-ttu-id="e0065-138">Sin embargo, al agregar ambos nodos en una instrucción SELECT de SQL única, debe traducir el mismo elemento DbPropertyExpression a `b.x`, ya que la entrada se ha definido con el alias "b".</span><span class="sxs-lookup"><span data-stu-id="e0065-138">However, when aggregating both the nodes into a single SQL SELECT statement, you need to translate the same DbPropertyExpression into `b.x`, as the input has been aliased with "b".</span></span>  
  
## <a name="join-alias-flattening"></a><span data-ttu-id="e0065-139">Eliminación de la información de estructura jerárquica de los alias de combinación</span><span class="sxs-lookup"><span data-stu-id="e0065-139">Join Alias Flattening</span></span>  
 <span data-ttu-id="e0065-140">A diferencia de cualquier otra expresión relacional en un árbol de comandos de salida, DbJoinExpression genera un tipo de resultado que es una fila compuesta de dos columnas, cada una de las cuales corresponde a una de las entradas.</span><span class="sxs-lookup"><span data-stu-id="e0065-140">Unlike any other relational expression in an output command tree, the DbJoinExpression outputs a result type that is a row consisting of two columns, each of which corresponds to one of the inputs.</span></span> <span data-ttu-id="e0065-141">Cuando se crea un elemento DbPropertyExpresssion para tener acceso a una propiedad escalar que procede de una combinación, se sitúa por encima de otro elemento DbPropertyExpresssion.</span><span class="sxs-lookup"><span data-stu-id="e0065-141">When a DbPropertyExpresssion is built to access a scalar property originating from a join, it is over another DbPropertyExpresssion.</span></span>  
  
 <span data-ttu-id="e0065-142">En los ejemplos se incluye "a.b.y" en el ejemplo 2 y "b.c.y" en el ejemplo 3.</span><span class="sxs-lookup"><span data-stu-id="e0065-142">Examples include "a.b.y" in example 2 and "b.c.y" in example 3.</span></span> <span data-ttu-id="e0065-143">Sin embargo, en las instrucciones SQL correspondientes se hace referencia a ellos como "b.y".</span><span class="sxs-lookup"><span data-stu-id="e0065-143">However in the corresponding SQL statements these are referred as "b.y".</span></span> <span data-ttu-id="e0065-144">Este nuevo uso de alias se denomina reducción de alias de combinación.</span><span class="sxs-lookup"><span data-stu-id="e0065-144">This re-aliasing is called join alias flattening.</span></span>  
  
## <a name="column-name-and-extent-alias-renaming"></a><span data-ttu-id="e0065-145">Cambio de nombre de una columna y de un alias de extensión</span><span class="sxs-lookup"><span data-stu-id="e0065-145">Column Name and Extent Alias Renaming</span></span>  
 <span data-ttu-id="e0065-146">Si una consulta SELECT de SQL que tiene una combinación se debe completar con una proyección, al enumerar todas las columnas que participan de las entradas, se puede producir un conflicto de nombres, ya que varias entradas pueden tener el mismo nombre de columna.</span><span class="sxs-lookup"><span data-stu-id="e0065-146">If a SQL SELECT query that has a join has to be completed with a projection, when enumerating all the participating columns from the inputs, a name collision may occur, as more than one input may have the same column name.</span></span> <span data-ttu-id="e0065-147">Utilice un nombre diferente en la columna para evitar el conflicto.</span><span class="sxs-lookup"><span data-stu-id="e0065-147">Use a different name for the column to avoid the collision.</span></span>  
  
 <span data-ttu-id="e0065-148">También, al reducir las combinaciones, las tablas (o subconsultas) que participan pueden usar alias en conflicto, en cuyo caso será necesario cambiar su nombre.</span><span class="sxs-lookup"><span data-stu-id="e0065-148">Also, when flattening joins, participating tables (or subqueries) may have colliding aliases in which case these need to be renamed.</span></span>  
  
## <a name="avoid-select-"></a><span data-ttu-id="e0065-149">Evitar SELECT *</span><span class="sxs-lookup"><span data-stu-id="e0065-149">Avoid SELECT *</span></span>  
 <span data-ttu-id="e0065-150">No utilice `SELECT *` para seleccionar en las tablas bases.</span><span class="sxs-lookup"><span data-stu-id="e0065-150">Do not use `SELECT *` to select from base tables.</span></span> <span data-ttu-id="e0065-151">El modelo de almacenamiento en un [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] aplicación solo puede contener un subconjunto de las columnas que se encuentran en la tabla de base de datos.</span><span class="sxs-lookup"><span data-stu-id="e0065-151">The storage model in an [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] application may only include a subset of the columns that are in the database table.</span></span> <span data-ttu-id="e0065-152">En este caso, `SELECT *` puede generar un resultado incorrecto.</span><span class="sxs-lookup"><span data-stu-id="e0065-152">In this case, `SELECT *` may produce an incorrect result.</span></span> <span data-ttu-id="e0065-153">En su lugar, debe especificar todas las columnas que participan utilizando los nombres de columna del tipo de resultado de las expresiones que participan.</span><span class="sxs-lookup"><span data-stu-id="e0065-153">Instead, you should specify all participating columns by using the column names from the result type of the participating expressions.</span></span>  
  
## <a name="reuse-of-expressions"></a><span data-ttu-id="e0065-154">Reutilizar expresiones</span><span class="sxs-lookup"><span data-stu-id="e0065-154">Reuse of Expressions</span></span>  
 <span data-ttu-id="e0065-155">Las expresiones se pueden reutilizar en el árbol de comandos de consulta pasado por [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e0065-155">Expressions may be reused in the query command tree passed by the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="e0065-156">No suponga que cada expresión aparece una sola vez en el árbol de comandos de consulta.</span><span class="sxs-lookup"><span data-stu-id="e0065-156">Do not assume that each expression appears only once in the query command tree.</span></span>  
  
## <a name="mapping-primitive-types"></a><span data-ttu-id="e0065-157">Asignar tipos primitivos</span><span class="sxs-lookup"><span data-stu-id="e0065-157">Mapping Primitive Types</span></span>  
 <span data-ttu-id="e0065-158">Al asignar tipos conceptuales (EDM) a los tipos de proveedor, debe asignar al tipo más ancho (Int32) para que quepan todos los valores posibles.</span><span class="sxs-lookup"><span data-stu-id="e0065-158">When mapping conceptual (EDM) types to provider types, you should map to the widest type (Int32) so that all possible values fit.</span></span> <span data-ttu-id="e0065-159">Evite además la asignación a los tipos que no se pueden utilizar para muchas operaciones, como los tipos BLOB (por ejemplo, `ntext` en [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="e0065-159">Also, avoid mapping to types that cannot be used for many operations, like BLOB types (for example, `ntext` in [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0065-160">Vea también</span><span class="sxs-lookup"><span data-stu-id="e0065-160">See Also</span></span>  
 [<span data-ttu-id="e0065-161">Generación de SQL</span><span class="sxs-lookup"><span data-stu-id="e0065-161">SQL Generation</span></span>](../../../../../docs/framework/data/adonet/ef/sql-generation.md)
