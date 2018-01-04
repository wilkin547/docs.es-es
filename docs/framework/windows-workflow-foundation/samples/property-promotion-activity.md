---
title: "Actividad de promoción de propiedad"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 802196b7-1159-4c05-b41b-d3bfdfcc88d9
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 244cea33b684a8674681c4d1974d5d857c4c402b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="property-promotion-activity"></a><span data-ttu-id="3272d-102">Actividad de promoción de propiedad</span><span class="sxs-lookup"><span data-stu-id="3272d-102">Property Promotion Activity</span></span>
<span data-ttu-id="3272d-103">Este ejemplo proporciona una solución integral que incluye la característica Promoción de <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> directamente en el flujo de trabajo que crea la experiencia.</span><span class="sxs-lookup"><span data-stu-id="3272d-103">This sample provides an end-to-end solution that integrates the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> Promotion feature directly into the workflow authoring experience.</span></span> <span data-ttu-id="3272d-104">Se proporciona una colección de elementos de configuración, actividades de flujo de trabajo y extensiones de flujo de trabajo que simplifican el uso de la característica Promoción.</span><span class="sxs-lookup"><span data-stu-id="3272d-104">A collection of configuration elements, workflow activities, and workflow extensions that simplify the use of the Promotion feature are provided.</span></span> <span data-ttu-id="3272d-105">Además, el ejemplo contiene un flujo de trabajo sencillo que muestra cómo utilizar esta colección.</span><span class="sxs-lookup"><span data-stu-id="3272d-105">Additionally, the sample contains a simple workflow that demonstrates how to use this collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3272d-106">Los ejemplos se proporcionan exclusivamente con fines formativos.</span><span class="sxs-lookup"><span data-stu-id="3272d-106">Samples are provided for educational purposes only.</span></span> <span data-ttu-id="3272d-107">No están pensados para un entorno de producción y no se han probado en un entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="3272d-107">They are not intended for a production environment, and have not been tested in a production environment.</span></span> <span data-ttu-id="3272d-108">Microsoft no proporciona soporte técnico para estos ejemplos.</span><span class="sxs-lookup"><span data-stu-id="3272d-108">Microsoft does not provide technical support for these samples.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3272d-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="3272d-109">Prerequisites</span></span>  
  
-   <span data-ttu-id="3272d-110">Una base de datos <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> inicializada</span><span class="sxs-lookup"><span data-stu-id="3272d-110">An initialized <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> database</span></span>  
  
-   [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]  
  
## <a name="sample-projects"></a><span data-ttu-id="3272d-111">Proyectos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="3272d-111">Sample Projects</span></span>  
  
-   <span data-ttu-id="3272d-112">El **PropertyPromotionActivity** proyecto contiene archivos que pertenecen a los elementos de configuración específicos de la promoción, las actividades de flujo de trabajo y extensiones de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3272d-112">The **PropertyPromotionActivity** project contains files pertaining to the promotion-specific configuration elements, workflow activities, and workflow extensions.</span></span>  
  
-   <span data-ttu-id="3272d-113">El **CounterServiceApplication** proyecto contiene un flujo de trabajo de ejemplo que usa el **SqlWorkflowInstanceStorePromotion** proyecto.</span><span class="sxs-lookup"><span data-stu-id="3272d-113">The **CounterServiceApplication** project contains a sample workflow that uses the **SqlWorkflowInstanceStorePromotion** project.</span></span>  
  
-   <span data-ttu-id="3272d-114">Un script SQL (PropertyPromotionActivitySQLSample.sql) que se debe ejecutar contra la base de datos <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>.</span><span class="sxs-lookup"><span data-stu-id="3272d-114">A SQL script (PropertyPromotionActivitySQLSample.sql) that must be run against the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> database.</span></span>  
  
-   <span data-ttu-id="3272d-115">Un archivo de solución que vincula los dos proyectos [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] (`PropertyPromotionActivity.sln`)</span><span class="sxs-lookup"><span data-stu-id="3272d-115">A solution file that links the two [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] projects (`PropertyPromotionActivity.sln`)</span></span>  
  
## <a name="to-set-up-and-run-the-sample"></a><span data-ttu-id="3272d-116">Configurar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="3272d-116">To set up and run the sample</span></span>  
  
