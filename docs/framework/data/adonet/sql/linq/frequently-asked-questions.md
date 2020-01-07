---
title: Preguntas más frecuentes
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 252ed666-0679-4eea-b71b-2f14117ef443
ms.openlocfilehash: 3cc879e97438138554f1d39cf588e01bfbba28a6
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634708"
---
# <a name="frequently-asked-questions"></a><span data-ttu-id="3b56e-102">Preguntas más frecuentes</span><span class="sxs-lookup"><span data-stu-id="3b56e-102">Frequently Asked Questions</span></span>

<span data-ttu-id="3b56e-103">En las secciones siguientes se responden algunos problemas comunes que pueden surgir al implementar LINQ.</span><span class="sxs-lookup"><span data-stu-id="3b56e-103">The following sections answer some common issues that you might encounter when you implement LINQ.</span></span>

<span data-ttu-id="3b56e-104">Se tratan problemas adicionales en la [solución de problemas](troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="3b56e-104">Additional issues are addressed in [Troubleshooting](troubleshooting.md).</span></span>

## <a name="cannot-connect"></a><span data-ttu-id="3b56e-105">No se puede establecer conexión</span><span class="sxs-lookup"><span data-stu-id="3b56e-105">Cannot Connect</span></span>

<span data-ttu-id="3b56e-106">P.</span><span class="sxs-lookup"><span data-stu-id="3b56e-106">Q.</span></span> <span data-ttu-id="3b56e-107">No puedo conectarme a mi base de datos.</span><span class="sxs-lookup"><span data-stu-id="3b56e-107">I cannot connect to my database.</span></span>

<span data-ttu-id="3b56e-108">Un archivo .</span><span class="sxs-lookup"><span data-stu-id="3b56e-108">A.</span></span> <span data-ttu-id="3b56e-109">Asegúrese de que la cadena de conexión es correcta y de que se está ejecutando la instancia de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3b56e-109">Make sure your connection string is correct and that your SQL Server instance is running.</span></span> <span data-ttu-id="3b56e-110">También tenga en cuenta que [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] requiere que el protocolo Canalizaciones con nombre esté habilitado.</span><span class="sxs-lookup"><span data-stu-id="3b56e-110">Note also that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] requires the Named Pipes protocol to be enabled.</span></span> <span data-ttu-id="3b56e-111">Para obtener más información, consulte [aprendizaje por tutoriales](learning-by-walkthroughs.md).</span><span class="sxs-lookup"><span data-stu-id="3b56e-111">For more information, see [Learning by Walkthroughs](learning-by-walkthroughs.md).</span></span>

## <a name="changes-to-database-lost"></a><span data-ttu-id="3b56e-112">La base de datos pierde los cambios realizados</span><span class="sxs-lookup"><span data-stu-id="3b56e-112">Changes to Database Lost</span></span>

<span data-ttu-id="3b56e-113">P.</span><span class="sxs-lookup"><span data-stu-id="3b56e-113">Q.</span></span> <span data-ttu-id="3b56e-114">Realicé un cambio en los datos de la base de datos, pero, cuando volví a ejecutar mi aplicación, el cambio ya no estaba.</span><span class="sxs-lookup"><span data-stu-id="3b56e-114">I made a change to data in the database, but when I reran my application, the change was no longer there.</span></span>

<span data-ttu-id="3b56e-115">Un archivo .</span><span class="sxs-lookup"><span data-stu-id="3b56e-115">A.</span></span> <span data-ttu-id="3b56e-116">Asegúrese de que llama a <xref:System.Data.Linq.DataContext.SubmitChanges%2A> para guardar los resultados en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="3b56e-116">Make sure that you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> to save results to the database.</span></span>

## <a name="database-connection-open-how-long"></a><span data-ttu-id="3b56e-117">Conexión a bases de datos: ¿cuánto tiempo permanece abierta?</span><span class="sxs-lookup"><span data-stu-id="3b56e-117">Database Connection: Open How Long?</span></span>

<span data-ttu-id="3b56e-118">P.</span><span class="sxs-lookup"><span data-stu-id="3b56e-118">Q.</span></span> <span data-ttu-id="3b56e-119">¿Cuánto tiempo permanece abierta mi conexión a una base de datos?</span><span class="sxs-lookup"><span data-stu-id="3b56e-119">How long does my database connection remain open?</span></span>

<span data-ttu-id="3b56e-120">Un archivo .</span><span class="sxs-lookup"><span data-stu-id="3b56e-120">A.</span></span> <span data-ttu-id="3b56e-121">Normalmente, una conexión permanece abierta hasta que se utilizan los resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="3b56e-121">A connection typically remains open until you consume the query results.</span></span> <span data-ttu-id="3b56e-122">Si espera que los resultados tarden tiempo en procesarse, y no se opone a que se almacenen en memoria caché, aplique <xref:System.Linq.Enumerable.ToList%2A> a la consulta.</span><span class="sxs-lookup"><span data-stu-id="3b56e-122">If you expect to take time to process all the results and are not opposed to caching the results, apply <xref:System.Linq.Enumerable.ToList%2A> to the query.</span></span> <span data-ttu-id="3b56e-123">En escenarios habituales donde cada objeto se procesa solo una vez, el modelo de transmisión por secuencias es superior tanto en `DataReader` como en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3b56e-123">In common scenarios where each object is processed only one time, the streaming model is superior in both `DataReader` and [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>

<span data-ttu-id="3b56e-124">Los detalles exactos de uso de la conexión dependen de lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3b56e-124">The exact details of connection usage depend on the following:</span></span>

- <span data-ttu-id="3b56e-125">Estado de la conexión si el <xref:System.Data.Linq.DataContext> se construye con un objeto de conexión.</span><span class="sxs-lookup"><span data-stu-id="3b56e-125">Connection status if the <xref:System.Data.Linq.DataContext> is constructed with a connection object.</span></span>

- <span data-ttu-id="3b56e-126">Opciones de la cadena de conexión; por ejemplo, habilitar conjuntos de resultados activos múltiples (MARS).</span><span class="sxs-lookup"><span data-stu-id="3b56e-126">Connection string settings (for example, enabling Multiple Active Result Sets (MARS).</span></span> <span data-ttu-id="3b56e-127">Para obtener más información, consulte [Conjuntos de resultados activos múltiples (MARS)](../multiple-active-result-sets-mars.md).</span><span class="sxs-lookup"><span data-stu-id="3b56e-127">For more information, see [Multiple Active Result Sets (MARS)](../multiple-active-result-sets-mars.md).</span></span>

## <a name="updating-without-querying"></a><span data-ttu-id="3b56e-128">Actualizaciones sin consultas</span><span class="sxs-lookup"><span data-stu-id="3b56e-128">Updating Without Querying</span></span>

<span data-ttu-id="3b56e-129">P.</span><span class="sxs-lookup"><span data-stu-id="3b56e-129">Q.</span></span> <span data-ttu-id="3b56e-130">¿Puedo actualizar los datos de la tabla sin consultar primero la base de datos?</span><span class="sxs-lookup"><span data-stu-id="3b56e-130">Can I update table data without first querying the database?</span></span>

<span data-ttu-id="3b56e-131">Un archivo .</span><span class="sxs-lookup"><span data-stu-id="3b56e-131">A.</span></span> <span data-ttu-id="3b56e-132">Aunque [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no posee comandos de actualización basados en conjuntos, puede utilizar cualquiera de las técnicas siguientes para actualizar sin consultar primero:</span><span class="sxs-lookup"><span data-stu-id="3b56e-132">Although [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] does not have set-based update commands, you can use either of the following techniques to update without first querying:</span></span>

- <span data-ttu-id="3b56e-133">Utilice <xref:System.Data.Linq.DataContext.ExecuteCommand%2A> para enviar código SQL.</span><span class="sxs-lookup"><span data-stu-id="3b56e-133">Use <xref:System.Data.Linq.DataContext.ExecuteCommand%2A> to send SQL code.</span></span>

- <span data-ttu-id="3b56e-134">Cree una nueva instancia del objeto e inicialice todos los valores (campos) actuales que afectan a la actualización.</span><span class="sxs-lookup"><span data-stu-id="3b56e-134">Create a new instance of the object and initialize all the current values (fields) that affect the update.</span></span> <span data-ttu-id="3b56e-135">A continuación, adjunte el objeto al <xref:System.Data.Linq.DataContext> utilizando <xref:System.Data.Linq.Table%601.Attach%2A> y modifique el campo que desee cambiar.</span><span class="sxs-lookup"><span data-stu-id="3b56e-135">Then attach the object to the <xref:System.Data.Linq.DataContext> by using <xref:System.Data.Linq.Table%601.Attach%2A> and modify the field you want to change.</span></span>

## <a name="unexpected-query-results"></a><span data-ttu-id="3b56e-136">Resultados inesperados en la consulta</span><span class="sxs-lookup"><span data-stu-id="3b56e-136">Unexpected Query Results</span></span>

<span data-ttu-id="3b56e-137">P.</span><span class="sxs-lookup"><span data-stu-id="3b56e-137">Q.</span></span> <span data-ttu-id="3b56e-138">Mi consulta devuelve resultados inesperados.</span><span class="sxs-lookup"><span data-stu-id="3b56e-138">My query is returning unexpected results.</span></span> <span data-ttu-id="3b56e-139">¿Cómo puedo inspeccionar lo que está ocurriendo?</span><span class="sxs-lookup"><span data-stu-id="3b56e-139">How can I inspect what is occurring?</span></span>

<span data-ttu-id="3b56e-140">Un archivo .</span><span class="sxs-lookup"><span data-stu-id="3b56e-140">A.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="3b56e-141">proporciona varias herramientas para inspeccionar el código SQL que genera.</span><span class="sxs-lookup"><span data-stu-id="3b56e-141">provides several tools for inspecting the SQL code it generates.</span></span> <span data-ttu-id="3b56e-142">Una de las más importantes es <xref:System.Data.Linq.DataContext.Log%2A>.</span><span class="sxs-lookup"><span data-stu-id="3b56e-142">One of the most important is <xref:System.Data.Linq.DataContext.Log%2A>.</span></span> <span data-ttu-id="3b56e-143">Para obtener más información, consulte [compatibilidad con la depuración](debugging-support.md).</span><span class="sxs-lookup"><span data-stu-id="3b56e-143">For more information, see [Debugging Support](debugging-support.md).</span></span>

## <a name="unexpected-stored-procedure-results"></a><span data-ttu-id="3b56e-144">Resultados inesperados del procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="3b56e-144">Unexpected Stored Procedure Results</span></span>

<span data-ttu-id="3b56e-145">P.</span><span class="sxs-lookup"><span data-stu-id="3b56e-145">Q.</span></span> <span data-ttu-id="3b56e-146">Tengo un procedimiento almacenado cuyo valor devuelto se calcula mediante `MAX()`.</span><span class="sxs-lookup"><span data-stu-id="3b56e-146">I have a stored procedure whose return value is calculated by `MAX()`.</span></span> <span data-ttu-id="3b56e-147">Al arrastrar el procedimiento almacenado a la superficie del diseñador de O/R, el valor devuelto no es correcto.</span><span class="sxs-lookup"><span data-stu-id="3b56e-147">When I drag the stored procedure to the O/R Designer surface, the return value is not correct.</span></span>

<span data-ttu-id="3b56e-148">Un archivo .</span><span class="sxs-lookup"><span data-stu-id="3b56e-148">A.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="3b56e-149">proporciona dos maneras de devolver los valores generados por la base de datos a través de procedimientos almacenados:</span><span class="sxs-lookup"><span data-stu-id="3b56e-149">provides two ways to return database-generated values by way of stored procedures:</span></span>

- <span data-ttu-id="3b56e-150">Asignando un nombre al resultado de salida.</span><span class="sxs-lookup"><span data-stu-id="3b56e-150">By naming the output result.</span></span>

- <span data-ttu-id="3b56e-151">Especificando explícitamente un parámetro de salida.</span><span class="sxs-lookup"><span data-stu-id="3b56e-151">By explicitly specifying an output parameter.</span></span>

<span data-ttu-id="3b56e-152">El siguiente es un ejemplo de resultado incorrecto.</span><span class="sxs-lookup"><span data-stu-id="3b56e-152">The following is an example of incorrect output.</span></span> <span data-ttu-id="3b56e-153">Dado que [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no puede asignar los resultados, siempre devuelve 0:</span><span class="sxs-lookup"><span data-stu-id="3b56e-153">Because [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] cannot map the results, it always returns 0:</span></span>

```sql
create procedure proc2

as

begin

select max(i) from t where name like 'hello'

end
```

<span data-ttu-id="3b56e-154">El siguiente es un ejemplo de resultado correcto que utiliza un parámetro de salida:</span><span class="sxs-lookup"><span data-stu-id="3b56e-154">The following is an example of correct output by using an output parameter:</span></span>

```sql
create procedure proc2

@result int OUTPUT

as

select @result = MAX(i) from t where name like 'hello'

go
```

<span data-ttu-id="3b56e-155">El siguiente es un ejemplo de resultado correcto que asigna un nombre al resultado de salida:</span><span class="sxs-lookup"><span data-stu-id="3b56e-155">The following is an example of correct output by naming the output result:</span></span>

```sql
create procedure proc2

as

begin

select nax(i) AS MaxResult from t where name like 'hello'

end
```

<span data-ttu-id="3b56e-156">Para obtener más información, vea [personalizar las operaciones mediante procedimientos almacenados](customizing-operations-by-using-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="3b56e-156">For more information, see [Customizing Operations By Using Stored Procedures](customizing-operations-by-using-stored-procedures.md).</span></span>

## <a name="serialization-errors"></a><span data-ttu-id="3b56e-157">Errores de serialización</span><span class="sxs-lookup"><span data-stu-id="3b56e-157">Serialization Errors</span></span>

<span data-ttu-id="3b56e-158">P.</span><span class="sxs-lookup"><span data-stu-id="3b56e-158">Q.</span></span> <span data-ttu-id="3b56e-159">Cuando intento serializar, obtengo el siguiente error: "type ' System. Data. Linq. ChangeTracker + StandardChangeTracker '... no está marcado como serializable ".</span><span class="sxs-lookup"><span data-stu-id="3b56e-159">When I try to serialize, I get the following error: "Type 'System.Data.Linq.ChangeTracker+StandardChangeTracker' ... is not marked as serializable."</span></span>

<span data-ttu-id="3b56e-160">Un archivo .</span><span class="sxs-lookup"><span data-stu-id="3b56e-160">A.</span></span> <span data-ttu-id="3b56e-161">La generación de código en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] admite serialización <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="3b56e-161">Code generation in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] supports <xref:System.Runtime.Serialization.DataContractSerializer> serialization.</span></span> <span data-ttu-id="3b56e-162">No admite <xref:System.Xml.Serialization.XmlSerializer> o <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>.</span><span class="sxs-lookup"><span data-stu-id="3b56e-162">It does not support <xref:System.Xml.Serialization.XmlSerializer> or <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>.</span></span> <span data-ttu-id="3b56e-163">Para obtener más información, vea [Serialización](serialization.md).</span><span class="sxs-lookup"><span data-stu-id="3b56e-163">For more information, see [Serialization](serialization.md).</span></span>

## <a name="multiple-dbml-files"></a><span data-ttu-id="3b56e-164">Múltiples archivos DBML</span><span class="sxs-lookup"><span data-stu-id="3b56e-164">Multiple DBML Files</span></span>

<span data-ttu-id="3b56e-165">P.</span><span class="sxs-lookup"><span data-stu-id="3b56e-165">Q.</span></span> <span data-ttu-id="3b56e-166">Cuando tengo varios archivos DBML que comparten algunas tablas, obtengo un error del compilador.</span><span class="sxs-lookup"><span data-stu-id="3b56e-166">When I have multiple DBML files that share some tables in common, I get a compiler error.</span></span>

<span data-ttu-id="3b56e-167">Un archivo .</span><span class="sxs-lookup"><span data-stu-id="3b56e-167">A.</span></span> <span data-ttu-id="3b56e-168">Establezca las propiedades espacio de nombres del **contexto** y espacio de **nombres de entidad** desde el Object Relational Designer en un valor distinto para cada archivo DBML.</span><span class="sxs-lookup"><span data-stu-id="3b56e-168">Set the **Context Namespace** and **Entity Namespace** properties from the Object Relational Designer to a distinct value for each DBML file.</span></span> <span data-ttu-id="3b56e-169">Este enfoque elimina la colisión entre nombres o espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="3b56e-169">This approach eliminates the name/namespace collision.</span></span>

## <a name="avoiding-explicit-setting-of-database-generated-values-on-insert-or-update"></a><span data-ttu-id="3b56e-170">Evitar el establecimiento explícito de valores generados por la base de datos al insertar o actualizar</span><span class="sxs-lookup"><span data-stu-id="3b56e-170">Avoiding Explicit Setting of Database-Generated Values on Insert or Update</span></span>

<span data-ttu-id="3b56e-171">P.</span><span class="sxs-lookup"><span data-stu-id="3b56e-171">Q.</span></span> <span data-ttu-id="3b56e-172">Tengo una tabla de base de datos con una columna `DateCreated` que tiene como valor predeterminado `Getdate()` de SQL.</span><span class="sxs-lookup"><span data-stu-id="3b56e-172">I have a database table with a `DateCreated` column that defaults to SQL `Getdate()`.</span></span> <span data-ttu-id="3b56e-173">Cuando intento insertar un nuevo registro utilizando [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], el valor queda establecido en `NULL`.</span><span class="sxs-lookup"><span data-stu-id="3b56e-173">When I try to insert a new record by using [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the value gets set to `NULL`.</span></span> <span data-ttu-id="3b56e-174">Lo que esperaba es que tomara el valor predeterminado de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="3b56e-174">I would expect it to be set to the database default.</span></span>

<span data-ttu-id="3b56e-175">Un archivo .</span><span class="sxs-lookup"><span data-stu-id="3b56e-175">A.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="3b56e-176">administra automáticamente esta situación para la identidad (incremento automático) y rowguidcol (GUID generado por base de datos) y para las columnas con marca de tiempo.</span><span class="sxs-lookup"><span data-stu-id="3b56e-176">handles this situation automatically for identity (auto-increment) and rowguidcol (database-generated GUID) and timestamp columns.</span></span> <span data-ttu-id="3b56e-177">En otros casos, debe establecer manualmente <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>=`true` y <xref:System.Data.Linq.Mapping.ColumnAttribute.AutoSync%2A>=<xref:System.Data.Linq.Mapping.AutoSync.Always>/<xref:System.Data.Linq.Mapping.AutoSync.OnInsert>/<xref:System.Data.Linq.Mapping.AutoSync.OnUpdate> propiedades.</span><span class="sxs-lookup"><span data-stu-id="3b56e-177">In other cases, you should manually set <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>=`true` and <xref:System.Data.Linq.Mapping.ColumnAttribute.AutoSync%2A>=<xref:System.Data.Linq.Mapping.AutoSync.Always>/<xref:System.Data.Linq.Mapping.AutoSync.OnInsert>/<xref:System.Data.Linq.Mapping.AutoSync.OnUpdate> properties.</span></span>

## <a name="multiple-dataloadoptions"></a><span data-ttu-id="3b56e-178">Múltiples DataLoadOptions</span><span class="sxs-lookup"><span data-stu-id="3b56e-178">Multiple DataLoadOptions</span></span>

<span data-ttu-id="3b56e-179">P.</span><span class="sxs-lookup"><span data-stu-id="3b56e-179">Q.</span></span> <span data-ttu-id="3b56e-180">¿Puedo especificar opciones de carga adicionales sin sobrescribir la primera?</span><span class="sxs-lookup"><span data-stu-id="3b56e-180">Can I specify additional load options without overwriting the first?</span></span>

<span data-ttu-id="3b56e-181">Un archivo .</span><span class="sxs-lookup"><span data-stu-id="3b56e-181">A.</span></span> <span data-ttu-id="3b56e-182">Sí.</span><span class="sxs-lookup"><span data-stu-id="3b56e-182">Yes.</span></span> <span data-ttu-id="3b56e-183">La primera no se sobrescribe, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3b56e-183">The first is not overwritten, as in the following example:</span></span>

```vb
Dim dlo As New DataLoadOptions()
dlo.LoadWith(Of Order)(Function(o As Order) o.Customer)
dlo.LoadWith(Of Order)(Function(o As Order) o.OrderDetails)
```

```csharp
DataLoadOptions dlo = new DataLoadOptions();
dlo.LoadWith<Order>(o => o.Customer);
dlo.LoadWith<Order>(o => o.OrderDetails);
```

## <a name="errors-using-sql-compact-35"></a><span data-ttu-id="3b56e-184">Errores en el uso de SQL Compact 3.5</span><span class="sxs-lookup"><span data-stu-id="3b56e-184">Errors Using SQL Compact 3.5</span></span>

<span data-ttu-id="3b56e-185">P.</span><span class="sxs-lookup"><span data-stu-id="3b56e-185">Q.</span></span> <span data-ttu-id="3b56e-186">Obtengo un error cuando arrastro tablas fuera de una base de datos SQL Server Compact 3,5.</span><span class="sxs-lookup"><span data-stu-id="3b56e-186">I get an error when I drag tables out of a SQL Server Compact 3.5 database.</span></span>

<span data-ttu-id="3b56e-187">Un archivo .</span><span class="sxs-lookup"><span data-stu-id="3b56e-187">A.</span></span> <span data-ttu-id="3b56e-188">El Object Relational Designer no admite SQL Server Compact 3,5, aunque el tiempo de ejecución de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3b56e-188">The Object Relational Designer does not support SQL Server Compact 3.5, although the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] runtime does.</span></span> <span data-ttu-id="3b56e-189">En esta situación, debe crear sus propias clases de entidad y agregar los atributos adecuados.</span><span class="sxs-lookup"><span data-stu-id="3b56e-189">In this situation, you must create your own entity classes and add the appropriate attributes.</span></span>

## <a name="errors-in-inheritance-relationships"></a><span data-ttu-id="3b56e-190">Errores en relaciones de herencia</span><span class="sxs-lookup"><span data-stu-id="3b56e-190">Errors in Inheritance Relationships</span></span>

<span data-ttu-id="3b56e-191">P.</span><span class="sxs-lookup"><span data-stu-id="3b56e-191">Q.</span></span> <span data-ttu-id="3b56e-192">He usado la forma herencia del cuadro de herramientas en el Object Relational Designer para conectar dos entidades, pero obtengo errores.</span><span class="sxs-lookup"><span data-stu-id="3b56e-192">I used the toolbox inheritance shape in the Object Relational Designer to connect two entities, but I get errors.</span></span>

<span data-ttu-id="3b56e-193">Un archivo .</span><span class="sxs-lookup"><span data-stu-id="3b56e-193">A.</span></span> <span data-ttu-id="3b56e-194">Crear una relación no es suficiente.</span><span class="sxs-lookup"><span data-stu-id="3b56e-194">Creating the relationship is not enough.</span></span> <span data-ttu-id="3b56e-195">Debe proporcionar información tal como la columna de discriminador, el valor de discriminador de la clase base y el valor de discriminador de la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="3b56e-195">You must provide information such as the discriminator column, base class discriminator value, and derived class discriminator value.</span></span>

## <a name="provider-model"></a><span data-ttu-id="3b56e-196">Modelo de proveedor</span><span class="sxs-lookup"><span data-stu-id="3b56e-196">Provider Model</span></span>

<span data-ttu-id="3b56e-197">P.</span><span class="sxs-lookup"><span data-stu-id="3b56e-197">Q.</span></span> <span data-ttu-id="3b56e-198">¿Existe un modelo de proveedor público disponible?</span><span class="sxs-lookup"><span data-stu-id="3b56e-198">Is a public provider model available?</span></span>

<span data-ttu-id="3b56e-199">Un archivo .</span><span class="sxs-lookup"><span data-stu-id="3b56e-199">A.</span></span> <span data-ttu-id="3b56e-200">No existe ningún modelo de proveedor público disponible.</span><span class="sxs-lookup"><span data-stu-id="3b56e-200">No public provider model is available.</span></span> <span data-ttu-id="3b56e-201">En este momento, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] solo admite SQL Server y SQL Server Compact 3,5.</span><span class="sxs-lookup"><span data-stu-id="3b56e-201">At this time, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] supports SQL Server and SQL Server Compact 3.5 only.</span></span>

## <a name="sql-injection-attacks"></a><span data-ttu-id="3b56e-202">Ataques mediante inserción de SQL</span><span class="sxs-lookup"><span data-stu-id="3b56e-202">SQL-Injection Attacks</span></span>

<span data-ttu-id="3b56e-203">P.</span><span class="sxs-lookup"><span data-stu-id="3b56e-203">Q.</span></span> <span data-ttu-id="3b56e-204">¿Cómo se protege [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] de ataques de inyección de código SQL?</span><span class="sxs-lookup"><span data-stu-id="3b56e-204">How is [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] protected from SQL-injection attacks?</span></span>

<span data-ttu-id="3b56e-205">Un archivo .</span><span class="sxs-lookup"><span data-stu-id="3b56e-205">A.</span></span> <span data-ttu-id="3b56e-206">La inyección de código SQL ha sido un riesgo significativo para las consultas SQL tradicionales formadas mediante concatenación de los datos proporcionados por el usuario.</span><span class="sxs-lookup"><span data-stu-id="3b56e-206">SQL injection has been a significant risk for traditional SQL queries formed by concatenating user input.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="3b56e-207">evita esa inyección de código mediante el uso de <xref:System.Data.SqlClient.SqlParameter> en las consultas.</span><span class="sxs-lookup"><span data-stu-id="3b56e-207">avoids such injection by using <xref:System.Data.SqlClient.SqlParameter> in queries.</span></span> <span data-ttu-id="3b56e-208">Los datos proporcionados por el usuario se convierten en valores de parámetro.</span><span class="sxs-lookup"><span data-stu-id="3b56e-208">User input is turned into parameter values.</span></span> <span data-ttu-id="3b56e-209">Este enfoque impide que se utilicen comandos malintencionados en los datos proporcionados por el cliente.</span><span class="sxs-lookup"><span data-stu-id="3b56e-209">This approach prevents malicious commands from being used from customer input.</span></span>

## <a name="changing-read-only-flag-in-dbml-files"></a><span data-ttu-id="3b56e-210">Cambiar la marca de solo lectura en archivos DBML</span><span class="sxs-lookup"><span data-stu-id="3b56e-210">Changing Read-only Flag in DBML Files</span></span>

<span data-ttu-id="3b56e-211">P.</span><span class="sxs-lookup"><span data-stu-id="3b56e-211">Q.</span></span> <span data-ttu-id="3b56e-212">¿Cómo elimino los establecedores procedentes de algunas propiedades cuando creo un modelo de objetos a partir de un archivo DBML?</span><span class="sxs-lookup"><span data-stu-id="3b56e-212">How do I eliminate setters from some properties when I create an object model from a DBML file?</span></span>

<span data-ttu-id="3b56e-213">Un archivo .</span><span class="sxs-lookup"><span data-stu-id="3b56e-213">A.</span></span> <span data-ttu-id="3b56e-214">Siga estos pasos para este escenario avanzado:</span><span class="sxs-lookup"><span data-stu-id="3b56e-214">Take the following steps for this advanced scenario:</span></span>

1. <span data-ttu-id="3b56e-215">En el archivo .dbml, modifique la propiedad cambiando la marca <xref:System.Data.Linq.ITable.IsReadOnly%2A> a `True`.</span><span class="sxs-lookup"><span data-stu-id="3b56e-215">In the .dbml file, modify the property by changing the <xref:System.Data.Linq.ITable.IsReadOnly%2A> flag to `True`.</span></span>

2. <span data-ttu-id="3b56e-216">Agregue una clase parcial.</span><span class="sxs-lookup"><span data-stu-id="3b56e-216">Add a partial class.</span></span> <span data-ttu-id="3b56e-217">Cree un constructor con parámetros para los miembros de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="3b56e-217">Create a constructor with parameters for the read-only members.</span></span>

3. <span data-ttu-id="3b56e-218">Revise el valor predeterminado de <xref:System.Data.Linq.Mapping.UpdateCheck> (<xref:System.Data.Linq.Mapping.UpdateCheck.Never>) para determinar si ése es el valor correcto para su aplicación.</span><span class="sxs-lookup"><span data-stu-id="3b56e-218">Review the default <xref:System.Data.Linq.Mapping.UpdateCheck> value (<xref:System.Data.Linq.Mapping.UpdateCheck.Never>) to determine whether that is the correct value for your application.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="3b56e-219">Si usa el Object Relational Designer en Visual Studio, es posible que se sobrescriban los cambios.</span><span class="sxs-lookup"><span data-stu-id="3b56e-219">If you are using the Object Relational Designer in Visual Studio, your changes might be overwritten.</span></span>

## <a name="aptca"></a><span data-ttu-id="3b56e-220">APTCA</span><span class="sxs-lookup"><span data-stu-id="3b56e-220">APTCA</span></span>

<span data-ttu-id="3b56e-221">P.</span><span class="sxs-lookup"><span data-stu-id="3b56e-221">Q.</span></span> <span data-ttu-id="3b56e-222">¿Está System.Data.Linq marcado para que el código de confianza parcial pueda utilizarlo?</span><span class="sxs-lookup"><span data-stu-id="3b56e-222">Is System.Data.Linq marked for use by partially trusted code?</span></span>

<span data-ttu-id="3b56e-223">Un archivo .</span><span class="sxs-lookup"><span data-stu-id="3b56e-223">A.</span></span> <span data-ttu-id="3b56e-224">Sí, el ensamblado System. Data. Linq. dll se encuentra entre los .NET Framework ensamblados marcados con el atributo <xref:System.Security.AllowPartiallyTrustedCallersAttribute>.</span><span class="sxs-lookup"><span data-stu-id="3b56e-224">Yes, the System.Data.Linq.dll assembly is among those .NET Framework assemblies marked with the <xref:System.Security.AllowPartiallyTrustedCallersAttribute> attribute.</span></span> <span data-ttu-id="3b56e-225">Sin este marcado, los ensamblados de la .NET Framework están pensados para su uso exclusivo de código de plena confianza.</span><span class="sxs-lookup"><span data-stu-id="3b56e-225">Without this marking, assemblies in the .NET Framework are intended for use only by fully trusted code.</span></span>

<span data-ttu-id="3b56e-226">El escenario principal de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] para permitir llamadores de confianza parcial es habilitar el acceso al ensamblado de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] desde aplicaciones Web, donde la configuración de *confianza* es media.</span><span class="sxs-lookup"><span data-stu-id="3b56e-226">The principal scenario in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] for allowing partially trusted callers is to enable the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] assembly to be accessed from Web applications, where the *trust* configuration is Medium.</span></span>

