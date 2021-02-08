---
description: 'Más información sobre: comunicación asincrónica'
title: Comunicación asincrónica
ms.date: 03/30/2017
ms.assetid: 128dc092-9eb2-4e33-9470-9a7f62b60df6
ms.openlocfilehash: 3e824c03a07682faaf60d8434f6af1a26742ead7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792601"
---
# <a name="asynchronous-communication"></a><span data-ttu-id="91ae0-103">Comunicación asincrónica</span><span class="sxs-lookup"><span data-stu-id="91ae0-103">Asynchronous Communication</span></span>

<span data-ttu-id="91ae0-104">Este ejemplo muestra cómo la comunicación entre dos servicios de Windows Workflow Foundation (WF) diferentes se realiza de forma asincrónica de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="91ae0-104">This sample demonstrates how the communication between two different Windows Workflow Foundation (WF) services is done asynchronously by default.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="91ae0-105">Muestra</span><span class="sxs-lookup"><span data-stu-id="91ae0-105">Demonstrates</span></span>  

 <span data-ttu-id="91ae0-106">Comunicación asincrónica entre servicios de [!INCLUDE[wf1](../../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="91ae0-106">Asynchronous communication between [!INCLUDE[wf1](../../../../includes/wf1-md.md)] services.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="91ae0-107">Debate</span><span class="sxs-lookup"><span data-stu-id="91ae0-107">Discussion</span></span>  

 <span data-ttu-id="91ae0-108">En este ejemplo se muestra cómo la comunicación entre aplicaciones de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] se realiza de forma asincrónica utilizando las actividades de mensajería proporcionadas por .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="91ae0-108">This sample shows how the communication between [!INCLUDE[wf1](../../../../includes/wf1-md.md)] applications is done asynchronously by using the messaging activities provided by .NET Framework.</span></span>  
  
 <span data-ttu-id="91ae0-109">Este ejemplo consta de los tres proyectos siguientes.</span><span class="sxs-lookup"><span data-stu-id="91ae0-109">This sample consists of the following three projects.</span></span>  
  
 <span data-ttu-id="91ae0-110">CreditCheckService</span><span class="sxs-lookup"><span data-stu-id="91ae0-110">CreditCheckService</span></span>  
 <span data-ttu-id="91ae0-111">Este servicio recibe la puntuación crediticia de una persona determinada o el valor del elemento que se va a adquirir y a continuación, decide si la persona recibe el crédito.</span><span class="sxs-lookup"><span data-stu-id="91ae0-111">This service receives the credit score of a particular person or the value of the item to acquire, and then decides whether the credit is given to the person.</span></span>  
  
 <span data-ttu-id="91ae0-112">RentalApprovalService</span><span class="sxs-lookup"><span data-stu-id="91ae0-112">RentalApprovalService</span></span>  
 <span data-ttu-id="91ae0-113">Este servicio recibe una solicitud de una persona que necesita crédito.</span><span class="sxs-lookup"><span data-stu-id="91ae0-113">This service receives an application from a person who is in need of some credit.</span></span> <span data-ttu-id="91ae0-114">Este servicio se comunica de forma asincrónica con `CreditCheckService` para decidir si la solicitud de crédito es válida.</span><span class="sxs-lookup"><span data-stu-id="91ae0-114">This service communicates asynchronously with the `CreditCheckService` to decide whether the credit application is valid.</span></span>  
  
 <span data-ttu-id="91ae0-115">Cliente</span><span class="sxs-lookup"><span data-stu-id="91ae0-115">Client</span></span>  
 <span data-ttu-id="91ae0-116">El cliente se comunica sincrónicamente con `RentalApprovalService` para saber si se aprueba el crédito.</span><span class="sxs-lookup"><span data-stu-id="91ae0-116">The client communicates synchronously with the `RentalApprovalService` to know whether the credit is approved.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="91ae0-117">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="91ae0-117">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="91ae0-118">Haga clic con el botón derecho en la solución **AsynchronousCommunication** y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="91ae0-118">Right-click the **AsynchronousCommunication** solution and select **Properties**.</span></span>  
  
2. <span data-ttu-id="91ae0-119">En **propiedades comunes**, seleccione **proyecto de inicio** y seleccione **proyectos de inicio múltiples**.</span><span class="sxs-lookup"><span data-stu-id="91ae0-119">In **Common Properties**, select **Startup Project**, and select **Multiple Startup Projects**.</span></span>  
  
3. <span data-ttu-id="91ae0-120">Mueva **RentalApprovalService** a la primera posición de la lista, seguida de **CreditCheckService**, seguido del **cliente**.</span><span class="sxs-lookup"><span data-stu-id="91ae0-120">Move **RentalApprovalService** to the first position in the list, followed by **CreditCheckService**, followed by **Client**.</span></span> <span data-ttu-id="91ae0-121">Establezca la acción **iniciar** en los tres proyectos.</span><span class="sxs-lookup"><span data-stu-id="91ae0-121">Set the **Start** action on all three projects.</span></span>  
  
4. <span data-ttu-id="91ae0-122">Haga clic en **Aceptar** y presione F5 para ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="91ae0-122">Click **OK**, and press F5 to run the sample.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="91ae0-123">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="91ae0-123">The samples may already be installed on your machine.</span></span> <span data-ttu-id="91ae0-124">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="91ae0-124">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="91ae0-125">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="91ae0-125">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="91ae0-126">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="91ae0-126">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\AsynchronousCommunication`
