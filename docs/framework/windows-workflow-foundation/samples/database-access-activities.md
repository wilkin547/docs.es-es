---
description: 'Más información sobre: actividades de acceso a bases de datos'
title: Actividades de acceso a bases de datos
ms.date: 03/30/2017
ms.assetid: 174a381e-1343-46a8-a62c-7c2ae2c4f0b2
ms.openlocfilehash: 421da4a55997dac62ccc5c598bc401a20711ec61
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792549"
---
# <a name="database-access-activities"></a><span data-ttu-id="9468c-103">Actividades de acceso a bases de datos</span><span class="sxs-lookup"><span data-stu-id="9468c-103">Database Access Activities</span></span>

<span data-ttu-id="9468c-104">Las actividades de acceso a bases de datos permiten tener acceso a una base de datos dentro de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="9468c-104">Database access activities allow you to access a database within a workflow.</span></span> <span data-ttu-id="9468c-105">Estas actividades permiten tener acceso a las bases de datos para recuperar o modificar información y usar [ADO.net](../../data/adonet/index.md) para tener acceso a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="9468c-105">These activities allow accessing databases to retrieve or modify information and use [ADO.NET](../../data/adonet/index.md) to access the database.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9468c-106">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="9468c-106">The samples may already be installed on your machine.</span></span> <span data-ttu-id="9468c-107">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="9468c-107">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="9468c-108">Si este directorio no existe, vaya a (página de descarga) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="9468c-108">If this directory does not exist, go to (download page) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="9468c-109">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="9468c-109">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\DbActivities`

## <a name="database-activities"></a><span data-ttu-id="9468c-110">Actividades de base de datos</span><span class="sxs-lookup"><span data-stu-id="9468c-110">Database Activities</span></span>

<span data-ttu-id="9468c-111">En las siguientes secciones se detalla la lista de actividades incluidas en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="9468c-111">The following sections detail the list of activities included in this sample.</span></span>

## <a name="dbupdate"></a><span data-ttu-id="9468c-112">DbUpdate</span><span class="sxs-lookup"><span data-stu-id="9468c-112">DbUpdate</span></span>

<span data-ttu-id="9468c-113">Ejecuta una consulta SQL que genera una modificación en la base de datos (inserción, actualización, eliminación y otras modificaciones).</span><span class="sxs-lookup"><span data-stu-id="9468c-113">Executes a SQL query that produces a modification in the database (insert, update, delete, and other modifications).</span></span>

<span data-ttu-id="9468c-114">Esta clase realiza su trabajo de forma asincrónica (deriva de <xref:System.Activities.AsyncCodeActivity> y usa sus capacidades asincrónicas).</span><span class="sxs-lookup"><span data-stu-id="9468c-114">This class performs its work asynchronously (it derives from <xref:System.Activities.AsyncCodeActivity> and uses its asynchronous capabilities).</span></span>

<span data-ttu-id="9468c-115">La información de conexión se puede configurar estableciendo un nombre invariable de proveedor (`ProviderName`) y la cadena de conexión (`ConnectionString`) o simplemente utilizando un nombre de configuración de cadena de conexión (`ConfigFileSectionName`) del archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9468c-115">The connection information can be configured by setting a provider invariant name (`ProviderName`) and the connection string (`ConnectionString`) or just using a connection string configuration name (`ConfigFileSectionName`) from the application configuration file.</span></span>

<span data-ttu-id="9468c-116">La consulta que se va a ejecutar se configura en su propiedad `Sql` y los parámetros se pasan a través de la colección `Parameters`.</span><span class="sxs-lookup"><span data-stu-id="9468c-116">The query to be executed is configured in its `Sql` property and the parameters are passed through the `Parameters` collection.</span></span>

<span data-ttu-id="9468c-117">Una vez ejecutado `DbUpdate`, el número de registros afectado se devuelve en la propiedad `AffectedRecords`.</span><span class="sxs-lookup"><span data-stu-id="9468c-117">After `DbUpdate` is executed, the number of affected records is returned in the `AffectedRecords` property.</span></span>

```csharp
Public class DbUpdate: AsyncCodeActivity
{
    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DefaultValue(null)]
    public InArgument<string> ProviderName { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DependsOn("ProviderName")]
    [DefaultValue(null)]
    public InArgument<string> ConnectionString { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConfigFileSectionName")]
    [DefaultValue(null)]
    public InArgument<string> ConfigName { get; set; }

    [DefaultValue(null)]
    public CommandType CommandType { get; set; }

    [RequiredArgument]
    public InArgument<string> Sql { get; set; }

    [DependsOn("Sql")]
    [DefaultValue(null)]
    public IDictionary<string, Argument> Parameters { get; }

    [DependsOn("Parameters")]
    public OutArgument<int> AffectedRecords { get; set; }
}
```