## <a name="mapping-data-from-multiple-tables"></a><span data-ttu-id="3b56e-227">Asignación de datos procedentes de varias tablas</span><span class="sxs-lookup"><span data-stu-id="3b56e-227">Mapping Data from Multiple Tables</span></span>

<span data-ttu-id="3b56e-228">P.</span><span class="sxs-lookup"><span data-stu-id="3b56e-228">Q.</span></span> <span data-ttu-id="3b56e-229">Los datos de mi entidad proceden de varias tablas.</span><span class="sxs-lookup"><span data-stu-id="3b56e-229">The data in my entity comes from multiple tables.</span></span> <span data-ttu-id="3b56e-230">¿Cómo realizo la asignación?</span><span class="sxs-lookup"><span data-stu-id="3b56e-230">How do I map it?</span></span>

<span data-ttu-id="3b56e-231">Un archivo .</span><span class="sxs-lookup"><span data-stu-id="3b56e-231">A.</span></span> <span data-ttu-id="3b56e-232">Puede crear una vista en una base de datos y asignar la entidad a la vista.</span><span class="sxs-lookup"><span data-stu-id="3b56e-232">You can create a view in a database and map the entity to the view.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="3b56e-233">genera el mismo código SQL para vistas que para tablas.</span><span class="sxs-lookup"><span data-stu-id="3b56e-233">generates the same SQL for views as it does for tables.</span></span>

