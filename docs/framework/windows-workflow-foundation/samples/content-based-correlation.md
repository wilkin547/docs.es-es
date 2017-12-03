---
title: "Correlación basada en contenidos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8638b5d6-1d59-456d-8acd-179a5b39b260
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b5fea83ff6ac73fc26c419d9f7d5e8c5fe571135
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="content-based-correlation"></a><span data-ttu-id="063f2-102">Correlación basada en contenidos</span><span class="sxs-lookup"><span data-stu-id="063f2-102">Content-Based Correlation</span></span>
<span data-ttu-id="063f2-103">En este ejemplo se muestra cómo las actividades de mensajería (<xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.SendReply> y <xref:System.ServiceModel.Activities.ReceiveReply>) se pueden utilizar con varias correlaciones basadas en contenido y con una correlación basada en contenido.</span><span class="sxs-lookup"><span data-stu-id="063f2-103">This sample demonstrates how the messaging activities (<xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.SendReply>, and <xref:System.ServiceModel.Activities.ReceiveReply>) can be used with multiple content-based correlations.and content-based correlation.</span></span> <span data-ttu-id="063f2-104">En este escenario, en primer lugar se inicializa una correlación en función de un identificador de pedido de compra y, a continuación, se crea otra correlación basada en el identificador del cliente.</span><span class="sxs-lookup"><span data-stu-id="063f2-104">In this scenario, a correlation is first initialized based on a purchase order ID, and then another correlation is created later based on the customer ID.</span></span> <span data-ttu-id="063f2-105">Así se muestra cómo una actividad <xref:System.ServiceModel.Activities.Receive> puede seguir una correlación existente e inicializar una nueva correlación basada en el mismo mensaje de entrada.</span><span class="sxs-lookup"><span data-stu-id="063f2-105">This shows how a <xref:System.ServiceModel.Activities.Receive> activity can both follow an existing correlation and initialize a new correlation based on the same incoming message.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="063f2-106">Demostraciones</span><span class="sxs-lookup"><span data-stu-id="063f2-106">Demonstrates</span></span>  
 <span data-ttu-id="063f2-107">Actividades de mensajería y correlación basada en contenido</span><span class="sxs-lookup"><span data-stu-id="063f2-107">Messaging activities and content-based correlation</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="063f2-108">Explicación</span><span class="sxs-lookup"><span data-stu-id="063f2-108">Discussion</span></span>  
 <span data-ttu-id="063f2-109">En este ejemplo se muestra cómo utilizar varias correlaciones basadas en contenido.</span><span class="sxs-lookup"><span data-stu-id="063f2-109">This sample shows how to use multiple content-based correlations.</span></span>  <span data-ttu-id="063f2-110">En este escenario, en primer lugar se inicializa una correlación en función de un identificador de pedido de compra y, a continuación, se crea otra correlación basada en el identificador del cliente.</span><span class="sxs-lookup"><span data-stu-id="063f2-110">In this scenario, a correlation is first initialized based on a purchase order ID, and then another correlation is created later based on the customer ID.</span></span>  <span data-ttu-id="063f2-111">Las correlaciones se colocan en cascada utilizando una actividad <xref:System.ServiceModel.Activities.Receive> que sigue una correlación existente (PurchaseOrderId) e inicializa una nueva correlación (CustomerId) en función del mismo mensaje de entrada.</span><span class="sxs-lookup"><span data-stu-id="063f2-111">The correlations are cascaded using a <xref:System.ServiceModel.Activities.Receive> activity that both follows an existing correlation (PurchaseOrderId) and initializes a new correlation (CustomerId) based on the same incoming message.</span></span>  <span data-ttu-id="063f2-112">Para ello, la actividad <xref:System.ServiceModel.Activities.Receive> utiliza las propiedades <xref:System.ServiceModel.Activities.Receive.CorrelatesOn%2A>, <xref:System.ServiceModel.Activities.Receive.CorrelatesWith%2A> y <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A>.</span><span class="sxs-lookup"><span data-stu-id="063f2-112">To accomplish this, the <xref:System.ServiceModel.Activities.Receive> activity uses the <xref:System.ServiceModel.Activities.Receive.CorrelatesOn%2A>, <xref:System.ServiceModel.Activities.Receive.CorrelatesWith%2A> and <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A> properties.</span></span>  
  
## <a name="to-use-this-sample"></a><span data-ttu-id="063f2-113">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="063f2-113">To use this sample</span></span>  
  
1.  <span data-ttu-id="063f2-114">Abra [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] con permisos elevados, haciendo clic en el [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] icono y seleccione **ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="063f2-114">Open [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] with elevated permissions, by right-clicking the [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] icon and selecting **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="063f2-115">Con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], abra el archivo de solución CascadingCorrelation.sln.</span><span class="sxs-lookup"><span data-stu-id="063f2-115">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the CascadingCorrelation.sln solution file.</span></span>  
  
3.  <span data-ttu-id="063f2-116">Para compilar la solución, presione Ctrl+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="063f2-116">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
4.  <span data-ttu-id="063f2-117">Presione F5 para ejecutar el servidor.</span><span class="sxs-lookup"><span data-stu-id="063f2-117">To run the server, press F5.</span></span>  
  
5.  <span data-ttu-id="063f2-118">Cuando el servicio está listo y realizando escuchas para los mensajes, en el Explorador de soluciones, haga clic con el botón secundario en el proyecto Cliente y ejecútelo.</span><span class="sxs-lookup"><span data-stu-id="063f2-118">Once the service is ready and listening for messages, in Solution Explorer, right-click the Client project and run it.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="063f2-119">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="063f2-119">The samples may already be installed on your machine.</span></span> <span data-ttu-id="063f2-120">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="063f2-120">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="063f2-121">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="063f2-121">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="063f2-122">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="063f2-122">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\ContentBasedCorrelation`