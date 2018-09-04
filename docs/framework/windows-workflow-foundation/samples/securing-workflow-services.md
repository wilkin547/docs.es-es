---
title: Proteger servicios de flujo de trabajo
ms.date: 03/30/2017
ms.assetid: 53f84ad5-1ed1-4114-8d0d-b12e8a021c6e
ms.openlocfilehash: 28c34ecf7d6d781bfa461b2737cb9325a657f47e
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43524340"
---
# <a name="securing-workflow-services"></a><span data-ttu-id="bc961-102">Proteger servicios de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="bc961-102">Securing Workflow Services</span></span>
<span data-ttu-id="bc961-103">En el ejemplo del servicio de flujo de trabajo seguro se muestran los siguientes procedimientos:</span><span class="sxs-lookup"><span data-stu-id="bc961-103">The Secured Workflow Service sample shows the following procedures:</span></span>  
  
-   <span data-ttu-id="bc961-104">Crear un servicio de flujo de trabajo básico mediante las actividades <xref:System.ServiceModel.Activities.Receive> y <xref:System.ServiceModel.Activities.SendReply>.</span><span class="sxs-lookup"><span data-stu-id="bc961-104">Creating a basic workflow service using the <xref:System.ServiceModel.Activities.Receive> and <xref:System.ServiceModel.Activities.SendReply> activities.</span></span>  
  
-   <span data-ttu-id="bc961-105">Mediante la configuración de Windows Communication Foundation (WCF) para definir puntos de conexión seguros para su uso por el servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="bc961-105">Using Windows Communication Foundation (WCF) configuration to define secure endpoints for use by the workflow service.</span></span>  
  