> [!NOTE]
> <span data-ttu-id="3b56e-234">El uso de vistas en este escenario presenta limitaciones.</span><span class="sxs-lookup"><span data-stu-id="3b56e-234">The use of views in this scenario has limitations.</span></span> <span data-ttu-id="3b56e-235">Este enfoque funciona de forma más segura cuando las operaciones realizadas sobre <xref:System.Data.Linq.Table%601> se admiten en la vista subyacente.</span><span class="sxs-lookup"><span data-stu-id="3b56e-235">This approach works most safely when the operations performed on <xref:System.Data.Linq.Table%601> are supported by the underlying view.</span></span> <span data-ttu-id="3b56e-236">Solo usted puede saber qué operaciones son las deseadas.</span><span class="sxs-lookup"><span data-stu-id="3b56e-236">Only you know which operations are intended.</span></span> <span data-ttu-id="3b56e-237">Por ejemplo, la mayoría de las aplicaciones son de solo lectura, y otro número más alto realiza `Create`/`Update`/`Delete` solo mediante procedimientos almacenados en las vistas.</span><span class="sxs-lookup"><span data-stu-id="3b56e-237">For example, most applications are read-only, and another sizeable number perform `Create`/`Update`/`Delete` operations only by using stored procedures against views.</span></span>

