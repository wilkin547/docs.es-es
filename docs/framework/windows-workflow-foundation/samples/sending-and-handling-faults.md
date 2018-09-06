---
title: Envío y control de errores
ms.date: 03/30/2017
ms.assetid: 98e8e04d-2ac9-4a33-ae08-462f757a7a14
ms.openlocfilehash: 896f209e7daeeab2bb33c1fde15298aae96c8776
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "44037716"
---
# <a name="sending-and-handling-faults"></a><span data-ttu-id="2edf5-102">Envío y control de errores</span><span class="sxs-lookup"><span data-stu-id="2edf5-102">Sending and Handling Faults</span></span>
<span data-ttu-id="2edf5-103">En este ejemplo se muestra cómo utilizar las actividades de mensajería <xref:System.ServiceModel.Activities.SendReply> y <xref:System.ServiceModel.Activities.ReceiveReply> para enviar y recibir errores esperados e inesperados.</span><span class="sxs-lookup"><span data-stu-id="2edf5-103">This sample demonstrates how to use the <xref:System.ServiceModel.Activities.SendReply> and <xref:System.ServiceModel.Activities.ReceiveReply> messaging activities to send and receive expected and unexpected faults.</span></span> <span data-ttu-id="2edf5-104">En este escenario, la primera solicitud de cliente genera un error esperado que se ha incluido en su colección <xref:System.ServiceModel.Activities.Send.KnownTypes%2A>.</span><span class="sxs-lookup"><span data-stu-id="2edf5-104">In this scenario, the first client request results in an expected fault that has been included in its <xref:System.ServiceModel.Activities.Send.KnownTypes%2A> collection.</span></span> <span data-ttu-id="2edf5-105">Las siguientes solicitudes de cliente producen la recepción de errores inesperados, antes de que la solicitud final se realice correctamente.</span><span class="sxs-lookup"><span data-stu-id="2edf5-105">The next few client requests result in receiving unexpected faults, before the final request succeeds.</span></span>  
  
## <a name="to-use-this-sample"></a><span data-ttu-id="2edf5-106">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="2edf5-106">To use this sample</span></span>  
  
1.  <span data-ttu-id="2edf5-107">Abra [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] con permisos elevados, haciendo clic con el [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] icono y seleccione **ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="2edf5-107">Open [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] with elevated permissions, by right-clicking the [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] icon and selecting **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="2edf5-108">Abra el archivo de solución Faults.sln.</span><span class="sxs-lookup"><span data-stu-id="2edf5-108">Open the Faults.sln solution file.</span></span>  
  
3.  <span data-ttu-id="2edf5-109">Para compilar la solución, presione Ctrl+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="2edf5-109">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
4.  <span data-ttu-id="2edf5-110">Ejecute el proyecto de servicio.</span><span class="sxs-lookup"><span data-stu-id="2edf5-110">Run the service project.</span></span>  
  
    1.  <span data-ttu-id="2edf5-111">En **el Explorador de soluciones**, haga clic en el `FaultService` del proyecto y seleccione **establecer como proyecto de inicio**.</span><span class="sxs-lookup"><span data-stu-id="2edf5-111">In **Solution Explorer**, right-click the `FaultService` project and select **Set as StartUp Project**.</span></span>  
  
    2.  <span data-ttu-id="2edf5-112">Presione CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="2edf5-112">Press CTRL+F5.</span></span>  
  
5.  <span data-ttu-id="2edf5-113">Abra otra copia del [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] con permisos elevados, haciendo clic con el [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] icono y seleccione **ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="2edf5-113">Open another copy of [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] with elevated permissions, by right-clicking the [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] icon and selecting **Run as administrator**.</span></span>  
  
6.  <span data-ttu-id="2edf5-114">Abra el archivo de solución Faults.sln.</span><span class="sxs-lookup"><span data-stu-id="2edf5-114">Open the Faults.sln solution file.</span></span>  
  
7.  <span data-ttu-id="2edf5-115">Ejecute el proyecto de cliente.</span><span class="sxs-lookup"><span data-stu-id="2edf5-115">Run the client project.</span></span>  
  
    1.  <span data-ttu-id="2edf5-116">En **el Explorador de soluciones**, haga clic en el `FaultClient` del proyecto y seleccione **establecer como proyecto de inicio**.</span><span class="sxs-lookup"><span data-stu-id="2edf5-116">In **Solution Explorer**, right-click the `FaultClient` project and select **Set as StartUp Project**.</span></span>  
  
    2.  <span data-ttu-id="2edf5-117">Presione CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="2edf5-117">Press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2edf5-118">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="2edf5-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="2edf5-119">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="2edf5-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="2edf5-120">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="2edf5-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="2edf5-121">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="2edf5-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\Faults`