|<span data-ttu-id="9468c-118">Argumento</span><span class="sxs-lookup"><span data-stu-id="9468c-118">Argument</span></span>|<span data-ttu-id="9468c-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="9468c-119">Description</span></span>|
|-|-|
|<span data-ttu-id="9468c-120">ProviderName</span><span class="sxs-lookup"><span data-stu-id="9468c-120">ProviderName</span></span>|<span data-ttu-id="9468c-121">Nombre invariable de proveedor de ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="9468c-121">ADO.NET provider invariant name.</span></span> <span data-ttu-id="9468c-122">Si se establece este argumento, también se debe establecer `ConnectionString`.</span><span class="sxs-lookup"><span data-stu-id="9468c-122">If this argument is set, then the `ConnectionString` must also be set.</span></span>|
|<span data-ttu-id="9468c-123">ConnectionString</span><span class="sxs-lookup"><span data-stu-id="9468c-123">ConnectionString</span></span>|<span data-ttu-id="9468c-124">Cadena de conexión para conectar a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="9468c-124">Connection string to connect to the database.</span></span> <span data-ttu-id="9468c-125">Si se establece este argumento, también se debe establecer `ProviderName`.</span><span class="sxs-lookup"><span data-stu-id="9468c-125">If this argument is set, then `ProviderName` must also be set.</span></span>|
|<span data-ttu-id="9468c-126">ConfigName</span><span class="sxs-lookup"><span data-stu-id="9468c-126">ConfigName</span></span>|<span data-ttu-id="9468c-127">Nombre de la sección de archivo de configuración donde se almacena la información de conexión.</span><span class="sxs-lookup"><span data-stu-id="9468c-127">Name of the configuration file section where the connection information is stored.</span></span> <span data-ttu-id="9468c-128">Cuando se establece este argumento no se requieren `ProviderName` ni `ConnectionString`.</span><span class="sxs-lookup"><span data-stu-id="9468c-128">When this argument is set `ProviderName` and `ConnectionString` are not required.</span></span>|
|<span data-ttu-id="9468c-129">CommandType</span><span class="sxs-lookup"><span data-stu-id="9468c-129">CommandType</span></span>|<span data-ttu-id="9468c-130">Tipo de <xref:System.Data.Common.DbCommand> que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="9468c-130">Type of the <xref:System.Data.Common.DbCommand> to be executed.</span></span>|
|<span data-ttu-id="9468c-131">Sql</span><span class="sxs-lookup"><span data-stu-id="9468c-131">Sql</span></span>|<span data-ttu-id="9468c-132">Comando SQL que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="9468c-132">The SQL command to be executed.</span></span>|
|<span data-ttu-id="9468c-133">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9468c-133">Parameters</span></span>|<span data-ttu-id="9468c-134">Colección de los parámetros de la consulta SQL.</span><span class="sxs-lookup"><span data-stu-id="9468c-134">Collection of the parameters of the SQL query.</span></span>|
|<span data-ttu-id="9468c-135">AffectedRecords</span><span class="sxs-lookup"><span data-stu-id="9468c-135">AffectedRecords</span></span>|<span data-ttu-id="9468c-136">Número de registros afectado por la última operación.</span><span class="sxs-lookup"><span data-stu-id="9468c-136">Number of records affected by the last operation.</span></span>|

## <a name="dbqueryscalar"></a><span data-ttu-id="9468c-137">DbQueryScalar</span><span class="sxs-lookup"><span data-stu-id="9468c-137">DbQueryScalar</span></span>

<span data-ttu-id="9468c-138">Ejecuta una consulta que recupera un único valor de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="9468c-138">Executes a query that retrieves a single value from the database.</span></span>

<span data-ttu-id="9468c-139">Esta clase realiza su trabajo de forma asincrónica (deriva de <xref:System.Activities.AsyncCodeActivity%601> y usa sus capacidades asincrónicas).</span><span class="sxs-lookup"><span data-stu-id="9468c-139">This class performs its work asynchronously (it derives from <xref:System.Activities.AsyncCodeActivity%601> and uses its asynchronous capabilities).</span></span>

<span data-ttu-id="9468c-140">La información de conexión se puede configurar estableciendo un nombre invariable de proveedor (`ProviderName`) y la cadena de conexión (`ConnectionString`) o simplemente utilizando un nombre de configuración de cadena de conexión (`ConfigFileSectionName`) del archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9468c-140">The connection information can be configured by setting a provider invariant name (`ProviderName`) and the connection string (`ConnectionString`) or just using a connection string configuration name (`ConfigFileSectionName`) from the application configuration file.</span></span>

<span data-ttu-id="9468c-141">La consulta que se va a ejecutar se configura en su propiedad `Sql` y los parámetros se pasan a través de la colección `Parameters`.</span><span class="sxs-lookup"><span data-stu-id="9468c-141">The query to be executed is configured in its `Sql` property and the parameters are passed through the `Parameters` collection.</span></span>

