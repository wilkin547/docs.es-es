---
title: Canales de WCF habilitados para ReceiveContext
ms.date: 03/30/2017
ms.assetid: d990d119-7321-4b8c-852b-10256f59f9b0
ms.openlocfilehash: d7f80d0874606129876fbf7dfa30c0327680b922
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43515935"
---
# <a name="receivecontext-enabled-wcf-channels"></a><span data-ttu-id="442ac-102">Canales de WCF habilitados para ReceiveContext</span><span class="sxs-lookup"><span data-stu-id="442ac-102">ReceiveContext-Enabled WCF Channels</span></span>
<span data-ttu-id="442ac-103">En este ejemplo se muestra la utilidad de los canales WCF habilitados para <xref:System.ServiceModel.Channels.ReceiveContext>.</span><span class="sxs-lookup"><span data-stu-id="442ac-103">This sample demonstrates the usefulness of <xref:System.ServiceModel.Channels.ReceiveContext>-enabled WCF channels.</span></span> <span data-ttu-id="442ac-104">En el ejemplo se implementa un servicio para encontrar el producto de dos números utilizando un canal de NetMSMQ.</span><span class="sxs-lookup"><span data-stu-id="442ac-104">The sample implements a service to find the product of two numbers using a NetMSMQ channel.</span></span>  
  
 <span data-ttu-id="442ac-105">La clase <xref:System.ServiceModel.Channels.ReceiveContext> permite a una aplicación decidir si tener acceso al mensaje o dejarlo en la cola para continuar su procesamiento, incluso una vez inspeccionado el contenido del mensaje.</span><span class="sxs-lookup"><span data-stu-id="442ac-105">The <xref:System.ServiceModel.Channels.ReceiveContext> class enables an application to decide whether to access the message or leave it in the queue for further processing, even after the contents of the message have been inspected.</span></span> <span data-ttu-id="442ac-106">En este ejemplo, un cliente envía números enteros aleatorios a una cola transaccional.</span><span class="sxs-lookup"><span data-stu-id="442ac-106">In this sample, a client sends random integers to a transactional queue.</span></span> <span data-ttu-id="442ac-107">El servicio `ProductCalculator` recibe los mensajes e inspecciona su contenido, que son números enteros, para determinar si se puede calcular el producto.</span><span class="sxs-lookup"><span data-stu-id="442ac-107">The `ProductCalculator` service receives the messages and inspects the message contents, which are integers, to determine whether the product can be computed.</span></span> <span data-ttu-id="442ac-108">Si la operación del servicio no calcula el producto, el mensaje se coloca en la cola y puede ser recibido de nuevo por el servicio que realiza escuchas en ella.</span><span class="sxs-lookup"><span data-stu-id="442ac-108">If the service operation does not compute the product, the message is put back into the queue and can be received again by the service listening on the queue.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="442ac-109">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="442ac-109">The samples may already be installed on your computer.</span></span> <span data-ttu-id="442ac-110">Compruebe el siguiente directorio (predeterminado) antes de continuar:</span><span class="sxs-lookup"><span data-stu-id="442ac-110">Check for the following (default) directory before continuing:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="442ac-111">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="442ac-111">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="442ac-112">Este ejemplo se encuentra en el siguiente directorio:</span><span class="sxs-lookup"><span data-stu-id="442ac-112">This sample is located in the following directory:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\ReceiveContextProductGenerator`  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="442ac-113">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="442ac-113">To use this sample</span></span>  
  
1.  <span data-ttu-id="442ac-114">Asegúrese de que está instalado Microsoft Message Queuing (MSMQ).</span><span class="sxs-lookup"><span data-stu-id="442ac-114">Ensure that Microsoft Message Queuing (MSMQ) is installed.</span></span>  
  
    1.  <span data-ttu-id="442ac-115">Para instalar MSMQ en [!INCLUDE[lserver](../../../../includes/lserver-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="442ac-115">To install MSMQ on [!INCLUDE[lserver](../../../../includes/lserver-md.md)]:</span></span>  
  
        1.  <span data-ttu-id="442ac-116">En **administrador del servidor**, haga clic en **características**.</span><span class="sxs-lookup"><span data-stu-id="442ac-116">In **Server Manager**, click **Features**.</span></span>  
  
        2.  <span data-ttu-id="442ac-117">En el panel derecho de **resumen de características**, haga clic en **agregar características**.</span><span class="sxs-lookup"><span data-stu-id="442ac-117">In the right pane under **Features Summary**, click **Add Features**.</span></span>  
  
        3.  <span data-ttu-id="442ac-118">En la ventana resultante, expanda **Message Queue Server**.</span><span class="sxs-lookup"><span data-stu-id="442ac-118">In the resulting window, expand **Message Queuing**.</span></span>  
  
        4.  <span data-ttu-id="442ac-119">Expanda **servicios de cola de mensajes**.</span><span class="sxs-lookup"><span data-stu-id="442ac-119">Expand **Message Queuing Services**.</span></span>  
  
        5.  <span data-ttu-id="442ac-120">Haga clic en **integración de servicios de directorio** (para equipos unidos a un dominio) y, a continuación, haga clic en **compatibilidad con HTTP**.</span><span class="sxs-lookup"><span data-stu-id="442ac-120">Click **Directory Services Integration** (for computers joined to a domain), and then click **HTTP Support**.</span></span>  
  
        6.  <span data-ttu-id="442ac-121">Haga clic en **siguiente**y, a continuación, haga clic en **instalar**.</span><span class="sxs-lookup"><span data-stu-id="442ac-121">Click **Next**, and then click **Install**.</span></span>  
  
    2.  <span data-ttu-id="442ac-122">Para instalar MSMQ en [!INCLUDE[wv](../../../../includes/wv-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="442ac-122">To install MSMQ on [!INCLUDE[wv](../../../../includes/wv-md.md)]:</span></span>  
  
        1.  <span data-ttu-id="442ac-123">Abra **Panel de Control**.</span><span class="sxs-lookup"><span data-stu-id="442ac-123">Open **Control Panel**.</span></span>  
  
        2.  <span data-ttu-id="442ac-124">Haga clic en **programas** y, a continuación, en **programas y características**, haga clic en **activar y desactivar las características de Windows**.</span><span class="sxs-lookup"><span data-stu-id="442ac-124">Click **Programs** and then, under **Programs and Features**, click **Turn Windows Features on and off**.</span></span>  
  
        3.  <span data-ttu-id="442ac-125">Expanda **Microsoft Message Queue (MSMQ) Server**, expanda **Microsoft Message Queue (MSMQ) Server Core**y, a continuación, seleccione las casillas de las siguientes características instalar Message Queue Server:</span><span class="sxs-lookup"><span data-stu-id="442ac-125">Expand **Microsoft Message Queue (MSMQ) Server**, expand **Microsoft Message Queue (MSMQ) Server Core**, and then select the check boxes for the following Message Queuing features to install:</span></span>  
  
            -   <span data-ttu-id="442ac-126">Message Queuing Server</span><span class="sxs-lookup"><span data-stu-id="442ac-126">Message Queuing Server</span></span>  
  
            -   <span data-ttu-id="442ac-127">Integración de Servicios de dominio de Active Directory MSMQ (para los equipos unidos a un dominio)</span><span class="sxs-lookup"><span data-stu-id="442ac-127">MSMQ Active Directory Domain Services Integration (for computers joined to a domain)</span></span>  
  
            -   <span data-ttu-id="442ac-128">Compatibilidad con MSMQ HTTP</span><span class="sxs-lookup"><span data-stu-id="442ac-128">MSMQ HTTP Support</span></span>  
  
        4.  <span data-ttu-id="442ac-129">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="442ac-129">Click **OK**.</span></span>  
  
        5.  <span data-ttu-id="442ac-130">Si se le pide que reinicie el equipo, haga clic en **Aceptar** para completar la instalación.</span><span class="sxs-lookup"><span data-stu-id="442ac-130">If you are prompted to restart the computer, click **OK** to complete the installation.</span></span>  
  
2.  <span data-ttu-id="442ac-131">Asegúrese de que [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] esté instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="442ac-131">Ensure that [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] is installed on the computer.</span></span>  
  
3.  <span data-ttu-id="442ac-132">Con [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], abra el archivo de la solución ReceiveContextProductGenerator.sln.</span><span class="sxs-lookup"><span data-stu-id="442ac-132">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the ReceiveContextProductGenerator.sln solution file.</span></span>  
  
4.  <span data-ttu-id="442ac-133">Para compilar la solución, presione Ctrl+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="442ac-133">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
5.  <span data-ttu-id="442ac-134">Para ejecutar la solución, presione CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="442ac-134">To run the solution, press CTRL+F5.</span></span>