1.  <span data-ttu-id="3272d-117">Inicialice una base de datos de persistencia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3272d-117">Initialize a workflow persistence database.</span></span>  
  
    1.  <span data-ttu-id="3272d-118">Navegue hasta el directorio de ejemplo (\WF\Basic\Persistence\PropertyPromotionActivity) y ejecute CreateInstanceStore.cmd.</span><span class="sxs-lookup"><span data-stu-id="3272d-118">Navigate to the sample directory (\WF\Basic\Persistence\PropertyPromotionActivity) and run CreateInstanceStore.cmd.</span></span>  
  
    2.  <span data-ttu-id="3272d-119">Si no dispone de privilegios de administrador, cree un inicio de sesión de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3272d-119">If Administrator privileges are not available, create a SQL Server login.</span></span> <span data-ttu-id="3272d-120">En SQL Server Management Studio, vaya a **seguridad**, **inicios de sesión**.</span><span class="sxs-lookup"><span data-stu-id="3272d-120">In SQL Server Management Studio, go to **Security**, **Logins**.</span></span> <span data-ttu-id="3272d-121">Haga clic en **inicios de sesión** y crear un nuevo inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="3272d-121">Right-click **Logins** and create a new login.</span></span> <span data-ttu-id="3272d-122">Agregue el usuario ACL al rol SQL abriendo **bases de datos**, **InstanceStore**, **seguridad**.</span><span class="sxs-lookup"><span data-stu-id="3272d-122">Add your ACL user to the SQL role by opening **Databases**, **InstanceStore**, **Security**.</span></span> <span data-ttu-id="3272d-123">Haga clic en **usuarios** y seleccione **nuevo usuario**.</span><span class="sxs-lookup"><span data-stu-id="3272d-123">Right-click **Users** and select **New user**.</span></span> <span data-ttu-id="3272d-124">Establecer el **nombre de inicio de sesión** para el usuario creado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="3272d-124">Set the **Login name** to the user created above.</span></span> <span data-ttu-id="3272d-125">Agregue el usuario a la pertenencia al rol de la base de datos System.Activities.DurableInstancing.InstanceStoreUsers (y otros).</span><span class="sxs-lookup"><span data-stu-id="3272d-125">Add the user to the Database role membership System.Activities.DurableInstancing.InstanceStoreUsers (and others).</span></span> <span data-ttu-id="3272d-126">Observe que el usuario ya podría existir (por ejemplo, el usuario dbo).</span><span class="sxs-lookup"><span data-stu-id="3272d-126">Note that the user might exist already (for example, user dbo).</span></span>  
  
2.  <span data-ttu-id="3272d-127">Abra el archivo de solución PropertyPromotionActivity.sln en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3272d-127">Open the PropertyPromotionActivity.sln solution file in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
3.  <span data-ttu-id="3272d-128">Si creó el almacén de instancia en una base de datos distinta de una instalación local de SQL Server Express, a continuación debe actualizar la cadena de conexión a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="3272d-128">If you created the instance store in a database other than a local installation of SQL Server Express, then you must update the database connection string.</span></span> <span data-ttu-id="3272d-129">Modifique el archivo App.config en el **CounterServiceApplication** estableciendo el valor de la `connectionString` del atributo en el `sqlWorkflowInstanceStorePromotion` nodo para que apunte a la base de datos de persistencia que se inicializó en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="3272d-129">Alter the App.config file under the **CounterServiceApplication** by setting the value of the `connectionString` attribute on the `sqlWorkflowInstanceStorePromotion` node so that it points to the persistence database that was initialized in step 1.</span></span>  
  
4.  <span data-ttu-id="3272d-130">Compile y ejecute la solución.</span><span class="sxs-lookup"><span data-stu-id="3272d-130">Build and run the solution.</span></span> <span data-ttu-id="3272d-131">Esto iniciará el servicio Counter WF e iniciará automáticamente una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3272d-131">This will start the Counter WF service and automatically start a workflow instance.</span></span>  
  