<span data-ttu-id="9468c-142">Una vez `DbQueryScalar` ejecutado, el valor escalar se devuelve en el `Result out` argumento (de tipo `TResult` , que se define en la clase base <xref:System.Activities.AsyncCodeActivity%601> ).</span><span class="sxs-lookup"><span data-stu-id="9468c-142">After `DbQueryScalar` is executed, the scalar is returned in the `Result out` argument (of type `TResult`, that is defined in the base class <xref:System.Activities.AsyncCodeActivity%601>).</span></span>

```csharp
public class DbQueryScalar<TResult> : AsyncCodeActivity<TResult>
{
    // public arguments
    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DefaultValue(null)]
    public InArgument<string> ProviderName { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DependsOn("ProviderName")]
    [DefaultValue(null)]
    public InArgument<string> ConnectionString { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConfigFileSectionName")]
    [DefaultValue(null)]
    public InArgument<string> ConfigName { get; set; }

    [DefaultValue(null)]
    public CommandType CommandType { get; set; }

    [RequiredArgument]
    public InArgument<string> Sql { get; set; }

    [DependsOn("Sql")]
    [DefaultValue(null)]
    public IDictionary<string, Argument> Parameters { get; }
}
```

|<span data-ttu-id="9468c-143">Argumento</span><span class="sxs-lookup"><span data-stu-id="9468c-143">Argument</span></span>|<span data-ttu-id="9468c-144">Descripción</span><span class="sxs-lookup"><span data-stu-id="9468c-144">Description</span></span>|
|-|-|
|<span data-ttu-id="9468c-145">ProviderName</span><span class="sxs-lookup"><span data-stu-id="9468c-145">ProviderName</span></span>|<span data-ttu-id="9468c-146">Nombre invariable de proveedor de ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="9468c-146">ADO.NET provider invariant name.</span></span> <span data-ttu-id="9468c-147">Si se establece este argumento, también se debe establecer `ConnectionString`.</span><span class="sxs-lookup"><span data-stu-id="9468c-147">If this argument is set, then the `ConnectionString` must also be set.</span></span>|
|<span data-ttu-id="9468c-148">ConnectionString</span><span class="sxs-lookup"><span data-stu-id="9468c-148">ConnectionString</span></span>|<span data-ttu-id="9468c-149">Cadena de conexión para conectar a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="9468c-149">Connection string to connect to the database.</span></span> <span data-ttu-id="9468c-150">Si se establece este argumento, también se debe establecer `ProviderName`.</span><span class="sxs-lookup"><span data-stu-id="9468c-150">If this argument is set, then `ProviderName` must also be set.</span></span>|
|<span data-ttu-id="9468c-151">ConfigName</span><span class="sxs-lookup"><span data-stu-id="9468c-151">ConfigName</span></span>|<span data-ttu-id="9468c-152">Nombre de la sección de archivo de configuración donde se almacena la información de conexión.</span><span class="sxs-lookup"><span data-stu-id="9468c-152">Name of the configuration file section where the connection information is stored.</span></span> <span data-ttu-id="9468c-153">Cuando se establece este argumento no se requieren `ProviderName` ni `ConnectionString`.</span><span class="sxs-lookup"><span data-stu-id="9468c-153">When this argument is set `ProviderName` and `ConnectionString` are not required.</span></span>|
|<span data-ttu-id="9468c-154">CommandType</span><span class="sxs-lookup"><span data-stu-id="9468c-154">CommandType</span></span>|<span data-ttu-id="9468c-155">Tipo de <xref:System.Data.Common.DbCommand> que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="9468c-155">Type of the <xref:System.Data.Common.DbCommand> to be executed.</span></span>|
|<span data-ttu-id="9468c-156">Sql</span><span class="sxs-lookup"><span data-stu-id="9468c-156">Sql</span></span>|<span data-ttu-id="9468c-157">Comando SQL que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="9468c-157">The SQL command to be executed.</span></span>|
|<span data-ttu-id="9468c-158">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9468c-158">Parameters</span></span>|<span data-ttu-id="9468c-159">Colección de los parámetros de la consulta SQL.</span><span class="sxs-lookup"><span data-stu-id="9468c-159">Collection of the parameters of the SQL query.</span></span>|
|<span data-ttu-id="9468c-160">Resultado</span><span class="sxs-lookup"><span data-stu-id="9468c-160">Result</span></span>|<span data-ttu-id="9468c-161">Valor escalar que se obtiene una vez ejecutada la consulta.</span><span class="sxs-lookup"><span data-stu-id="9468c-161">Scalar that is obtained after the query is executed.</span></span> <span data-ttu-id="9468c-162">Este argumento es de tipo `TResult`.</span><span class="sxs-lookup"><span data-stu-id="9468c-162">This argument is of type `TResult`.</span></span>|

## <a name="dbquery"></a><span data-ttu-id="9468c-163">DbQuery</span><span class="sxs-lookup"><span data-stu-id="9468c-163">DbQuery</span></span>