## <a name="connection-pooling"></a><span data-ttu-id="3b56e-238">Agrupación de conexiones</span><span class="sxs-lookup"><span data-stu-id="3b56e-238">Connection Pooling</span></span>

<span data-ttu-id="3b56e-239">P.</span><span class="sxs-lookup"><span data-stu-id="3b56e-239">Q.</span></span> <span data-ttu-id="3b56e-240">¿Existe una construcción que pueda ayudar al agrupamiento de <xref:System.Data.Linq.DataContext>?</span><span class="sxs-lookup"><span data-stu-id="3b56e-240">Is there a construct that can help with <xref:System.Data.Linq.DataContext> pooling?</span></span>

<span data-ttu-id="3b56e-241">Un archivo .</span><span class="sxs-lookup"><span data-stu-id="3b56e-241">A.</span></span> <span data-ttu-id="3b56e-242">No intente reutilizar instancias de <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="3b56e-242">Do not try to reuse instances of <xref:System.Data.Linq.DataContext>.</span></span> <span data-ttu-id="3b56e-243">Cada <xref:System.Data.Linq.DataContext> mantiene el estado (incluida una caché de identidad) para una sesión de edición o consulta particular.</span><span class="sxs-lookup"><span data-stu-id="3b56e-243">Each <xref:System.Data.Linq.DataContext> maintains state (including an identity cache) for one particular edit/query session.</span></span> <span data-ttu-id="3b56e-244">Para obtener nuevas instancias según el estado actual de la base de datos, utilice un nuevo <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="3b56e-244">To obtain new instances based on the current state of the database, use a new <xref:System.Data.Linq.DataContext>.</span></span>

