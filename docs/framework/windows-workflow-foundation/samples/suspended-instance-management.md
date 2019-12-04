---
title: Administración de instancias suspendidas
ms.date: 03/30/2017
ms.assetid: f5ca3faa-ba1f-4857-b92c-d927e4b29598
ms.openlocfilehash: 3f1f4f8edcbe0e05067d3ca739ef3d5f4fe4d798
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715941"
---
# <a name="suspended-instance-management"></a><span data-ttu-id="fa471-102">Administración de instancias suspendidas</span><span class="sxs-lookup"><span data-stu-id="fa471-102">Suspended Instance Management</span></span>
<span data-ttu-id="fa471-103">En este ejemplo se muestra cómo administrar instancias de flujo de trabajo que se han suspendido.</span><span class="sxs-lookup"><span data-stu-id="fa471-103">This sample demonstrates how to manage workflow instances that have been suspended.</span></span>  <span data-ttu-id="fa471-104">La acción predeterminada para <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> es `AbandonAndSuspend`.</span><span class="sxs-lookup"><span data-stu-id="fa471-104">The default action for <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> is `AbandonAndSuspend`.</span></span> <span data-ttu-id="fa471-105">Esto significa que, de forma predeterminada, las excepciones no controladas producidas por una instancia de flujo de trabajo hospedada en <xref:System.ServiceModel.WorkflowServiceHost> causarán que la instancia se elimine de la memoria (se abandone) y la versión duradera/conservada de la instancia se marque como suspendida.</span><span class="sxs-lookup"><span data-stu-id="fa471-105">This means that by default, unhandled exceptions thrown from a workflow instance hosted in the <xref:System.ServiceModel.WorkflowServiceHost> will cause the instance to be disposed from memory (abandoned) and the durable/persisted version of the instance to be marked as suspended.</span></span> <span data-ttu-id="fa471-106">Una instancia de flujo de trabajo suspendida no se podrá ejecutar hasta que no se anule la suspensión.</span><span class="sxs-lookup"><span data-stu-id="fa471-106">A suspended workflow instance will not be able to run until it has been unsuspended.</span></span>

 <span data-ttu-id="fa471-107">El ejemplo muestra cómo se puede implementar una utilidad de línea de comandos para consultar las instancias suspendidas y cómo otorgarle al usuario la opción de reanudar o finalizar la instancia.</span><span class="sxs-lookup"><span data-stu-id="fa471-107">The sample shows how a command-line utility can be implemented to query for suspended instances, and how to give the user the option to resume or terminate the instance.</span></span> <span data-ttu-id="fa471-108">En este ejemplo, un servicio de flujo de trabajo produce una excepción de forma intencionada, haciendo que se suspenda.</span><span class="sxs-lookup"><span data-stu-id="fa471-108">In this sample, a workflow service intentionally throws an exception, causing it to become suspended.</span></span> <span data-ttu-id="fa471-109">La utilidad de línea de comandos se puede utilizar a continuación para consultar la instancia y reanudarla o finalizarla.</span><span class="sxs-lookup"><span data-stu-id="fa471-109">The command-line utility can then be used to query for the instance and subsequently resume or terminate the instance.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="fa471-110">Demostraciones</span><span class="sxs-lookup"><span data-stu-id="fa471-110">Demonstrates</span></span>
 <span data-ttu-id="fa471-111"><xref:System.ServiceModel.WorkflowServiceHost> con <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> y <xref:System.ServiceModel.Activities.WorkflowControlEndpoint> en Windows Workflow Foundation (WF).</span><span class="sxs-lookup"><span data-stu-id="fa471-111"><xref:System.ServiceModel.WorkflowServiceHost> with <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> and <xref:System.ServiceModel.Activities.WorkflowControlEndpoint> in Windows Workflow Foundation (WF).</span></span>