<span data-ttu-id="9468c-164">Ejecuta una consulta que recupera una lista de objetos.</span><span class="sxs-lookup"><span data-stu-id="9468c-164">Executes a query that retrieves a list of objects.</span></span> <span data-ttu-id="9468c-165">Una vez ejecutada la consulta, se ejecuta una función de asignación (puede ser <xref:System.Func%601> < `DbDataReader` , `TResult`> o un <xref:System.Activities.ActivityFunc%601> < `DbDataReader` `TResult`>).</span><span class="sxs-lookup"><span data-stu-id="9468c-165">After the query is executed, a mapping function is executed (it can be <xref:System.Func%601><`DbDataReader`, `TResult`> or an <xref:System.Activities.ActivityFunc%601><`DbDataReader`, `TResult`>).</span></span> <span data-ttu-id="9468c-166">Esta función de asignación obtiene un registro de `DbDataReader` y lo asigna al objeto que se va a devolver.</span><span class="sxs-lookup"><span data-stu-id="9468c-166">This mapping function gets a record in a `DbDataReader` and maps it to the object to be returned.</span></span>

<span data-ttu-id="9468c-167">La información de conexión se puede configurar estableciendo un nombre invariable de proveedor (`ProviderName`) y la cadena de conexión (`ConnectionString`) o simplemente utilizando un nombre de configuración de cadena de conexión (`ConfigFileSectionName`) del archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9468c-167">The connection information can be configured by setting a provider invariant name (`ProviderName`) and the connection string (`ConnectionString`) or just using a connection string configuration name (`ConfigFileSectionName`) from the application configuration file.</span></span>

<span data-ttu-id="9468c-168">La consulta que se va a ejecutar se configura en su propiedad `Sql` y los parámetros se pasan a través de la colección `Parameters`.</span><span class="sxs-lookup"><span data-stu-id="9468c-168">The query to be executed is configured in its `Sql` property and the parameters are passed through the `Parameters` collection.</span></span>

<span data-ttu-id="9468c-169">Los resultados de la consulta SQL se recuperan utilizando `DbDataReader`.</span><span class="sxs-lookup"><span data-stu-id="9468c-169">The results of the SQL query are retrieved using a `DbDataReader`.</span></span> <span data-ttu-id="9468c-170">La actividad recorre en iteración `DbDataReader` y asigna las filas de `DbDataReader` a una instancia de `TResult`.</span><span class="sxs-lookup"><span data-stu-id="9468c-170">The activity iterates through the `DbDataReader` and maps the rows in the `DbDataReader` to an instance of `TResult`.</span></span> <span data-ttu-id="9468c-171">El usuario de `DbQuery` tiene que proporcionar el código de asignación y esto se puede hacer de dos maneras: mediante <xref:System.Func%601> < `DbDataReader` , `TResult`> o <xref:System.Activities.ActivityFunc%601> < `DbDataReader` , `TResult`>.</span><span class="sxs-lookup"><span data-stu-id="9468c-171">The user of `DbQuery` has to provide the mapping code and this can be done in two ways: using a <xref:System.Func%601><`DbDataReader`, `TResult`> or an <xref:System.Activities.ActivityFunc%601><`DbDataReader`, `TResult`>.</span></span> <span data-ttu-id="9468c-172">En el primer caso, la asignación se realiza en un pulso único de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9468c-172">In the first case, the map is done in a single pulse of execution.</span></span> <span data-ttu-id="9468c-173">Por tanto, es más rápida, pero esto no se puede serializar en XAML.</span><span class="sxs-lookup"><span data-stu-id="9468c-173">Therefore, it is faster, but this cannot be serialized to XAML.</span></span> <span data-ttu-id="9468c-174">En el último caso, la asignación se realiza en varios pulsos.</span><span class="sxs-lookup"><span data-stu-id="9468c-174">In the last case, the map is performed in multiple pulses.</span></span> <span data-ttu-id="9468c-175">Por tanto, puede ser más lenta pero se serializar en XAML y crear mediante declaración (cualquier actividad existente puede participar en la asignación).</span><span class="sxs-lookup"><span data-stu-id="9468c-175">Therefore, it might be slower but can be serialized to XAML and authored declaratively (any existing activity can participate in the mapping).</span></span>

```csharp
public class DbQuery<TResult> : AsyncCodeActivity<IList<TResult>> where TResult : class
{
    // public arguments
    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DefaultValue(null)]
    public InArgument<string> ProviderName { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DependsOn("ProviderName")]
    [DefaultValue(null)]
    public InArgument<string> ConnectionString { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConfigFileSectionName")]
    [DefaultValue(null)]
    public InArgument<string> ConfigName { get; set; }

    [DefaultValue(null)]
    public CommandType CommandType { get; set; }

    [RequiredArgument]
    public InArgument<string> Sql { get; set; }

    [DependsOn("Sql")]
    [DefaultValue(null)]
    public IDictionary<string, Argument> Parameters { get; }

    [OverloadGroup("DirectMapping")]
    [DefaultValue(null)]
    public Func<DbDataReader, TResult> Mapper { get; set; }

    [OverloadGroup("MultiplePulseMapping")]
    [DefaultValue(null)]
    public ActivityFunc<DbDataReader, TResult> MapperFunc { get; set; }
}
```

