---
title: Actividades de acceso a bases de datos
ms.date: 03/30/2017
ms.assetid: 174a381e-1343-46a8-a62c-7c2ae2c4f0b2
ms.openlocfilehash: ed3f0ad3f2fd19f622c9cb0faf7d5cd864b81995
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094649"
---
# <a name="database-access-activities"></a><span data-ttu-id="b8cc3-102">Actividades de acceso a bases de datos</span><span class="sxs-lookup"><span data-stu-id="b8cc3-102">Database Access Activities</span></span>

<span data-ttu-id="b8cc3-103">Las actividades de acceso a bases de datos permiten tener acceso a una base de datos dentro de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-103">Database access activities allow you to access a database within a workflow.</span></span> <span data-ttu-id="b8cc3-104">Estas actividades permiten tener acceso a las bases de datos para recuperar o modificar información y usar [ADO.net](../../data/adonet/index.md) para tener acceso a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-104">These activities allow accessing databases to retrieve or modify information and use [ADO.NET](../../data/adonet/index.md) to access the database.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b8cc3-105">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-105">The samples may already be installed on your machine.</span></span> <span data-ttu-id="b8cc3-106">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-106">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="b8cc3-107">Si este directorio no existe, vaya a (página de descarga) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b8cc3-107">If this directory does not exist, go to (download page) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b8cc3-108">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-108">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\DbActivities`

## <a name="database-activities"></a><span data-ttu-id="b8cc3-109">Actividades de base de datos</span><span class="sxs-lookup"><span data-stu-id="b8cc3-109">Database Activities</span></span>

<span data-ttu-id="b8cc3-110">En las siguientes secciones se detalla la lista de actividades incluidas en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-110">The following sections detail the list of activities included in this sample.</span></span>

## <a name="dbupdate"></a><span data-ttu-id="b8cc3-111">DbUpdate</span><span class="sxs-lookup"><span data-stu-id="b8cc3-111">DbUpdate</span></span>

<span data-ttu-id="b8cc3-112">Ejecuta una consulta SQL que genera una modificación en la base de datos (inserción, actualización, eliminación y otras modificaciones).</span><span class="sxs-lookup"><span data-stu-id="b8cc3-112">Executes a SQL query that produces a modification in the database (insert, update, delete, and other modifications).</span></span>

<span data-ttu-id="b8cc3-113">Esta clase realiza su trabajo de forma asincrónica (deriva de <xref:System.Activities.AsyncCodeActivity> y usa sus capacidades asincrónicas).</span><span class="sxs-lookup"><span data-stu-id="b8cc3-113">This class performs its work asynchronously (it derives from <xref:System.Activities.AsyncCodeActivity> and uses its asynchronous capabilities).</span></span>

<span data-ttu-id="b8cc3-114">La información de conexión se puede configurar estableciendo un nombre invariable de proveedor (`ProviderName`) y la cadena de conexión (`ConnectionString`) o simplemente utilizando un nombre de configuración de cadena de conexión (`ConfigFileSectionName`) del archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-114">The connection information can be configured by setting a provider invariant name (`ProviderName`) and the connection string (`ConnectionString`) or just using a connection string configuration name (`ConfigFileSectionName`) from the application configuration file.</span></span>

<span data-ttu-id="b8cc3-115">La consulta que se va a ejecutar se configura en su propiedad `Sql` y los parámetros se pasan a través de la colección `Parameters`.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-115">The query to be executed is configured in its `Sql` property and the parameters are passed through the `Parameters` collection.</span></span>

<span data-ttu-id="b8cc3-116">Una vez ejecutado `DbUpdate`, el número de registros afectado se devuelve en la propiedad `AffectedRecords`.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-116">After `DbUpdate` is executed, the number of affected records is returned in the `AffectedRecords` property.</span></span>

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

|<span data-ttu-id="b8cc3-117">Argumento</span><span class="sxs-lookup"><span data-stu-id="b8cc3-117">Argument</span></span>|<span data-ttu-id="b8cc3-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="b8cc3-118">Description</span></span>|
|-|-|
|<span data-ttu-id="b8cc3-119">ProviderName</span><span class="sxs-lookup"><span data-stu-id="b8cc3-119">ProviderName</span></span>|<span data-ttu-id="b8cc3-120">Nombre invariable de proveedor de ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-120">ADO.NET provider invariant name.</span></span> <span data-ttu-id="b8cc3-121">Si se establece este argumento, también se debe establecer `ConnectionString`.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-121">If this argument is set, then the `ConnectionString` must also be set.</span></span>|
|<span data-ttu-id="b8cc3-122">ConnectionString</span><span class="sxs-lookup"><span data-stu-id="b8cc3-122">ConnectionString</span></span>|<span data-ttu-id="b8cc3-123">Cadena de conexión para conectar a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-123">Connection string to connect to the database.</span></span> <span data-ttu-id="b8cc3-124">Si se establece este argumento, también se debe establecer `ProviderName`.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-124">If this argument is set, then `ProviderName` must also be set.</span></span>|
|<span data-ttu-id="b8cc3-125">ConfigName</span><span class="sxs-lookup"><span data-stu-id="b8cc3-125">ConfigName</span></span>|<span data-ttu-id="b8cc3-126">Nombre de la sección de archivo de configuración donde se almacena la información de conexión.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-126">Name of the configuration file section where the connection information is stored.</span></span> <span data-ttu-id="b8cc3-127">Cuando se establece este argumento no se requieren `ProviderName` ni `ConnectionString`.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-127">When this argument is set `ProviderName` and `ConnectionString` are not required.</span></span>|
|<span data-ttu-id="b8cc3-128">CommandType</span><span class="sxs-lookup"><span data-stu-id="b8cc3-128">CommandType</span></span>|<span data-ttu-id="b8cc3-129">Tipo de <xref:System.Data.Common.DbCommand> que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-129">Type of the <xref:System.Data.Common.DbCommand> to be executed.</span></span>|
|<span data-ttu-id="b8cc3-130">Sql</span><span class="sxs-lookup"><span data-stu-id="b8cc3-130">Sql</span></span>|<span data-ttu-id="b8cc3-131">Comando SQL que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-131">The SQL command to be executed.</span></span>|
|<span data-ttu-id="b8cc3-132">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b8cc3-132">Parameters</span></span>|<span data-ttu-id="b8cc3-133">Colección de los parámetros de la consulta SQL.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-133">Collection of the parameters of the SQL query.</span></span>|
|<span data-ttu-id="b8cc3-134">AffectedRecords</span><span class="sxs-lookup"><span data-stu-id="b8cc3-134">AffectedRecords</span></span>|<span data-ttu-id="b8cc3-135">Número de registros afectado por la última operación.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-135">Number of records affected by the last operation.</span></span>|

## <a name="dbqueryscalar"></a><span data-ttu-id="b8cc3-136">DbQueryScalar</span><span class="sxs-lookup"><span data-stu-id="b8cc3-136">DbQueryScalar</span></span>

<span data-ttu-id="b8cc3-137">Ejecuta una consulta que recupera un único valor de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-137">Executes a query that retrieves a single value from the database.</span></span>

<span data-ttu-id="b8cc3-138">Esta clase realiza su trabajo de forma asincrónica (deriva de <xref:System.Activities.AsyncCodeActivity%601> y usa sus capacidades asincrónicas).</span><span class="sxs-lookup"><span data-stu-id="b8cc3-138">This class performs its work asynchronously (it derives from <xref:System.Activities.AsyncCodeActivity%601> and uses its asynchronous capabilities).</span></span>

<span data-ttu-id="b8cc3-139">La información de conexión se puede configurar estableciendo un nombre invariable de proveedor (`ProviderName`) y la cadena de conexión (`ConnectionString`) o simplemente utilizando un nombre de configuración de cadena de conexión (`ConfigFileSectionName`) del archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-139">The connection information can be configured by setting a provider invariant name (`ProviderName`) and the connection string (`ConnectionString`) or just using a connection string configuration name (`ConfigFileSectionName`) from the application configuration file.</span></span>

<span data-ttu-id="b8cc3-140">La consulta que se va a ejecutar se configura en su propiedad `Sql` y los parámetros se pasan a través de la colección `Parameters`.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-140">The query to be executed is configured in its `Sql` property and the parameters are passed through the `Parameters` collection.</span></span>

<span data-ttu-id="b8cc3-141">Una vez ejecutada la `DbQueryScalar`, el valor escalar se devuelve en el `Result out` argumento (de tipo `TResult`, que se define en la clase base <xref:System.Activities.AsyncCodeActivity%601>).</span><span class="sxs-lookup"><span data-stu-id="b8cc3-141">After `DbQueryScalar` is executed, the scalar is returned in the `Result out` argument (of type `TResult`, that is defined in the base class <xref:System.Activities.AsyncCodeActivity%601>).</span></span>

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

|<span data-ttu-id="b8cc3-142">Argumento</span><span class="sxs-lookup"><span data-stu-id="b8cc3-142">Argument</span></span>|<span data-ttu-id="b8cc3-143">Descripción</span><span class="sxs-lookup"><span data-stu-id="b8cc3-143">Description</span></span>|
|-|-|
|<span data-ttu-id="b8cc3-144">ProviderName</span><span class="sxs-lookup"><span data-stu-id="b8cc3-144">ProviderName</span></span>|<span data-ttu-id="b8cc3-145">Nombre invariable de proveedor de ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-145">ADO.NET provider invariant name.</span></span> <span data-ttu-id="b8cc3-146">Si se establece este argumento, también se debe establecer `ConnectionString`.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-146">If this argument is set, then the `ConnectionString` must also be set.</span></span>|
|<span data-ttu-id="b8cc3-147">ConnectionString</span><span class="sxs-lookup"><span data-stu-id="b8cc3-147">ConnectionString</span></span>|<span data-ttu-id="b8cc3-148">Cadena de conexión para conectar a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-148">Connection string to connect to the database.</span></span> <span data-ttu-id="b8cc3-149">Si se establece este argumento, también se debe establecer `ProviderName`.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-149">If this argument is set, then `ProviderName` must also be set.</span></span>|
|<span data-ttu-id="b8cc3-150">ConfigName</span><span class="sxs-lookup"><span data-stu-id="b8cc3-150">ConfigName</span></span>|<span data-ttu-id="b8cc3-151">Nombre de la sección de archivo de configuración donde se almacena la información de conexión.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-151">Name of the configuration file section where the connection information is stored.</span></span> <span data-ttu-id="b8cc3-152">Cuando se establece este argumento no se requieren `ProviderName` ni `ConnectionString`.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-152">When this argument is set `ProviderName` and `ConnectionString` are not required.</span></span>|
|<span data-ttu-id="b8cc3-153">CommandType</span><span class="sxs-lookup"><span data-stu-id="b8cc3-153">CommandType</span></span>|<span data-ttu-id="b8cc3-154">Tipo de <xref:System.Data.Common.DbCommand> que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-154">Type of the <xref:System.Data.Common.DbCommand> to be executed.</span></span>|
|<span data-ttu-id="b8cc3-155">Sql</span><span class="sxs-lookup"><span data-stu-id="b8cc3-155">Sql</span></span>|<span data-ttu-id="b8cc3-156">Comando SQL que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-156">The SQL command to be executed.</span></span>|
|<span data-ttu-id="b8cc3-157">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b8cc3-157">Parameters</span></span>|<span data-ttu-id="b8cc3-158">Colección de los parámetros de la consulta SQL.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-158">Collection of the parameters of the SQL query.</span></span>|
|<span data-ttu-id="b8cc3-159">Resultado</span><span class="sxs-lookup"><span data-stu-id="b8cc3-159">Result</span></span>|<span data-ttu-id="b8cc3-160">Valor escalar que se obtiene una vez ejecutada la consulta.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-160">Scalar that is obtained after the query is executed.</span></span> <span data-ttu-id="b8cc3-161">Este argumento es de tipo `TResult`.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-161">This argument is of type `TResult`.</span></span>|

## <a name="dbquery"></a><span data-ttu-id="b8cc3-162">DbQuery</span><span class="sxs-lookup"><span data-stu-id="b8cc3-162">DbQuery</span></span>

<span data-ttu-id="b8cc3-163">Ejecuta una consulta que recupera una lista de objetos.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-163">Executes a query that retrieves a list of objects.</span></span> <span data-ttu-id="b8cc3-164">Una vez ejecutada la consulta, se ejecuta una función de asignación (puede ser <xref:System.Func%601><`DbDataReader`, `TResult`> o <xref:System.Activities.ActivityFunc%601><`DbDataReader``TResult`>).</span><span class="sxs-lookup"><span data-stu-id="b8cc3-164">After the query is executed, a mapping function is executed (it can be <xref:System.Func%601><`DbDataReader`, `TResult`> or an <xref:System.Activities.ActivityFunc%601><`DbDataReader`, `TResult`>).</span></span> <span data-ttu-id="b8cc3-165">Esta función de asignación obtiene un registro de `DbDataReader` y lo asigna al objeto que se va a devolver.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-165">This mapping function gets a record in a `DbDataReader` and maps it to the object to be returned.</span></span>

<span data-ttu-id="b8cc3-166">La información de conexión se puede configurar estableciendo un nombre invariable de proveedor (`ProviderName`) y la cadena de conexión (`ConnectionString`) o simplemente utilizando un nombre de configuración de cadena de conexión (`ConfigFileSectionName`) del archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-166">The connection information can be configured by setting a provider invariant name (`ProviderName`) and the connection string (`ConnectionString`) or just using a connection string configuration name (`ConfigFileSectionName`) from the application configuration file.</span></span>

<span data-ttu-id="b8cc3-167">La consulta que se va a ejecutar se configura en su propiedad `Sql` y los parámetros se pasan a través de la colección `Parameters`.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-167">The query to be executed is configured in its `Sql` property and the parameters are passed through the `Parameters` collection.</span></span>

<span data-ttu-id="b8cc3-168">Los resultados de la consulta SQL se recuperan utilizando `DbDataReader`.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-168">The results of the SQL query are retrieved using a `DbDataReader`.</span></span> <span data-ttu-id="b8cc3-169">La actividad recorre en iteración `DbDataReader` y asigna las filas de `DbDataReader` a una instancia de `TResult`.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-169">The activity iterates through the `DbDataReader` and maps the rows in the `DbDataReader` to an instance of `TResult`.</span></span> <span data-ttu-id="b8cc3-170">El usuario de `DbQuery` tiene que proporcionar el código de asignación y esto puede realizarse de dos maneras: mediante un <xref:System.Func%601><`DbDataReader`, `TResult`> o un <xref:System.Activities.ActivityFunc%601><`DbDataReader`, `TResult`>.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-170">The user of `DbQuery` has to provide the mapping code and this can be done in two ways: using a <xref:System.Func%601><`DbDataReader`, `TResult`> or an <xref:System.Activities.ActivityFunc%601><`DbDataReader`, `TResult`>.</span></span> <span data-ttu-id="b8cc3-171">En el primer caso, la asignación se realiza en un pulso único de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-171">In the first case, the map is done in a single pulse of execution.</span></span> <span data-ttu-id="b8cc3-172">Por tanto, es más rápida, pero esto no se puede serializar en XAML.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-172">Therefore, it is faster, but this cannot be serialized to XAML.</span></span> <span data-ttu-id="b8cc3-173">En el último caso, la asignación se realiza en varios pulsos.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-173">In the last case, the map is performed in multiple pulses.</span></span> <span data-ttu-id="b8cc3-174">Por tanto, puede ser más lenta pero se serializar en XAML y crear mediante declaración (cualquier actividad existente puede participar en la asignación).</span><span class="sxs-lookup"><span data-stu-id="b8cc3-174">Therefore, it might be slower but can be serialized to XAML and authored declaratively (any existing activity can participate in the mapping).</span></span>

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

|<span data-ttu-id="b8cc3-175">Argumento</span><span class="sxs-lookup"><span data-stu-id="b8cc3-175">Argument</span></span>|<span data-ttu-id="b8cc3-176">Descripción</span><span class="sxs-lookup"><span data-stu-id="b8cc3-176">Description</span></span>|
|-|-|
|<span data-ttu-id="b8cc3-177">ProviderName</span><span class="sxs-lookup"><span data-stu-id="b8cc3-177">ProviderName</span></span>|<span data-ttu-id="b8cc3-178">Nombre invariable de proveedor de ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-178">ADO.NET provider invariant name.</span></span> <span data-ttu-id="b8cc3-179">Si se establece este argumento, también se debe establecer `ConnectionString`.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-179">If this argument is set, then the `ConnectionString` must also be set.</span></span>|
|<span data-ttu-id="b8cc3-180">ConnectionString</span><span class="sxs-lookup"><span data-stu-id="b8cc3-180">ConnectionString</span></span>|<span data-ttu-id="b8cc3-181">Cadena de conexión para conectar a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-181">Connection string to connect to the database.</span></span> <span data-ttu-id="b8cc3-182">Si se establece este argumento, también se debe establecer `ProviderName`.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-182">If this argument is set, then `ProviderName` must also be set.</span></span>|
|<span data-ttu-id="b8cc3-183">ConfigName</span><span class="sxs-lookup"><span data-stu-id="b8cc3-183">ConfigName</span></span>|<span data-ttu-id="b8cc3-184">Nombre de la sección de archivo de configuración donde se almacena la información de conexión.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-184">Name of the configuration file section where the connection information is stored.</span></span> <span data-ttu-id="b8cc3-185">Cuando se establece este argumento no se requieren `ProviderName` ni `ConnectionString`.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-185">When this argument is set `ProviderName` and `ConnectionString` are not required.</span></span>|
|<span data-ttu-id="b8cc3-186">CommandType</span><span class="sxs-lookup"><span data-stu-id="b8cc3-186">CommandType</span></span>|<span data-ttu-id="b8cc3-187">Tipo de <xref:System.Data.Common.DbCommand> que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-187">Type of the <xref:System.Data.Common.DbCommand> to be executed.</span></span>|
|<span data-ttu-id="b8cc3-188">Sql</span><span class="sxs-lookup"><span data-stu-id="b8cc3-188">Sql</span></span>|<span data-ttu-id="b8cc3-189">Comando SQL que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-189">The SQL command to be executed.</span></span>|
|<span data-ttu-id="b8cc3-190">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b8cc3-190">Parameters</span></span>|<span data-ttu-id="b8cc3-191">Colección de los parámetros de la consulta SQL.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-191">Collection of the parameters of the SQL query.</span></span>|
|<span data-ttu-id="b8cc3-192">Mapper</span><span class="sxs-lookup"><span data-stu-id="b8cc3-192">Mapper</span></span>|<span data-ttu-id="b8cc3-193">Función de asignación (<xref:System.Func%601><`DbDataReader`, `TResult`>) que toma un registro en el `DataReader` obtenido como resultado de la ejecución de la consulta y devuelve una instancia de un objeto de tipo `TResult` que se va a agregar a la colección de `Result`.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-193">Mapping function (<xref:System.Func%601><`DbDataReader`, `TResult`>) that takes a record in the `DataReader` obtained as result of executing the query and returns an instance of an object of type `TResult` to be added to the `Result` collection.</span></span><br /><br /> <span data-ttu-id="b8cc3-194">En este caso, la asignación se realiza mediante un único pulso de ejecución, pero no se puede crear mediante declaración utilizando el diseñador.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-194">In this case, mapping is done in a single pulse of execution, but it cannot be authored declaratively using the designer.</span></span>|
|<span data-ttu-id="b8cc3-195">MapperFunc</span><span class="sxs-lookup"><span data-stu-id="b8cc3-195">MapperFunc</span></span>|<span data-ttu-id="b8cc3-196">Función de asignación (<xref:System.Activities.ActivityFunc%601><`DbDataReader`, `TResult`>) que toma un registro en el `DataReader` obtenido como resultado de la ejecución de la consulta y devuelve una instancia de un objeto de tipo `TResult` que se va a agregar a la colección de `Result`.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-196">Mapping function (<xref:System.Activities.ActivityFunc%601><`DbDataReader`, `TResult`>) that takes a record in the `DataReader` obtained as result of executing the query and returns an instance of an object of type `TResult` to be added to the `Result` collection.</span></span><br /><br /> <span data-ttu-id="b8cc3-197">En este caso, la asignación se realiza en varios pulsos de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-197">In this case, the mapping is done in multiple pulses of execution.</span></span> <span data-ttu-id="b8cc3-198">Esta función se puede serializar en XAML y crear mediante declaración (cualquier actividad existente puede participar en la asignación).</span><span class="sxs-lookup"><span data-stu-id="b8cc3-198">This function can be serialized to XAML and authored declaratively (any existing activity can participate in the mapping).</span></span>|
|<span data-ttu-id="b8cc3-199">Resultado</span><span class="sxs-lookup"><span data-stu-id="b8cc3-199">Result</span></span>|<span data-ttu-id="b8cc3-200">Lista de objetos obtenidos como resultado de ejecutar la consulta y ejecutar la función de asignación para cada registro de `DataReader`.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-200">List of objects obtained as result of executing the query and executing the mapping function for each record in the `DataReader`.</span></span>|

## <a name="dbquerydataset"></a><span data-ttu-id="b8cc3-201">DbQueryDataSet</span><span class="sxs-lookup"><span data-stu-id="b8cc3-201">DbQueryDataSet</span></span>

<span data-ttu-id="b8cc3-202">Ejecuta una consulta que devuelve una clase <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-202">Executes a query that returns a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="b8cc3-203">Esta clase realiza su trabajo de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-203">This class performs its work asynchronously.</span></span> <span data-ttu-id="b8cc3-204">Deriva de <xref:System.Activities.AsyncCodeActivity><`TResult`> y utiliza sus capacidades asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-204">It derives from <xref:System.Activities.AsyncCodeActivity><`TResult`> and uses its asynchronous capabilities.</span></span>

<span data-ttu-id="b8cc3-205">La información de conexión se puede configurar estableciendo un nombre invariable de proveedor (`ProviderName`) y la cadena de conexión (`ConnectionString`) o simplemente utilizando un nombre de configuración de cadena de conexión (`ConfigFileSectionName`) del archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-205">The connection information can be configured by setting a provider invariant name (`ProviderName`) and the connection string (`ConnectionString`) or just using a connection string configuration name (`ConfigFileSectionName`) from the application configuration file.</span></span>

<span data-ttu-id="b8cc3-206">La consulta que se va a ejecutar se configura en su propiedad `Sql` y los parámetros se pasan a través de la colección `Parameters`.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-206">The query to be executed is configured in its `Sql` property and the parameters are passed through the `Parameters` collection.</span></span>

<span data-ttu-id="b8cc3-207">Una vez ejecutada la `DbQueryDataSet`, se devuelve `DataSet` en el argumento `Result out` (de tipo `TResult`, que se define en la <xref:System.Activities.AsyncCodeActivity%601>de la clase base).</span><span class="sxs-lookup"><span data-stu-id="b8cc3-207">After the `DbQueryDataSet` is executed the `DataSet` is returned in the `Result out` argument (of type `TResult`, that is defined in the base class <xref:System.Activities.AsyncCodeActivity%601>).</span></span>

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

|<span data-ttu-id="b8cc3-208">Argumento</span><span class="sxs-lookup"><span data-stu-id="b8cc3-208">Argument</span></span>|<span data-ttu-id="b8cc3-209">Descripción</span><span class="sxs-lookup"><span data-stu-id="b8cc3-209">Description</span></span>|
|-|-|
|<span data-ttu-id="b8cc3-210">ProviderName</span><span class="sxs-lookup"><span data-stu-id="b8cc3-210">ProviderName</span></span>|<span data-ttu-id="b8cc3-211">Nombre invariable de proveedor de ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-211">ADO.NET provider invariant name.</span></span> <span data-ttu-id="b8cc3-212">Si se establece este argumento, también se debe establecer `ConnectionString`.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-212">If this argument is set, then the `ConnectionString` must also be set.</span></span>|
|<span data-ttu-id="b8cc3-213">ConnectionString</span><span class="sxs-lookup"><span data-stu-id="b8cc3-213">ConnectionString</span></span>|<span data-ttu-id="b8cc3-214">Cadena de conexión para conectar a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-214">Connection string to connect to the database.</span></span> <span data-ttu-id="b8cc3-215">Si se establece este argumento, también se debe establecer `ProviderName`.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-215">If this argument is set, then `ProviderName` must also be set.</span></span>|
|<span data-ttu-id="b8cc3-216">ConfigName</span><span class="sxs-lookup"><span data-stu-id="b8cc3-216">ConfigName</span></span>|<span data-ttu-id="b8cc3-217">Nombre de la sección de archivo de configuración donde se almacena la información de conexión.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-217">Name of the configuration file section where the connection information is stored.</span></span> <span data-ttu-id="b8cc3-218">Cuando se establece este argumento no se requieren `ProviderName` ni `ConnectionString`.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-218">When this argument is set `ProviderName` and `ConnectionString` are not required.</span></span>|
|<span data-ttu-id="b8cc3-219">CommandType</span><span class="sxs-lookup"><span data-stu-id="b8cc3-219">CommandType</span></span>|<span data-ttu-id="b8cc3-220">Tipo de <xref:System.Data.Common.DbCommand> que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-220">Type of the <xref:System.Data.Common.DbCommand> to be executed.</span></span>|
|<span data-ttu-id="b8cc3-221">Sql</span><span class="sxs-lookup"><span data-stu-id="b8cc3-221">Sql</span></span>|<span data-ttu-id="b8cc3-222">Comando SQL que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-222">The SQL command to be executed.</span></span>|
|<span data-ttu-id="b8cc3-223">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b8cc3-223">Parameters</span></span>|<span data-ttu-id="b8cc3-224">Colección de los parámetros de la consulta SQL.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-224">Collection of the parameters of the SQL query.</span></span>|
|<span data-ttu-id="b8cc3-225">Resultado</span><span class="sxs-lookup"><span data-stu-id="b8cc3-225">Result</span></span>|<span data-ttu-id="b8cc3-226"><xref:System.Data.DataSet> que se obtiene una vez ejecutada la consulta.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-226"><xref:System.Data.DataSet> that is obtained after the query is executed.</span></span>|

## <a name="configuring-connection-information"></a><span data-ttu-id="b8cc3-227">Configurar información de conexión</span><span class="sxs-lookup"><span data-stu-id="b8cc3-227">Configuring Connection Information</span></span>

<span data-ttu-id="b8cc3-228">Todas las actividades de base de datos comparten los mismos parámetros de configuración.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-228">All DbActivities share the same configuration parameters.</span></span> <span data-ttu-id="b8cc3-229">Se pueden configurar de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="b8cc3-229">They can be configured in two ways:</span></span>

- <span data-ttu-id="b8cc3-230">`ConnectionString + InvariantName`: establezca el nombre invariable de proveedor de ADO.NET y la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-230">`ConnectionString + InvariantName`: Set the ADO.NET provider invariant name and connection string.</span></span>

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

- <span data-ttu-id="b8cc3-231">`ConfigName`: establezca el nombre de la sección de configuración que contiene la información de conexión.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-231">`ConfigName`: Set the name of the configuration section that contains the connection information.</span></span>

  ```xml
  <connectionStrings>
      <add name="DbActivitiesSample"
            providerName="System.Data.SqlClient"
            connectionString="Data Source=.\SQLExpress;Initial Catalog=DbActivitiesSample;Integrated Security=true"/>
    </connectionStrings>
  ```

- <span data-ttu-id="b8cc3-232">En la actividad:</span><span class="sxs-lookup"><span data-stu-id="b8cc3-232">In the activity:</span></span>

  ```csharp
  Activity dbSelectCount = new DbQueryScalar<int>()
  {
      ConfigName = "DbActivitiesSample",
      Sql = "SELECT COUNT(*) FROM Roles"
  };
  ```

## <a name="running-this-sample"></a><span data-ttu-id="b8cc3-233">Ejecutar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="b8cc3-233">Running this sample</span></span>

### <a name="setup-instructions"></a><span data-ttu-id="b8cc3-234">Instrucciones de instalación</span><span class="sxs-lookup"><span data-stu-id="b8cc3-234">Setup instructions</span></span>

<span data-ttu-id="b8cc3-235">En este ejemplo se utiliza una base de datos.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-235">This sample uses a database.</span></span> <span data-ttu-id="b8cc3-236">Con el ejemplo se proporciona un script de instalación y carga (Setup.cmd).</span><span class="sxs-lookup"><span data-stu-id="b8cc3-236">A set-up and load script (Setup.cmd) is provided with the sample.</span></span> <span data-ttu-id="b8cc3-237">Debe ejecutar ese archivo mediante el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-237">You must execute that file using the command prompt.</span></span>

<span data-ttu-id="b8cc3-238">El script Setup.cmd invoca el archivo de script CreateDb.sql, que contiene comandos SQL con los que realiza lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b8cc3-238">The Setup.cmd script invokes the CreateDb.sql script file, which contains SQL commands that do the following:</span></span>

- <span data-ttu-id="b8cc3-239">Crea una base de datos llamada DbActivitiesSample.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-239">Creates a database called DbActivitiesSample.</span></span>

- <span data-ttu-id="b8cc3-240">Crea la tabla Roles.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-240">Creates the Roles table.</span></span>

- <span data-ttu-id="b8cc3-241">Crea la tabla Employees.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-241">Creates Employees table.</span></span>

- <span data-ttu-id="b8cc3-242">Inserta tres registros en la tabla Roles.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-242">Inserts three records into the Roles table.</span></span>

- <span data-ttu-id="b8cc3-243">Inserta doce registros en la tabla Employees.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-243">Inserts twelve records into the Employees table.</span></span>

##### <a name="to-run-setupcmd"></a><span data-ttu-id="b8cc3-244">Para ejecutar Setup.cmd</span><span class="sxs-lookup"><span data-stu-id="b8cc3-244">To run Setup.cmd</span></span>

1. <span data-ttu-id="b8cc3-245">Abra un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-245">Open a command prompt.</span></span>

2. <span data-ttu-id="b8cc3-246">Vaya a la carpeta de ejemplo DbActivities.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-246">Go to the DbActivities sample folder.</span></span>

3. <span data-ttu-id="b8cc3-247">Escriba "Setup. cmd" y presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-247">Type "setup.cmd" and press ENTER.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b8cc3-248">Setup.cmd intenta instalar el ejemplo en la instancia de SqlExpress del equipo local.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-248">Setup.cmd attempts to install the sample in your local machine SqlExpress instance.</span></span> <span data-ttu-id="b8cc3-249">Si desea instalarlo en otra instancia de SQL Server, modifique Setup.cmd con el nombre de la nueva instancia.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-249">If you want to install it in other SQL server instance, edit Setup.cmd with the new instance name.</span></span>

##### <a name="to-uninstall-the-sample-database"></a><span data-ttu-id="b8cc3-250">Para desinstalar la base de datos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="b8cc3-250">To uninstall the sample database</span></span>

1. <span data-ttu-id="b8cc3-251">Ejecute Cleanup.cmd desde la carpeta de ejemplo en un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-251">Run Cleanup.cmd from the sample folder in a command prompt.</span></span>

##### <a name="to-run-the-sample"></a><span data-ttu-id="b8cc3-252">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="b8cc3-252">To run the sample</span></span>

1. <span data-ttu-id="b8cc3-253">Abra la solución en Visual Studio 2010</span><span class="sxs-lookup"><span data-stu-id="b8cc3-253">Open the solution in Visual Studio 2010</span></span>

2. <span data-ttu-id="b8cc3-254">Para compilar la solución, presione Ctrl+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-254">To compile the solution, press CTRL+SHIFT+B.</span></span>

3. <span data-ttu-id="b8cc3-255">Para ejecutar el ejemplo sin depurar, presione CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-255">To run the sample without debugging, press CTRL+F5.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b8cc3-256">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-256">The samples may already be installed on your machine.</span></span> <span data-ttu-id="b8cc3-257">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-257">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="b8cc3-258">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b8cc3-258">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b8cc3-259">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="b8cc3-259">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\DbActivities`