<span data-ttu-id="3b56e-245">Todavía puede usar la agrupación de conexiones de ADO.NET subyacente.</span><span class="sxs-lookup"><span data-stu-id="3b56e-245">You can still use underlying ADO.NET connection pooling.</span></span> <span data-ttu-id="3b56e-246">Para obtener más información, vea [Agrupación de conexiones de SQL Server (ADO.NET)](../../sql-server-connection-pooling.md).</span><span class="sxs-lookup"><span data-stu-id="3b56e-246">For more information, see [SQL Server Connection Pooling (ADO.NET)](../../sql-server-connection-pooling.md).</span></span>

## <a name="second-datacontext-is-not-updated"></a><span data-ttu-id="3b56e-247">El segundo DataContext no resulta actualizado</span><span class="sxs-lookup"><span data-stu-id="3b56e-247">Second DataContext Is Not Updated</span></span>

<span data-ttu-id="3b56e-248">P.</span><span class="sxs-lookup"><span data-stu-id="3b56e-248">Q.</span></span> <span data-ttu-id="3b56e-249">Utilizo una instancia de <xref:System.Data.Linq.DataContext> para almacenar valores en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="3b56e-249">I used one instance of <xref:System.Data.Linq.DataContext> to store values in the database.</span></span> <span data-ttu-id="3b56e-250">Sin embargo, un segundo <xref:System.Data.Linq.DataContext> en la misma base de datos no refleja los valores actualizados.</span><span class="sxs-lookup"><span data-stu-id="3b56e-250">However, a second <xref:System.Data.Linq.DataContext> on the same database does not reflect the updated values.</span></span> <span data-ttu-id="3b56e-251">La segunda instancia de <xref:System.Data.Linq.DataContext> parece devolver valores almacenados en memoria caché.</span><span class="sxs-lookup"><span data-stu-id="3b56e-251">The second <xref:System.Data.Linq.DataContext> instance seems to return cached values.</span></span>