|<span data-ttu-id="9468c-176">Argumento</span><span class="sxs-lookup"><span data-stu-id="9468c-176">Argument</span></span>|<span data-ttu-id="9468c-177">Descripción</span><span class="sxs-lookup"><span data-stu-id="9468c-177">Description</span></span>|
|-|-|
|<span data-ttu-id="9468c-178">ProviderName</span><span class="sxs-lookup"><span data-stu-id="9468c-178">ProviderName</span></span>|<span data-ttu-id="9468c-179">Nombre invariable de proveedor de ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="9468c-179">ADO.NET provider invariant name.</span></span> <span data-ttu-id="9468c-180">Si se establece este argumento, también se debe establecer `ConnectionString`.</span><span class="sxs-lookup"><span data-stu-id="9468c-180">If this argument is set, then the `ConnectionString` must also be set.</span></span>|
|<span data-ttu-id="9468c-181">ConnectionString</span><span class="sxs-lookup"><span data-stu-id="9468c-181">ConnectionString</span></span>|<span data-ttu-id="9468c-182">Cadena de conexión para conectar a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="9468c-182">Connection string to connect to the database.</span></span> <span data-ttu-id="9468c-183">Si se establece este argumento, también se debe establecer `ProviderName`.</span><span class="sxs-lookup"><span data-stu-id="9468c-183">If this argument is set, then `ProviderName` must also be set.</span></span>|
|<span data-ttu-id="9468c-184">ConfigName</span><span class="sxs-lookup"><span data-stu-id="9468c-184">ConfigName</span></span>|<span data-ttu-id="9468c-185">Nombre de la sección de archivo de configuración donde se almacena la información de conexión.</span><span class="sxs-lookup"><span data-stu-id="9468c-185">Name of the configuration file section where the connection information is stored.</span></span> <span data-ttu-id="9468c-186">Cuando se establece este argumento no se requieren `ProviderName` ni `ConnectionString`.</span><span class="sxs-lookup"><span data-stu-id="9468c-186">When this argument is set `ProviderName` and `ConnectionString` are not required.</span></span>|
|<span data-ttu-id="9468c-187">CommandType</span><span class="sxs-lookup"><span data-stu-id="9468c-187">CommandType</span></span>|<span data-ttu-id="9468c-188">Tipo de <xref:System.Data.Common.DbCommand> que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="9468c-188">Type of the <xref:System.Data.Common.DbCommand> to be executed.</span></span>|
|<span data-ttu-id="9468c-189">Sql</span><span class="sxs-lookup"><span data-stu-id="9468c-189">Sql</span></span>|<span data-ttu-id="9468c-190">Comando SQL que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="9468c-190">The SQL command to be executed.</span></span>|
|<span data-ttu-id="9468c-191">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9468c-191">Parameters</span></span>|<span data-ttu-id="9468c-192">Colección de los parámetros de la consulta SQL.</span><span class="sxs-lookup"><span data-stu-id="9468c-192">Collection of the parameters of the SQL query.</span></span>|
|<span data-ttu-id="9468c-193">Mapper</span><span class="sxs-lookup"><span data-stu-id="9468c-193">Mapper</span></span>|<span data-ttu-id="9468c-194">Función de asignación ( <xref:System.Func%601> < `DbDataReader` , `TResult`>) que toma un registro en el `DataReader` obtenido como resultado de la ejecución de la consulta y devuelve una instancia de un objeto de tipo `TResult` que se va a agregar a la `Result` colección.</span><span class="sxs-lookup"><span data-stu-id="9468c-194">Mapping function (<xref:System.Func%601><`DbDataReader`, `TResult`>) that takes a record in the `DataReader` obtained as result of executing the query and returns an instance of an object of type `TResult` to be added to the `Result` collection.</span></span><br /><br /> <span data-ttu-id="9468c-195">En este caso, la asignación se realiza mediante un único pulso de ejecución, pero no se puede crear mediante declaración utilizando el diseñador.</span><span class="sxs-lookup"><span data-stu-id="9468c-195">In this case, mapping is done in a single pulse of execution, but it cannot be authored declaratively using the designer.</span></span>|
|<span data-ttu-id="9468c-196">MapperFunc</span><span class="sxs-lookup"><span data-stu-id="9468c-196">MapperFunc</span></span>|<span data-ttu-id="9468c-197">Función de asignación ( <xref:System.Activities.ActivityFunc%601> < `DbDataReader` , `TResult`>) que toma un registro en el `DataReader` obtenido como resultado de la ejecución de la consulta y devuelve una instancia de un objeto de tipo `TResult` que se va a agregar a la `Result` colección.</span><span class="sxs-lookup"><span data-stu-id="9468c-197">Mapping function (<xref:System.Activities.ActivityFunc%601><`DbDataReader`, `TResult`>) that takes a record in the `DataReader` obtained as result of executing the query and returns an instance of an object of type `TResult` to be added to the `Result` collection.</span></span><br /><br /> <span data-ttu-id="9468c-198">En este caso, la asignación se realiza en varios pulsos de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9468c-198">In this case, the mapping is done in multiple pulses of execution.</span></span> <span data-ttu-id="9468c-199">Esta función se puede serializar en XAML y crear mediante declaración (cualquier actividad existente puede participar en la asignación).</span><span class="sxs-lookup"><span data-stu-id="9468c-199">This function can be serialized to XAML and authored declaratively (any existing activity can participate in the mapping).</span></span>|
|<span data-ttu-id="9468c-200">Resultado</span><span class="sxs-lookup"><span data-stu-id="9468c-200">Result</span></span>|<span data-ttu-id="9468c-201">Lista de objetos obtenidos como resultado de ejecutar la consulta y ejecutar la función de asignación para cada registro de `DataReader`.</span><span class="sxs-lookup"><span data-stu-id="9468c-201">List of objects obtained as result of executing the query and executing the mapping function for each record in the `DataReader`.</span></span>|

