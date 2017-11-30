---
title: Obtener acceso a OperationContext
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4e92efe8-7e79-41f3-b50e-bdc38b9f41f8
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 861329c3945a53bf6c8ceeb7487aa0ef9902c93a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="accessing-operationcontext"></a><span data-ttu-id="fb347-102">Obtener acceso a OperationContext</span><span class="sxs-lookup"><span data-stu-id="fb347-102">Accessing OperationContext</span></span>
<span data-ttu-id="fb347-103">Este ejemplo se muestra cómo las actividades de mensajería (<xref:System.ServiceModel.Activities.Receive> y <xref:System.ServiceModel.Activities.Send>) puede utilizarse con una actividad de ámbito personalizada para tener acceso a <xref:System.ServiceModel.OperationContext.Current%2A> y adjuntar o recuperar un encabezado de mensaje personalizado dentro de un mensaje entrante o saliente.</span><span class="sxs-lookup"><span data-stu-id="fb347-103">This sample demonstrates how the messaging activities (<xref:System.ServiceModel.Activities.Receive> and <xref:System.ServiceModel.Activities.Send>) can be used with a custom scope activity to access <xref:System.ServiceModel.OperationContext.Current%2A> and attach or retrieve a custom message header within an outgoing or incoming message.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="fb347-104">Demostraciones</span><span class="sxs-lookup"><span data-stu-id="fb347-104">Demonstrates</span></span>  
 <span data-ttu-id="fb347-105">Actividades de mensajería, <xref:System.ServiceModel.Activities.ISendMessageCallback>, <xref:System.ServiceModel.Activities.IReceiveMessageCallback>.</span><span class="sxs-lookup"><span data-stu-id="fb347-105">Messaging Activities, <xref:System.ServiceModel.Activities.ISendMessageCallback>, <xref:System.ServiceModel.Activities.IReceiveMessageCallback>.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="fb347-106">Explicación</span><span class="sxs-lookup"><span data-stu-id="fb347-106">Discussion</span></span>  
 <span data-ttu-id="fb347-107">En este ejemplo se muestra cómo utilizar puntos de extensibilidad (<xref:System.ServiceModel.Activities.ISendMessageCallback> y <xref:System.ServiceModel.Activities.IReceiveMessageCallback>) en las actividades de mensajería para tener acceso a <xref:System.ServiceModel.OperationContext.Current%2A>.</span><span class="sxs-lookup"><span data-stu-id="fb347-107">This sample shows how to use extensibility points (<xref:System.ServiceModel.Activities.ISendMessageCallback>) <xref:System.ServiceModel.Activities.IReceiveMessageCallback>) in the messaging activities to access <xref:System.ServiceModel.OperationContext.Current%2A>.</span></span> <span data-ttu-id="fb347-108">Las devoluciones de llamada se registran dentro del tiempo de ejecución del flujo de trabajo como una implementación de <xref:System.Activities.IExecutionProperty> que utilizan las actividades de mensajería en la ejecución.</span><span class="sxs-lookup"><span data-stu-id="fb347-108">The callbacks are registered within the workflow runtime as an implementation of <xref:System.Activities.IExecutionProperty> that is picked up by the messaging activities upon execution.</span></span> <span data-ttu-id="fb347-109">Se ven afectadas todas las actividades de mensajería incluidas en el mismo ámbito que la implementación de <xref:System.Activities.IExecutionProperty>.</span><span class="sxs-lookup"><span data-stu-id="fb347-109">Any messaging activity in the same scope as that <xref:System.Activities.IExecutionProperty> implementation is affected.</span></span> <span data-ttu-id="fb347-110">Concretamente, en este ejemplo se utiliza una actividad de ámbito personalizada para exigir el comportamiento de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="fb347-110">In particular, this sample uses a custom scope activity to enforce the callback behavior.</span></span> <span data-ttu-id="fb347-111">En el flujo de trabajo del cliente se utiliza la interfaz <xref:System.ServiceModel.Activities.ISendMessageCallback> para incluir la propiedad <xref:System.Activities.WorkflowApplication.Id%2A> del flujo de trabajo como una clase <xref:System.ServiceModel.Channels.MessageHeader> de salida.</span><span class="sxs-lookup"><span data-stu-id="fb347-111">The <xref:System.ServiceModel.Activities.ISendMessageCallback> is used in the client workflow to include the workflow’s <xref:System.Activities.WorkflowApplication.Id%2A> as an outgoing <xref:System.ServiceModel.Channels.MessageHeader>.</span></span> <span data-ttu-id="fb347-112">A continuación, este encabezado se utiliza en el servicio mediante la interfaz <xref:System.ServiceModel.Activities.IReceiveMessageCallback>, y su valor se imprime en la consola.</span><span class="sxs-lookup"><span data-stu-id="fb347-112">This header is then picked up in the service using the <xref:System.ServiceModel.Activities.IReceiveMessageCallback> and the value of the header is printed out to the console.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="fb347-113">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="fb347-113">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="fb347-114">En este ejemplo se expone un servicio del flujo de trabajo mediante puntos de conexión HTTP.</span><span class="sxs-lookup"><span data-stu-id="fb347-114">This sample exposes a workflow service using HTTP endpoints.</span></span> <span data-ttu-id="fb347-115">Para ejecutar este ejemplo, correcto ACL de dirección URL debe agregarse (vea [configurar HTTP y HTTPS](http://go.microsoft.com/fwlink/?LinkId=70353) para obtener más detalles), ya sea ejecutando Visual Studio como administrador o ejecutando el siguiente comando en un símbolo del sistema con privilegios elevados para agregar las ACL adecuadas.</span><span class="sxs-lookup"><span data-stu-id="fb347-115">To run this sample, proper URL ACLs must be added (see [Configuring HTTP and HTTPS](http://go.microsoft.com/fwlink/?LinkId=70353) for details), either by running Visual Studio as Administrator or by executing the following command at an elevated prompt to add the appropriate ACLs.</span></span> <span data-ttu-id="fb347-116">Asegúrese de que su dominio y su nombre de usuario se sustituyen.</span><span class="sxs-lookup"><span data-stu-id="fb347-116">Ensure that your Domain and Username are substituted.</span></span>  
  
    ```  
    netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%  
    ```  
  
2.  <span data-ttu-id="fb347-117">Una vez agregadas las listas de control de acceso de dirección URL, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="fb347-117">Once the URL ACLs are added, use the following steps.</span></span>  
  
    1.  <span data-ttu-id="fb347-118">Compile la solución.</span><span class="sxs-lookup"><span data-stu-id="fb347-118">Build the solution.</span></span>  
  
    2.  <span data-ttu-id="fb347-119">Establezca varios proyectos de inicio haciendo clic en la solución y seleccione **Establecer proyectos de inicio**.</span><span class="sxs-lookup"><span data-stu-id="fb347-119">Set multiple start-up projects by right-clicking the solution and selecting **Set Startup Projects**.</span></span>  
  
    3.  <span data-ttu-id="fb347-120">Agregar **servicio** y **cliente** (en ese orden) como varios proyectos de inicio.</span><span class="sxs-lookup"><span data-stu-id="fb347-120">Add **Service** and **Client** (in that order) as multiple start-up projects.</span></span>  
  
    4.  <span data-ttu-id="fb347-121">Ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fb347-121">Run the application.</span></span> <span data-ttu-id="fb347-122">La consola del cliente muestra un flujo de trabajo que se ejecuta dos veces y la ventana Service muestra el identificador de instancia de estos flujos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="fb347-122">The client console shows a workflow running twice and the Service window shows the instance ID of those workflows.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fb347-123">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="fb347-123">The samples may already be installed on your machine.</span></span> <span data-ttu-id="fb347-124">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="fb347-124">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="fb347-125">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fb347-125">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="fb347-126">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="fb347-126">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\Accessing Operation Context`
