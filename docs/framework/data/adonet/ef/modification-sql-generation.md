---
title: Generar SQL de modificación
ms.date: 03/30/2017
ms.assetid: 2188a39d-46ed-4a8b-906a-c9f15e6fefd1
ms.openlocfilehash: b6c1b71effba17d33c035d0f1df386bf56d405b5
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039898"
---
# <a name="modification-sql-generation"></a><span data-ttu-id="abf42-102">Generar SQL de modificación</span><span class="sxs-lookup"><span data-stu-id="abf42-102">Modification SQL Generation</span></span>

<span data-ttu-id="abf42-103">En esta sección se describe cómo desarrollar un módulo de generación de SQL de modificación para el proveedor (de bases de datos conformes a SQL:1999).</span><span class="sxs-lookup"><span data-stu-id="abf42-103">This section discusses how to develop a modification SQL generation module for your (SQL:1999-compliant database) provider.</span></span> <span data-ttu-id="abf42-104">Este módulo es responsable de la conversión de un árbol de comandos de modificación en las instrucciones INSERT, UPDATE o DELETE de SQL adecuadas.</span><span class="sxs-lookup"><span data-stu-id="abf42-104">This module is responsible for translating a modification command tree into the appropriate SQL INSERT, UPDATE or DELETE statements.</span></span>

<span data-ttu-id="abf42-105">Para obtener información sobre la generación de SQL para las instrucciones SELECT, vea [generación de SQL](sql-generation.md).</span><span class="sxs-lookup"><span data-stu-id="abf42-105">For information about SQL generation for select statements, see [SQL Generation](sql-generation.md).</span></span>

## <a name="overview-of-modification-command-trees"></a><span data-ttu-id="abf42-106">Información general sobre los árboles de comandos de modificación</span><span class="sxs-lookup"><span data-stu-id="abf42-106">Overview of Modification Command Trees</span></span>

<span data-ttu-id="abf42-107">El módulo de generación de SQL de modificación genera instrucciones SQL de modificación específicas de la base de datos en función de un DbModificationCommandTree de entrada determinado.</span><span class="sxs-lookup"><span data-stu-id="abf42-107">The modification SQL generation module generates database-specific modification SQL statements based on a given input DbModificationCommandTree.</span></span>

<span data-ttu-id="abf42-108">DbModificationCommandTree es una representación del modelo de objetos de una operación DML de modificación (una operación de inserción, actualización o eliminación), que hereda de DbCommandTree.</span><span class="sxs-lookup"><span data-stu-id="abf42-108">A DbModificationCommandTree is an object model representation of a modification DML operation (an insert, an update, or a delete operation), inheriting from DbCommandTree.</span></span> <span data-ttu-id="abf42-109">Hay tres implementaciones de DbModificationCommandTree:</span><span class="sxs-lookup"><span data-stu-id="abf42-109">There are three implementations of DbModificationCommandTree:</span></span>

- <span data-ttu-id="abf42-110">DbInsertCommandTree</span><span class="sxs-lookup"><span data-stu-id="abf42-110">DbInsertCommandTree</span></span>

- <span data-ttu-id="abf42-111">DbUpdateCommandTree</span><span class="sxs-lookup"><span data-stu-id="abf42-111">DbUpdateCommandTree</span></span>

- <span data-ttu-id="abf42-112">DbDeleteCommandTree</span><span class="sxs-lookup"><span data-stu-id="abf42-112">DbDeleteCommandTree</span></span>

<span data-ttu-id="abf42-113">DbModificationCommandTree y sus implementaciones generadas por el Entity Framework siempre representan una operación de una sola fila.</span><span class="sxs-lookup"><span data-stu-id="abf42-113">DbModificationCommandTree and its implementations that are produced by the Entity Framework always represent a single row operation.</span></span> <span data-ttu-id="abf42-114">En esta sección se describen estos tipos con sus restricciones en .NET Framework versión 3.5.</span><span class="sxs-lookup"><span data-stu-id="abf42-114">This section describes these types with their constraints in the .NET Framework version 3.5.</span></span>

<span data-ttu-id="abf42-115">![Diagram](./media/558ba7b3-dd19-48d0-b91e-30a76415bf5f.gif "558ba7b3-dd19-48d0-b91e-30a76415bf5f")</span><span class="sxs-lookup"><span data-stu-id="abf42-115">![Diagram](./media/558ba7b3-dd19-48d0-b91e-30a76415bf5f.gif "558ba7b3-dd19-48d0-b91e-30a76415bf5f")</span></span>