-   <span data-ttu-id="bc961-106">Crear notificaciones dentro de una directiva personalizada y utilizar <xref:System.ServiceModel.ServiceAuthorizationManager> para validarlas.</span><span class="sxs-lookup"><span data-stu-id="bc961-106">Creating claims inside a custom policy and using the <xref:System.ServiceModel.ServiceAuthorizationManager> to validate claims.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="bc961-107">Demostraciones</span><span class="sxs-lookup"><span data-stu-id="bc961-107">Demonstrates</span></span>  
 <span data-ttu-id="bc961-108">Usar la seguridad WCF para proteger la comunicación entre el cliente y el servicio de flujo de trabajo, con autorización basada en notificaciones</span><span class="sxs-lookup"><span data-stu-id="bc961-108">Using WCF security to secure communication between client and Workflow service, Claims based authorization</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="bc961-109">Explicación</span><span class="sxs-lookup"><span data-stu-id="bc961-109">Discussion</span></span>  
 <span data-ttu-id="bc961-110">Este ejemplo muestra el uso de la infraestructura de seguridad WCF para proteger un servicio de flujo de trabajo, tal como lo haría con un servicio WCF normal.</span><span class="sxs-lookup"><span data-stu-id="bc961-110">This sample demonstrates the use of WCF security infrastructure to secure a workflow service just like you would with a normal WCF service.</span></span> <span data-ttu-id="bc961-111">Concretamente, usa una notificación personalizada para la autorización.</span><span class="sxs-lookup"><span data-stu-id="bc961-111">Specifically, it uses a custom claim for authorization.</span></span> <span data-ttu-id="bc961-112">En este caso, utiliza <xref:System.ServiceModel.WSHttpBinding> y la seguridad de modo de mensaje con credenciales de Windows.</span><span class="sxs-lookup"><span data-stu-id="bc961-112">In this case, it uses <xref:System.ServiceModel.WSHttpBinding> and message mode security with Windows credentials.</span></span>  
  
 <span data-ttu-id="bc961-113">La interfaz <xref:System.IdentityModel.Policy.IAuthorizationPolicy> personalizada (`CustomNameCheckerPolicy`) comprueba el nombre de usuario de Windows del cliente y busca un carácter concreto.</span><span class="sxs-lookup"><span data-stu-id="bc961-113">The custom <xref:System.IdentityModel.Policy.IAuthorizationPolicy> (`CustomNameCheckerPolicy`) checks the client's Windows username and for a specific character.</span></span> <span data-ttu-id="bc961-114">Si ese carácter está presente, crea y agrega la notificación a la clase <xref:System.IdentityModel.Policy.EvaluationContext>.</span><span class="sxs-lookup"><span data-stu-id="bc961-114">If that character is present, it creates and adds the claim to the <xref:System.IdentityModel.Policy.EvaluationContext>.</span></span> <span data-ttu-id="bc961-115">Al llevar esto a cabo, la directiva personalizada indica que el cliente tiene este carácter en el nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="bc961-115">By doing this, the custom policy is making the statement that the client has this character in the username.</span></span> <span data-ttu-id="bc961-116">Esta notificación se puede consultar mientras dura la llamada.</span><span class="sxs-lookup"><span data-stu-id="bc961-116">This claim can be queried throughout the lifetime of the call.</span></span> <span data-ttu-id="bc961-117">Puede encontrar el carácter en `Constants.cs`.</span><span class="sxs-lookup"><span data-stu-id="bc961-117">You can find that character in `Constants.cs`.</span></span>  
  
 <span data-ttu-id="bc961-118">La directiva de autorización busca la notificación dentro de `SecureWorkFlowAuthZManager`.</span><span class="sxs-lookup"><span data-stu-id="bc961-118">The authorization policy looks for the claim inside the `SecureWorkFlowAuthZManager`.</span></span> <span data-ttu-id="bc961-119">Si la encuentra, devuelve `true` y permite que el flujo de trabajo continúe.</span><span class="sxs-lookup"><span data-stu-id="bc961-119">If it finds it, it returns `true` and allow the workflow to proceed.</span></span> <span data-ttu-id="bc961-120">De lo contrario, devuelve `false`, lo que produce que se devuelva un mensaje de acceso denegado al cliente.</span><span class="sxs-lookup"><span data-stu-id="bc961-120">Otherwise, it returns `false`, which causes an 'Access Denied' message to be returned to the client.</span></span> <span data-ttu-id="bc961-121">En el contexto hay otras notificaciones, que también se pueden examinar dentro de `SecureWorkFlowAuthZManager`.</span><span class="sxs-lookup"><span data-stu-id="bc961-121">Other claims are present in the context and can be examined as well inside the `SecureWorkFlowAuthZManager`.</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="bc961-122">Para ejecutar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="bc961-122">To run this sample</span></span>  
  
1.  <span data-ttu-id="bc961-123">Ejecute [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="bc961-123">Run [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] with administrator privileges.</span></span>  
  
2.  <span data-ttu-id="bc961-124">Cargue SecuringWorkflowServices.sln en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bc961-124">Load SecuringWorkflowServices.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
3.  <span data-ttu-id="bc961-125">Para compilar la solución, presione Ctrl+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="bc961-125">Press CTRL+SHIFT+B to compile the solution.</span></span>  
  
4.  <span data-ttu-id="bc961-126">Establezca el proyecto Service como proyecto de inicio para la solución.</span><span class="sxs-lookup"><span data-stu-id="bc961-126">Set the Service project as the start-up project for the solution.</span></span>  
  
5.  <span data-ttu-id="bc961-127">Para iniciar el servicio sin depurar, presione CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="bc961-127">Press CTRL+F5 to start the service without debugging.</span></span>  
  
6.  <span data-ttu-id="bc961-128">Establezca el proyecto Client como proyecto de inicio para la solución.</span><span class="sxs-lookup"><span data-stu-id="bc961-128">Set the Client project as the start-up project for the solution.</span></span>  
  
7.  <span data-ttu-id="bc961-129">Para iniciar el cliente sin depurar, presione CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="bc961-129">Press CTRL+F5 to start the client without debugging.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="bc961-130">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="bc961-130">The samples may already be installed on your machine.</span></span> <span data-ttu-id="bc961-131">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="bc961-131">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="bc961-132">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="bc961-132">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="bc961-133">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="bc961-133">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\SecuringWorkflowServices`