5.  <span data-ttu-id="3272d-132">Seleccione rápidamente todas las filas de la vista [dbo]. [CounterService] en su base de datos de persistencia (esta vista se agregó al ejecutar CreateInstanceStore.cmd en el paso 1).</span><span class="sxs-lookup"><span data-stu-id="3272d-132">Quickly select all the rows in the [dbo].[CounterService] view in your persistence database (this view was added by running CreateInstanceStore.cmd in step 1).</span></span> <span data-ttu-id="3272d-133">Verá un conjunto de resultados similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="3272d-133">You will see a result set similar to the following:</span></span>  
  
    |<span data-ttu-id="3272d-134">InstanceId</span><span class="sxs-lookup"><span data-stu-id="3272d-134">InstanceId</span></span>|<span data-ttu-id="3272d-135">CounterValue</span><span class="sxs-lookup"><span data-stu-id="3272d-135">CounterValue</span></span>|<span data-ttu-id="3272d-136">CounterValueLastUpdated</span><span class="sxs-lookup"><span data-stu-id="3272d-136">CounterValueLastUpdated</span></span>|  
    |----------------|------------------|-----------------------------|  
    |<span data-ttu-id="3272d-137">2FA2C302-929E-4C0D-8C25-768A3DA20CE5</span><span class="sxs-lookup"><span data-stu-id="3272d-137">2FA2C302-929E-4C0D-8C25-768A3DA20CE5</span></span>|<span data-ttu-id="3272d-138">12</span><span class="sxs-lookup"><span data-stu-id="3272d-138">12</span></span>|<span data-ttu-id="3272d-139">2010-02-18 22:48:01.740</span><span class="sxs-lookup"><span data-stu-id="3272d-139">2010-02-18 22:48:01.740</span></span>|  
  
     <span data-ttu-id="3272d-140">Mientras sigue actualizando la vista, observará que CounterValue y CounterValueLastUpdated cambian cada dos segundos.</span><span class="sxs-lookup"><span data-stu-id="3272d-140">As you keep refreshing the view, you will notice that CounterValue and CounterValueLastUpdated change every two seconds.</span></span> <span data-ttu-id="3272d-141">Este es el intervalo en el que el contador se actualiza.</span><span class="sxs-lookup"><span data-stu-id="3272d-141">This is the interval at which the counter updates itself.</span></span> <span data-ttu-id="3272d-142">CounterValue and CounterValueLastUpdated representan las propiedades que se han promovido para este flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3272d-142">CounterValue and CounterValueLastUpdated represent promoted properties for this workflow.</span></span>  
  
## <a name="to-remove-the-sample"></a><span data-ttu-id="3272d-143">Para quitar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="3272d-143">To remove the sample</span></span>  
  
-   <span data-ttu-id="3272d-144">Ejecute RemoveInstanceStore.cmd en el directorio de ejemplos (\WF\Basic\Persistence\PropertyPromotionActivity).</span><span class="sxs-lookup"><span data-stu-id="3272d-144">Run RemoveInstanceStore.cmd in the sample directory (\WF\Basic\Persistence\PropertyPromotionActivity).</span></span>  
  
## <a name="understanding-this-sample"></a><span data-ttu-id="3272d-145">Descripción de este ejemplo</span><span class="sxs-lookup"><span data-stu-id="3272d-145">Understanding This Sample</span></span>  
 <span data-ttu-id="3272d-146">El ejemplo contiene dos proyectos y un archivo SQL:</span><span class="sxs-lookup"><span data-stu-id="3272d-146">The sample contains two projects and an SQL file:</span></span>  
  
-   <span data-ttu-id="3272d-147">**CounterServiceApplication** es una aplicación de consola que hospeda un servicio Counter WF simple.</span><span class="sxs-lookup"><span data-stu-id="3272d-147">**CounterServiceApplication** is a console application that hosts a simple Counter WF service.</span></span> <span data-ttu-id="3272d-148">Al recibir un mensaje unidireccional a través del extremo `Start`, el flujo de trabajo cuenta de 0 a 29, incrementando una variable de contador cada dos segundos.</span><span class="sxs-lookup"><span data-stu-id="3272d-148">Upon receiving a one-way message through the `Start` endpoint, the workflow counts from 0 to 29, incrementing a counter variable every two seconds.</span></span> <span data-ttu-id="3272d-149">Después de cada incremento del contador, el flujo de trabajo persiste y las propiedades promovidas están actualizadas en la vista [dbo].[CounterService].</span><span class="sxs-lookup"><span data-stu-id="3272d-149">After every counter increment, the workflow persists, and the promoted properties are updated in the [dbo].[CounterService] view.</span></span> <span data-ttu-id="3272d-150">Cuando se ejecuta la aplicación de consola, hospeda el servicio WF y envía un mensaje al extremo `Start`, creando una instancia de Counter WF.</span><span class="sxs-lookup"><span data-stu-id="3272d-150">When the console application is run, it hosts the WF service and sends a message to the `Start` endpoint, creating a Counter WF instance.</span></span>  
  
