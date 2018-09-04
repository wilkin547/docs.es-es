---
title: Ejemplo de punto de conexión de administración de flujo de trabajo
ms.date: 03/30/2017
ms.assetid: 3ac6e08f-c43d-4bb7-83c3-e3890a4dac03
ms.openlocfilehash: 3d99cbef20895381f5e40ee939e1d94a409f1391
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43536719"
---
# <a name="workflow-management-endpoint-sample"></a><span data-ttu-id="69873-102">Ejemplo de punto de conexión de administración de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="69873-102">Workflow Management Endpoint Sample</span></span>
<span data-ttu-id="69873-103">En este ejemplo se muestra cómo un punto de conexión de control de flujo de trabajo se puede utilizar para crear y ejecutar flujos de trabajo de forma local y remota.</span><span class="sxs-lookup"><span data-stu-id="69873-103">This sample shows how a workflow control endpoint can be used to create and run workflows both locally and remotely.</span></span> <span data-ttu-id="69873-104">En el ejemplo se muestra cómo hospedar un extremo de control y cómo escribir clientes que llamen al extremo de control para crear y ejecutar la instancia de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="69873-104">The sample demonstrates how to host a control endpoint and write clients that call the control endpoint to create and run the instance of a workflow.</span></span> <span data-ttu-id="69873-105">El flujo de trabajo no es un servicio.</span><span class="sxs-lookup"><span data-stu-id="69873-105">The workflow is not a service.</span></span>  
  
 <span data-ttu-id="69873-106">En el lado del servicio del ejemplo un flujo de trabajo se hospeda con WorkflowServiceHost y se agrega un WorkflowControlEndpoint de modo que los clientes puedan realizar operaciones de control (Suspend, Start, etc.).</span><span class="sxs-lookup"><span data-stu-id="69873-106">On the service side of the sample a workflow is hosted with WorkflowServiceHost and a WorkflowControlEndpoint is added so that clients can perform control operations (Suspend, Start, etc).</span></span> <span data-ttu-id="69873-107">También se agrega un CreationEndpoint definido por el usuario para permitir la creación del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="69873-107">A user-defined CreationEndpoint is also added to allow the workflow to be created.</span></span> <span data-ttu-id="69873-108">El servicio usará posteriormente estos extremos para iniciar el flujo de trabajo en un estado suspendido y después reanudar el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="69873-108">The service then uses these endpoints to start the workflow in a suspended state and then resume the workflow.</span></span> <span data-ttu-id="69873-109">El cliente realiza las mismas operaciones pero desde el código de cliente.</span><span class="sxs-lookup"><span data-stu-id="69873-109">The client performs the same operations but from the client code.</span></span> <span data-ttu-id="69873-110">Para obtener más información acerca de estas interfaces, vea [punto de conexión de Control de flujo de trabajo](../../../../docs/framework/wcf/feature-details/workflow-control-endpoint.md) y [Cómo: hospedar un flujo de trabajo no perteneciente al servicio en IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-non-service-workflow-in-iis.md)</span><span class="sxs-lookup"><span data-stu-id="69873-110">For more information about these interfaces see, [Workflow Control Endpoint](../../../../docs/framework/wcf/feature-details/workflow-control-endpoint.md) and [How to: Host a non-service workflow in IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-non-service-workflow-in-iis.md)</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="69873-111">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="69873-111">To run the sample</span></span>  
  
1.  <span data-ttu-id="69873-112">Ejecute [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="69873-112">Run [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] with administrator privileges.</span></span>  
  
2.  <span data-ttu-id="69873-113">Abra la solución ManagementEndpoint.sln en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="69873-113">Open the ManagementEndpoint.sln solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
3.  <span data-ttu-id="69873-114">Para compilar la solución, presione CTRL + MAYÚS + B o seleccione **compilar solución** desde el **compilar** menú.</span><span class="sxs-lookup"><span data-stu-id="69873-114">To build the solution, press CTRL+SHIFT+B or select **Build Solution** from the **Build** menu.</span></span>  
  
4.  <span data-ttu-id="69873-115">Inicie la aplicación ManagementEndpoint.exe.</span><span class="sxs-lookup"><span data-stu-id="69873-115">Start the ManagementEndpoint.exe application.</span></span>  
  
5.  <span data-ttu-id="69873-116">Inicie la aplicación Client.exe.</span><span class="sxs-lookup"><span data-stu-id="69873-116">Start the Client.exe application.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="69873-117">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="69873-117">The samples may already be installed on your computer.</span></span> <span data-ttu-id="69873-118">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="69873-118">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="69873-119">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="69873-119">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="69873-120">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="69873-120">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\ManagementEndpoint`