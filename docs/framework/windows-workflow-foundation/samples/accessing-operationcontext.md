---
description: Más información acerca de cómo obtener acceso a OperationContext
title: Obtener acceso a OperationContext
ms.date: 03/30/2017
ms.assetid: 4e92efe8-7e79-41f3-b50e-bdc38b9f41f8
ms.openlocfilehash: 768475f115f653630aaedeee976d0c96bc9e4dd7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792627"
---
# <a name="accessing-operationcontext"></a><span data-ttu-id="a4434-103">Obtener acceso a OperationContext</span><span class="sxs-lookup"><span data-stu-id="a4434-103">Accessing OperationContext</span></span>

<span data-ttu-id="a4434-104">Este ejemplo muestra cómo se pueden utilizar las actividades de mensajería ( <xref:System.ServiceModel.Activities.Receive> y <xref:System.ServiceModel.Activities.Send> ) con una actividad de ámbito personalizada para tener acceso <xref:System.ServiceModel.OperationContext.Current%2A> y adjuntar o recuperar un encabezado de mensaje personalizado dentro de un mensaje saliente o entrante.</span><span class="sxs-lookup"><span data-stu-id="a4434-104">This sample demonstrates how the messaging activities (<xref:System.ServiceModel.Activities.Receive> and <xref:System.ServiceModel.Activities.Send>) can be used with a custom scope activity to access <xref:System.ServiceModel.OperationContext.Current%2A> and attach or retrieve a custom message header within an outgoing or incoming message.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="a4434-105">Muestra</span><span class="sxs-lookup"><span data-stu-id="a4434-105">Demonstrates</span></span>  

 <span data-ttu-id="a4434-106">Actividades de mensajería, <xref:System.ServiceModel.Activities.ISendMessageCallback>, <xref:System.ServiceModel.Activities.IReceiveMessageCallback>.</span><span class="sxs-lookup"><span data-stu-id="a4434-106">Messaging Activities, <xref:System.ServiceModel.Activities.ISendMessageCallback>, <xref:System.ServiceModel.Activities.IReceiveMessageCallback>.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="a4434-107">Debate</span><span class="sxs-lookup"><span data-stu-id="a4434-107">Discussion</span></span>  

 <span data-ttu-id="a4434-108">En este ejemplo se muestra cómo utilizar puntos de extensibilidad (<xref:System.ServiceModel.Activities.ISendMessageCallback> y <xref:System.ServiceModel.Activities.IReceiveMessageCallback>) en las actividades de mensajería para tener acceso a <xref:System.ServiceModel.OperationContext.Current%2A>.</span><span class="sxs-lookup"><span data-stu-id="a4434-108">This sample shows how to use extensibility points (<xref:System.ServiceModel.Activities.ISendMessageCallback>) <xref:System.ServiceModel.Activities.IReceiveMessageCallback>) in the messaging activities to access <xref:System.ServiceModel.OperationContext.Current%2A>.</span></span> <span data-ttu-id="a4434-109">Las devoluciones de llamada se registran dentro del tiempo de ejecución del flujo de trabajo como una implementación de <xref:System.Activities.IExecutionProperty> que utilizan las actividades de mensajería en la ejecución.</span><span class="sxs-lookup"><span data-stu-id="a4434-109">The callbacks are registered within the workflow runtime as an implementation of <xref:System.Activities.IExecutionProperty> that is picked up by the messaging activities upon execution.</span></span> <span data-ttu-id="a4434-110">Se ven afectadas todas las actividades de mensajería incluidas en el mismo ámbito que la implementación de <xref:System.Activities.IExecutionProperty>.</span><span class="sxs-lookup"><span data-stu-id="a4434-110">Any messaging activity in the same scope as that <xref:System.Activities.IExecutionProperty> implementation is affected.</span></span> <span data-ttu-id="a4434-111">Concretamente, en este ejemplo se utiliza una actividad de ámbito personalizada para exigir el comportamiento de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="a4434-111">In particular, this sample uses a custom scope activity to enforce the callback behavior.</span></span> <span data-ttu-id="a4434-112">En el flujo de trabajo del cliente se utiliza la interfaz <xref:System.ServiceModel.Activities.ISendMessageCallback> para incluir la propiedad <xref:System.Activities.WorkflowApplication.Id%2A> del flujo de trabajo como una clase <xref:System.ServiceModel.Channels.MessageHeader> de salida.</span><span class="sxs-lookup"><span data-stu-id="a4434-112">The <xref:System.ServiceModel.Activities.ISendMessageCallback> is used in the client workflow to include the workflow’s <xref:System.Activities.WorkflowApplication.Id%2A> as an outgoing <xref:System.ServiceModel.Channels.MessageHeader>.</span></span> <span data-ttu-id="a4434-113">A continuación, este encabezado se utiliza en el servicio mediante la interfaz <xref:System.ServiceModel.Activities.IReceiveMessageCallback>, y su valor se imprime en la consola.</span><span class="sxs-lookup"><span data-stu-id="a4434-113">This header is then picked up in the service using the <xref:System.ServiceModel.Activities.IReceiveMessageCallback> and the value of the header is printed out to the console.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="a4434-114">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="a4434-114">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="a4434-115">En este ejemplo se expone un servicio del flujo de trabajo mediante puntos de conexión HTTP.</span><span class="sxs-lookup"><span data-stu-id="a4434-115">This sample exposes a workflow service using HTTP endpoints.</span></span> <span data-ttu-id="a4434-116">Para ejecutar este ejemplo, se deben agregar las ACL de dirección URL adecuadas (consulte [configuración de http y https](../../wcf/feature-details/configuring-http-and-https.md) para obtener detalles), ya sea ejecutando Visual Studio como administrador o ejecutando el siguiente comando en un símbolo del sistema con privilegios elevados para agregar las ACL adecuadas.</span><span class="sxs-lookup"><span data-stu-id="a4434-116">To run this sample, proper URL ACLs must be added (see [Configuring HTTP and HTTPS](../../wcf/feature-details/configuring-http-and-https.md) for details), either by running Visual Studio as Administrator or by executing the following command at an elevated prompt to add the appropriate ACLs.</span></span> <span data-ttu-id="a4434-117">Asegúrese de que su dominio y su nombre de usuario se sustituyen.</span><span class="sxs-lookup"><span data-stu-id="a4434-117">Ensure that your Domain and Username are substituted.</span></span>  
  
    ```console  
    netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%  
    ```  
  