-   <span data-ttu-id="3272d-151">**PropertyPromotionActivity** es una biblioteca de clases que contiene los elementos de configuración, actividades de flujo de trabajo y extensiones de flujo de trabajo que el **CounterServiceApplication** usa.</span><span class="sxs-lookup"><span data-stu-id="3272d-151">**PropertyPromotionActivity** is a class library that contains the configuration elements, workflow activities, and workflow extensions that the **CounterServiceApplication** uses.</span></span>  
  
-   <span data-ttu-id="3272d-152">**PropertyPromotionActivitySQLSample.sql** crea y agrega la vista [dbo]. [ CounterService] a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="3272d-152">**PropertyPromotionActivitySQLSample.sql** creates and adds the view [dbo].[CounterService] to the database.</span></span>  
  
### <a name="counterserviceapplication"></a><span data-ttu-id="3272d-153">CounterServiceApplication</span><span class="sxs-lookup"><span data-stu-id="3272d-153">CounterServiceApplication</span></span>  
  
#### <a name="using-the-sqlworkflowinstancestorepromotion-configuration-element"></a><span data-ttu-id="3272d-154">Utilizar el elemento de configuración SqlWorkflowInstanceStorePromotion</span><span class="sxs-lookup"><span data-stu-id="3272d-154">Using the SqlWorkflowInstanceStorePromotion Configuration Element</span></span>  
 <span data-ttu-id="3272d-155">El elemento de configuración `SqlWorkflowInstanceStorePromotion` se hereda del elemento de configuración `SqlWorkflowInstanceStore`, pero agrega un elemento de configuración adicional llamado `promotionSets`.</span><span class="sxs-lookup"><span data-stu-id="3272d-155">The `SqlWorkflowInstanceStorePromotion` configuration element inherits from the `SqlWorkflowInstanceStore` configuration element, but adds an additional configuration element called `promotionSets`.</span></span> <span data-ttu-id="3272d-156">El elemento `promotionSets` le permite al usuario especificar las propiedades promovidas mediante la configuración.</span><span class="sxs-lookup"><span data-stu-id="3272d-156">The `promotionSets` element enables the user to specify promoted properties through configuration.</span></span> <span data-ttu-id="3272d-157">Es el archivo de configuración que utiliza el ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3272d-157">This is the configuration file that is used by the sample:</span></span>  
  
```xml  
<sqlWorkflowInstanceStorePromotion connectionString ="Data Source=.;Initial Catalog=SqlWorkflowInstanceStoreTest;Integrated Security=True;">  
  <promotionSets>  
    <promotionSet name="CounterService">  
      <promotedValue propertyName="Count"/>  
      <promotedValue propertyName="LastIncrementedAt"/>  
    </promotionSet>  
  </promotionSets>  
</sqlWorkflowInstanceStorePromotion>  
```  
  
 <span data-ttu-id="3272d-158">Examine la definición para la vista [dbo].[CounterService].</span><span class="sxs-lookup"><span data-stu-id="3272d-158">Examine the definition for the [dbo].[CounterService] view.</span></span>  
  