<span data-ttu-id="abf42-116">DbModificationCommandTree tiene una propiedad de destino que representa el conjunto de destinos para la operación de modificación.</span><span class="sxs-lookup"><span data-stu-id="abf42-116">DbModificationCommandTree has a Target property that represents the target set for the modification operation.</span></span> <span data-ttu-id="abf42-117">La propiedad Expression del destino, que define el conjunto de entrada, siempre es DbScanExpression.</span><span class="sxs-lookup"><span data-stu-id="abf42-117">The Target’s Expression property, which defines the input set is always DbScanExpression.</span></span>  <span data-ttu-id="abf42-118">Un DbScanExpression puede representar una tabla o una vista, o un conjunto de datos definido con una consulta si la propiedad de metadatos "definiendo consulta" de su destino no es NULL.</span><span class="sxs-lookup"><span data-stu-id="abf42-118">A DbScanExpression can either represent a table or a view, or a set of data defined with a query if the metadata property "Defining Query" of its Target is non-null.</span></span>

<span data-ttu-id="abf42-119">Una expresión DbScanExpression que representa una consulta solo puede alcanzar un proveedor como destino de la modificación si el conjunto se definió mediante una consulta de definición del modelo pero no se proporcionó ninguna función para la operación de modificación correspondiente.</span><span class="sxs-lookup"><span data-stu-id="abf42-119">A DbScanExpression that represents a query could only reach a provider as a target of modification if the set was defined by using a defining query in the model but no function was provided for the corresponding modification operation.</span></span> <span data-ttu-id="abf42-120">Es posible que los proveedores no puedan admitir este tipo de escenario (por ejemplo, SqlClient no puede).</span><span class="sxs-lookup"><span data-stu-id="abf42-120">Providers may not be able to support such a scenario (SqlClient, for example, does not).</span></span>

<span data-ttu-id="abf42-121">DbInsertCommandTree representa una operación de inserción de una sola fila expresada como un árbol de comandos.</span><span class="sxs-lookup"><span data-stu-id="abf42-121">DbInsertCommandTree represents a single row insert operation expressed as a command tree.</span></span>

```csharp
public sealed class DbInsertCommandTree : DbModificationCommandTree {
   public IList<DbModificationClause> SetClauses { get }
   public DbExpression Returning { get }
}
```

<span data-ttu-id="abf42-122">DbUpdateCommandTree representa una operación de actualización de una sola fila expresada como un árbol de comandos.</span><span class="sxs-lookup"><span data-stu-id="abf42-122">DbUpdateCommandTree represents a single-row update operation expressed as a command tree.</span></span>

<span data-ttu-id="abf42-123">DbDeleteCommandTree representa una operación de eliminación de una sola fila expresada como un árbol de comandos.</span><span class="sxs-lookup"><span data-stu-id="abf42-123">DbDeleteCommandTree represents a single row delete operation expressed as a command tree.</span></span>

### <a name="restrictions-on-modification-command-tree-properties"></a><span data-ttu-id="abf42-124">Restricciones en las propiedades del árbol de comandos de modificación</span><span class="sxs-lookup"><span data-stu-id="abf42-124">Restrictions on Modification Command Tree Properties</span></span>

<span data-ttu-id="abf42-125">La información y restricciones siguientes se aplican a las propiedades del árbol de comandos de modificación.</span><span class="sxs-lookup"><span data-stu-id="abf42-125">The following information and restrictions apply to the modification command tree properties.</span></span>

#### <a name="returning-in-dbinsertcommandtree-and-dbupdatecommandtree"></a><span data-ttu-id="abf42-126">Returning en DbInsertCommandTree y DbUpdateCommandTree</span><span class="sxs-lookup"><span data-stu-id="abf42-126">Returning in DbInsertCommandTree and DbUpdateCommandTree</span></span>

<span data-ttu-id="abf42-127">Cuando no es NULL, Returning indica que el comando devuelve un lector.</span><span class="sxs-lookup"><span data-stu-id="abf42-127">When non-null, Returning indicates that the command returns a reader.</span></span> <span data-ttu-id="abf42-128">De lo contrario, el comando debe devolver un valor escalar que indique el número de filas afectadas (insertadas o actualizadas).</span><span class="sxs-lookup"><span data-stu-id="abf42-128">Otherwise, the command should return a scalar value indicating the number of rows affected (inserted or updated).</span></span>

