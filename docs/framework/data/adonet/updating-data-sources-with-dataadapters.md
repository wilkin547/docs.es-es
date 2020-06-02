---
title: Actualizar orígenes de datos con objetos DataAdapter
description: Obtenga información sobre cómo el método Update de DataAdapter resuelve los cambios de un conjunto de datos de nuevo en el origen de datos de las aplicaciones de ADO.NET.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d1bd9a8c-0e29-40e3-bda8-d89176b72fb1
ms.openlocfilehash: e2348a3a89aa1c28856bfc21aaa25f2c8327aac7
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286189"
---
# <a name="updating-data-sources-with-dataadapters"></a><span data-ttu-id="def3f-103">Actualizar orígenes de datos con objetos DataAdapter</span><span class="sxs-lookup"><span data-stu-id="def3f-103">Updating Data Sources with DataAdapters</span></span>

<span data-ttu-id="def3f-104">El método `Update` de <xref:System.Data.Common.DataAdapter> se llama para reflejar en el origen de datos todos los cambios efectuados en <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="def3f-104">The `Update` method of the <xref:System.Data.Common.DataAdapter> is called to resolve changes from a <xref:System.Data.DataSet> back to the data source.</span></span> <span data-ttu-id="def3f-105">El método `Update`, al igual que el método `Fill`, acepta como argumentos una instancia de `DataSet` y, de forma opcional, un objeto <xref:System.Data.DataTable> o un nombre de `DataTable`.</span><span class="sxs-lookup"><span data-stu-id="def3f-105">The `Update` method, like the `Fill` method, takes as arguments an instance of a `DataSet`, and an optional <xref:System.Data.DataTable> object or `DataTable` name.</span></span> <span data-ttu-id="def3f-106">La instancia de `DataSet` es el `DataSet` que contiene los cambios efectuados, y `DataTable` identifica la tabla desde la que se pueden recuperar esos cambios.</span><span class="sxs-lookup"><span data-stu-id="def3f-106">The `DataSet` instance is the `DataSet` that contains the changes that have been made, and the `DataTable` identifies the table from which to retrieve the changes.</span></span> <span data-ttu-id="def3f-107">Si no se especifica `DataTable`, se utiliza el primer `DataTable` de `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="def3f-107">If no `DataTable` is specified, the first `DataTable` in the `DataSet` is used.</span></span>

<span data-ttu-id="def3f-108">Al llamar al método `Update`, `DataAdapter` analiza los cambios efectuados y ejecuta el comando apropiado (INSERT, UPDATE o DELETE).</span><span class="sxs-lookup"><span data-stu-id="def3f-108">When you call the `Update` method, the `DataAdapter` analyzes the changes that have been made and executes the appropriate command (INSERT, UPDATE, or DELETE).</span></span> <span data-ttu-id="def3f-109">Cuando `DataAdapter` encuentra un cambio en <xref:System.Data.DataRow>, utiliza los comandos <xref:System.Data.Common.DbDataAdapter.InsertCommand%2A>, <xref:System.Data.Common.DbDataAdapter.UpdateCommand%2A> o <xref:System.Data.Common.DbDataAdapter.DeleteCommand%2A> para reflejarlo.</span><span class="sxs-lookup"><span data-stu-id="def3f-109">When the `DataAdapter` encounters a change to a <xref:System.Data.DataRow>, it uses the <xref:System.Data.Common.DbDataAdapter.InsertCommand%2A>, <xref:System.Data.Common.DbDataAdapter.UpdateCommand%2A>, or <xref:System.Data.Common.DbDataAdapter.DeleteCommand%2A> to process the change.</span></span> <span data-ttu-id="def3f-110">De esta forma, se obtiene el máximo rendimiento de la aplicación de ADO.NET al especificar la sintaxis del comando en la fase de diseño y utilizar, siempre que es posible, procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="def3f-110">This allows you to maximize the performance of your ADO.NET application by specifying command syntax at design time and, where possible, through the use of stored procedures.</span></span> <span data-ttu-id="def3f-111">Antes de llamar a `Update` deben establecerse de forma explícita los comandos.</span><span class="sxs-lookup"><span data-stu-id="def3f-111">You must explicitly set the commands before calling `Update`.</span></span> <span data-ttu-id="def3f-112">Si se llama a `Update` y el comando correspondiente a una actualización determinada no existe (por ejemplo, no hay un comando `DeleteCommand` para las filas eliminadas), se inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="def3f-112">If `Update` is called and the appropriate command does not exist for a particular update (for example, no `DeleteCommand` for deleted rows), an exception is thrown.</span></span>

> [!NOTE]
> <span data-ttu-id="def3f-113">Si está utilizando procedimientos almacenados de SQL Server para editar o eliminar datos con `DataAdapter`, asegúrese de que no utiliza SET NOCOUNT ON en la definición del procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="def3f-113">If you are using SQL Server stored procedures to edit or delete data using a `DataAdapter`, make sure that you do not use SET NOCOUNT ON in the stored procedure definition.</span></span> <span data-ttu-id="def3f-114">Esto hace que el recuento de filas afectadas vuelva a cero, lo que `DataAdapter` interpreta como un conflicto de simultaneidad.</span><span class="sxs-lookup"><span data-stu-id="def3f-114">This causes the rows affected count returned to be zero, which the `DataAdapter` interprets as a concurrency conflict.</span></span> <span data-ttu-id="def3f-115">En este caso, se iniciará una <xref:System.Data.DBConcurrencyException>.</span><span class="sxs-lookup"><span data-stu-id="def3f-115">In this event, a <xref:System.Data.DBConcurrencyException> will be thrown.</span></span>

<span data-ttu-id="def3f-116">Se pueden usar los parámetros de comando para especificar los valores de entrada y salida de una instrucción SQL o un procedimiento almacenado para cada fila modificada en `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="def3f-116">Command parameters can be used to specify input and output values for an SQL statement or stored procedure for each modified row in a `DataSet`.</span></span> <span data-ttu-id="def3f-117">Para obtener más información, vea [DataAdapter Parameters](dataadapter-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="def3f-117">For more information, see [DataAdapter Parameters](dataadapter-parameters.md).</span></span>

> [!NOTE]
> <span data-ttu-id="def3f-118">Es importante comprender la diferencia entre eliminar una fila de una <xref:System.Data.DataTable> y quitar la fila.</span><span class="sxs-lookup"><span data-stu-id="def3f-118">It is important to understand the difference between deleting a row in a <xref:System.Data.DataTable> and removing the row.</span></span> <span data-ttu-id="def3f-119">Al llamar al método `Remove` o `RemoveAt`, la fila se quita inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="def3f-119">When you call the `Remove` or `RemoveAt` method, the row is removed immediately.</span></span> <span data-ttu-id="def3f-120">Cualquier fila correspondiente en el origen de datos back end no se verá afectada si a continuación se pasa `DataTable` o `DataSet` a `DataAdapter` y se llama a `Update`.</span><span class="sxs-lookup"><span data-stu-id="def3f-120">Any corresponding rows in the back end data source will not be affected if you then pass the `DataTable` or `DataSet` to a `DataAdapter` and call `Update`.</span></span> <span data-ttu-id="def3f-121">Al utilizar el método `Delete`, la fila permanece en `DataTable` y se marca para eliminación.</span><span class="sxs-lookup"><span data-stu-id="def3f-121">When you use the `Delete` method, the row remains in the `DataTable` and is marked for deletion.</span></span> <span data-ttu-id="def3f-122">Si a continuación se pasa `DataTable` o `DataSet` a `DataAdapter` y se llama a `Update`, la fila correspondiente en el origen de datos back end se elimina.</span><span class="sxs-lookup"><span data-stu-id="def3f-122">If you then pass the `DataTable` or `DataSet` to a `DataAdapter` and call `Update`, the corresponding row in the back end data source is deleted.</span></span>

<span data-ttu-id="def3f-123">Si `DataTable` está asignada a una única base de datos o se ha generado a partir de ella, puede utilizar el objeto <xref:System.Data.Common.DbCommandBuilder> para generar automáticamente los objetos `DeleteCommand`, `InsertCommand` y `UpdateCommand` de `DataAdapter`.</span><span class="sxs-lookup"><span data-stu-id="def3f-123">If your `DataTable` maps to or is generated from a single database table, you can take advantage of the <xref:System.Data.Common.DbCommandBuilder> object to automatically generate the `DeleteCommand`, `InsertCommand`, and `UpdateCommand` objects for the `DataAdapter`.</span></span> <span data-ttu-id="def3f-124">Para obtener más información, vea [generar comandos con objetos CommandBuilder](generating-commands-with-commandbuilders.md).</span><span class="sxs-lookup"><span data-stu-id="def3f-124">For more information, see [Generating Commands with CommandBuilders](generating-commands-with-commandbuilders.md).</span></span>

## <a name="using-updatedrowsource-to-map-values-to-a-dataset"></a><span data-ttu-id="def3f-125">Utilizar UpdatedRowSource para asignar valores a DataSet</span><span class="sxs-lookup"><span data-stu-id="def3f-125">Using UpdatedRowSource to Map Values to a DataSet</span></span>

<span data-ttu-id="def3f-126">Puede controlar la forma en que los valores devueltos desde el origen de datos se asignan a `DataTable` después de una llamada al método Update de `DataAdapter`, utilizando la propiedad <xref:System.Data.Common.DbCommand.UpdatedRowSource%2A> de un objeto <xref:System.Data.Common.DbCommand>.</span><span class="sxs-lookup"><span data-stu-id="def3f-126">You can control how the values returned from the data source are mapped back to the `DataTable` following a call to the Update method of a `DataAdapter`, by using the <xref:System.Data.Common.DbCommand.UpdatedRowSource%2A> property of a <xref:System.Data.Common.DbCommand> object.</span></span> <span data-ttu-id="def3f-127">Al asignar la propiedad `UpdatedRowSource` a uno de los valores de enumeración <xref:System.Data.UpdateRowSource>, puede determinar si los parámetros que devuelven los comandos `DataAdapter` se deben omitir o se deben aplicar a la fila cambiada en `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="def3f-127">By setting the `UpdatedRowSource` property to one of the <xref:System.Data.UpdateRowSource> enumeration values, you can control whether output parameters returned by the `DataAdapter` commands are ignored or applied to the changed row in the `DataSet`.</span></span> <span data-ttu-id="def3f-128">También puede especificar si la primera fila devuelta (si existe) se aplica a la fila modificada en `DataTable`.</span><span class="sxs-lookup"><span data-stu-id="def3f-128">You can also specify whether the first returned row (if it exists) is applied to the changed row in the `DataTable`.</span></span>

<span data-ttu-id="def3f-129">En la tabla siguiente se describen los distintos valores de la enumeración `UpdateRowSource` y la forma en que afectan al comportamiento del comando utilizado con `DataAdapter`.</span><span class="sxs-lookup"><span data-stu-id="def3f-129">The following table describes the different values of the `UpdateRowSource` enumeration and how they affect the behavior of a command used with a `DataAdapter`.</span></span>

|<span data-ttu-id="def3f-130">Enumeración UpdatedRowSource</span><span class="sxs-lookup"><span data-stu-id="def3f-130">UpdatedRowSource Enumeration</span></span>|<span data-ttu-id="def3f-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="def3f-131">Description</span></span>|
|----------------------------------|-----------------|
|<xref:System.Data.UpdateRowSource.Both>|<span data-ttu-id="def3f-132">Tanto los parámetros de salida como la primera fila del conjunto de resultados devuelto se pueden asignar a la fila modificada en `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="def3f-132">Both the output parameters and the first row of a returned result set may be mapped to the changed row in the `DataSet`.</span></span>|
|<xref:System.Data.UpdateRowSource.FirstReturnedRecord>|<span data-ttu-id="def3f-133">Solo los datos de la primera fila del conjunto de resultados devuelto se pueden asignar a la fila modificada en el `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="def3f-133">Only the data in the first row of a returned result set may be mapped to the changed row in the `DataSet`.</span></span>|
|<xref:System.Data.UpdateRowSource.None>|<span data-ttu-id="def3f-134">Se pasan por alto todos los parámetros de salida y las filas del conjunto de resultados devuelto.</span><span class="sxs-lookup"><span data-stu-id="def3f-134">Any output parameters or rows of a returned result set are ignored.</span></span>|
|<xref:System.Data.UpdateRowSource.OutputParameters>|<span data-ttu-id="def3f-135">Solo los parámetros de salida se pueden asignar a la fila modificada en `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="def3f-135">Only output parameters may be mapped to the changed row in the `DataSet`.</span></span>|

<span data-ttu-id="def3f-136">El método `Update` vuelve a resolver los cambios en el origen de datos; sin embargo, puede que otros clientes hayan modificado datos en el origen de datos desde la última vez que se llenó `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="def3f-136">The `Update` method resolves your changes back to the data source; however other clients may have modified data at the data source since the last time you filled the `DataSet`.</span></span> <span data-ttu-id="def3f-137">Para actualizar `DataSet` con datos actuales, utilice el `DataAdapter` y el método `Fill`.</span><span class="sxs-lookup"><span data-stu-id="def3f-137">To refresh your `DataSet` with current data, use the `DataAdapter` and `Fill` method.</span></span> <span data-ttu-id="def3f-138">De esta forma se agregan las filas nuevas a la tabla y se actualiza la información en las filas ya existentes.</span><span class="sxs-lookup"><span data-stu-id="def3f-138">New rows will be added to the table, and updated information will be incorporated into existing rows.</span></span> <span data-ttu-id="def3f-139">El método `Fill` determina si se va a agregar una nueva fila o si se va a actualizar una fila existente mediante el examen de los valores de clave principal de las filas de `DataSet` y las filas devueltas por `SelectCommand`.</span><span class="sxs-lookup"><span data-stu-id="def3f-139">The `Fill` method determines whether a new row will be added or an existing row will be updated by examining the primary key values of the rows in the `DataSet` and the rows returned by the `SelectCommand`.</span></span> <span data-ttu-id="def3f-140">Si el método `Fill` encuentra un valor de clave principal de una fila de `DataSet` que coincide con un valor de clave principal de una fila de los resultados devueltos por `SelectCommand`, éste actualiza la fila existente con la información de la fila devuelta por `SelectCommand` y establece el <xref:System.Data.DataRow.RowState%2A> de la fila existente en `Unchanged`.</span><span class="sxs-lookup"><span data-stu-id="def3f-140">If the `Fill` method encounters a primary key value for a row in the `DataSet` that matches a primary key value from a row in the results returned by the `SelectCommand`, it updates the existing row with the information from the row returned by the `SelectCommand` and sets the <xref:System.Data.DataRow.RowState%2A> of the existing row to `Unchanged`.</span></span> <span data-ttu-id="def3f-141">Si una fila devuelta por `SelectCommand` tiene un valor de clave principal que no coincide con ninguno de los valores de clave principal de las filas de `DataSet`, el método `Fill` agrega una nueva fila con un `RowState` de `Unchanged`.</span><span class="sxs-lookup"><span data-stu-id="def3f-141">If a row returned by the `SelectCommand` has a primary key value that does not match any of the primary key values of the rows in the `DataSet`, the `Fill` method adds a new row with a `RowState` of `Unchanged`.</span></span>

> [!NOTE]
> <span data-ttu-id="def3f-142">Si `SelectCommand` devuelve los resultados de una combinación externa (OUTER JOIN), `DataAdapter` no establecerá un valor `PrimaryKey` para la tabla `DataTable` resultante.</span><span class="sxs-lookup"><span data-stu-id="def3f-142">If the `SelectCommand` returns the results of an OUTER JOIN, the `DataAdapter` will not set a `PrimaryKey` value for the resulting `DataTable`.</span></span> <span data-ttu-id="def3f-143">Debe definir `PrimaryKey` para asegurarse de que las filas duplicadas se resuelven correctamente.</span><span class="sxs-lookup"><span data-stu-id="def3f-143">You must define the `PrimaryKey` yourself to ensure that duplicate rows are resolved correctly.</span></span> <span data-ttu-id="def3f-144">Para obtener más información, vea [definir claves principales](./dataset-datatable-dataview/defining-primary-keys.md).</span><span class="sxs-lookup"><span data-stu-id="def3f-144">For more information, see [Defining Primary Keys](./dataset-datatable-dataview/defining-primary-keys.md).</span></span>

<span data-ttu-id="def3f-145">Para controlar las excepciones que se pueden producir al llamar al `Update` método, puede utilizar el `RowUpdated` evento para responder a los errores de actualización de la fila a medida que se producen (vea [controlar eventos DataAdapter](handling-dataadapter-events.md)), o puede establecer `DataAdapter.ContinueUpdateOnError` en `true` antes de llamar a `Update` y responder a la información de error almacenada en la `RowError` propiedad de una fila determinada cuando se completa la actualización (vea la [información de error de fila](./dataset-datatable-dataview/row-error-information.md)).</span><span class="sxs-lookup"><span data-stu-id="def3f-145">To handle exceptions that may occur when calling the `Update` method, you can use the `RowUpdated` event to respond to row update errors as they occur (see [Handling DataAdapter Events](handling-dataadapter-events.md)), or you can set `DataAdapter.ContinueUpdateOnError` to `true` before calling `Update`, and respond to the error information stored in the `RowError` property of a particular row when the update is complete (see [Row Error Information](./dataset-datatable-dataview/row-error-information.md)).</span></span>

> [!NOTE]
> <span data-ttu-id="def3f-146">Llamar a `AcceptChanges` en `DataSet` , `DataTable` o hará `DataRow` que todos los `Original` valores de `DataRow` se sobrescriban con los `Current` valores de `DataRow` .</span><span class="sxs-lookup"><span data-stu-id="def3f-146">Calling `AcceptChanges` on the `DataSet`, `DataTable`, or `DataRow` will cause all `Original` values for a `DataRow` to be overwritten with the `Current` values for the `DataRow`.</span></span> <span data-ttu-id="def3f-147">Si se han modificado los valores de campo que identifican de forma única a una fila, los valores `AcceptChanges` dejarán de coincidir con los valores del origen de datos después de llamar a `Original`.</span><span class="sxs-lookup"><span data-stu-id="def3f-147">If the field values that identify the row as unique have been modified, after calling `AcceptChanges` the `Original` values will no longer match the values in the data source.</span></span> <span data-ttu-id="def3f-148">Se llama automáticamente a `AcceptChanges` para cada fila durante una llamada al método Update de `DataAdapter`.</span><span class="sxs-lookup"><span data-stu-id="def3f-148">`AcceptChanges` is called automatically for each row during a call to the Update method of a `DataAdapter`.</span></span> <span data-ttu-id="def3f-149">Puede conservar los valores originales durante una llamada al método Update estableciendo primero la propiedad `AcceptChangesDuringUpdate` de `DataAdapter` en false o creando un controlador de eventos para el evento `RowUpdated` y estableciendo <xref:System.Data.Common.RowUpdatedEventArgs.Status%2A> en <xref:System.Data.UpdateStatus.SkipCurrentRow>.</span><span class="sxs-lookup"><span data-stu-id="def3f-149">You can preserve the original values during a call to the Update method by first setting the `AcceptChangesDuringUpdate` property of the `DataAdapter` to false, or by creating an event handler for the `RowUpdated` event and setting the <xref:System.Data.Common.RowUpdatedEventArgs.Status%2A> to <xref:System.Data.UpdateStatus.SkipCurrentRow>.</span></span> <span data-ttu-id="def3f-150">Para obtener más información, vea [combinar el contenido](./dataset-datatable-dataview/merging-dataset-contents.md) de un conjunto de datos y [controlar eventos DataAdapter](handling-dataadapter-events.md).</span><span class="sxs-lookup"><span data-stu-id="def3f-150">For more information, see [Merging DataSet Contents](./dataset-datatable-dataview/merging-dataset-contents.md) and [Handling DataAdapter Events](handling-dataadapter-events.md).</span></span>

## <a name="example"></a><span data-ttu-id="def3f-151">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="def3f-151">Example</span></span>

<span data-ttu-id="def3f-152">En los siguientes ejemplos se muestra cómo realizar actualizaciones de las filas modificadas estableciendo explícitamente el valor `UpdateCommand` de `DataAdapter` y llamando a su `Update` método.</span><span class="sxs-lookup"><span data-stu-id="def3f-152">The following examples demonstrate how to perform updates to modified rows by explicitly setting the `UpdateCommand` of a `DataAdapter` and calling its `Update` method.</span></span> <span data-ttu-id="def3f-153">Observe cómo el parámetro especificado en la cláusula WHERE de la instrucción UPDATE tiene el valor adecuado para usar el valor `Original` de `SourceColumn`.</span><span class="sxs-lookup"><span data-stu-id="def3f-153">Notice that the parameter specified in the WHERE clause of the UPDATE statement is set to use the `Original` value of the `SourceColumn`.</span></span> <span data-ttu-id="def3f-154">Este hecho es muy importante ya que el valor `Current` puede haber sido modificado de forma que ya no coincida con el valor del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="def3f-154">This is important, because the `Current` value may have been modified and may not match the value in the data source.</span></span> <span data-ttu-id="def3f-155">El valor `Original` es el que se usó para rellenar la tabla `DataTable` a partir del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="def3f-155">The `Original` value is the value that was used to populate the `DataTable` from the data source.</span></span>

[!code-csharp[DataWorks SqlClient.DataAdapterUpdate#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.DataAdapterUpdate/CS/source.cs#1)]
[!code-vb[DataWorks SqlClient.DataAdapterUpdate#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.DataAdapterUpdate/VB/source.vb#1)]

## <a name="autoincrement-columns"></a><span data-ttu-id="def3f-156">Columnas AutoIncrement</span><span class="sxs-lookup"><span data-stu-id="def3f-156">AutoIncrement Columns</span></span>

<span data-ttu-id="def3f-157">Si las tablas del origen de datos tienen columnas con incremento automático, puede rellenar las columnas de `DataSet` devolviendo el valor de incremento automático como un parámetro de salida de un procedimiento almacenado y asignándolo a una columna de la tabla, o devolviendo el valor de incremento automático de la primera fila de un conjunto de resultados devuelto por un procedimiento almacenado o una instrucción SQL, o mediante el evento `RowUpdated` de `DataAdapter` para ejecutar una instrucción SELECT adicional.</span><span class="sxs-lookup"><span data-stu-id="def3f-157">If the tables from your data source have auto-incrementing columns, you can fill the columns in your `DataSet` either by returning the auto-increment value as an output parameter of a stored procedure and mapping that to a column in a table, by returning the auto-increment value in the first row of a result set returned by a stored procedure or SQL statement, or by using the `RowUpdated` event of the `DataAdapter` to execute an additional SELECT statement.</span></span> <span data-ttu-id="def3f-158">Para obtener más información y un ejemplo, vea [recuperar valores de identidad o Autonumérico](retrieving-identity-or-autonumber-values.md).</span><span class="sxs-lookup"><span data-stu-id="def3f-158">For more information and an example, see [Retrieving Identity or Autonumber Values](retrieving-identity-or-autonumber-values.md).</span></span>

## <a name="ordering-of-inserts-updates-and-deletes"></a><span data-ttu-id="def3f-159">Orden de las inserciones, actualizaciones y eliminaciones</span><span class="sxs-lookup"><span data-stu-id="def3f-159">Ordering of Inserts, Updates, and Deletes</span></span>

<span data-ttu-id="def3f-160">En algunas circunstancias, es importante el orden en que se envían al origen de datos los cambios realizados en el `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="def3f-160">In many circumstances, the order in which changes made through the `DataSet` are sent to the data source is important.</span></span> <span data-ttu-id="def3f-161">Por ejemplo, si se actualiza el valor de una clave principal de una fila existente y se ha agregado una nueva fila con el nuevo valor de la clave principal como una clave externa, es importante que la actualización de la fila se procese antes que la inserción.</span><span class="sxs-lookup"><span data-stu-id="def3f-161">For example, if a primary key value for an existing row is updated, and a new row has been added with the new primary key value as a foreign key, it is important to process the update before the insert.</span></span>

<span data-ttu-id="def3f-162">Puede usar el método `Select` de `DataTable` para devolver una matriz `DataRow` que solo haga referencia a filas con un estado `RowState` determinado.</span><span class="sxs-lookup"><span data-stu-id="def3f-162">You can use the `Select` method of the `DataTable` to return a `DataRow` array that only references rows with a particular `RowState`.</span></span> <span data-ttu-id="def3f-163">A continuación, puede pasar la matriz `DataRow` al método `Update` de `DataAdapter` para procesar las filas modificadas.</span><span class="sxs-lookup"><span data-stu-id="def3f-163">You can then pass the returned `DataRow` array to the `Update` method of the `DataAdapter` to process the modified rows.</span></span> <span data-ttu-id="def3f-164">Al especificar un subconjunto de filas que modificar, puede controlar el orden en que se procesan las inserciones, actualizaciones y eliminaciones.</span><span class="sxs-lookup"><span data-stu-id="def3f-164">By specifying a subset of rows to be updated, you can control the order in which inserts, updates, and deletes are processed.</span></span>

## <a name="example"></a><span data-ttu-id="def3f-165">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="def3f-165">Example</span></span>

<span data-ttu-id="def3f-166">Por ejemplo, en el código siguiente se garantiza que en primer lugar se realizan en la tabla las eliminaciones de filas, después las actualizaciones y finalmente las inserciones.</span><span class="sxs-lookup"><span data-stu-id="def3f-166">For example, the following code ensures that the deleted rows of the table are processed first, then the updated rows, and then the inserted rows.</span></span>

```vb
Dim table As DataTable = dataSet.Tables("Customers")

' First process deletes.
dataSet.Update(table.Select(Nothing, Nothing, _
  DataViewRowState.Deleted))

' Next process updates.
adapter.Update(table.Select(Nothing, Nothing, _
  DataViewRowState.ModifiedCurrent))

' Finally, process inserts.
adapter.Update(table.Select(Nothing, Nothing, _
  DataViewRowState.Added))
```

```csharp
DataTable table = dataSet.Tables["Customers"];

// First process deletes.
adapter.Update(table.Select(null, null, DataViewRowState.Deleted));

// Next process updates.
adapter.Update(table.Select(null, null,
  DataViewRowState.ModifiedCurrent));

// Finally, process inserts.
adapter.Update(table.Select(null, null, DataViewRowState.Added));
```

## <a name="use-a-dataadapter-to-retrieve-and-update-data"></a><span data-ttu-id="def3f-167">Usar un objeto DataAdapter para recuperar y actualizar datos</span><span class="sxs-lookup"><span data-stu-id="def3f-167">Use a DataAdapter to Retrieve and Update Data</span></span>

<span data-ttu-id="def3f-168">Puede usar un objeto DataAdapter para recuperar y actualizar los datos.</span><span class="sxs-lookup"><span data-stu-id="def3f-168">You can use a DataAdapter to retrieve and update the data.</span></span>

- <span data-ttu-id="def3f-169">El ejemplo usa DataAdapter.AcceptChangesDuringFill para clonar los datos en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="def3f-169">The sample uses DataAdapter.AcceptChangesDuringFill to clone the data in the database.</span></span> <span data-ttu-id="def3f-170">Si la propiedad se establece como false, no se llama a AcceptChanges al rellenar la tabla y las filas que se acaban de agregar se tratan como filas insertadas.</span><span class="sxs-lookup"><span data-stu-id="def3f-170">If the property is set as false, AcceptChanges is not called when filling the table, and the newly added rows are treated as inserted rows.</span></span> <span data-ttu-id="def3f-171">Por lo tanto, el ejemplo usa estas filas para insertar las filas nuevas en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="def3f-171">So, the sample uses these rows to insert the new rows into the database.</span></span>

- <span data-ttu-id="def3f-172">Los ejemplos usan DataAdapter.TableMappings para definir la asignación entre la tabla de origen y DataTable.</span><span class="sxs-lookup"><span data-stu-id="def3f-172">The samples uses DataAdapter.TableMappings to define the mapping between the source table and DataTable.</span></span>

- <span data-ttu-id="def3f-173">El ejemplo usa DataAdapter.FillLoadOption para determinar cómo rellena el adaptador el objeto DataTable de DbDataReader.</span><span class="sxs-lookup"><span data-stu-id="def3f-173">The sample uses DataAdapter.FillLoadOption to determine how the adapter fills the DataTable from the DbDataReader.</span></span> <span data-ttu-id="def3f-174">Al crear un objeto DataTable, solo puede escribir los datos de la base de datos en la versión actual o en la versión original si establece la propiedad como LoadOption.Upsert o LoadOption.PreserveChanges.</span><span class="sxs-lookup"><span data-stu-id="def3f-174">When you create a DataTable, you can only write the data from database to the current version or the original version by setting the property as the LoadOption.Upsert or the LoadOption.PreserveChanges.</span></span>

- <span data-ttu-id="def3f-175">El ejemplo también actualizará la tabla mediante DbDataAdapter.UpdateBatchSize para realizar operaciones por lotes.</span><span class="sxs-lookup"><span data-stu-id="def3f-175">The sample will also update the table by using DbDataAdapter.UpdateBatchSize to perform batch operations.</span></span>

<span data-ttu-id="def3f-176">Antes de compilar y ejecutar el ejemplo, debe crear la base de datos de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="def3f-176">Before you compile and run the sample, you need to create the sample database:</span></span>

```sql
USE [master]
GO

CREATE DATABASE [MySchool]

GO

USE [MySchool]
GO

SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[Course]([CourseID] [nvarchar](10) NOT NULL,
[Year] [smallint] NOT NULL,
[Title] [nvarchar](100) NOT NULL,
[Credits] [int] NOT NULL,
[DepartmentID] [int] NOT NULL,
 CONSTRAINT [PK_Course] PRIMARY KEY CLUSTERED
(
[CourseID] ASC,
[Year] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]) ON [PRIMARY]

GO

SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[Department]([DepartmentID] [int] IDENTITY(1,1) NOT NULL,
[Name] [nvarchar](50) NOT NULL,
[Budget] [money] NOT NULL,
[StartDate] [datetime] NOT NULL,
[Administrator] [int] NULL,
 CONSTRAINT [PK_Department] PRIMARY KEY CLUSTERED
(
[DepartmentID] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]) ON [PRIMARY]

GO

INSERT [dbo].[Course] ([CourseID], [Year], [Title], [Credits], [DepartmentID]) VALUES (N'C1045', 2012, N'Calculus', 4, 7)
INSERT [dbo].[Course] ([CourseID], [Year], [Title], [Credits], [DepartmentID]) VALUES (N'C1061', 2012, N'Physics', 4, 1)
INSERT [dbo].[Course] ([CourseID], [Year], [Title], [Credits], [DepartmentID]) VALUES (N'C2021', 2012, N'Composition', 3, 2)
INSERT [dbo].[Course] ([CourseID], [Year], [Title], [Credits], [DepartmentID]) VALUES (N'C2042', 2012, N'Literature', 4, 2)

SET IDENTITY_INSERT [dbo].[Department] ON

INSERT [dbo].[Department] ([DepartmentID], [Name], [Budget], [StartDate], [Administrator]) VALUES (1, N'Engineering', 350000.0000, CAST(0x0000999C00000000 AS DateTime), 2)
INSERT [dbo].[Department] ([DepartmentID], [Name], [Budget], [StartDate], [Administrator]) VALUES (2, N'English', 120000.0000, CAST(0x0000999C00000000 AS DateTime), 6)
INSERT [dbo].[Department] ([DepartmentID], [Name], [Budget], [StartDate], [Administrator]) VALUES (4, N'Economics', 200000.0000, CAST(0x0000999C00000000 AS DateTime), 4)
INSERT [dbo].[Department] ([DepartmentID], [Name], [Budget], [StartDate], [Administrator]) VALUES (7, N'Mathematics', 250024.0000, CAST(0x0000999C00000000 AS DateTime), 3)
SET IDENTITY_INSERT [dbo].[Department] OFF

ALTER TABLE [dbo].[Course]  WITH CHECK ADD  CONSTRAINT [FK_Course_Department] FOREIGN KEY([DepartmentID])
REFERENCES [dbo].[Department] ([DepartmentID])
GO
ALTER TABLE [dbo].[Course] CHECK CONSTRAINT [FK_Course_Department]
GO
```

<span data-ttu-id="def3f-177">Los proyectos de C# y Visual Basic con este ejemplo de código se pueden encontrar en [ejemplos de código para desarrolladores](https://code.msdn.microsoft.com/site/search?f%5B0%5D.Type=SearchText&f%5B0%5D.Value=How%20to%20use%20DataAdapter%20to%20retrieve%20and%20update%20data&f%5B1%5D).</span><span class="sxs-lookup"><span data-stu-id="def3f-177">C# and Visual Basic projects with this code sample can be found on [Developer Code Samples](https://code.msdn.microsoft.com/site/search?f%5B0%5D.Type=SearchText&f%5B0%5D.Value=How%20to%20use%20DataAdapter%20to%20retrieve%20and%20update%20data&f%5B1%5D).</span></span>

```csharp
using System;
using System.Data;
using System.Data.Common;
using System.Data.SqlClient;
using System.Linq;
using CSDataAdapterOperations.Properties;

namespace CSDataAdapterOperations.Properties {
   internal sealed partial class Settings : global::System.Configuration.ApplicationSettingsBase {

      private static Settings defaultInstance = ((Settings)(global::System.Configuration.ApplicationSettingsBase.Synchronized(new Settings())));

      public static Settings Default {
         get {
            return defaultInstance;
         }
      }

      [global::System.Configuration.ApplicationScopedSettingAttribute()]
      [global::System.Configuration.DefaultSettingValueAttribute("Data Source=(local);Initial Catalog=MySchool;Integrated Security=True")]
      public string MySchoolConnectionString {
         get {
            return ((string)(this["MySchoolConnectionString"]));
         }
      }
   }
}

class Program {
   static void Main(string[] args) {
      Settings settings = new Settings();

      // Copy the data from the database.  Get the table Department and Course from the database.
      String selectString = @"SELECT [DepartmentID],[Name],[Budget],[StartDate],[Administrator]
                                     FROM [MySchool].[dbo].[Department];

                                   SELECT [CourseID],@Year as [Year],Max([Title]) as [Title],
                                   Max([Credits]) as [Credits],Max([DepartmentID]) as [DepartmentID]
                                   FROM [MySchool].[dbo].[Course]
                                   Group by [CourseID]";

      DataSet mySchool = new DataSet();

      SqlCommand selectCommand = new SqlCommand(selectString);
      SqlParameter parameter = selectCommand.Parameters.Add("@Year", SqlDbType.SmallInt, 2);
      parameter.Value = new Random(DateTime.Now.Millisecond).Next(9999);

      // Use DataTableMapping to map the source tables and the destination tables.
      DataTableMapping[] tableMappings = {new DataTableMapping("Table", "Department"), new DataTableMapping("Table1", "Course")};
      CopyData(mySchool, settings.MySchoolConnectionString, selectCommand, tableMappings);

      Console.WriteLine("The following tables are from the database.");
      foreach (DataTable table in mySchool.Tables) {
         Console.WriteLine(table.TableName);
         ShowDataTable(table);
      }

      // Roll back the changes
      DataTable department = mySchool.Tables["Department"];
      DataTable course = mySchool.Tables["Course"];

      department.Rows[0]["Name"] = "New" + department.Rows[0][1];
      course.Rows[0]["Title"] = "New" + course.Rows[0]["Title"];
      course.Rows[0]["Credits"] = 10;

      Console.WriteLine("After we changed the tables:");
      foreach (DataTable table in mySchool.Tables) {
         Console.WriteLine(table.TableName);
         ShowDataTable(table);
      }

      department.RejectChanges();
      Console.WriteLine("After use the RejectChanges method in Department table to roll back the changes:");
      ShowDataTable(department);

      DataColumn[] primaryColumns = { course.Columns["CourseID"] };
      DataColumn[] resetColumns = { course.Columns["Title"] };
      ResetCourse(course, settings.MySchoolConnectionString, primaryColumns, resetColumns);
      Console.WriteLine("After use the ResetCourse method in Course table to roll back the changes:");
      ShowDataTable(course);

      // Batch update the table.
      String insertString = @"Insert into [MySchool].[dbo].[Course]([CourseID],[Year],[Title],
                                   [Credits],[DepartmentID])
             values (@CourseID,@Year,@Title,@Credits,@DepartmentID)";
      SqlCommand insertCommand = new SqlCommand(insertString);
      insertCommand.Parameters.Add("@CourseID", SqlDbType.NVarChar, 10, "CourseID");
      insertCommand.Parameters.Add("@Year", SqlDbType.SmallInt, 2, "Year");
      insertCommand.Parameters.Add("@Title", SqlDbType.NVarChar, 100, "Title");
      insertCommand.Parameters.Add("@Credits", SqlDbType.Int, 4, "Credits");
      insertCommand.Parameters.Add("@DepartmentID", SqlDbType.Int, 4, "DepartmentID");

      const Int32 batchSize = 10;
      BatchInsertUpdate(course, settings.MySchoolConnectionString, insertCommand, batchSize);
   }

   private static void CopyData(DataSet dataSet, String connectionString, SqlCommand selectCommand, DataTableMapping[] tableMappings) {
      using (SqlConnection connection = new SqlConnection(connectionString)) {
         selectCommand.Connection = connection;

         connection.Open();

         using (SqlDataAdapter adapter = new SqlDataAdapter(selectCommand)) {adapter.TableMappings.AddRange(tableMappings);
            // If set the AcceptChangesDuringFill as the false, AcceptChanges will not be called on a
            // DataRow after it is added to the DataTable during any of the Fill operations.
            adapter.AcceptChangesDuringFill = false;

            adapter.Fill(dataSet);
         }
      }
   }

   // Roll back only one column or several columns data of the Course table by call ResetDataTable method.
   private static void ResetCourse(DataTable table, String connectionString,
       DataColumn[] primaryColumns, DataColumn[] resetColumns) {
      table.PrimaryKey = primaryColumns;

      // Build the query string
      String primaryCols = String.Join(",", primaryColumns.Select(col => col.ColumnName));
      String resetCols = String.Join(",", resetColumns.Select(col => $"Max({col.ColumnName}) as {col.ColumnName}"));

      String selectString = $"Select {primaryCols},{resetCols} from Course Group by {primaryCols}");

      SqlCommand selectCommand = new SqlCommand(selectString);

      ResetDataTable(table, connectionString, selectCommand);
   }

   // RejectChanges will roll back all changes made to the table since it was loaded, or the last time AcceptChanges
   // was called. When you copy from the database, you can lose all the data after calling RejectChanges
   // The ResetDataTable method rolls back one or more columns of data.
   private static void ResetDataTable(DataTable table, String connectionString,
       SqlCommand selectCommand) {
      using (SqlConnection connection = new SqlConnection(connectionString)) {
         selectCommand.Connection = connection;

         connection.Open();

         using (SqlDataAdapter adapter = new SqlDataAdapter(selectCommand)) {
            // The incoming values for this row will be written to the current version of each
            // column. The original version of each column's data will not be changed.
            adapter.FillLoadOption = LoadOption.Upsert;

            adapter.Fill(table);
         }
      }
   }

   private static void BatchInsertUpdate(DataTable table, String connectionString,
       SqlCommand insertCommand, Int32 batchSize) {
      using (SqlConnection connection = new SqlConnection(connectionString)) {
         insertCommand.Connection = connection;
         // When setting UpdateBatchSize to a value other than 1, all the commands
         // associated with the SqlDataAdapter have to have their UpdatedRowSource
         // property set to None or OutputParameters. An exception is thrown otherwise.
         insertCommand.UpdatedRowSource = UpdateRowSource.None;

         connection.Open();

         using (SqlDataAdapter adapter = new SqlDataAdapter()) {
            adapter.InsertCommand = insertCommand;
            // Gets or sets the number of rows that are processed in each round-trip to the server.
            // Setting it to 1 disables batch updates, as rows are sent one at a time.
            adapter.UpdateBatchSize = batchSize;

            adapter.Update(table);

            Console.WriteLine("Successfully to update the table.");
         }
      }
   }

   private static void ShowDataTable(DataTable table) {
      foreach (DataColumn col in table.Columns) {
         Console.Write("{0,-14}", col.ColumnName);
      }
      Console.WriteLine("{0,-14}", "RowState");

      foreach (DataRow row in table.Rows) {
         foreach (DataColumn col in table.Columns) {
            if (col.DataType.Equals(typeof(DateTime)))
               Console.Write("{0,-14:d}", row[col]);
            else if (col.DataType.Equals(typeof(Decimal)))
               Console.Write("{0,-14:C}", row[col]);
            else
               Console.Write("{0,-14}", row[col]);
         }
         Console.WriteLine("{0,-14}", row.RowState);
      }
   }
}
```

## <a name="see-also"></a><span data-ttu-id="def3f-178">Consulte también</span><span class="sxs-lookup"><span data-stu-id="def3f-178">See also</span></span>

- [<span data-ttu-id="def3f-179">Objetos DataAdapter y DataReader</span><span class="sxs-lookup"><span data-stu-id="def3f-179">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="def3f-180">Estados y versiones de filas</span><span class="sxs-lookup"><span data-stu-id="def3f-180">Row States and Row Versions</span></span>](./dataset-datatable-dataview/row-states-and-row-versions.md)
- [<span data-ttu-id="def3f-181">Objetos AcceptChange y RejectChange</span><span class="sxs-lookup"><span data-stu-id="def3f-181">AcceptChanges and RejectChanges</span></span>](./dataset-datatable-dataview/acceptchanges-and-rejectchanges.md)
- [<span data-ttu-id="def3f-182">Combinar contenido de DataSet</span><span class="sxs-lookup"><span data-stu-id="def3f-182">Merging DataSet Contents</span></span>](./dataset-datatable-dataview/merging-dataset-contents.md)
- [<span data-ttu-id="def3f-183">Recuperar valores autonuméricos y de identidad</span><span class="sxs-lookup"><span data-stu-id="def3f-183">Retrieving Identity or Autonumber Values</span></span>](retrieving-identity-or-autonumber-values.md)
- [<span data-ttu-id="def3f-184">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="def3f-184">ADO.NET Overview</span></span>](ado-net-overview.md)
