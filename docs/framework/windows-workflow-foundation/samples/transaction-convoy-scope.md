---
title: "Ámbito de convoy de transacción"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 37141708-a29f-4b6a-81fe-f8a11f825061
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b5fc8834fb72163a615633d81232e25768683278
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="transaction-convoy-scope"></a><span data-ttu-id="35308-102">Ámbito de convoy de transacción</span><span class="sxs-lookup"><span data-stu-id="35308-102">Transaction Convoy Scope</span></span>
<span data-ttu-id="35308-103">En este ejemplo se muestra cómo crear un patrón de actividad de mensajería de convoy paralelo junto con un objeto <xref:System.ServiceModel.Activities.TransactedReceiveScope> para modelar un protocolo donde varias operaciones pueden suceder en cualquier orden y todas en la misma transacción.</span><span class="sxs-lookup"><span data-stu-id="35308-103">This sample demonstrates how to create a Parallel Convoy messaging activity pattern in conjunction with a <xref:System.ServiceModel.Activities.TransactedReceiveScope> to model a protocol where a number of operations can happen in any order all under the same transaction.</span></span> <span data-ttu-id="35308-104">Este ejemplo también muestra cómo <xref:System.ServiceModel.Activities.TransactedReceiveScope> crea automáticamente una nueva transacción cuando una no fluye al servidor, de modo que el cliente no utiliza ninguna transacción.</span><span class="sxs-lookup"><span data-stu-id="35308-104">This sample also demonstrates how a <xref:System.ServiceModel.Activities.TransactedReceiveScope> automatically creates a new transaction when one is not flowed to the server, so the client does not make use of any transactions.</span></span>  
  
 <span data-ttu-id="35308-105">El ejemplo consta de dos proyectos de flujo de trabajo que representan el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="35308-105">The sample consists of two workflow projects that represent the client and server.</span></span> <span data-ttu-id="35308-106">El proyecto de cliente ejecuta un flujo de trabajo que comienza enviando a un mensaje que arranca el flujo de trabajo del servidor, que a su vez inicializa una correlación e inicia un ámbito transaccional para el resto de las actividades de mensajería.</span><span class="sxs-lookup"><span data-stu-id="35308-106">The client project runs a workflow that begins by sending a message to bootstrap the server workflow, which initializes a correlation and starts a transactional scope for the remainder of the messaging activities.</span></span> <span data-ttu-id="35308-107">La actividad <xref:System.Activities.Statements.Sequence> del cliente contiene una pareja de <xref:System.ServiceModel.Activities.Send> y <xref:System.ServiceModel.Activities.ReceiveReply> inicial y una actividad <xref:System.Activities.Statements.Parallel> con tres bifurcaciones.</span><span class="sxs-lookup"><span data-stu-id="35308-107">The client <xref:System.Activities.Statements.Sequence> activity contains an initial <xref:System.ServiceModel.Activities.Send> and <xref:System.ServiceModel.Activities.ReceiveReply> pair and then a <xref:System.Activities.Statements.Parallel> activity with three branches.</span></span> <span data-ttu-id="35308-108">Cada bifurcación envía un mensaje unidireccional al servidor.</span><span class="sxs-lookup"><span data-stu-id="35308-108">Each branch sends a one-way message to the server.</span></span> <span data-ttu-id="35308-109">La propiedad <xref:System.Activities.Statements.Parallel.CompletionCondition%2A> de la actividad <xref:System.Activities.Statements.Parallel> está establecida en `false` para que las tres bifurcaciones se completen.</span><span class="sxs-lookup"><span data-stu-id="35308-109">The <xref:System.Activities.Statements.Parallel.CompletionCondition%2A> property of the <xref:System.Activities.Statements.Parallel> activity is set to `false` so that all three branches complete.</span></span>  
  
 <span data-ttu-id="35308-110">El flujo de trabajo del servidor es similar al flujo de trabajo del cliente excepto que las actividades de mensajería se orientan hacia el lado del servidor de la comunicación y se incluyen dentro de una actividad <xref:System.ServiceModel.Activities.TransactedReceiveScope> para que todo el trabajo realizado se ejecute bajo la misma transacción.</span><span class="sxs-lookup"><span data-stu-id="35308-110">The server workflow is similar to the client workflow except the messaging activities are oriented towards the server side of the communication and they are contained within a <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity so that all work done executes under the same transaction.</span></span> <span data-ttu-id="35308-111">Cuando el primer mensaje se recibe en el servidor, se crea una transacción y se establece como transacción ambiente para el ámbito del cuerpo de <xref:System.ServiceModel.Activities.TransactedReceiveScope> de modo que cualquier actividad dentro de este ámbito pueda tener acceso a la transacción.</span><span class="sxs-lookup"><span data-stu-id="35308-111">When the first message is received on the server, a transaction is created and is made ambient for the scope of the <xref:System.ServiceModel.Activities.TransactedReceiveScope> body so that any activity within this scope can access the transaction.</span></span> <span data-ttu-id="35308-112">Después de esto, todo lo que se recibe se ejecuta en paralelo.</span><span class="sxs-lookup"><span data-stu-id="35308-112">After this, all receives execute in parallel.</span></span> <span data-ttu-id="35308-113">Todas las recepciones deben ejecutarse exactamente una vez, según describe la condición de finalización de la actividad paralela.</span><span class="sxs-lookup"><span data-stu-id="35308-113">All receives must execute exactly once as described by the completion condition on the parallel activity.</span></span> <span data-ttu-id="35308-114">Al final del cuerpo de <xref:System.ServiceModel.Activities.TransactedReceiveScope> existe un punto de persistencia implícito y la operación de persistencia también se ejecuta bajo la misma transacción.</span><span class="sxs-lookup"><span data-stu-id="35308-114">An implicit persistence point exists at the end of the <xref:System.ServiceModel.Activities.TransactedReceiveScope> body and the persistence operation is also executed under the same transaction.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="35308-115">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="35308-115">To use this sample</span></span>  
  