<span data-ttu-id="abf42-129">El valor de Returning especifica una proyección de resultados que se van a devolver en función de la fila insertada o actualizada.</span><span class="sxs-lookup"><span data-stu-id="abf42-129">The Returning value specifies a projection of results to be returned based on the inserted or the updated row.</span></span> <span data-ttu-id="abf42-130">Solo puede ser de tipo DbNewInstanceExpression que representa una fila, y cada uno de sus argumentos es DbPropertyExpression en una expresión DbVariableReferenceExpression que representa una referencia al destino del árbol DbModificationCommandTree correspondiente.</span><span class="sxs-lookup"><span data-stu-id="abf42-130">It can only be of type DbNewInstanceExpression representing a row, with each of its arguments being a DbPropertyExpression over a DbVariableReferenceExpression representing a reference to the Target of the corresponding DbModificationCommandTree.</span></span> <span data-ttu-id="abf42-131">Las propiedades representadas por las expresiones DbPropertyExpressions utilizadas en la propiedad Returning siempre son valores calculados o generados por el almacén.</span><span class="sxs-lookup"><span data-stu-id="abf42-131">The properties represented by the DbPropertyExpressions used in the property Returning are always store generated or computed values.</span></span> <span data-ttu-id="abf42-132">En DbInsertCommandTree, Returning no es NULL cuando al menos una propiedad de la tabla en la que se inserta la fila se especifica como calculada o generada por el almacén (se marca como StoreGeneratedPattern.Identity o StoreGeneratedPattern.Computed en ssdl).</span><span class="sxs-lookup"><span data-stu-id="abf42-132">In DbInsertCommandTree, Returning is not null when at least one property of the table in which the row is being inserted is specified as store generated or computed (marked as StoreGeneratedPattern.Identity or StoreGeneratedPattern.Computed in the ssdl).</span></span> <span data-ttu-id="abf42-133">En DbUpdateCommandTrees, Returning no es NULL cuando al menos una propiedad de la tabla en la que se actualiza la fila se especifica como calculada en el almacén (se marca como StoreGeneratedPattern.Computed en ssdl).</span><span class="sxs-lookup"><span data-stu-id="abf42-133">In DbUpdateCommandTrees, Returning is not null when at least one property of the table in which the row is being updated is specified as store computed (marked as StoreGeneratedPattern.Computed in the ssdl).</span></span>

#### <a name="setclauses-in-dbinsertcommandtree-and-dbupdatecommandtree"></a><span data-ttu-id="abf42-134">SetClauses en DbInsertCommandTree y DbUpdateCommandTree</span><span class="sxs-lookup"><span data-stu-id="abf42-134">SetClauses in DbInsertCommandTree and DbUpdateCommandTree</span></span>

<span data-ttu-id="abf42-135">SetClauses especifica la lista de cláusulas de inserción o actualización que definen la operación de inserción o actualización.</span><span class="sxs-lookup"><span data-stu-id="abf42-135">SetClauses specifies the list of insert or update set clauses that define the insert or update operation.</span></span>

<span data-ttu-id="abf42-136">Los elementos de la lista se especifican como tipo DbModificationClause, que especifica una sola cláusula en una operación de modificación de inserción o actualización.</span><span class="sxs-lookup"><span data-stu-id="abf42-136">The elements of the list are specified as type DbModificationClause, which specifies a single clause in an insert or update modification operation.</span></span> <span data-ttu-id="abf42-137">DbSetClause hereda de DbModificationClause y especifica la cláusula en una operación de modificación que establece el valor de una propiedad.</span><span class="sxs-lookup"><span data-stu-id="abf42-137">DbSetClause inherits from DbModificationClause and specifies the clause in a modification operation that sets the value of a property.</span></span> <span data-ttu-id="abf42-138">A partir de la versión 3,5 del .NET Framework, todos los elementos de SetClauses son del tipo SetClause.</span><span class="sxs-lookup"><span data-stu-id="abf42-138">Beginning in version 3.5 of the .NET Framework, all elements in SetClauses are of type SetClause.</span></span>

