---
title: Canales de WCF habilitados para ReceiveContext
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d990d119-7321-4b8c-852b-10256f59f9b0
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 729bf8bd1371bf64b9b05a235331120608824083
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="receivecontext-enabled-wcf-channels"></a><span data-ttu-id="ffe35-102">Canales de WCF habilitados para ReceiveContext</span><span class="sxs-lookup"><span data-stu-id="ffe35-102">ReceiveContext-Enabled WCF Channels</span></span>
<span data-ttu-id="ffe35-103">En este ejemplo se muestra la utilidad de los canales WCF habilitados para <xref:System.ServiceModel.Channels.ReceiveContext>.</span><span class="sxs-lookup"><span data-stu-id="ffe35-103">This sample demonstrates the usefulness of <xref:System.ServiceModel.Channels.ReceiveContext>-enabled WCF channels.</span></span> <span data-ttu-id="ffe35-104">En el ejemplo se implementa un servicio para encontrar el producto de dos números utilizando un canal de NetMSMQ.</span><span class="sxs-lookup"><span data-stu-id="ffe35-104">The sample implements a service to find the product of two numbers using a NetMSMQ channel.</span></span>  
  
 <span data-ttu-id="ffe35-105">La clase <xref:System.ServiceModel.Channels.ReceiveContext> permite a una aplicación decidir si tener acceso al mensaje o dejarlo en la cola para continuar su procesamiento, incluso una vez inspeccionado el contenido del mensaje.</span><span class="sxs-lookup"><span data-stu-id="ffe35-105">The <xref:System.ServiceModel.Channels.ReceiveContext> class enables an application to decide whether to access the message or leave it in the queue for further processing, even after the contents of the message have been inspected.</span></span> <span data-ttu-id="ffe35-106">En este ejemplo, un cliente envía números enteros aleatorios a una cola transaccional.</span><span class="sxs-lookup"><span data-stu-id="ffe35-106">In this sample, a client sends random integers to a transactional queue.</span></span> <span data-ttu-id="ffe35-107">El servicio `ProductCalculator` recibe los mensajes e inspecciona su contenido, que son números enteros, para determinar si se puede calcular el producto.</span><span class="sxs-lookup"><span data-stu-id="ffe35-107">The `ProductCalculator` service receives the messages and inspects the message contents, which are integers, to determine whether the product can be computed.</span></span> <span data-ttu-id="ffe35-108">Si la operación del servicio no calcula el producto, el mensaje se coloca en la cola y puede ser recibido de nuevo por el servicio que realiza escuchas en ella.</span><span class="sxs-lookup"><span data-stu-id="ffe35-108">If the service operation does not compute the product, the message is put back into the queue and can be received again by the service listening on the queue.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ffe35-109">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="ffe35-109">The samples may already be installed on your computer.</span></span> <span data-ttu-id="ffe35-110">Compruebe el siguiente directorio (predeterminado) antes de continuar:</span><span class="sxs-lookup"><span data-stu-id="ffe35-110">Check for the following (default) directory before continuing:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ffe35-111">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ffe35-111">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ffe35-112">Este ejemplo se encuentra en el siguiente directorio:</span><span class="sxs-lookup"><span data-stu-id="ffe35-112">This sample is located in the following directory:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\ReceiveContextProductGenerator`  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="ffe35-113">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="ffe35-113">To use this sample</span></span>  
  
1.  <span data-ttu-id="ffe35-114">Asegúrese de que está instalado Microsoft Message Queuing (MSMQ).</span><span class="sxs-lookup"><span data-stu-id="ffe35-114">Ensure that Microsoft Message Queuing (MSMQ) is installed.</span></span>  
  
    1.  <span data-ttu-id="ffe35-115">Para instalar MSMQ en [!INCLUDE[lserver](../../../../includes/lserver-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="ffe35-115">To install MSMQ on [!INCLUDE[lserver](../../../../includes/lserver-md.md)]:</span></span>  
  
        1.  <span data-ttu-id="ffe35-116">En **el administrador del servidor**, haga clic en **características**.</span><span class="sxs-lookup"><span data-stu-id="ffe35-116">In **Server Manager**, click **Features**.</span></span>  
  
        2.  <span data-ttu-id="ffe35-117">En el panel derecho de **resumen de características**, haga clic en **agregar características**.</span><span class="sxs-lookup"><span data-stu-id="ffe35-117">In the right pane under **Features Summary**, click **Add Features**.</span></span>  
  
        3.  <span data-ttu-id="ffe35-118">En la ventana resultante, expanda **Message Queue Server**.</span><span class="sxs-lookup"><span data-stu-id="ffe35-118">In the resulting window, expand **Message Queuing**.</span></span>  
  
        4.  <span data-ttu-id="ffe35-119">Expanda **servicios puesta en cola de mensajes**.</span><span class="sxs-lookup"><span data-stu-id="ffe35-119">Expand **Message Queuing Services**.</span></span>  
  
        5.  <span data-ttu-id="ffe35-120">Haga clic en **integración de servicios de directorio** (para los equipos unidos a un dominio) y, a continuación, haga clic en **compatibilidad con HTTP**.</span><span class="sxs-lookup"><span data-stu-id="ffe35-120">Click **Directory Services Integration** (for computers joined to a domain), and then click **HTTP Support**.</span></span>  
  
        6.  <span data-ttu-id="ffe35-121">Haga clic en **siguiente**y, a continuación, haga clic en **instalar**.</span><span class="sxs-lookup"><span data-stu-id="ffe35-121">Click **Next**, and then click **Install**.</span></span>  
  
    2.  <span data-ttu-id="ffe35-122">Para instalar MSMQ en [!INCLUDE[wv](../../../../includes/wv-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="ffe35-122">To install MSMQ on [!INCLUDE[wv](../../../../includes/wv-md.md)]:</span></span>  
  
        1.  <span data-ttu-id="ffe35-123">Abra **Panel de Control**.</span><span class="sxs-lookup"><span data-stu-id="ffe35-123">Open **Control Panel**.</span></span>  
  
        2.  <span data-ttu-id="ffe35-124">Haga clic en **programas** y, a continuación, en **programas y características**, haga clic en **activar o desactivar las características de Windows**.</span><span class="sxs-lookup"><span data-stu-id="ffe35-124">Click **Programs** and then, under **Programs and Features**, click **Turn Windows Features on and off**.</span></span>  
  
        3.  <span data-ttu-id="ffe35-125">Expanda **Microsoft Message Queue (MSMQ) Server**, expanda **Microsoft Message Queue (MSMQ) Server Core**y, a continuación, active las casillas de verificación de las siguientes características de Message Queue Server instalar:</span><span class="sxs-lookup"><span data-stu-id="ffe35-125">Expand **Microsoft Message Queue (MSMQ) Server**, expand **Microsoft Message Queue (MSMQ) Server Core**, and then select the check boxes for the following Message Queuing features to install:</span></span>  
  
            -   <span data-ttu-id="ffe35-126">Message Queuing Server</span><span class="sxs-lookup"><span data-stu-id="ffe35-126">Message Queuing Server</span></span>  
  
            -   <span data-ttu-id="ffe35-127">Integración de Servicios de dominio de Active Directory MSMQ (para los equipos unidos a un dominio)</span><span class="sxs-lookup"><span data-stu-id="ffe35-127">MSMQ Active Directory Domain Services Integration (for computers joined to a domain)</span></span>  
  
            -   <span data-ttu-id="ffe35-128">Compatibilidad con MSMQ HTTP</span><span class="sxs-lookup"><span data-stu-id="ffe35-128">MSMQ HTTP Support</span></span>  
  
        4.  <span data-ttu-id="ffe35-129">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ffe35-129">Click **OK**.</span></span>  
  
        5.  <span data-ttu-id="ffe35-130">Si se le pide que reinicie el equipo, haga clic en **Aceptar** para completar la instalación.</span><span class="sxs-lookup"><span data-stu-id="ffe35-130">If you are prompted to restart the computer, click **OK** to complete the installation.</span></span>  
  
2.  <span data-ttu-id="ffe35-131">Asegúrese de que [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] esté instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="ffe35-131">Ensure that [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] is installed on the computer.</span></span>  
  
3.  <span data-ttu-id="ffe35-132">Con [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], abra el archivo de la solución ReceiveContextProductGenerator.sln.</span><span class="sxs-lookup"><span data-stu-id="ffe35-132">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the ReceiveContextProductGenerator.sln solution file.</span></span>  
  
4.  <span data-ttu-id="ffe35-133">Para compilar la solución, presione Ctrl+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="ffe35-133">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
5.  <span data-ttu-id="ffe35-134">Para ejecutar la solución, presione CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="ffe35-134">To run the solution, press CTRL+F5.</span></span>