```sql  
create view [dbo].[CounterService] as  
      select [InstanceId],  
 [Value1] as [CounterValue],  
 [Value2] as [CounterValueLastUpdated]  
      from [System.Activities.DurableInstancing].[InstancePromotedProperties]  
      where [PromotionName] = 'CounterService'  
go  
```  
  
 <span data-ttu-id="3272d-159">Cuando una instancia de flujo de trabajo persiste, se inserta una fila en la vista `InstancePromotedProperties` vista para cada `PromotionSet` que se define en la configuración.</span><span class="sxs-lookup"><span data-stu-id="3272d-159">When a workflow instance persists, a row is inserted into the `InstancePromotedProperties` view for each `PromotionSet` defined in the configuration.</span></span> <span data-ttu-id="3272d-160">Esta fila contiene todas las propiedades promovidasl de (una propiedad promocionada por columna) `PromotionSet` (una propiedad promovida por columna).</span><span class="sxs-lookup"><span data-stu-id="3272d-160">This row contains all the promoted properties of the `PromotionSet` (one promoted property per column).</span></span> <span data-ttu-id="3272d-161">La tupla recibe la clave de `PromotionSet`: `InstanceId, PromotionName`.</span><span class="sxs-lookup"><span data-stu-id="3272d-161">This `PromotionSet` is keyed by the tuple: `InstanceId, PromotionName`.</span></span> <span data-ttu-id="3272d-162">En este ejemplo, tenemos un `PromotionSet` definido en configuración cuyo atributo de nombre es `CounterService`.</span><span class="sxs-lookup"><span data-stu-id="3272d-162">In this sample, we have one `PromotionSet` defined in configuration whose name attribute is `CounterService`.</span></span> <span data-ttu-id="3272d-163">Observe que el valor de columna `PromotionName` es igual al atributo de nombre del elemento `PromotionSet`.</span><span class="sxs-lookup"><span data-stu-id="3272d-163">Note how the `PromotionName` column value is equal to the name attribute of the `PromotionSet` element.</span></span>  
  
 <span data-ttu-id="3272d-164">El orden de los elementos `promotedValue` se correlaciona con la colocación de las propiedades promovidas en la vista `InstancePromotedProperties`.</span><span class="sxs-lookup"><span data-stu-id="3272d-164">The order of the `promotedValue` elements correlates with the placement of the promoted properties in the `InstancePromotedProperties` view.</span></span> <span data-ttu-id="3272d-165">`Count` es el primer elemento `promotedValue`.</span><span class="sxs-lookup"><span data-stu-id="3272d-165">`Count` is the first `promotedValue` element.</span></span> <span data-ttu-id="3272d-166">Como resultado, se asigna a la columna `Value1` de la vista `InstancePromotedProperties`.</span><span class="sxs-lookup"><span data-stu-id="3272d-166">As a result, it is mapped to the `Value1` column in the `InstancePromotedProperties` view.</span></span> <span data-ttu-id="3272d-167">`LastIncrementedAt` es el segundo elemento `promotedValue`.</span><span class="sxs-lookup"><span data-stu-id="3272d-167">`LastIncrementedAt` is the second `promotedValue` element.</span></span> <span data-ttu-id="3272d-168">Como resultado, se asigna a la columna `Value2` de la vista `InstancePromotedProperties`.</span><span class="sxs-lookup"><span data-stu-id="3272d-168">As a result, it is mapped to the `Value2` column in the `InstancePromotedProperties` view.</span></span>  
  
