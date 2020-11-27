---
title: Comunicación asincrónica
ms.date: 03/30/2017
ms.assetid: 128dc092-9eb2-4e33-9470-9a7f62b60df6
ms.openlocfilehash: db5a8f415479967d7579357bd0c8058c7fb961c5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96255850"
---
# <a name="asynchronous-communication"></a><span data-ttu-id="85647-102">Comunicación asincrónica</span><span class="sxs-lookup"><span data-stu-id="85647-102">Asynchronous Communication</span></span>

<span data-ttu-id="85647-103">Este ejemplo muestra cómo la comunicación entre dos servicios de Windows Workflow Foundation (WF) diferentes se realiza de forma asincrónica de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="85647-103">This sample demonstrates how the communication between two different Windows Workflow Foundation (WF) services is done asynchronously by default.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="85647-104">Muestra</span><span class="sxs-lookup"><span data-stu-id="85647-104">Demonstrates</span></span>  

 <span data-ttu-id="85647-105">Comunicación asincrónica entre servicios de [!INCLUDE[wf1](../../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="85647-105">Asynchronous communication between [!INCLUDE[wf1](../../../../includes/wf1-md.md)] services.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="85647-106">Discusión</span><span class="sxs-lookup"><span data-stu-id="85647-106">Discussion</span></span>  

 <span data-ttu-id="85647-107">En este ejemplo se muestra cómo la comunicación entre aplicaciones de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] se realiza de forma asincrónica utilizando las actividades de mensajería proporcionadas por .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="85647-107">This sample shows how the communication between [!INCLUDE[wf1](../../../../includes/wf1-md.md)] applications is done asynchronously by using the messaging activities provided by .NET Framework.</span></span>  
  
 <span data-ttu-id="85647-108">Este ejemplo consta de los tres proyectos siguientes.</span><span class="sxs-lookup"><span data-stu-id="85647-108">This sample consists of the following three projects.</span></span>  
  
 <span data-ttu-id="85647-109">CreditCheckService</span><span class="sxs-lookup"><span data-stu-id="85647-109">CreditCheckService</span></span>  
 <span data-ttu-id="85647-110">Este servicio recibe la puntuación crediticia de una persona determinada o el valor del elemento que se va a adquirir y a continuación, decide si la persona recibe el crédito.</span><span class="sxs-lookup"><span data-stu-id="85647-110">This service receives the credit score of a particular person or the value of the item to acquire, and then decides whether the credit is given to the person.</span></span>  
  
 <span data-ttu-id="85647-111">RentalApprovalService</span><span class="sxs-lookup"><span data-stu-id="85647-111">RentalApprovalService</span></span>  
 <span data-ttu-id="85647-112">Este servicio recibe una solicitud de una persona que necesita crédito.</span><span class="sxs-lookup"><span data-stu-id="85647-112">This service receives an application from a person who is in need of some credit.</span></span> <span data-ttu-id="85647-113">Este servicio se comunica de forma asincrónica con `CreditCheckService` para decidir si la solicitud de crédito es válida.</span><span class="sxs-lookup"><span data-stu-id="85647-113">This service communicates asynchronously with the `CreditCheckService` to decide whether the credit application is valid.</span></span>  
  
 <span data-ttu-id="85647-114">Cliente</span><span class="sxs-lookup"><span data-stu-id="85647-114">Client</span></span>  
 <span data-ttu-id="85647-115">El cliente se comunica sincrónicamente con `RentalApprovalService` para saber si se aprueba el crédito.</span><span class="sxs-lookup"><span data-stu-id="85647-115">The client communicates synchronously with the `RentalApprovalService` to know whether the credit is approved.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="85647-116">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="85647-116">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="85647-117">Haga clic con el botón derecho en la solución **AsynchronousCommunication** y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="85647-117">Right-click the **AsynchronousCommunication** solution and select **Properties**.</span></span>  
  
2. <span data-ttu-id="85647-118">En **propiedades comunes**, seleccione **proyecto de inicio** y seleccione **proyectos de inicio múltiples**.</span><span class="sxs-lookup"><span data-stu-id="85647-118">In **Common Properties**, select **Startup Project**, and select **Multiple Startup Projects**.</span></span>  
  
3. <span data-ttu-id="85647-119">Mueva **RentalApprovalService** a la primera posición de la lista, seguida de **CreditCheckService**, seguido del **cliente**.</span><span class="sxs-lookup"><span data-stu-id="85647-119">Move **RentalApprovalService** to the first position in the list, followed by **CreditCheckService**, followed by **Client**.</span></span> <span data-ttu-id="85647-120">Establezca la acción **iniciar** en los tres proyectos.</span><span class="sxs-lookup"><span data-stu-id="85647-120">Set the **Start** action on all three projects.</span></span>  
  
4. <span data-ttu-id="85647-121">Haga clic en **Aceptar** y presione F5 para ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="85647-121">Click **OK**, and press F5 to run the sample.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="85647-122">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="85647-122">The samples may already be installed on your machine.</span></span> <span data-ttu-id="85647-123">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="85647-123">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="85647-124">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="85647-124">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="85647-125">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="85647-125">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\AsynchronousCommunication`