2. <span data-ttu-id="a4434-118">Una vez agregadas las listas de control de acceso de dirección URL, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="a4434-118">Once the URL ACLs are added, use the following steps.</span></span>  
  
    1. <span data-ttu-id="a4434-119">Compile la solución.</span><span class="sxs-lookup"><span data-stu-id="a4434-119">Build the solution.</span></span>  
  
    2. <span data-ttu-id="a4434-120">Establezca varios proyectos de inicio haciendo clic con el botón derecho en la solución y seleccionando **establecer proyectos de inicio**.</span><span class="sxs-lookup"><span data-stu-id="a4434-120">Set multiple start-up projects by right-clicking the solution and selecting **Set Startup Projects**.</span></span>  
  
    3. <span data-ttu-id="a4434-121">Agregue el **servicio** y el **cliente** (en ese orden) como varios proyectos de inicio.</span><span class="sxs-lookup"><span data-stu-id="a4434-121">Add **Service** and **Client** (in that order) as multiple start-up projects.</span></span>  
  
    4. <span data-ttu-id="a4434-122">Ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a4434-122">Run the application.</span></span> <span data-ttu-id="a4434-123">La consola del cliente muestra un flujo de trabajo que se ejecuta dos veces y la ventana Service muestra el identificador de instancia de estos flujos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a4434-123">The client console shows a workflow running twice and the Service window shows the instance ID of those workflows.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="a4434-124">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="a4434-124">The samples may already be installed on your machine.</span></span> <span data-ttu-id="a4434-125">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="a4434-125">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="a4434-126">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="a4434-126">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a4434-127">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="a4434-127">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\Accessing Operation Context`
