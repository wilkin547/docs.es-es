---
title: Retraso duradero en XAMLX
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: efc38df4-2d34-453c-8e59-2c21d1307354
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7396c5ca2119dcf096036695233d5c89a3f014f7
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="durable-delay-in-xamlx"></a><span data-ttu-id="26a22-102">Retraso duradero en XAMLX</span><span class="sxs-lookup"><span data-stu-id="26a22-102">Durable Delay in XAMLX</span></span>
<span data-ttu-id="26a22-103">En este ejemplo se muestra cómo utilizar un retraso duradero, que es un retraso que conserva el flujo de trabajo en un dispositivo duradero durante el tiempo que dura.</span><span class="sxs-lookup"><span data-stu-id="26a22-103">This sample demonstrates how to use a durable delay, which is a delay that persists the workflow to a durable device during the delay.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="26a22-104">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="26a22-104">The samples may already be installed on your machine.</span></span> <span data-ttu-id="26a22-105">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="26a22-105">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="26a22-106">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="26a22-106">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="26a22-107">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="26a22-107">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\DurableDelayXamlx`  
  
## <a name="discussion"></a><span data-ttu-id="26a22-108">Explicación</span><span class="sxs-lookup"><span data-stu-id="26a22-108">Discussion</span></span>  
 <span data-ttu-id="26a22-109">El flujo de trabajo de muestra contiene dos mensajes a un archivo local, separados por un retraso.</span><span class="sxs-lookup"><span data-stu-id="26a22-109">The sample workflow contains two messages to a local file that are separated by a delay.</span></span> <span data-ttu-id="26a22-110">Cuando el retraso se activa, el flujo de trabajo se descarga y espera 5 segundos en el almacén de instancias de flujo de trabajo antes de recargarse en la memoria.</span><span class="sxs-lookup"><span data-stu-id="26a22-110">When the delay is triggered, the workflow is unloaded and waits 5 seconds in the workflow instance store before being reloaded in memory.</span></span>  
  
 <span data-ttu-id="26a22-111">El archivo .xamlx es un servicio de flujo de trabajo hospedado en [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="26a22-111">The .xamlx file is a workflow service that is hosted in [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].</span></span> [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]<span data-ttu-id="26a22-112"> usa Cassini que usa un host de servicio de flujo de trabajo para hospedar el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="26a22-112"> uses Cassini that uses a workflow service host to host the workflow.</span></span>  
  
 <span data-ttu-id="26a22-113">Además de hospedar el flujo de trabajo, el host de servicio de flujo de trabajo administra las instancias de flujo de trabajo cargándolas y descargándolas.</span><span class="sxs-lookup"><span data-stu-id="26a22-113">In addition to hosting the workflow, the workflow service host manages the workflow instances by loading and unloading them.</span></span> <span data-ttu-id="26a22-114">Para iniciar una instancia de la definición de [!INCLUDE[wf](../../../../includes/wf-md.md)] (en el host de servicio de flujo de trabajo), establezca un cliente que envíe un mensaje a la actividad <xref:System.ServiceModel.Activities.Receive> en el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="26a22-114">To start an instance of the [!INCLUDE[wf](../../../../includes/wf-md.md)] definition (on the workflow service host), set a client that sends a message to the <xref:System.ServiceModel.Activities.Receive> activity in the workflow.</span></span> <span data-ttu-id="26a22-115"><xref:System.ServiceModel.Activities.Receive> tiene su propiedad <xref:System.ServiceModel.Activities.Receive.CanCreateInstance%2A> establecida en `true`, lo que le permite crear una nueva instancia del flujo de trabajo después de recibir un mensaje.</span><span class="sxs-lookup"><span data-stu-id="26a22-115">This <xref:System.ServiceModel.Activities.Receive> has its <xref:System.ServiceModel.Activities.Receive.CanCreateInstance%2A> property set to `true`, enabling it to create a new instance of the workflow once it receives a message.</span></span>  
  
 <span data-ttu-id="26a22-116">Durante la inicialización, se agrega un comportamiento de instancia de descarga al archivo de configuración que especifica al host de servicio de flujo de trabajo en el que debe descargarse una instancia al almacén de persistencia (base de datos).</span><span class="sxs-lookup"><span data-stu-id="26a22-116">During initialization, an unload instance behavior is added to the configuration file that specifies to the workflow service host under which it should unload an instance to the persistence store (database).</span></span> <span data-ttu-id="26a22-117">En este ejemplo, descarga la instancia de forma inmediata cuando el flujo de trabajo pasa a estado inactivo (cuando el retraso se activa).</span><span class="sxs-lookup"><span data-stu-id="26a22-117">For this sample, it unloads the instance immediately after the workflow goes idle (when the delay is triggered).</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="26a22-118">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="26a22-118">To use this sample</span></span>  
  
1.  <span data-ttu-id="26a22-119">Abra un símbolo del sistema de [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="26a22-119">Open a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt.</span></span>  
  
2.  <span data-ttu-id="26a22-120">Navegue hasta la carpeta DurableDelayXamlx\CS.</span><span class="sxs-lookup"><span data-stu-id="26a22-120">Navigate to the DurableDelayXamlx\CS folder.</span></span>  
  
3.  <span data-ttu-id="26a22-121">Ejecute Setup.cmd.</span><span class="sxs-lookup"><span data-stu-id="26a22-121">Run Setup.cmd.</span></span>  
  
4.  <span data-ttu-id="26a22-122">Ejecute [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] como administrador.</span><span class="sxs-lookup"><span data-stu-id="26a22-122">Run [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] as an administrator.</span></span>  
  
5.  <span data-ttu-id="26a22-123">Abra el archivo de solución DurableDelayXamlx.sln.</span><span class="sxs-lookup"><span data-stu-id="26a22-123">Open the DurableDelayXamlx.sln solution file.</span></span>  
  
6.  <span data-ttu-id="26a22-124">En **el Explorador de soluciones**, haga clic en la solución y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="26a22-124">In **Solution Explorer**, right-click the solution and select **Properties**.</span></span>  
  
7.  <span data-ttu-id="26a22-125">Seleccione **proyectos de inicio múltiples** y establezca ambos proyectos en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="26a22-125">Select **Multiple startup projects** and set both projects to **Start**.</span></span>  
  
8.  <span data-ttu-id="26a22-126">Para compilar la solución, presione Ctrl+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="26a22-126">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
9. <span data-ttu-id="26a22-127">Para ejecutar la solución, presione CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="26a22-127">To run the solution, press CTRL+F5.</span></span>  
  
#### <a name="to-uninstall-this-sample"></a><span data-ttu-id="26a22-128">Para desinstalar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="26a22-128">To uninstall this sample</span></span>  
  
1.  <span data-ttu-id="26a22-129">Abra un símbolo del sistema de [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="26a22-129">Open a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt.</span></span>  
  
2.  <span data-ttu-id="26a22-130">Navegue hasta la carpeta DurableDelayXamlx\CS.</span><span class="sxs-lookup"><span data-stu-id="26a22-130">Navigate to the DurableDelayXamlx\CS folder.</span></span>  
  
3.  <span data-ttu-id="26a22-131">Ejecute Cleanup.cmd.</span><span class="sxs-lookup"><span data-stu-id="26a22-131">Run Cleanup.cmd.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="26a22-132">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="26a22-132">The samples may already be installed on your machine.</span></span> <span data-ttu-id="26a22-133">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="26a22-133">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="26a22-134">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="26a22-134">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="26a22-135">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="26a22-135">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\DurableDelayXamlX`