<span data-ttu-id="abf42-139">Property especifica la propiedad que se debe actualizar.</span><span class="sxs-lookup"><span data-stu-id="abf42-139">Property specifies the property that should be updated.</span></span> <span data-ttu-id="abf42-140">Siempre es DbPropertyExpression en DbVariableReferenceExpression, que representa una referencia al destino del árbol DbModificationCommandTree correspondiente.</span><span class="sxs-lookup"><span data-stu-id="abf42-140">It is always a DbPropertyExpression over a DbVariableReferenceExpression, which represents a reference to the Target of the corresponding DbModificationCommandTree.</span></span>

<span data-ttu-id="abf42-141">Value especifica el nuevo valor con el que se actualiza la propiedad.</span><span class="sxs-lookup"><span data-stu-id="abf42-141">Value specifies the new value with which to update the property.</span></span> <span data-ttu-id="abf42-142">Es de tipo DbConstantExpression o DbNullExpression.</span><span class="sxs-lookup"><span data-stu-id="abf42-142">It is either of type DbConstantExpression or DbNullExpression.</span></span>

#### <a name="predicate-in-dbupdatecommandtree-and-dbdeletecommandtree"></a><span data-ttu-id="abf42-143">Predicate en DbUpdateCommandTree y DbDeleteCommandTree</span><span class="sxs-lookup"><span data-stu-id="abf42-143">Predicate in DbUpdateCommandTree and DbDeleteCommandTree</span></span>

<span data-ttu-id="abf42-144">Predicate especifica el predicado que se usa para determinar qué miembros de la colección de destino se deben actualizar o eliminar.</span><span class="sxs-lookup"><span data-stu-id="abf42-144">Predicate specifies the predicate used to determine which members of the target collection should be updated or deleted.</span></span> <span data-ttu-id="abf42-145">Es un árbol de expresión generado del siguiente subconjunto de DbExpressions:</span><span class="sxs-lookup"><span data-stu-id="abf42-145">It is an expression tree built of the following subset of DbExpressions:</span></span>

- <span data-ttu-id="abf42-146">DbComparisonExpression of Kind es igual a, donde el elemento secundario Right es DbPropertyExpression como Restricted a continuación y el elemento secundario Left a DbConstantExpression.</span><span class="sxs-lookup"><span data-stu-id="abf42-146">DbComparisonExpression of kind Equals, with the right child being a DbPropertyExpression as restricted below and the left child a DbConstantExpression.</span></span>

- <span data-ttu-id="abf42-147">DbConstantExpression</span><span class="sxs-lookup"><span data-stu-id="abf42-147">DbConstantExpression</span></span>

- <span data-ttu-id="abf42-148">DbIsNullExpression a través de DbPropertyExpression como restringido a continuación</span><span class="sxs-lookup"><span data-stu-id="abf42-148">DbIsNullExpression over a DbPropertyExpression as restricted below</span></span>

- <span data-ttu-id="abf42-149">DbPropertyExpression en DbVariableReferenceExpression, que representa una referencia al destino del árbol DbModificationCommandTree correspondiente.</span><span class="sxs-lookup"><span data-stu-id="abf42-149">DbPropertyExpression over a DbVariableReferenceExpression representing a reference to the Target of the corresponding DbModificationCommandTree.</span></span>

- <span data-ttu-id="abf42-150">DbAndExpression</span><span class="sxs-lookup"><span data-stu-id="abf42-150">DbAndExpression</span></span>

- <span data-ttu-id="abf42-151">DbNotExpression</span><span class="sxs-lookup"><span data-stu-id="abf42-151">DbNotExpression</span></span>

- <span data-ttu-id="abf42-152">DbOrExpression</span><span class="sxs-lookup"><span data-stu-id="abf42-152">DbOrExpression</span></span>

## <a name="modification-sql-generation-in-the-sample-provider"></a><span data-ttu-id="abf42-153">Generación de SQL de modificación en el proveedor de ejemplo</span><span class="sxs-lookup"><span data-stu-id="abf42-153">Modification SQL Generation in the Sample Provider</span></span>

<span data-ttu-id="abf42-154">En el [Entity Framework proveedor de ejemplo](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) se muestran los componentes de los proveedores de datos de ADO.net que admiten el Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="abf42-154">The [Entity Framework Sample Provider](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) demonstrates the components of ADO.NET Data Providers that support the Entity Framework.</span></span> <span data-ttu-id="abf42-155">Tiene como destino una base de datos de SQL Server 2005 y se implementa como un contenedor en el proveedor de datos ADO.NET 2.0 System.Data.SqlClient.</span><span class="sxs-lookup"><span data-stu-id="abf42-155">It targets a SQL Server 2005 database and is implemented as a wrapper on top of System.Data.SqlClient ADO.NET 2.0 Data Provider.</span></span>

