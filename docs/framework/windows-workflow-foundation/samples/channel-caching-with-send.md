---
title: "Almacenamiento en caché de canales con envío"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e69a2502-25cb-43bf-b8d2-95fbdecb41cb
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7f8a11397fe161edad6f726c1d6df9ed09dad54a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="channel-caching-with-send"></a><span data-ttu-id="1a59e-102">Almacenamiento en caché de canales con envío</span><span class="sxs-lookup"><span data-stu-id="1a59e-102">Channel Caching with Send</span></span>
<span data-ttu-id="1a59e-103"><xref:System.ServiceModel.Activities.SendMessageChannelCache> permite a los usuarios tener niveles diferentes de almacenamiento en caché de canales con actividades <xref:System.ServiceModel.Activities.Send> y <xref:System.ServiceModel.Activities.SendParametersContent>.</span><span class="sxs-lookup"><span data-stu-id="1a59e-103">The <xref:System.ServiceModel.Activities.SendMessageChannelCache> enables users to have different levels of channel caching with <xref:System.ServiceModel.Activities.Send> and <xref:System.ServiceModel.Activities.SendParametersContent> activities.</span></span> <span data-ttu-id="1a59e-104">El almacenamiento en caché en el nivel de instancia se habilita de forma predeterminada y en este ejemplo se muestran las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="1a59e-104">Instance-level caching is enabled by default and this sample demonstrates the following features:</span></span>  
  
1.  <span data-ttu-id="1a59e-105">Comparta un <xref:System.ServiceModel.Activities.SendMessageChannelCache> en un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="1a59e-105">Share a <xref:System.ServiceModel.Activities.SendMessageChannelCache> across an application domain.</span></span>  
  
2.  <span data-ttu-id="1a59e-106">Deshabilite el almacenamiento en caché de canales.</span><span class="sxs-lookup"><span data-stu-id="1a59e-106">Disable channel caching.</span></span>  
  
3.  <span data-ttu-id="1a59e-107">Comparta <xref:System.ServiceModel.Activities.SendMessageChannelCache> entre distintas instancias de flujo de trabajo en <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="1a59e-107">Share a <xref:System.ServiceModel.Activities.SendMessageChannelCache> among workflow instances in a <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="1a59e-108">Demostraciones</span><span class="sxs-lookup"><span data-stu-id="1a59e-108">Demonstrates</span></span>  
 <span data-ttu-id="1a59e-109">Extensión de <xref:System.ServiceModel.Activities.SendMessageChannelCache> y actividades <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.ReceiveContent> y <xref:System.ServiceModel.Activities.SendReply>.</span><span class="sxs-lookup"><span data-stu-id="1a59e-109"><xref:System.ServiceModel.Activities.SendMessageChannelCache> extension, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.ReceiveContent> and <xref:System.ServiceModel.Activities.SendReply> activities.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="1a59e-110">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="1a59e-110">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="1a59e-111">Cargue la solución de proyecto en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] y compile el proyecto.</span><span class="sxs-lookup"><span data-stu-id="1a59e-111">Load the project solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] and build the project.</span></span>  
  
2.  <span data-ttu-id="1a59e-112">Ejecute la aplicación EchoWorkflowService generada en \EchoWorkflowService\bin\debug.</span><span class="sxs-lookup"><span data-stu-id="1a59e-112">Run the EchoWorkflowService application generated in \EchoWorkflowService\bin\debug.</span></span>  
  
3.  <span data-ttu-id="1a59e-113">Ejecute la aplicación EchoWorkflowClient generada en .\EchoWorkflowClient\bin\debug.</span><span class="sxs-lookup"><span data-stu-id="1a59e-113">Run the EchoWorkflowClient application generated in .\EchoWorkflowClient\bin\debug.</span></span>  
  
4.  <span data-ttu-id="1a59e-114">El cliente llama a la operación Echo en el servicio e imprime los resultados.</span><span class="sxs-lookup"><span data-stu-id="1a59e-114">The client calls the Echo operation on the service and prints the results.</span></span> <span data-ttu-id="1a59e-115">Cuando se impriman los resultados, presione ENTRAR para salir del cliente y del servicio.</span><span class="sxs-lookup"><span data-stu-id="1a59e-115">When the results have been printed, press ENTER to exit the client and the service.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1a59e-116">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="1a59e-116">The samples may already be installed on your machine.</span></span> <span data-ttu-id="1a59e-117">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="1a59e-117">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="1a59e-118">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1a59e-118">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="1a59e-119">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="1a59e-119">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\ChannelCache`