<span data-ttu-id="3b56e-252">Un archivo .</span><span class="sxs-lookup"><span data-stu-id="3b56e-252">A.</span></span> <span data-ttu-id="3b56e-253">Este comportamiento está diseñado así.</span><span class="sxs-lookup"><span data-stu-id="3b56e-253">This behavior is by design.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="3b56e-254">continúa devolviendo los mismos valores o instancias que aparecen en la primera instancia.</span><span class="sxs-lookup"><span data-stu-id="3b56e-254">continues to return the same instances/values that you saw in the first instance.</span></span> <span data-ttu-id="3b56e-255">Cuando se realizan actualizaciones, se utiliza simultaneidad optimista.</span><span class="sxs-lookup"><span data-stu-id="3b56e-255">When you make updates, you use optimistic concurrency.</span></span> <span data-ttu-id="3b56e-256">Los datos originales se utilizan para realizar una comprobación contra el estado de la base de datos actual a fin de comprobar que, de hecho, permanecen sin modificar.</span><span class="sxs-lookup"><span data-stu-id="3b56e-256">The original data is used to check against the current database state to assert that it is in fact still unchanged.</span></span> <span data-ttu-id="3b56e-257">Si han cambiado, se produce un conflicto, y su aplicación deberá resolverlo.</span><span class="sxs-lookup"><span data-stu-id="3b56e-257">If it has changed, a conflict occurs and your application must resolve it.</span></span> <span data-ttu-id="3b56e-258">Una opción para su aplicación es restablecer el estado original al estado actual de la base de datos e intentar de nuevo la actualización.</span><span class="sxs-lookup"><span data-stu-id="3b56e-258">One option of your application is to reset the original state to the current database state and to try the update again.</span></span> <span data-ttu-id="3b56e-259">Para obtener más información, vea [Cómo: administrar conflictos de cambios](how-to-manage-change-conflicts.md).</span><span class="sxs-lookup"><span data-stu-id="3b56e-259">For more information, see [How to: Manage Change Conflicts](how-to-manage-change-conflicts.md).</span></span>

