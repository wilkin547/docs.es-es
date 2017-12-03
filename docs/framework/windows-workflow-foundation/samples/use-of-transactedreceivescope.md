---
title: Uso de TransactedReceiveScope
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d455f1dc-bfc5-43d6-8ae9-bc3b3a3ea08a
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9d20e6280b440e3b1595dd25535857ac7828d2d0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="use-of-transactedreceivescope"></a><span data-ttu-id="7d5ee-102">Uso de TransactedReceiveScope</span><span class="sxs-lookup"><span data-stu-id="7d5ee-102">Use of TransactedReceiveScope</span></span>
<span data-ttu-id="7d5ee-103">En este ejemplo se muestra cómo pasar una transacción de un cliente a un servidor utilizando <xref:System.Activities.Statements.TransactionScope> para crear una transacción en el cliente y <xref:System.ServiceModel.Activities.TransactedReceiveScope> para recibir un mensaje con una transacción de flujo y determinar la duración de la transacción en el servidor.</span><span class="sxs-lookup"><span data-stu-id="7d5ee-103">This sample shows how to flow a transaction from a client to a server using <xref:System.Activities.Statements.TransactionScope> to create a new transaction on the client and a <xref:System.ServiceModel.Activities.TransactedReceiveScope> to receive a message with a flowed transaction and scope the lifetime of the transaction on the server.</span></span> <span data-ttu-id="7d5ee-104">El ejemplo consta de dos proyectos que representan los roles de cliente y servidor.</span><span class="sxs-lookup"><span data-stu-id="7d5ee-104">The sample consists of two projects that fill the roles of client and server.</span></span>  
  
## <a name="client-application"></a><span data-ttu-id="7d5ee-105">Aplicación de cliente</span><span class="sxs-lookup"><span data-stu-id="7d5ee-105">Client Application</span></span>  
 <span data-ttu-id="7d5ee-106">La aplicación cliente ejecuta un flujo de trabajo que imprime el Id. de la transacción distribuida, envía un mensaje al servidor, pasa la transacción, recibe la respuesta, imprime de nuevo el Id. de la transacción distribuida y finaliza.</span><span class="sxs-lookup"><span data-stu-id="7d5ee-106">The client application runs a workflow that prints the distributed transaction ID, sends a message to the server, flows the transaction, receives the reply, prints the distributed transaction ID again and completes.</span></span> <span data-ttu-id="7d5ee-107">Cuando el Id. de la transacción distribuida se imprime inicialmente, es un GUID vacío, puesto que la transacción es todavía solo local.</span><span class="sxs-lookup"><span data-stu-id="7d5ee-107">When the distributed transaction ID is initially prints, it is an empty GUID as the transaction is still only local.</span></span>  
  
## <a name="server-application"></a><span data-ttu-id="7d5ee-108">Servidor de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="7d5ee-108">Server Application</span></span>  
 <span data-ttu-id="7d5ee-109">El proyecto de servidor es similar; sin embargo, el flujo de trabajo se hospeda en <xref:System.ServiceModel.Activities.WorkflowServiceHost> porque debe realizar escuchas en un extremo del mensaje procedente del cliente.</span><span class="sxs-lookup"><span data-stu-id="7d5ee-109">The server project is similar, however, the workflow is hosted in <xref:System.ServiceModel.Activities.WorkflowServiceHost> because it must listen on an endpoint for the message from the client.</span></span> <span data-ttu-id="7d5ee-110">El flujo de trabajo se centra en el objeto <xref:System.ServiceModel.Activities.TransactedReceiveScope>, que recibe la transacción de flujo del cliente, imprime el mensaje que se envió, imprime el Id. de la transacción distribuida y envía la respuesta al cliente.</span><span class="sxs-lookup"><span data-stu-id="7d5ee-110">The workflow is centered on the <xref:System.ServiceModel.Activities.TransactedReceiveScope>, which receives the flowed transaction from the client, prints the message that was sent, prints the distributed transaction ID and sends the reply to the client.</span></span> <span data-ttu-id="7d5ee-111">El Id. de la transacción distribuida es ahora un GUID que no está vacío y si se agregara una actividad que tenga en cuenta las transacciones al cuerpo de <xref:System.ServiceModel.Activities.TransactedReceiveScope>, se ejecutaría bajo la transacción de flujo.</span><span class="sxs-lookup"><span data-stu-id="7d5ee-111">The distributed transaction ID is now a non-empty GUID and if a transaction-aware activity was added to the body of the <xref:System.ServiceModel.Activities.TransactedReceiveScope>, it would execute under the flowed transaction.</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="7d5ee-112">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="7d5ee-112">To run the sample</span></span>  
  
1.  <span data-ttu-id="7d5ee-113">Abra la solución TransactedReceiveScope.sln en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7d5ee-113">Open the TransactedReceiveScope.sln solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="7d5ee-114">Para compilar la solución, presione CTRL + MAYÚS + B o seleccione **generar solución** desde el **generar** menú.</span><span class="sxs-lookup"><span data-stu-id="7d5ee-114">To build the solution, press CTRL+SHIFT+B or select **Build Solution** from the **Build** menu.</span></span>  
  
3.  <span data-ttu-id="7d5ee-115">Una vez que la compilación finalice correctamente, haga clic en la solución y seleccione **Establecer proyectos de inicio**.</span><span class="sxs-lookup"><span data-stu-id="7d5ee-115">Once the build has succeeded, right-click the solution and select **Set Startup Projects**.</span></span> <span data-ttu-id="7d5ee-116">En el cuadro de diálogo, seleccione **proyectos de inicio múltiples** y asegúrese de que la acción para ambos proyectos es **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="7d5ee-116">From the dialog, select **Multiple Startup Projects** and ensure the action for both projects is **Start**.</span></span>  
  
4.  <span data-ttu-id="7d5ee-117">Presione F5 o seleccione **Iniciar depuración** desde el **depurar** menú.</span><span class="sxs-lookup"><span data-stu-id="7d5ee-117">Press F5 or select **Start Debugging** from the **Debug** menu.</span></span> <span data-ttu-id="7d5ee-118">Como alternativa, puede presionar CTRL + F5 o seleccione **iniciar sin depurar** desde el **depurar** menú para ejecutarlo sin depuración.</span><span class="sxs-lookup"><span data-stu-id="7d5ee-118">Alternatively, you can press CTRL+F5 or select **Start Without Debugging** from the **Debug** menu to run without debugging.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7d5ee-119">El servidor debe estar en ejecución antes de iniciar el cliente.</span><span class="sxs-lookup"><span data-stu-id="7d5ee-119">The server must be running prior to starting the client.</span></span> <span data-ttu-id="7d5ee-120">El resultado de la ventana de la consola que hospeda el servicio indica cuándo se ha iniciado.</span><span class="sxs-lookup"><span data-stu-id="7d5ee-120">The output from the console window hosting the service indicates when it has started.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7d5ee-121">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="7d5ee-121">The samples may already be installed on your machine.</span></span> <span data-ttu-id="7d5ee-122">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="7d5ee-122">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="7d5ee-123">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7d5ee-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="7d5ee-124">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="7d5ee-124">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Transactions\TransactedReceiveScope`