## <a name="dbquerydataset"></a><span data-ttu-id="9468c-202">DbQueryDataSet</span><span class="sxs-lookup"><span data-stu-id="9468c-202">DbQueryDataSet</span></span>

<span data-ttu-id="9468c-203">Ejecuta una consulta que devuelve una clase <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="9468c-203">Executes a query that returns a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="9468c-204">Esta clase realiza su trabajo de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="9468c-204">This class performs its work asynchronously.</span></span> <span data-ttu-id="9468c-205">Deriva de <xref:System.Activities.AsyncCodeActivity> < `TResult`> y utiliza sus capacidades asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="9468c-205">It derives from <xref:System.Activities.AsyncCodeActivity><`TResult`> and uses its asynchronous capabilities.</span></span>

<span data-ttu-id="9468c-206">La información de conexión se puede configurar estableciendo un nombre invariable de proveedor (`ProviderName`) y la cadena de conexión (`ConnectionString`) o simplemente utilizando un nombre de configuración de cadena de conexión (`ConfigFileSectionName`) del archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9468c-206">The connection information can be configured by setting a provider invariant name (`ProviderName`) and the connection string (`ConnectionString`) or just using a connection string configuration name (`ConfigFileSectionName`) from the application configuration file.</span></span>

<span data-ttu-id="9468c-207">La consulta que se va a ejecutar se configura en su propiedad `Sql` y los parámetros se pasan a través de la colección `Parameters`.</span><span class="sxs-lookup"><span data-stu-id="9468c-207">The query to be executed is configured in its `Sql` property and the parameters are passed through the `Parameters` collection.</span></span>

<span data-ttu-id="9468c-208">Una vez `DbQueryDataSet` que se ejecuta `DataSet` , se devuelve en el `Result out` argumento (de tipo `TResult` , que se define en la clase base <xref:System.Activities.AsyncCodeActivity%601> ).</span><span class="sxs-lookup"><span data-stu-id="9468c-208">After the `DbQueryDataSet` is executed the `DataSet` is returned in the `Result out` argument (of type `TResult`, that is defined in the base class <xref:System.Activities.AsyncCodeActivity%601>).</span></span>

```csharp
public class DbQueryDataSet : AsyncCodeActivity<DataSet>
{
    // public arguments
    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DefaultValue(null)]
    public InArgument<string> ProviderName { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DependsOn("ProviderName")]
    [DefaultValue(null)]
    public InArgument<string> ConnectionString { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConfigFileSectionName")]
    [DefaultValue(null)]
    public InArgument<string> ConfigName { get; set; }

    [DefaultValue(null)]
    public CommandType CommandType { get; set; }

    [RequiredArgument]
    public InArgument<string> Sql { get; set; }

    [DependsOn("Sql")]
    [DefaultValue(null)]
    public IDictionary<string, Argument> Parameters { get; }
}
```