#### <a name="using-the-promotevalue-activity"></a><span data-ttu-id="3272d-169">Utilizar la actividad PromoteValue</span><span class="sxs-lookup"><span data-stu-id="3272d-169">Using the PromoteValue Activity</span></span>  
 <span data-ttu-id="3272d-170">Examine el archivo CounterService.xamlx en el Diseñador [!INCLUDE[wf2](../../../../includes/wf2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3272d-170">Examine the CounterService.xamlx file in the [!INCLUDE[wf2](../../../../includes/wf2-md.md)] Designer.</span></span> <span data-ttu-id="3272d-171">Observe que hay dos actividades especiales en la definición de WF: `PromoteValue<DateTime>` y `PromoteValue<Int32>`.</span><span class="sxs-lookup"><span data-stu-id="3272d-171">Notice that there are two special activities in the WF definition: `PromoteValue<DateTime>` and `PromoteValue<Int32>`.</span></span>  
  
 <span data-ttu-id="3272d-172">La actividad `PromoteValue<Int32>` tiene su miembro `Name` definido como `Count`.</span><span class="sxs-lookup"><span data-stu-id="3272d-172">The `PromoteValue<Int32>` activity has its `Name` member defined as `Count`.</span></span> <span data-ttu-id="3272d-173">Esto coincide con el primer elemento de `promotedValue` en la configuración y tiene `Value` definido como la variable de flujo de trabajo `Counter`.</span><span class="sxs-lookup"><span data-stu-id="3272d-173">This matches with the first `promotedValue` element in the configuration, and has its `Value` defined as the `Counter` workflow variable.</span></span> <span data-ttu-id="3272d-174">Cuando el flujo de trabajo persiste, la variable de flujo de trabajo `Counter` se guarda como una propiedad promovida en la columna `Value1` de la vista `InstancePromotedProperties`.</span><span class="sxs-lookup"><span data-stu-id="3272d-174">When the workflow persists, the `Counter` workflow variable is persisted as a promoted property into the `Value1` column of the `InstancePromotedProperties` view.</span></span>  
  
 <span data-ttu-id="3272d-175">La actividad `PromoteValue<DateTime>` tiene su miembro `Name` definido como `LastIncrementedAt`.</span><span class="sxs-lookup"><span data-stu-id="3272d-175">The `PromoteValue<DateTime>` activity has its `Name` member defined as `LastIncrementedAt`.</span></span> <span data-ttu-id="3272d-176">Esto coincide con el segundo elemento de `promotedValue` en la configuración y tiene `Value` definido como la variable de flujo de trabajo `TimeLastIncremented`.</span><span class="sxs-lookup"><span data-stu-id="3272d-176">This matches with the second `promotedValue` element in the configuration, and has its `Value` defined as the `TimeLastIncremented` workflow variable.</span></span> <span data-ttu-id="3272d-177">Esto significa que cuando el flujo de trabajo persiste, el valor para la variable de flujo de trabajo `TimeLastIncremented` se guardará como una propiedad promovida en la columna `Value2` de la vista `InstancePromotedProperties`.</span><span class="sxs-lookup"><span data-stu-id="3272d-177">This means that when the workflow persists, the value for the `TimeLastIncremented` workflow variable will be persisted as a promoted property into the `Value2` column of the `InstancePromotedProperties` view.</span></span>  
  
 <span data-ttu-id="3272d-178">Observe que la actividad `PromotedValue` también tiene un miembro Boolean llamado `ClearExistingPromotedData`.</span><span class="sxs-lookup"><span data-stu-id="3272d-178">Note that the `PromotedValue` activity also has a Boolean member called `ClearExistingPromotedData`.</span></span> <span data-ttu-id="3272d-179">Cuando este miembro está establecido en `true`, se borran todos los valores de la propiedad promovida hasta ese punto del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3272d-179">When this member is set to `true`, this clears all the promoted property values up to that point in the workflow.</span></span> <span data-ttu-id="3272d-180">Por ejemplo, si una actividad Sequence se define como sigue:</span><span class="sxs-lookup"><span data-stu-id="3272d-180">For example, if a Sequence activity is defined as follows:</span></span>  
  
1.  <span data-ttu-id="3272d-181">PromoteValue {nombre = "Count", valor = 3}</span><span class="sxs-lookup"><span data-stu-id="3272d-181">PromoteValue { Name = "Count", Value = 3}</span></span>  
  
2.  <span data-ttu-id="3272d-182">PromoteValue {nombre = "LastIncrementedAt", valor = 1-1-2000}</span><span class="sxs-lookup"><span data-stu-id="3272d-182">PromoteValue {Name = "LastIncrementedAt", Value = 1-1-2000 }</span></span>  
  
3.  <span data-ttu-id="3272d-183">Conservar</span><span class="sxs-lookup"><span data-stu-id="3272d-183">Persist</span></span>  
  
4.  <span data-ttu-id="3272d-184">PromoteValue {nombre = "Count", valor = 4, ClearExistingPromotedData = true}</span><span class="sxs-lookup"><span data-stu-id="3272d-184">PromoteValue {Name = "Count", Value = 4, ClearExistingPromotedData = true}</span></span>  
  
5.  <span data-ttu-id="3272d-185">Conservar</span><span class="sxs-lookup"><span data-stu-id="3272d-185">Persist</span></span>  
  
 <span data-ttu-id="3272d-186">En la segunda persistencia, el valor promovido para `Count` será 4.</span><span class="sxs-lookup"><span data-stu-id="3272d-186">On the second persist, the promoted value for `Count` will be 4.</span></span> <span data-ttu-id="3272d-187">Sin embargo, el valor promovido para `LastIncrementedAt` será `NULL`.</span><span class="sxs-lookup"><span data-stu-id="3272d-187">However, the promoted value for `LastIncrementedAt` will be `NULL`.</span></span> <span data-ttu-id="3272d-188">Si `ClearExistingPromotedData` no se hubiera establecido en `true` para el paso 4, después de la segunda persistencia el valor promovido para Count sería 4.</span><span class="sxs-lookup"><span data-stu-id="3272d-188">If `ClearExistingPromotedData` was not set to `true` for step 4, then after the second persist, the promoted value for Count would be 4.</span></span> <span data-ttu-id="3272d-189">Como resultado, el valor promovido para `LastIncrementedAt` todavía sería 1-1-2000.</span><span class="sxs-lookup"><span data-stu-id="3272d-189">As a result, the promoted value for `LastIncrementedAt` would still be 1-1-2000.</span></span>  
  
### <a name="propertypromotionactivity"></a><span data-ttu-id="3272d-190">PropertyPromotionActivity</span><span class="sxs-lookup"><span data-stu-id="3272d-190">PropertyPromotionActivity</span></span>  
 <span data-ttu-id="3272d-191">Esta biblioteca de clases contiene las siguientes clases pública para simplificar uso de la característica Promoción de <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>.</span><span class="sxs-lookup"><span data-stu-id="3272d-191">This class library contains the following public classes to simplify use of the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> Promotion feature.</span></span>  
  
#### <a name="promotevalue-class"></a><span data-ttu-id="3272d-192">Clase PromoteValue</span><span class="sxs-lookup"><span data-stu-id="3272d-192">PromoteValue Class</span></span>  
 <span data-ttu-id="3272d-193">Esta clase promueve una propiedad.</span><span class="sxs-lookup"><span data-stu-id="3272d-193">This class promotes one property.</span></span> <span data-ttu-id="3272d-194">El nombre de la propiedad promovida debería coincidir con un atributo de nombre de un elemento `promotedValue` de la configuración.</span><span class="sxs-lookup"><span data-stu-id="3272d-194">The name of the promoted property should match a name attribute of a `promotedValue` element in the configuration.</span></span> <span data-ttu-id="3272d-195">Esta actividad se puede usar en el Diseñador de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3272d-195">This activity can be used in the Workflow Designer.</span></span> <span data-ttu-id="3272d-196">Vea CounterServiceApplication para un uso del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="3272d-196">See the CounterServiceApplication for an example usage.</span></span>  
  
```csharp  
public class PromoteValue<T> : CodeActivity  
{  
    public PromoteValue()  
    {  
    }  
  
    public bool ClearExistingPromotedData { get; set; }  
    public string Name { get; set; }  
    public InArgument<T> Value { get; set; }  
}  
```  
  
 <span data-ttu-id="3272d-197">ClearExistingPromotedData (Bool)</span><span class="sxs-lookup"><span data-stu-id="3272d-197">ClearExistingPromotedData (Bool)</span></span>  
 <span data-ttu-id="3272d-198">Borra todos los valores que se promovieron antes de esta actividad.</span><span class="sxs-lookup"><span data-stu-id="3272d-198">Clears all values that were promoted before this activity.</span></span>  
  
 <span data-ttu-id="3272d-199">Name (string)</span><span class="sxs-lookup"><span data-stu-id="3272d-199">Name (string)</span></span>  
 <span data-ttu-id="3272d-200">El nombre que representa a esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="3272d-200">The name that represents this property.</span></span> <span data-ttu-id="3272d-201">Esto debe coincidir con el atributo de nombre de un \<promotedValue > elemento en la configuración.</span><span class="sxs-lookup"><span data-stu-id="3272d-201">This should match the name attribute of a \<promotedValue> element in the configuration.</span></span>  
  
 <span data-ttu-id="3272d-202">Valor (InArgument\<T >)</span><span class="sxs-lookup"><span data-stu-id="3272d-202">Value (InArgument\<T>)</span></span>  
 <span data-ttu-id="3272d-203">La variable / valor que desea almacenar en la columna.</span><span class="sxs-lookup"><span data-stu-id="3272d-203">The variable / value that you want to store in the column.</span></span>  
  
#### <a name="promotevalues-class"></a><span data-ttu-id="3272d-204">Clase PromoteValues</span><span class="sxs-lookup"><span data-stu-id="3272d-204">PromoteValues Class</span></span>  
 <span data-ttu-id="3272d-205">Promueve varias propiedades.</span><span class="sxs-lookup"><span data-stu-id="3272d-205">Promotes multiple properties.</span></span> <span data-ttu-id="3272d-206">Los nombres de las propiedades promovidas deberían coincidir con todos los atributos de nombre de los elementos `promotedValue` de la configuración.</span><span class="sxs-lookup"><span data-stu-id="3272d-206">The names of the promoted properties should match all name attributes in the `promotedValue` elements in the configuration.</span></span> <span data-ttu-id="3272d-207">El uso es similar al de la actividad `PromoteValue`, salvo por el hecho de que se pueden promover varias propiedades al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="3272d-207">Usage is similar to the `PromoteValue` activity, except for the fact that multiple properties can be promoted at the same time.</span></span> <span data-ttu-id="3272d-208">Esta actividad no se puede usar en el Diseñador de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3272d-208">This activity cannot be used in the Workflow Designer.</span></span>  
  
```  
public class PromoteValues : CodeActivity  
{  
    public PromoteValues()  
    {  
        this.ValuesToPromote = new Dictionary<string, InArgument>();  
    }  
  
    public bool ClearExistingPromotedData { get; set; }  
    public IDictionary<string, InArgument> ValuesToPromote { get; set; }  
}  
```  
  
#### <a name="sqlworkflowinstancestorepromotionbehavior"></a><span data-ttu-id="3272d-209">SqlWorkflowInstanceStorePromotionBehavior</span><span class="sxs-lookup"><span data-stu-id="3272d-209">SqlWorkflowInstanceStorePromotionBehavior</span></span>  
 <span data-ttu-id="3272d-210">Deriva de `SqlWorkflowInstanceStoreBehavior`.</span><span class="sxs-lookup"><span data-stu-id="3272d-210">Derives from `SqlWorkflowInstanceStoreBehavior`.</span></span> <span data-ttu-id="3272d-211">Esta clase derivada agrega un participante de persistencia personalizado (también una parte de esta biblioteca) como una extensión de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3272d-211">This derived class adds a custom persistence participant (also a part of this library) as a workflow extension.</span></span> <span data-ttu-id="3272d-212">La implementación de las dos actividades de flujo de trabajo anteriores se basa en este participante de persistencia personalizado.</span><span class="sxs-lookup"><span data-stu-id="3272d-212">The implementation of the previous two workflow activities relies on this custom persistence participant.</span></span>  
  
```  
public class SqlWorkflowInstanceStorePromotionBehavior :  
             SqlWorkflowInstanceStoreBehavior, IServiceBehavior  
{  
        public void Promote(string name, IEnumerable<string> promoteAsSqlVariant,  
                            IEnumerable<string> promoteAsBinary)  
  
}  
```  
  
 <span data-ttu-id="3272d-213">Esta biblioteca de clases también contiene la implementación `ConfigurationElement` para `SqlWorkflowInstanceStorePromotionElement` y un participante de persistencia personalizado utilizado por las actividades de promoción anteriores.</span><span class="sxs-lookup"><span data-stu-id="3272d-213">This class library also contains the `ConfigurationElement` implementation for the `SqlWorkflowInstanceStorePromotionElement` and a custom persistence participant used by the previous promotion activities.</span></span>  
  
### <a name="propertypromotionactivitysqlsample"></a><span data-ttu-id="3272d-214">PropertyPromotionActivitySQLSample</span><span class="sxs-lookup"><span data-stu-id="3272d-214">PropertyPromotionActivitySQLSample</span></span>  
 <span data-ttu-id="3272d-215">Este archivo SQL crea una vista `[dbo].[CounterService]` además de la vista `[InstancePromotedProperties]` ven para consultar todas las instancias que un conjunto de Promoción de CounterService.</span><span class="sxs-lookup"><span data-stu-id="3272d-215">This SQL file creates a `[dbo].[CounterService]` view in addition to the `[InstancePromotedProperties]` view for querying all instances that have a CounterService Promotion set.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3272d-216">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="3272d-216">The samples may already be installed on your computer.</span></span> <span data-ttu-id="3272d-217">Compruebe el siguiente directorio (predeterminado) antes de continuar:</span><span class="sxs-lookup"><span data-stu-id="3272d-217">Check for the following (default) directory before continuing:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="3272d-218">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3272d-218">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="3272d-219">Este ejemplo se encuentra en el siguiente directorio:</span><span class="sxs-lookup"><span data-stu-id="3272d-219">This sample is located in the following directory:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Persistence\PropertyPromotionActivity`  
  
## <a name="see-also"></a><span data-ttu-id="3272d-220">Vea también</span><span class="sxs-lookup"><span data-stu-id="3272d-220">See Also</span></span>  
 [<span data-ttu-id="3272d-221">Ejemplos de persistencia y el hospedaje de AppFabric</span><span class="sxs-lookup"><span data-stu-id="3272d-221">AppFabric Hosting and Persistence Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193961)