<span data-ttu-id="abf42-156">El módulo de generación de SQL de modificación del proveedor de ejemplo (situado en el archivo SQL Generation\DmlSqlGenerator.cs) toma un árbol DbModificationCommandTree como entrada y genera una única instrucción SQL de modificación posiblemente seguida por una instrucción SELECT para devolver un lector si se especifica en DbModificationCommandTree.</span><span class="sxs-lookup"><span data-stu-id="abf42-156">The modification SQL generation module of the sample provider (located in the file SQL Generation\DmlSqlGenerator.cs) takes an input DbModificationCommandTree and produces a single modification SQL statement possibly followed by a select statement to return a reader if specified by the DbModificationCommandTree.</span></span> <span data-ttu-id="abf42-157">Observe que la base de datos de SQL Server de destino afecta a la forma de los comandos generados.</span><span class="sxs-lookup"><span data-stu-id="abf42-157">Note that the shape of the commands generated is affected by the target SQL Server database.</span></span>

### <a name="helper-classes-expressiontranslator"></a><span data-ttu-id="abf42-158">clases del asistente: ExpressionTranslator</span><span class="sxs-lookup"><span data-stu-id="abf42-158">Helper Classes: ExpressionTranslator</span></span>

<span data-ttu-id="abf42-159">ExpressionTranslator actúa como un traductor ligero común para todas las propiedades del árbol de comandos de modificación de tipo DbExpression.</span><span class="sxs-lookup"><span data-stu-id="abf42-159">ExpressionTranslator serves as a common lightweight translator for all modification command tree properties of type DbExpression.</span></span> <span data-ttu-id="abf42-160">Únicamente admite la traducción de los tipos de expresión a los que están restringidas las propiedades del árbol de comandos de modificación y se genera con las restricciones determinadas en mente.</span><span class="sxs-lookup"><span data-stu-id="abf42-160">It supports translation of only the expression types to which the properties of the modification command tree are constrained and is built with the particular constraints in mind.</span></span>

<span data-ttu-id="abf42-161">La siguiente información describe la visita de tipos de expresión específicos (se omiten los nodos con traducciones triviales).</span><span class="sxs-lookup"><span data-stu-id="abf42-161">The following information discusses visiting specific expression types (nodes with trivial translations are omitted).</span></span>

### <a name="dbcomparisonexpression"></a><span data-ttu-id="abf42-162">DbComparisonExpression</span><span class="sxs-lookup"><span data-stu-id="abf42-162">DbComparisonExpression</span></span>

<span data-ttu-id="abf42-163">Cuando ExpressionTranslator se construye con preserveMemberValues = true y la constante de la derecha es DbConstantExpression (en lugar de DbNullExpression), asocia el operando izquierdo (DbPropertyExpressions) a DbConstantExpression.</span><span class="sxs-lookup"><span data-stu-id="abf42-163">When the ExpressionTranslator is constructed with preserveMemberValues = true, and when the constant to the right is a DbConstantExpression (instead of DbNullExpression), it associates the left operand (a DbPropertyExpressions) with that DbConstantExpression.</span></span> <span data-ttu-id="abf42-164">Se utiliza eso si es necesario generar una instrucción Select devuelta para identificar la fila afectada.</span><span class="sxs-lookup"><span data-stu-id="abf42-164">That is used if a return Select statement needs to be generated to identify the affected row.</span></span>

### <a name="dbconstantexpression"></a><span data-ttu-id="abf42-165">DbConstantExpression</span><span class="sxs-lookup"><span data-stu-id="abf42-165">DbConstantExpression</span></span>

<span data-ttu-id="abf42-166">Se crea un parámetro para cada constante visitada.</span><span class="sxs-lookup"><span data-stu-id="abf42-166">For each visited constant a parameter is created.</span></span>

### <a name="dbpropertyexpression"></a><span data-ttu-id="abf42-167">DbPropertyExpression</span><span class="sxs-lookup"><span data-stu-id="abf42-167">DbPropertyExpression</span></span>

