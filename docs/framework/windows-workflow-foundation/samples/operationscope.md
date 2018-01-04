---
title: OperationScope
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 56206a21-1e63-422d-b92a-e5d8b713e707
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 837be2de516f604dd6869449d99df238fb6dbd24
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="operationscope"></a><span data-ttu-id="104f8-102">OperationScope</span><span class="sxs-lookup"><span data-stu-id="104f8-102">OperationScope</span></span>
<span data-ttu-id="104f8-103">En este ejemplo se muestra cómo las actividades de mensajería, <xref:System.ServiceModel.Activities.Receive> y <xref:System.ServiceModel.Activities.SendReply>, se pueden utilizar para exponer una actividad personalizada existente como una operación en un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="104f8-103">This sample demonstrates how the messaging activities, <xref:System.ServiceModel.Activities.Receive> and <xref:System.ServiceModel.Activities.SendReply> can be used to expose an existing custom activity as an operation in a workflow service.</span></span> <span data-ttu-id="104f8-104">En este ejemplo se incluye una nueva actividad personalizada denominada `OperationScope`.</span><span class="sxs-lookup"><span data-stu-id="104f8-104">This sample includes a new custom activity called an `OperationScope`.</span></span> <span data-ttu-id="104f8-105">Pretende facilitar el desarrollo de un servicio de flujo de trabajo permitiendo a los usuarios crear el cuerpo de sus operaciones por separado como actividades personalizadas y exponiéndolas fácilmente como operaciones del servicio mediante la actividad `OperationScope`.</span><span class="sxs-lookup"><span data-stu-id="104f8-105">It is intended to ease the development of a workflow service by allowing users to author the body of their operations separately as custom activities and then easily exposing them as service operations using the `OperationScope` activity.</span></span> <span data-ttu-id="104f8-106">Por ejemplo, una actividad `Add` personalizada que toma dos argumentos `in` y devuelve un argumento `out` se puede exponer como una operación `Add` en el servicio de flujo de trabajo si se coloca en una actividad `OperationScope`.</span><span class="sxs-lookup"><span data-stu-id="104f8-106">For example, a custom `Add` activity that takes two `in` arguments and returns one `out` argument could be exposed as an `Add` operation on the workflow service by dropping it into an `OperationScope`.</span></span>  
  
 <span data-ttu-id="104f8-107">El ámbito funciona inspeccionando la actividad proporcionada como su cuerpo.</span><span class="sxs-lookup"><span data-stu-id="104f8-107">The scope works by inspecting the activity provided as its body.</span></span> <span data-ttu-id="104f8-108">Se supone que los argumentos `in` no enlazados son entradas del mensaje entrante.</span><span class="sxs-lookup"><span data-stu-id="104f8-108">Any unbound `in` arguments are assumed to be inputs from the incoming message.</span></span> <span data-ttu-id="104f8-109">Se supone que todos los argumentos `out`, independientemente de si están enlazados, son salidas en el mensaje de respuesta subsiguiente.</span><span class="sxs-lookup"><span data-stu-id="104f8-109">All `out` arguments, regardless of whether they are bound, are assumed to be outputs in the subsequent reply message.</span></span> <span data-ttu-id="104f8-110">El nombre de la operación expuesta se toma del nombre para mostrar de la actividad `OperationScope`.</span><span class="sxs-lookup"><span data-stu-id="104f8-110">The exposed operation’s name is taken from the display name of the `OperationScope` activity.</span></span> <span data-ttu-id="104f8-111">El resultado final es que la actividad del cuerpo se incluye en las actividades <xref:System.ServiceModel.Activities.Receive> y <xref:System.ServiceModel.Activities.SendReply> con los parámetros de los mensajes enlazados a los argumentos de la actividad.</span><span class="sxs-lookup"><span data-stu-id="104f8-111">The end result is that the body activity is wrapped in a <xref:System.ServiceModel.Activities.Receive> and <xref:System.ServiceModel.Activities.SendReply> with the parameters from the messages bound to the arguments of the activity.</span></span>  
  
 <span data-ttu-id="104f8-112">En este ejemplo se expone un servicio del flujo de trabajo mediante extremos HTTP.</span><span class="sxs-lookup"><span data-stu-id="104f8-112">This sample exposes a workflow service using HTTP endpoints.</span></span> <span data-ttu-id="104f8-113">Para ejecutarlo, se deben agregar las ACL de dirección URL apropiadas.</span><span class="sxs-lookup"><span data-stu-id="104f8-113">To run, proper URL ACLs must be added.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="104f8-114">[Configurar HTTP y HTTPS](http://go.microsoft.com/fwlink/?LinkId=70353).</span><span class="sxs-lookup"><span data-stu-id="104f8-114"> [Configuring HTTP and HTTPS](http://go.microsoft.com/fwlink/?LinkId=70353).</span></span> <span data-ttu-id="104f8-115">Ejecutar el comando siguiente en un símbolo del sistema con privilegios elevados agrega las ACL adecuadas (asegúrese de que su dominio y el nombre de usuario se sustituyen por dominio %\\% UserName %).</span><span class="sxs-lookup"><span data-stu-id="104f8-115">Executing the following command at an elevated prompt adds the appropriate ACLs (ensure that your Domain and Username are substituted for %DOMAIN%\\%UserName%).</span></span>  
  
 <span data-ttu-id="104f8-116">**netsh http agregar dirección url urlacl = http: / / +: 8000 / usuario = % DOMAIN %\\% UserName %**</span><span class="sxs-lookup"><span data-stu-id="104f8-116">**netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\\%UserName%**</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="104f8-117">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="104f8-117">To run the sample</span></span>  
  
1.  <span data-ttu-id="104f8-118">Abra la solución OperationScope.sln en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="104f8-118">Open the OperationScope.sln solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="104f8-119">Establezca varios proyectos de inicio haciendo clic en la solución en el Explorador de soluciones y seleccionando **Establecer proyectos de inicio**.</span><span class="sxs-lookup"><span data-stu-id="104f8-119">Set multiple start-up projects by right-clicking the solution in Solution Explorer and selecting **Set Startup Projects**.</span></span> <span data-ttu-id="104f8-120">Agregue Scenario y Scenario_Client (en ese orden) como proyectos de inicio múltiples.</span><span class="sxs-lookup"><span data-stu-id="104f8-120">Add Scenario and Scenario_Client (in that order) as multiple start-up projects.</span></span>  
  
3.  <span data-ttu-id="104f8-121">Presione Ctrl+MAYÚS+B para compilar la solución.</span><span class="sxs-lookup"><span data-stu-id="104f8-121">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
    > [!WARNING]
    >  <span data-ttu-id="104f8-122">Este paso es necesario para ver el flujo de trabajo de BankService.xaml debido a la actividad `OperationScope` personalizada.</span><span class="sxs-lookup"><span data-stu-id="104f8-122">This step is required to view the BankService.xaml workflow due to the custom activity `OperationScope`.</span></span>  
  
4.  <span data-ttu-id="104f8-123">Presione CTRL+F5 para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="104f8-123">Press CTRL+F5 to run the application.</span></span> <span data-ttu-id="104f8-124">La consola de Scenario_Client solicita las entradas; el resultado correspondiente se ve en la consola de Scenario.</span><span class="sxs-lookup"><span data-stu-id="104f8-124">The Scenario_Client console prompts you for inputs and the corresponding output is seen in the Scenario console.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="104f8-125">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="104f8-125">The samples may already be installed on your machine.</span></span> <span data-ttu-id="104f8-126">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="104f8-126">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="104f8-127">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="104f8-127">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="104f8-128">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="104f8-128">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\OperationScope`