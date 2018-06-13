---
title: Retraso duradero
ms.date: 03/30/2017
ms.assetid: 220ec240-b958-430c-81ff-b734a6aa97ae
ms.openlocfilehash: 5307b8144e17f91cd3ba8c2e385492f86c167820
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33516027"
---
# <a name="durable-delay"></a><span data-ttu-id="c6e91-102">Retraso duradero</span><span class="sxs-lookup"><span data-stu-id="c6e91-102">Durable Delay</span></span>
<span data-ttu-id="c6e91-103">En este ejemplo se muestra cómo utilizar un retraso duradero, que es un retraso que conserva el flujo de trabajo en un dispositivo duradero durante el tiempo que dura.</span><span class="sxs-lookup"><span data-stu-id="c6e91-103">This sample demonstrates how to use a durable delay, which is a delay that persists the workflow to a durable device during the delay.</span></span> <span data-ttu-id="c6e91-104">El flujo de trabajo de muestra contiene dos mensajes a la consola, separados por un retraso.</span><span class="sxs-lookup"><span data-stu-id="c6e91-104">The sample workflow contains two messages to the console that are separated by a delay.</span></span> <span data-ttu-id="c6e91-105">Cuando el retraso se activa, el flujo de trabajo se descarga y espera 5 segundos en el almacén de instancias de flujo de trabajo antes de recargarse en la memoria.</span><span class="sxs-lookup"><span data-stu-id="c6e91-105">When the delay is triggered, the workflow is unloaded and waits 5 seconds in the workflow instance store before being reloaded in memory.</span></span>  
  
## <a name="workflow-details"></a><span data-ttu-id="c6e91-106">Detalles del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="c6e91-106">Workflow Details</span></span>  
 <span data-ttu-id="c6e91-107">El host de servicio de flujo de trabajo hospeda el flujo de trabajo y administra las instancias de flujo de trabajo cargándolas y descargándolas.</span><span class="sxs-lookup"><span data-stu-id="c6e91-107">The workflow service host hosts the workflow and manages the workflow instances by loading and unloading them.</span></span> <span data-ttu-id="c6e91-108">Para iniciar una instancia de la definición de flujo de trabajo, el ejemplo establece un proxy que envía un mensaje a la actividad <xref:System.ServiceModel.Activities.Receive> del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c6e91-108">To start an instance of the workflow definition, the sample sets a proxy that sends a message to the <xref:System.ServiceModel.Activities.Receive> activity in the workflow.</span></span> <span data-ttu-id="c6e91-109">La propiedad <xref:System.ServiceModel.Activities.Receive.CanCreateInstance%2A> se establece en `true`, lo que permite crear una nueva instancia del flujo de trabajo después de recibir un mensaje.</span><span class="sxs-lookup"><span data-stu-id="c6e91-109">The <xref:System.ServiceModel.Activities.Receive.CanCreateInstance%2A> property is set to `true`, enabling it to create a new instance of the workflow once it receives a message.</span></span>  
  
 <span data-ttu-id="c6e91-110">La siguiente lista detalla la configuración que realiza el host de servicio de flujo de trabajo durante la inicialización.</span><span class="sxs-lookup"><span data-stu-id="c6e91-110">The following list details the set-up by the workflow service host during initialization.</span></span>  
  