<span data-ttu-id="abf42-168">Dado que la instancia de DbPropertyExpression siempre representa la tabla de entrada, a menos que la generación haya creado un alias (lo que solo sucede en escenarios de actualización cuando se utiliza una variable de tabla), no es necesario especificar ningún alias para la entrada; la traducción tiene como valor predeterminado el nombre de propiedad.</span><span class="sxs-lookup"><span data-stu-id="abf42-168">Given that the Instance of the DbPropertyExpression always represents the input table, unless the generation has created an alias (which only happens in update scenarios when a table variable is used), no alias needs to be specified for the input; the translation defaults to the property name.</span></span>

## <a name="generating-an-insert-sql-command"></a><span data-ttu-id="abf42-169">Generar un comando SQL de inserción</span><span class="sxs-lookup"><span data-stu-id="abf42-169">Generating an Insert SQL Command</span></span>

<span data-ttu-id="abf42-170">Para una implementación DbInsertCommandTree determinada en el proveedor de ejemplo, el comando de inserción generado sigue una de las dos plantillas de inserción siguientes.</span><span class="sxs-lookup"><span data-stu-id="abf42-170">For a given DbInsertCommandTree in the sample provider, the generated insert command follows one of the two insert templates below.</span></span>

<span data-ttu-id="abf42-171">La primera plantilla incluye un comando para realizar la inserción dados los valores de la lista de SetClauses y una instrucción SELECT para devolver las propiedades especificadas en la propiedad Returning para la fila insertada si la propiedad Returning no es NULL.</span><span class="sxs-lookup"><span data-stu-id="abf42-171">The first template has a command to perform the insert given the values in the list of SetClauses, and a SELECT statement to return the properties specified in the Returning property for the inserted row if the Returning property was not null.</span></span> <span data-ttu-id="abf42-172">El elemento de predicado "\@@ROWCOUNT > 0" es true si se insertó una fila.</span><span class="sxs-lookup"><span data-stu-id="abf42-172">The predicate element "\@@ROWCOUNT > 0" is true if a row was inserted.</span></span> <span data-ttu-id="abf42-173">El elemento de predicado "keyMemberI &#124; = keyValueI SCOPE_IDENTITY ()" toma la forma "keyMemberI = SCOPE_IDENTITY ()" solo si keyMemberI es una clave generada por el almacén, ya que SCOPE_IDENTITY () devuelve el último valor de identidad insertado en una identidad ( columna generada por el almacén).</span><span class="sxs-lookup"><span data-stu-id="abf42-173">The predicate element "keyMemberI =  keyValueI &#124; scope_identity()" takes the shape  "keyMemberI =  scope_identity()" only if keyMemberI is a store-generated key, because scope_identity() returns the last identity value inserted into an identity (store-generated) column.</span></span>

```sql
-- first insert Template
INSERT <target>   [ (setClauseProperty0, .. setClausePropertyN)]
VALUES (setClauseValue0, .. setClauseValueN) |  DEFAULT VALUES

[SELECT <returning>
 FROM <target>
 WHERE @@ROWCOUNT > 0 AND keyMember0 = keyValue0 AND .. keyMemberI =  keyValueI | scope_identity()  .. AND  keyMemberN = keyValueN]
```

<span data-ttu-id="abf42-174">La segunda plantilla es necesaria si la inserción especifica la inserción de una fila cuya clave principal es generada por el almacén pero no es de tipo entero y, por tanto, no se puede usar con scope_identity().</span><span class="sxs-lookup"><span data-stu-id="abf42-174">The second template is needed if the insert specifies inserting a row where the primary key is store-generated but is not an integer type and therefore can't be used with scope_identity()).</span></span> <span data-ttu-id="abf42-175">También se usa si existe una clave compuesta generada por el almacén.</span><span class="sxs-lookup"><span data-stu-id="abf42-175">It is also used if there is a compound store-generated key.</span></span>

```sql
-- second insert template
DECLARE @generated_keys TABLE [(keyMember0, … keyMemberN)

INSERT <target>   [ (setClauseProperty0, .. setClausePropertyN)]
 OUTPUT inserted.KeyMember0, …, inserted.KeyMemberN INTO @generated_keys
 VALUES (setClauseValue0, .. setClauseValueN) |  DEFAULT VALUES

[SELECT <returning_over_t>
 FROM @generated_keys  AS g
JOIN <target> AS t ON g.KeyMember0 = t.KeyMember0 AND … g.KeyMemberN = t.KeyMemberN
 WHERE @@ROWCOUNT > 0
```