|<span data-ttu-id="9468c-209">Argumento</span><span class="sxs-lookup"><span data-stu-id="9468c-209">Argument</span></span>|<span data-ttu-id="9468c-210">Descripción</span><span class="sxs-lookup"><span data-stu-id="9468c-210">Description</span></span>|
|-|-|
|<span data-ttu-id="9468c-211">ProviderName</span><span class="sxs-lookup"><span data-stu-id="9468c-211">ProviderName</span></span>|<span data-ttu-id="9468c-212">Nombre invariable de proveedor de ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="9468c-212">ADO.NET provider invariant name.</span></span> <span data-ttu-id="9468c-213">Si se establece este argumento, también se debe establecer `ConnectionString`.</span><span class="sxs-lookup"><span data-stu-id="9468c-213">If this argument is set, then the `ConnectionString` must also be set.</span></span>|
|<span data-ttu-id="9468c-214">ConnectionString</span><span class="sxs-lookup"><span data-stu-id="9468c-214">ConnectionString</span></span>|<span data-ttu-id="9468c-215">Cadena de conexión para conectar a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="9468c-215">Connection string to connect to the database.</span></span> <span data-ttu-id="9468c-216">Si se establece este argumento, también se debe establecer `ProviderName`.</span><span class="sxs-lookup"><span data-stu-id="9468c-216">If this argument is set, then `ProviderName` must also be set.</span></span>|
|<span data-ttu-id="9468c-217">ConfigName</span><span class="sxs-lookup"><span data-stu-id="9468c-217">ConfigName</span></span>|<span data-ttu-id="9468c-218">Nombre de la sección de archivo de configuración donde se almacena la información de conexión.</span><span class="sxs-lookup"><span data-stu-id="9468c-218">Name of the configuration file section where the connection information is stored.</span></span> <span data-ttu-id="9468c-219">Cuando se establece este argumento no se requieren `ProviderName` ni `ConnectionString`.</span><span class="sxs-lookup"><span data-stu-id="9468c-219">When this argument is set `ProviderName` and `ConnectionString` are not required.</span></span>|
|<span data-ttu-id="9468c-220">CommandType</span><span class="sxs-lookup"><span data-stu-id="9468c-220">CommandType</span></span>|<span data-ttu-id="9468c-221">Tipo de <xref:System.Data.Common.DbCommand> que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="9468c-221">Type of the <xref:System.Data.Common.DbCommand> to be executed.</span></span>|
|<span data-ttu-id="9468c-222">Sql</span><span class="sxs-lookup"><span data-stu-id="9468c-222">Sql</span></span>|<span data-ttu-id="9468c-223">Comando SQL que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="9468c-223">The SQL command to be executed.</span></span>|
|<span data-ttu-id="9468c-224">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9468c-224">Parameters</span></span>|<span data-ttu-id="9468c-225">Colección de los parámetros de la consulta SQL.</span><span class="sxs-lookup"><span data-stu-id="9468c-225">Collection of the parameters of the SQL query.</span></span>|
|<span data-ttu-id="9468c-226">Resultado</span><span class="sxs-lookup"><span data-stu-id="9468c-226">Result</span></span>|<span data-ttu-id="9468c-227"><xref:System.Data.DataSet> que se obtiene una vez ejecutada la consulta.</span><span class="sxs-lookup"><span data-stu-id="9468c-227"><xref:System.Data.DataSet> that is obtained after the query is executed.</span></span>|

## <a name="configuring-connection-information"></a><span data-ttu-id="9468c-228">Configurar información de conexión</span><span class="sxs-lookup"><span data-stu-id="9468c-228">Configuring Connection Information</span></span>

<span data-ttu-id="9468c-229">Todas las actividades de base de datos comparten los mismos parámetros de configuración.</span><span class="sxs-lookup"><span data-stu-id="9468c-229">All DbActivities share the same configuration parameters.</span></span> <span data-ttu-id="9468c-230">Se pueden configurar de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="9468c-230">They can be configured in two ways:</span></span>

- <span data-ttu-id="9468c-231">`ConnectionString + InvariantName`: establezca el nombre invariable de proveedor de ADO.NET y la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="9468c-231">`ConnectionString + InvariantName`: Set the ADO.NET provider invariant name and connection string.</span></span>

  ```csharp
  Activity dbSelectCount = new DbQueryScalar<DateTime>()
  {
      ProviderName = "System.Data.SqlClient",
      ConnectionString = @"Data Source=.\SQLExpress;
                            Initial Catalog=DbActivitiesSample;
                            Integrated Security=True",
      Sql = "SELECT GetDate()"
  };
  ```

- <span data-ttu-id="9468c-232">`ConfigName`: establezca el nombre de la sección de configuración que contiene la información de conexión.</span><span class="sxs-lookup"><span data-stu-id="9468c-232">`ConfigName`: Set the name of the configuration section that contains the connection information.</span></span>

  ```xml
  <connectionStrings>
      <add name="DbActivitiesSample"
            providerName="System.Data.SqlClient"
            connectionString="Data Source=.\SQLExpress;Initial Catalog=DbActivitiesSample;Integrated Security=true"/>
    </connectionStrings>
  ```

- <span data-ttu-id="9468c-233">En la actividad:</span><span class="sxs-lookup"><span data-stu-id="9468c-233">In the activity:</span></span>

  ```csharp
  Activity dbSelectCount = new DbQueryScalar<int>()
  {
      ConfigName = "DbActivitiesSample",
      Sql = "SELECT COUNT(*) FROM Roles"
  };
  ```

