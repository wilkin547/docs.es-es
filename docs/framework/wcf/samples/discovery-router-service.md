---
title: "Servicio de enrutador de detección"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3d30af47-b24f-40e5-833a-24d77125c9e6
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 663ece44a18ae073412376bc11a1d70927740e8a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="discovery-router-service"></a><span data-ttu-id="d0acf-102">Servicio de enrutador de detección</span><span class="sxs-lookup"><span data-stu-id="d0acf-102">Discovery Router Service</span></span>
<span data-ttu-id="d0acf-103">En este ejemplo se muestra cómo reenviar los mensajes de detección a otro punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="d0acf-103">This sample demonstrates how to forward discovery messages to another endpoint.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="d0acf-104">Demostraciones</span><span class="sxs-lookup"><span data-stu-id="d0acf-104">Demonstrates</span></span>  
 <span data-ttu-id="d0acf-105">Enrutamiento de la detección</span><span class="sxs-lookup"><span data-stu-id="d0acf-105">Discovery Routing</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="d0acf-106">Explicación</span><span class="sxs-lookup"><span data-stu-id="d0acf-106">Discussion</span></span>  
 <span data-ttu-id="d0acf-107">El enrutamiento de la detección es útil en un escenario en el que un cliente busca un servicio mediante un proxy y el proxy no conoce dicho servicio, pero conoce otro proxy.</span><span class="sxs-lookup"><span data-stu-id="d0acf-107">Discovery routing is useful in a scenario in which a client is looking for a service using a proxy and the proxy is unaware of such a service, but knows of another proxy.</span></span> <span data-ttu-id="d0acf-108">Este proxy puede reenviar el paquete de detección desde este cliente al segundo proxy.</span><span class="sxs-lookup"><span data-stu-id="d0acf-108">This proxy can forward the discovery packet from this client to the second proxy.</span></span> <span data-ttu-id="d0acf-109">El segundo proxy puede buscar el servicio y devolver las respuestas al cliente original.</span><span class="sxs-lookup"><span data-stu-id="d0acf-109">The second proxy can look for the service and return the responses to the original client.</span></span>  
  
 <span data-ttu-id="d0acf-110">En este ejemplo, un cliente envía un mensaje a un componente de enrutamiento de la detección.</span><span class="sxs-lookup"><span data-stu-id="d0acf-110">In this sample, a client sends a message to a discovery routing component.</span></span> <span data-ttu-id="d0acf-111">Este mensaje se envía a un extremo concreto en el enrutador de detección.</span><span class="sxs-lookup"><span data-stu-id="d0acf-111">This message is sent to a specific endpoint on the discovery router.</span></span> <span data-ttu-id="d0acf-112">A continuación, el enrutador reenvía el mensaje a un extremo de multidifusión UDP.</span><span class="sxs-lookup"><span data-stu-id="d0acf-112">The router then forwards the message to a UDP multicast endpoint.</span></span> <span data-ttu-id="d0acf-113">El mensaje de sondeo sale al extremo de multidifusión y un servicio que realiza escuchas en una dirección de multidifusión UDP responde a ese enrutador de detección.</span><span class="sxs-lookup"><span data-stu-id="d0acf-113">The probe message goes out to the multicast endpoint and a service listening on a UDP multicast address responds to that discovery router.</span></span> <span data-ttu-id="d0acf-114">El enrutador de detección recopila las respuestas y las envía de nuevo al cliente.</span><span class="sxs-lookup"><span data-stu-id="d0acf-114">The discovery router collects the responses and sends them back to the client.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="d0acf-115">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="d0acf-115">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="d0acf-116">Compilar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="d0acf-116">Build the sample.</span></span>  
  
2.  <span data-ttu-id="d0acf-117">Ejecute la aplicación ejecutable DiscoveryRouter.</span><span class="sxs-lookup"><span data-stu-id="d0acf-117">Run the DiscoveryRouter executable.</span></span>  
  
3.  <span data-ttu-id="d0acf-118">Ejecute el ejecutable de servicio desde el directorio de compilación.</span><span class="sxs-lookup"><span data-stu-id="d0acf-118">Run the service executable from the build directory.</span></span>  
  
4.  <span data-ttu-id="d0acf-119">Ejecute la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="d0acf-119">Run the client executable.</span></span> <span data-ttu-id="d0acf-120">Observe que el cliente busca el servicio.</span><span class="sxs-lookup"><span data-stu-id="d0acf-120">Note that the client locates the service.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d0acf-121">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="d0acf-121">The samples may already be installed on your machine.</span></span> <span data-ttu-id="d0acf-122">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="d0acf-122">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="d0acf-123">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d0acf-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d0acf-124">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="d0acf-124">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\DiscoveryRouter`