<span data-ttu-id="abf42-176">A continuación se muestra un ejemplo que utiliza el modelo incluido con el proveedor de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="abf42-176">The following is an example that uses the model that is included with the sample provider.</span></span> <span data-ttu-id="abf42-177">Genera un comando de inserción a partir de una implementación DbInsertCommandTree.</span><span class="sxs-lookup"><span data-stu-id="abf42-177">It generates an insert command from a DbInsertCommandTree.</span></span>

<span data-ttu-id="abf42-178">El siguiente código inserta una categoría:</span><span class="sxs-lookup"><span data-stu-id="abf42-178">The following code inserts a Category:</span></span>

```csharp
using (NorthwindEntities northwindContext = new NorthwindEntities()) {
   Category c = new Category();
   c.CategoryName = "Test Category";
   c.Description = "A new category for testing";
   northwindContext.AddObject("Categories", c);
   northwindContext.SaveChanges();
}
```

<span data-ttu-id="abf42-179">Este código genera el siguiente árbol de comandos, que se pasa al proveedor:</span><span class="sxs-lookup"><span data-stu-id="abf42-179">This code produces the following command tree, which is passed to the provider:</span></span>

```output
DbInsertCommandTree
|_Parameters
|_Target : 'target'
| |_Scan : dbo.Categories
|_SetClauses
| |_DbSetClause
| | |_Property
| | | |_Var(target).CategoryName
| | |_Value
| |   |_'Test Category'
| |_DbSetClause
| | |_Property
| | | |_Var(target).Description
| | |_Value
| |   |_'A new category for testing'
| |_DbSetClause
|   |_Property
|   | |_Var(target).Picture
|   |_Value
|     |_null
|_Returning
  |_NewInstance : Record['CategoryID'=Edm.Int32]
    |_Column : 'CategoryID'
      |_Var(target).CategoryID
```

<span data-ttu-id="abf42-180">El comando de almacén que el proveedor de ejemplo genera es la siguiente instrucción SQL:</span><span class="sxs-lookup"><span data-stu-id="abf42-180">The store command that the sample provider produces is the following SQL statement:</span></span>

```sql
insert [dbo].[Categories]([CategoryName], [Description], [Picture])
values (@p0, @p1, null)
select [CategoryID]
from [dbo].[Categories]
where @@ROWCOUNT > 0 and [CategoryID] = scope_identity()
```

## <a name="generating-an-update-sql-command"></a><span data-ttu-id="abf42-181">Generar un comando SQL de actualización</span><span class="sxs-lookup"><span data-stu-id="abf42-181">Generating an Update SQL Command</span></span>

<span data-ttu-id="abf42-182">Para una implementación DbUpdateCommandTree determinada, el comando de actualización generado se basa en la siguiente plantilla:</span><span class="sxs-lookup"><span data-stu-id="abf42-182">For a given DbUpdateCommandTree, the generated update command is based on the following template:</span></span>

```sql
-- UPDATE Template
UPDATE <target>
SET setClauseProperty0 = setClauseValue0, .. setClausePropertyN = setClauseValueN  | @i = 0
WHERE <predicate>

[SELECT <returning>
 FROM <target>
 WHERE @@ROWCOUNT > 0 AND keyMember0 = keyValue0 AND .. keyMemberI =  keyValueI | scope_identity()  .. AND  keyMemberN = keyValueN]
```

<span data-ttu-id="abf42-183">La cláusula SET tiene la cláusula SET falsa ("@i = 0") solo si no se especifica ninguna cláusula SET.</span><span class="sxs-lookup"><span data-stu-id="abf42-183">The set clause has the fake set clause ("@i = 0") only if no set clauses are specified.</span></span> <span data-ttu-id="abf42-184">Esto permite garantizar que las columnas calculadas en el almacén se vuelven a calcular.</span><span class="sxs-lookup"><span data-stu-id="abf42-184">This is to ensure that any store-computed columns are recomputed.</span></span>

<span data-ttu-id="abf42-185">Únicamente si la propiedad Returning no es NULL, se genera una instrucción SELECT para devolver las propiedades especificadas en la propiedad Returning.</span><span class="sxs-lookup"><span data-stu-id="abf42-185">Only if the Returning property is not null, a select statement is generated to return the properties specified in the Returning property.</span></span>