<span data-ttu-id="3b56e-260">También puede establecer <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> como falso, lo cual desactiva el almacenamiento en memoria caché y el seguimiento de cambios.</span><span class="sxs-lookup"><span data-stu-id="3b56e-260">You can also set <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> to false, which turns off caching and change tracking.</span></span> <span data-ttu-id="3b56e-261">A continuación, puede recuperar los últimos valores cada vez que realiza una consulta.</span><span class="sxs-lookup"><span data-stu-id="3b56e-261">You can then retrieve the latest values every time that you query.</span></span>

## <a name="cannot-call-submitchanges-in-read-only-mode"></a><span data-ttu-id="3b56e-262">No se puede llamar a SubmitChanges en modo de solo lectura</span><span class="sxs-lookup"><span data-stu-id="3b56e-262">Cannot Call SubmitChanges in Read-only Mode</span></span>

<span data-ttu-id="3b56e-263">P.</span><span class="sxs-lookup"><span data-stu-id="3b56e-263">Q.</span></span> <span data-ttu-id="3b56e-264">Cuando intento llamar a <xref:System.Data.Linq.DataContext.SubmitChanges%2A> en modo de solo lectura, obtengo un error.</span><span class="sxs-lookup"><span data-stu-id="3b56e-264">When I try to call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> in read-only mode, I get an error.</span></span>

<span data-ttu-id="3b56e-265">Un archivo .</span><span class="sxs-lookup"><span data-stu-id="3b56e-265">A.</span></span> <span data-ttu-id="3b56e-266">El modo de solo lectura desactiva la capacidad del contexto de realizar seguimiento de cambios.</span><span class="sxs-lookup"><span data-stu-id="3b56e-266">Read-only mode turns off the ability of the context to track changes.</span></span>

## <a name="see-also"></a><span data-ttu-id="3b56e-267">Vea también</span><span class="sxs-lookup"><span data-stu-id="3b56e-267">See also</span></span>

- [<span data-ttu-id="3b56e-268">Referencia</span><span class="sxs-lookup"><span data-stu-id="3b56e-268">Reference</span></span>](reference.md)
- [<span data-ttu-id="3b56e-269">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="3b56e-269">Troubleshooting</span></span>](troubleshooting.md)
- [<span data-ttu-id="3b56e-270">Seguridad de LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="3b56e-270">Security in LINQ to SQL</span></span>](security-in-linq-to-sql.md)
