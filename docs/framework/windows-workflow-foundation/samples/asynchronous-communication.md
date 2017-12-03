---
title: "Comunicación asincrónica"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 128dc092-9eb2-4e33-9470-9a7f62b60df6
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5ea2d705a38ddae1689d212bbd50196920fe73fe
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="asynchronous-communication"></a><span data-ttu-id="80f6c-102">Comunicación asincrónica</span><span class="sxs-lookup"><span data-stu-id="80f6c-102">Asynchronous Communication</span></span>
<span data-ttu-id="80f6c-103">En este ejemplo se muestra cómo se realiza asincrónicamente de forma predeterminada la comunicación entre dos servicios de [!INCLUDE[wf](../../../../includes/wf-md.md)] diferentes.</span><span class="sxs-lookup"><span data-stu-id="80f6c-103">This sample demonstrates how the communication between two different [!INCLUDE[wf](../../../../includes/wf-md.md)] services is done asynchronously by default.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="80f6c-104">Demostraciones</span><span class="sxs-lookup"><span data-stu-id="80f6c-104">Demonstrates</span></span>  
 <span data-ttu-id="80f6c-105">Comunicación asincrónica entre servicios de [!INCLUDE[wf1](../../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="80f6c-105">Asynchronous communication between [!INCLUDE[wf1](../../../../includes/wf1-md.md)] services.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="80f6c-106">Explicación</span><span class="sxs-lookup"><span data-stu-id="80f6c-106">Discussion</span></span>  
 <span data-ttu-id="80f6c-107">En este ejemplo se muestra cómo la comunicación entre aplicaciones de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] se realiza de forma asincrónica utilizando las actividades de mensajería proporcionadas por .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="80f6c-107">This sample shows how the communication between [!INCLUDE[wf1](../../../../includes/wf1-md.md)] applications is done asynchronously by using the messaging activities provided by .NET Framework.</span></span>  
  
 <span data-ttu-id="80f6c-108">Este ejemplo consta de los tres proyectos siguientes.</span><span class="sxs-lookup"><span data-stu-id="80f6c-108">This sample consists of the following three projects.</span></span>  
  
 <span data-ttu-id="80f6c-109">CreditCheckService</span><span class="sxs-lookup"><span data-stu-id="80f6c-109">CreditCheckService</span></span>  
 <span data-ttu-id="80f6c-110">Este servicio recibe la puntuación crediticia de una persona determinada o el valor del elemento que se va a adquirir y a continuación, decide si la persona recibe el crédito.</span><span class="sxs-lookup"><span data-stu-id="80f6c-110">This service receives the credit score of a particular person or the value of the item to acquire, and then decides whether the credit is given to the person.</span></span>  
  
 <span data-ttu-id="80f6c-111">RentalApprovalService</span><span class="sxs-lookup"><span data-stu-id="80f6c-111">RentalApprovalService</span></span>  
 <span data-ttu-id="80f6c-112">Este servicio recibe una solicitud de una persona que necesita crédito.</span><span class="sxs-lookup"><span data-stu-id="80f6c-112">This service receives an application from a person who is in need of some credit.</span></span> <span data-ttu-id="80f6c-113">Este servicio se comunica de forma asincrónica con `CreditCheckService` para decidir si la solicitud de crédito es válida.</span><span class="sxs-lookup"><span data-stu-id="80f6c-113">This service communicates asynchronously with the `CreditCheckService` to decide whether the credit application is valid.</span></span>  
  
 <span data-ttu-id="80f6c-114">Cliente</span><span class="sxs-lookup"><span data-stu-id="80f6c-114">Client</span></span>  
 <span data-ttu-id="80f6c-115">El cliente se comunica sincrónicamente con `RentalApprovalService` para saber si se aprueba el crédito.</span><span class="sxs-lookup"><span data-stu-id="80f6c-115">The client communicates synchronously with the `RentalApprovalService` to know whether the credit is approved.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="80f6c-116">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="80f6c-116">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="80f6c-117">Haga clic en el **AsynchronousCommunication** solución y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="80f6c-117">Right-click the **AsynchronousCommunication** solution and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="80f6c-118">En **propiedades comunes**, seleccione **proyecto de inicio**y seleccione **proyectos de inicio múltiples**.</span><span class="sxs-lookup"><span data-stu-id="80f6c-118">In **Common Properties**, select **Startup Project**, and select **Multiple Startup Projects**.</span></span>  
  
3.  <span data-ttu-id="80f6c-119">Mover **RentalApprovalService** a la primera posición en la lista, seguido por **CreditCheckService**, seguido de **cliente**.</span><span class="sxs-lookup"><span data-stu-id="80f6c-119">Move **RentalApprovalService** to the first position in the list, followed by **CreditCheckService**, followed by **Client**.</span></span> <span data-ttu-id="80f6c-120">Establecer el **iniciar** acción en los tres proyectos.</span><span class="sxs-lookup"><span data-stu-id="80f6c-120">Set the **Start** action on all three projects.</span></span>  
  
4.  <span data-ttu-id="80f6c-121">Haga clic en **Aceptar**, y presione F5 para ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="80f6c-121">Click **OK**, and press F5 to run the sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="80f6c-122">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="80f6c-122">The samples may already be installed on your machine.</span></span> <span data-ttu-id="80f6c-123">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="80f6c-123">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="80f6c-124">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="80f6c-124">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="80f6c-125">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="80f6c-125">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\AsynchronousCommunication`