<span data-ttu-id="abf42-186">En el siguiente ejemplo se utiliza el modelo que se incluye con el proveedor de ejemplo para generar un comando de actualización.</span><span class="sxs-lookup"><span data-stu-id="abf42-186">The following example uses the model that is included with the sample provider to generate an update command.</span></span>

<span data-ttu-id="abf42-187">El siguiente código de usuario actualiza una categoría:</span><span class="sxs-lookup"><span data-stu-id="abf42-187">The following user code updates a Category:</span></span>

```csharp
using (NorthwindEntities northwindContext = new NorthwindEntities()) {
   Category c = northwindContext.Categories.Where(i => i.CategoryName == "Test Category").First();
   c.CategoryName = "New test name";
   northwindContext.SaveChanges();
}
```

<span data-ttu-id="abf42-188">Este código de usuario genera el siguiente árbol de comandos, que se pasa al proveedor:</span><span class="sxs-lookup"><span data-stu-id="abf42-188">This user code produces the following command tree, which is passed to the provider:</span></span>

```output
DbUpdateCommandTree
|_Parameters
|_Target : 'target'
| |_Scan : dbo.Categories
|_SetClauses
| |_DbSetClause
|   |_Property
|   | |_Var(target).CategoryName
|   |_Value
|     |_'New test name'
|_Predicate
| |_
|   |_Var(target).CategoryID
|   |_=
|   |_10
|_Returning
```

<span data-ttu-id="abf42-189">El proveedor de ejemplo genera el siguiente comando de almacén:</span><span class="sxs-lookup"><span data-stu-id="abf42-189">The sample provider produces the following store command:</span></span>

```sql
update [dbo].[Categories]
set [CategoryName] = @p0
where ([CategoryID] = @p1)
```

### <a name="generating-a-delete-sql-command"></a><span data-ttu-id="abf42-190">Generar un comando SQL de eliminación</span><span class="sxs-lookup"><span data-stu-id="abf42-190">Generating a Delete SQL Command</span></span>

<span data-ttu-id="abf42-191">Para una implementación DbDeleteCommandTree determinada, el comando DELETE generado se basa en la siguiente plantilla:</span><span class="sxs-lookup"><span data-stu-id="abf42-191">For a given DbDeleteCommandTree, the generated DELETE command is based on the following template:</span></span>

```sql
-- DELETE Template
DELETE <target>
WHERE <predicate>
```

<span data-ttu-id="abf42-192">En el siguiente ejemplo se utiliza el modelo que se incluye con el proveedor de ejemplo para generar un comando de eliminación.</span><span class="sxs-lookup"><span data-stu-id="abf42-192">The following example uses the model that is included with the sample provider to generate a delete command.</span></span>

<span data-ttu-id="abf42-193">El siguiente código de usuario elimina una categoría:</span><span class="sxs-lookup"><span data-stu-id="abf42-193">The following user code deletes a Category:</span></span>

```csharp
using (NorthwindEntities northwindContext = new NorthwindEntities()) {
   Category c = northwindContext.Categories.Where(i => i.CategoryName == "New test name").First();
   northwindContext.DeleteObject(c);
   northwindContext.SaveChanges();
}
```

<span data-ttu-id="abf42-194">Este código de usuario genera el siguiente árbol de comandos, que se pasa al proveedor.</span><span class="sxs-lookup"><span data-stu-id="abf42-194">This user code produces the following command tree, which is passed to the provider.</span></span>

```output
DbDeleteCommandTree
|_Parameters
|_Target : 'target'
| |_Scan : dbo.Categories
|_Predicate
  |_
    |_Var(target).CategoryID
    |_=
    |_10
```

<span data-ttu-id="abf42-195">El proveedor de ejemplo genera el siguiente comando de almacén:</span><span class="sxs-lookup"><span data-stu-id="abf42-195">The following store command is produced by the sample provider:</span></span>

```sql
delete [dbo].[Categories]
where ([CategoryID] = @p0)
```

## <a name="see-also"></a><span data-ttu-id="abf42-196">Vea también</span><span class="sxs-lookup"><span data-stu-id="abf42-196">See also</span></span>

- [<span data-ttu-id="abf42-197">Escritura de un proveedor de datos de Entity Framework</span><span class="sxs-lookup"><span data-stu-id="abf42-197">Writing an Entity Framework Data Provider</span></span>](writing-an-ef-data-provider.md)