1.  <span data-ttu-id="35308-116">Con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], abra el archivo de solución ParallelConvoySample.sln.</span><span class="sxs-lookup"><span data-stu-id="35308-116">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the ParallelConvoySample.sln solution file.</span></span>  
  
2.  <span data-ttu-id="35308-117">Para compilar la solución, presione Ctrl+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="35308-117">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="35308-118">Asegúrese de que ambos proyectos están establecidos para iniciarse.</span><span class="sxs-lookup"><span data-stu-id="35308-118">Ensure both projects are set to start.</span></span>  
  
    1.  <span data-ttu-id="35308-119">En **el Explorador de soluciones**, haga clic en la solución y seleccione **Establecer proyectos de inicio**.</span><span class="sxs-lookup"><span data-stu-id="35308-119">In **Solution Explorer**, right-click the solution and select **Set Startup Projects**.</span></span>  
  
    2.  <span data-ttu-id="35308-120">Seleccione **proyectos de inicio múltiples** y asegúrese de que la acción para ambos proyectos se establece en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="35308-120">Select **Multiple Startup Projects** and ensure the action for both projects is set to **Start**.</span></span>  
  
4.  <span data-ttu-id="35308-121">Para ejecutar la solución, presione CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="35308-121">To run the solution, press CTRL+F5.</span></span>  
  
     <span data-ttu-id="35308-122">El servidor imprime `Server is running`, que indica que el servidor está listo.</span><span class="sxs-lookup"><span data-stu-id="35308-122">The server prints `Server is running`, which indicates the server is ready.</span></span>  
  
     <span data-ttu-id="35308-123">Presione cualquier tecla en la ventana de la consola del cliente para iniciar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="35308-123">Press any key in the client console window to start the sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="35308-124">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="35308-124">The samples may already be installed on your machine.</span></span> <span data-ttu-id="35308-125">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="35308-125">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="35308-126">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="35308-126">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="35308-127">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="35308-127">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Transactions\TransactedConvoyScope`  
  
## <a name="see-also"></a><span data-ttu-id="35308-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="35308-128">See Also</span></span>