## <a name="running-this-sample"></a><span data-ttu-id="9468c-234">Ejecutar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="9468c-234">Running this sample</span></span>

### <a name="setup-instructions"></a><span data-ttu-id="9468c-235">Instrucciones de instalación</span><span class="sxs-lookup"><span data-stu-id="9468c-235">Setup instructions</span></span>

<span data-ttu-id="9468c-236">En este ejemplo se utiliza una base de datos.</span><span class="sxs-lookup"><span data-stu-id="9468c-236">This sample uses a database.</span></span> <span data-ttu-id="9468c-237">Con el ejemplo se proporciona un script de instalación y carga (Setup.cmd).</span><span class="sxs-lookup"><span data-stu-id="9468c-237">A set-up and load script (Setup.cmd) is provided with the sample.</span></span> <span data-ttu-id="9468c-238">Debe ejecutar ese archivo mediante el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="9468c-238">You must execute that file using the command prompt.</span></span>

<span data-ttu-id="9468c-239">El script Setup.cmd invoca el archivo de script CreateDb.sql, que contiene comandos SQL con los que realiza lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9468c-239">The Setup.cmd script invokes the CreateDb.sql script file, which contains SQL commands that do the following:</span></span>

- <span data-ttu-id="9468c-240">Crea una base de datos llamada DbActivitiesSample.</span><span class="sxs-lookup"><span data-stu-id="9468c-240">Creates a database called DbActivitiesSample.</span></span>

- <span data-ttu-id="9468c-241">Crea la tabla Roles.</span><span class="sxs-lookup"><span data-stu-id="9468c-241">Creates the Roles table.</span></span>

- <span data-ttu-id="9468c-242">Crea la tabla Employees.</span><span class="sxs-lookup"><span data-stu-id="9468c-242">Creates Employees table.</span></span>

- <span data-ttu-id="9468c-243">Inserta tres registros en la tabla Roles.</span><span class="sxs-lookup"><span data-stu-id="9468c-243">Inserts three records into the Roles table.</span></span>

- <span data-ttu-id="9468c-244">Inserta doce registros en la tabla Employees.</span><span class="sxs-lookup"><span data-stu-id="9468c-244">Inserts twelve records into the Employees table.</span></span>

##### <a name="to-run-setupcmd"></a><span data-ttu-id="9468c-245">Para ejecutar Setup.cmd</span><span class="sxs-lookup"><span data-stu-id="9468c-245">To run Setup.cmd</span></span>

1. <span data-ttu-id="9468c-246">Abra un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="9468c-246">Open a command prompt.</span></span>

2. <span data-ttu-id="9468c-247">Vaya a la carpeta de ejemplo DbActivities.</span><span class="sxs-lookup"><span data-stu-id="9468c-247">Go to the DbActivities sample folder.</span></span>

3. <span data-ttu-id="9468c-248">Escriba "Setup. cmd" y presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="9468c-248">Type "setup.cmd" and press ENTER.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9468c-249">Setup.cmd intenta instalar el ejemplo en la instancia de SqlExpress del equipo local.</span><span class="sxs-lookup"><span data-stu-id="9468c-249">Setup.cmd attempts to install the sample in your local machine SqlExpress instance.</span></span> <span data-ttu-id="9468c-250">Si desea instalarlo en otra instancia de SQL Server, modifique Setup.cmd con el nombre de la nueva instancia.</span><span class="sxs-lookup"><span data-stu-id="9468c-250">If you want to install it in other SQL server instance, edit Setup.cmd with the new instance name.</span></span>

##### <a name="to-uninstall-the-sample-database"></a><span data-ttu-id="9468c-251">Para desinstalar la base de datos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="9468c-251">To uninstall the sample database</span></span>

1. <span data-ttu-id="9468c-252">Ejecute Cleanup.cmd desde la carpeta de ejemplo en un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="9468c-252">Run Cleanup.cmd from the sample folder in a command prompt.</span></span>

##### <a name="to-run-the-sample"></a><span data-ttu-id="9468c-253">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="9468c-253">To run the sample</span></span>

1. <span data-ttu-id="9468c-254">Abra la solución en Visual Studio 2010</span><span class="sxs-lookup"><span data-stu-id="9468c-254">Open the solution in Visual Studio 2010</span></span>

2. <span data-ttu-id="9468c-255">Para compilar la solución, presione Ctrl+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="9468c-255">To compile the solution, press CTRL+SHIFT+B.</span></span>

3. <span data-ttu-id="9468c-256">Para ejecutar el ejemplo sin depurar, presione CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="9468c-256">To run the sample without debugging, press CTRL+F5.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9468c-257">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="9468c-257">The samples may already be installed on your machine.</span></span> <span data-ttu-id="9468c-258">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="9468c-258">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="9468c-259">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="9468c-259">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="9468c-260">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="9468c-260">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\DbActivities`