## <a name="discussion"></a><span data-ttu-id="fa471-112">Discusión</span><span class="sxs-lookup"><span data-stu-id="fa471-112">Discussion</span></span>
 <span data-ttu-id="fa471-113">La utilidad de línea de comandos implementada en este ejemplo es específica de la implementación del almacén de instancias de SQL que se distribuye con [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fa471-113">The command-line utility implemented in this sample is specific to the SQL instance store implementation that ships in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span></span> <span data-ttu-id="fa471-114">Si tiene una implementación personalizada del almacén de instancias, podrá adaptar esta utilidad reemplazando las implementaciones de `WorkflowInstanceCommand` en el ejemplo con implementaciones que sean específicas de su almacén de instancias.</span><span class="sxs-lookup"><span data-stu-id="fa471-114">If you have a custom implementation of the instance store, then you can adapt this utility by replacing the `WorkflowInstanceCommand` implementations in the sample with implementations that are specific to your instance store.</span></span>

 <span data-ttu-id="fa471-115">La implementación proporcionada ejecuta directamente comandos SQL en el almacén de instancias de SQL para enumerar las instancias suspendidas y se basa en un objeto <xref:System.ServiceModel.Activities.WorkflowControlEndpoint> agregado al host <xref:System.ServiceModel.WorkflowServiceHost> para reanudar o finalizar las instancias.</span><span class="sxs-lookup"><span data-stu-id="fa471-115">The provided implementation runs SQL commands against the SQL instance store directly to list suspended instances, and it relies on a <xref:System.ServiceModel.Activities.WorkflowControlEndpoint> added to the <xref:System.ServiceModel.WorkflowServiceHost> in order to resume or terminate the instances.</span></span>

#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="fa471-116">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="fa471-116">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="fa471-117">En este ejemplo se requiere que los siguientes componentes de Windows estén habilitados:</span><span class="sxs-lookup"><span data-stu-id="fa471-117">This sample requires that the following Windows components are enabled:</span></span>

    1. <span data-ttu-id="fa471-118">Microsoft Message Queuing (MSMQ)</span><span class="sxs-lookup"><span data-stu-id="fa471-118">Microsoft Message Queues (MSMQ) Server</span></span>

    2. <span data-ttu-id="fa471-119">SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="fa471-119">SQL Server Express</span></span>

2. <span data-ttu-id="fa471-120">Configure la base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fa471-120">Set up the SQL Server database.</span></span>

    1. <span data-ttu-id="fa471-121">En un símbolo del sistema de Visual Studio 2010, ejecute "Setup. cmd" desde el directorio de ejemplo SuspendedInstanceManagement, que hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fa471-121">From a Visual Studio 2010 command prompt, run "setup.cmd" from the SuspendedInstanceManagement sample directory, which does the following:</span></span>

        1. <span data-ttu-id="fa471-122">Crea una base de datos de persistencia mediante SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="fa471-122">Creates a persistence database using SQL Server Express.</span></span> <span data-ttu-id="fa471-123">Si la base de datos de persistencia ya existe, se quita y se vuelve a crear.</span><span class="sxs-lookup"><span data-stu-id="fa471-123">If the persistence database already exists, then it is dropped and re-created</span></span>

        2. <span data-ttu-id="fa471-124">Configura la base de datos para la persistencia.</span><span class="sxs-lookup"><span data-stu-id="fa471-124">Sets up the database for persistence.</span></span>

        3. <span data-ttu-id="fa471-125">Agrega IIS APPPOOL\DefaultAppPool y NT AUTHORITY\Network Service al rol InstanceStoreUsers que se definió al configurar la base de datos para la persistencia.</span><span class="sxs-lookup"><span data-stu-id="fa471-125">Adds IIS APPPOOL\DefaultAppPool and NT AUTHORITY\Network Service to the InstanceStoreUsers role that was defined when setting up the database for persistence.</span></span>

3. <span data-ttu-id="fa471-126">Configure la cola del servicio.</span><span class="sxs-lookup"><span data-stu-id="fa471-126">Set up the service queue.</span></span>

    1. <span data-ttu-id="fa471-127">En Visual Studio 2010, haga clic con el botón derecho en el proyecto **SampleWorkflowApp** y haga clic en **establecer como proyecto de inicio**.</span><span class="sxs-lookup"><span data-stu-id="fa471-127">In Visual Studio 2010, right-click the **SampleWorkflowApp** project and click **Set as Startup Project**.</span></span>

    2. <span data-ttu-id="fa471-128">Compile y ejecute SampleWorkflowApp presionando **F5**.</span><span class="sxs-lookup"><span data-stu-id="fa471-128">Compile and run the SampleWorkflowApp by pressing **F5**.</span></span> <span data-ttu-id="fa471-129">Esto creará la cola necesaria.</span><span class="sxs-lookup"><span data-stu-id="fa471-129">This will create the required queue.</span></span>

    3. <span data-ttu-id="fa471-130">Presione **entrar** para detener el SampleWorkflowApp.</span><span class="sxs-lookup"><span data-stu-id="fa471-130">Press **Enter** to stop the SampleWorkflowApp.</span></span>

    4. <span data-ttu-id="fa471-131">En un símbolo del sistema, ejecute Compmgmt.msc para abrir la consola Administración de equipos.</span><span class="sxs-lookup"><span data-stu-id="fa471-131">Open the Computer Management console by running Compmgmt.msc from a command prompt.</span></span>

    5. <span data-ttu-id="fa471-132">Expanda **servicios y aplicaciones**, **Message Queue Server**, **colas privadas**.</span><span class="sxs-lookup"><span data-stu-id="fa471-132">Expand **Service and Applications**, **Message Queuing**, **Private Queues**.</span></span>

    6. <span data-ttu-id="fa471-133">Haga clic con el botón derecho en la cola **ReceiveTx** y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="fa471-133">Right click the **ReceiveTx** queue and select **Properties**.</span></span>

    7. <span data-ttu-id="fa471-134">Seleccione la **pestaña seguridad** y permita **que todos** tengan permisos para **recibir mensajes**, **Inspeccionar mensaje**y **Enviar mensaje**.</span><span class="sxs-lookup"><span data-stu-id="fa471-134">Select the **Security** tab and allow **Everyone** to have permissions to **Receive Message**, **Peek Message**, and **Send Message**.</span></span>

4. <span data-ttu-id="fa471-135">Ejecute el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="fa471-135">Now, run the sample.</span></span>

    1. <span data-ttu-id="fa471-136">En Visual Studio 2010, vuelva a ejecutar el proyecto SampleWorkflowApp sin depurar presionando **Ctrl + F5**.</span><span class="sxs-lookup"><span data-stu-id="fa471-136">In Visual Studio 2010, run the SampleWorkflowApp project again without debugging by pressing **Ctrl+F5**.</span></span> <span data-ttu-id="fa471-137">En la ventana de la consola se imprimirán dos direcciones de extremo: una para el extremo de la aplicación y otra procedente de <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="fa471-137">Two endpoint addresses will be printed in the console window: one for the application endpoint and then other from the <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>.</span></span> <span data-ttu-id="fa471-138">A continuación, se crea una instancia de flujo de trabajo y en la ventana de la consola aparecerán los registros de seguimiento de esa instancia.</span><span class="sxs-lookup"><span data-stu-id="fa471-138">A workflow instance is then created, and tracking records for that instance will appear in the console window.</span></span> <span data-ttu-id="fa471-139">La instancia de flujo de trabajo producirá una excepción que hará que la instancia se suspenda y se anule.</span><span class="sxs-lookup"><span data-stu-id="fa471-139">The workflow instance will throw an exception causing the instance to be suspended and aborted.</span></span>

    2. <span data-ttu-id="fa471-140">La utilidad de línea de comandos se puede utilizar a continuación para realizar más acciones en cualquiera de estas instancias.</span><span class="sxs-lookup"><span data-stu-id="fa471-140">The command-line utility can then be used to take further action on any of these instances.</span></span> <span data-ttu-id="fa471-141">La sintaxis para los argumentos de la línea de comandos es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="fa471-141">The syntax for command line arguments is as follows::</span></span>

         `SuspendedInstanceManagement -Command:[CommandName] -Server:[ServerName] -Database:[DatabaseName] -InstanceId:[InstanceId]`

         <span data-ttu-id="fa471-142">Los comandos admitidos son: `Query`, `Resume` y `Terminate`.</span><span class="sxs-lookup"><span data-stu-id="fa471-142">The supported commands are: `Query`, `Resume`, and `Terminate`.</span></span>  <span data-ttu-id="fa471-143">El modificador InstanceId solo es necesario para las operaciones `Resume` y `Terminate`.</span><span class="sxs-lookup"><span data-stu-id="fa471-143">The InstanceId switch is only required for `Resume` and `Terminate` operations.</span></span>

#### <a name="to-cleanup-optional"></a><span data-ttu-id="fa471-144">Para realizar la limpieza (Opcional)</span><span class="sxs-lookup"><span data-stu-id="fa471-144">To cleanup (Optional)</span></span>

1. <span data-ttu-id="fa471-145">En un símbolo del sistema de `vs2010`, ejecute Compmgmt.msc para abrir la consola Administración de equipos.</span><span class="sxs-lookup"><span data-stu-id="fa471-145">Open the Computer Management console by running Compmgmt.msc from a `vs2010` command prompt.</span></span>

2. <span data-ttu-id="fa471-146">Expanda **servicios y aplicaciones**, **Message Queue Server**, **colas privadas**.</span><span class="sxs-lookup"><span data-stu-id="fa471-146">Expand **Service and Applications**, **Message Queuing**, **Private Queues**.</span></span>

3. <span data-ttu-id="fa471-147">Elimine la cola **ReceiveTx** .</span><span class="sxs-lookup"><span data-stu-id="fa471-147">Delete the **ReceiveTx** queue.</span></span>

4. <span data-ttu-id="fa471-148">Para quitar la base de datos de persistencia, ejecute cleanup.cmd.</span><span class="sxs-lookup"><span data-stu-id="fa471-148">To remove the persistence database, run cleanup.cmd.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fa471-149">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="fa471-149">The samples may already be installed on your machine.</span></span> <span data-ttu-id="fa471-150">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="fa471-150">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="fa471-151">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fa471-151">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="fa471-152">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="fa471-152">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Application\SuspendedInstanceManagement`