1.  <span data-ttu-id="c6e91-111">Crea un host de servicio con una dirección (http://localhost:8080/Client).</span><span class="sxs-lookup"><span data-stu-id="c6e91-111">Creates a service host with an address (http://localhost:8080/Client).</span></span>  
  
2.  <span data-ttu-id="c6e91-112">Crea un extremo en el host de servicio para habilitar la comunicación con la actividad <xref:System.ServiceModel.Activities.Receive> dentro del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c6e91-112">Creates an endpoint in the service host to enable communication with the <xref:System.ServiceModel.Activities.Receive> activity inside the workflow.</span></span>  
  
3.  <span data-ttu-id="c6e91-113">Configura un almacén de instancias de SQL.</span><span class="sxs-lookup"><span data-stu-id="c6e91-113">Sets up a SQL instance store.</span></span>  
  
4.  <span data-ttu-id="c6e91-114">Agrega un comportamiento de instancia de descarga que especifica las condiciones bajo las que el host de servicio de flujo de trabajo debe descargar una instancia de flujo de trabajo al almacén de persistencia de SQL.</span><span class="sxs-lookup"><span data-stu-id="c6e91-114">Adds an unload instance behavior that specifies the conditions under which the workflow service host should unload a workflow instance to the SQL persistence store.</span></span> <span data-ttu-id="c6e91-115">En este ejemplo, descarga la instancia de forma inmediata cuando el flujo de trabajo pasa a estado inactivo (cuando el retraso se activa).</span><span class="sxs-lookup"><span data-stu-id="c6e91-115">For this sample, it unloads the instance immediately after the workflow goes idle (when the delay is triggered).</span></span>  
  
5.  <span data-ttu-id="c6e91-116">Crea el proxy que envía un mensaje a la actividad <xref:System.ServiceModel.Activities.Receive> del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c6e91-116">Creates the proxy that sends a message to the <xref:System.ServiceModel.Activities.Receive> activity in the workflow.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="c6e91-117">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="c6e91-117">To use this sample</span></span>  
  
1.  <span data-ttu-id="c6e91-118">Configure la base de datos de persistencia.</span><span class="sxs-lookup"><span data-stu-id="c6e91-118">Set up the persistence database.</span></span>  
  
    1.  <span data-ttu-id="c6e91-119">Abra un símbolo del sistema de [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c6e91-119">Open a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt.</span></span>  
  
    2.  <span data-ttu-id="c6e91-120">Navegue hasta la [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] directorio (C:\Windows\Microsoft.NET\Framework\v4. X\\).</span><span class="sxs-lookup"><span data-stu-id="c6e91-120">Navigate to the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] directory (C:\Windows\Microsoft.NET\Framework\v4.X\\).</span></span>  
  
    3.  <span data-ttu-id="c6e91-121">Edite el archivo WorkflowManagementService.exe.config y agregue la siguiente cadena de conexión dentro del elemento <`database`>.</span><span class="sxs-lookup"><span data-stu-id="c6e91-121">Edit the WorkflowManagementService.exe.config file and add the following connection string inside the <`database`> element.</span></span>  
  
        ```xml  
        <database connectionString="Data Source=localhost\SQLEXPRESS;Initial Catalog=DefaultSampleStore;Integrated Security=True;Asynchronous Processing=True" />  
        ```  
  
    4.  <span data-ttu-id="c6e91-122">Desplácese hasta el directorio DurableDelay\CS.</span><span class="sxs-lookup"><span data-stu-id="c6e91-122">Navigate to the DurableDelay\CS directory.</span></span>  
  
    5.  <span data-ttu-id="c6e91-123">Ejecute Setup.cmd.</span><span class="sxs-lookup"><span data-stu-id="c6e91-123">Run Setup.cmd.</span></span>  
  
2.  <span data-ttu-id="c6e91-124">Ejecutar [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] con permisos elevados haciendo clic en el [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] icono y seleccione **ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="c6e91-124">Run [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] using elevated permissions by right-clicking the [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] icon and selecting **Run as administrator**.</span></span>  
  
3.  <span data-ttu-id="c6e91-125">Abra el archivo de solución Delay.sln.</span><span class="sxs-lookup"><span data-stu-id="c6e91-125">Open the Delay.sln solution file.</span></span>  
  
4.  <span data-ttu-id="c6e91-126">Presione Ctrl+MAYÚS+B para compilar la solución.</span><span class="sxs-lookup"><span data-stu-id="c6e91-126">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
5.  <span data-ttu-id="c6e91-127">Presione CTRL+F5 para ejecutar la solución.</span><span class="sxs-lookup"><span data-stu-id="c6e91-127">Press CTRL+F5 to run the solution.</span></span>  
  
#### <a name="to-uninstall-this-sample"></a><span data-ttu-id="c6e91-128">Para desinstalar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="c6e91-128">To uninstall this sample</span></span>  
  
1.  <span data-ttu-id="c6e91-129">Abra un símbolo del sistema de [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c6e91-129">Open a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt.</span></span>  
  
2.  <span data-ttu-id="c6e91-130">Desplácese hasta el directorio DurableDelay\CS.</span><span class="sxs-lookup"><span data-stu-id="c6e91-130">Navigate to the DurableDelay\CS directory.</span></span>  
  
3.  <span data-ttu-id="c6e91-131">Ejecute Cleanup.cmd.</span><span class="sxs-lookup"><span data-stu-id="c6e91-131">Run Cleanup.cmd.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c6e91-132">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="c6e91-132">The samples may already be installed on your machine.</span></span> <span data-ttu-id="c6e91-133">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="c6e91-133">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="c6e91-134">Si este directorio no existe, vaya a [Windows Communication Foundation (WCF) y ejemplos de Windows Workflow Foundation (WF) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="c6e91-134">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c6e91-135">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="c6e91-135">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\DurableDelay`