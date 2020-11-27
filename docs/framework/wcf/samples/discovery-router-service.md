---
title: Servicio de enrutador de detección
ms.date: 03/30/2017
ms.assetid: 3d30af47-b24f-40e5-833a-24d77125c9e6
ms.openlocfilehash: f3ea32d10e27eceb3edcee8b6aeacbf9c5ebc6f1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96292654"
---
# <a name="discovery-router-service"></a><span data-ttu-id="3f761-102">Servicio de enrutador de detección</span><span class="sxs-lookup"><span data-stu-id="3f761-102">Discovery Router Service</span></span>

<span data-ttu-id="3f761-103">En este ejemplo se muestra cómo reenviar los mensajes de detección a otro punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="3f761-103">This sample demonstrates how to forward discovery messages to another endpoint.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="3f761-104">Muestra</span><span class="sxs-lookup"><span data-stu-id="3f761-104">Demonstrates</span></span>  

 <span data-ttu-id="3f761-105">Enrutamiento de la detección</span><span class="sxs-lookup"><span data-stu-id="3f761-105">Discovery Routing</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="3f761-106">Discusión</span><span class="sxs-lookup"><span data-stu-id="3f761-106">Discussion</span></span>  

 <span data-ttu-id="3f761-107">El enrutamiento de la detección es útil en un escenario en el que un cliente busca un servicio mediante un proxy y el proxy no conoce dicho servicio, pero conoce otro proxy.</span><span class="sxs-lookup"><span data-stu-id="3f761-107">Discovery routing is useful in a scenario in which a client is looking for a service using a proxy and the proxy is unaware of such a service, but knows of another proxy.</span></span> <span data-ttu-id="3f761-108">Este proxy puede reenviar el paquete de detección desde este cliente al segundo proxy.</span><span class="sxs-lookup"><span data-stu-id="3f761-108">This proxy can forward the discovery packet from this client to the second proxy.</span></span> <span data-ttu-id="3f761-109">El segundo proxy puede buscar el servicio y devolver las respuestas al cliente original.</span><span class="sxs-lookup"><span data-stu-id="3f761-109">The second proxy can look for the service and return the responses to the original client.</span></span>  
  
 <span data-ttu-id="3f761-110">En este ejemplo, un cliente envía un mensaje a un componente de enrutamiento de la detección.</span><span class="sxs-lookup"><span data-stu-id="3f761-110">In this sample, a client sends a message to a discovery routing component.</span></span> <span data-ttu-id="3f761-111">Este mensaje se envía a un extremo concreto en el enrutador de detección.</span><span class="sxs-lookup"><span data-stu-id="3f761-111">This message is sent to a specific endpoint on the discovery router.</span></span> <span data-ttu-id="3f761-112">A continuación, el enrutador reenvía el mensaje a un extremo de multidifusión UDP.</span><span class="sxs-lookup"><span data-stu-id="3f761-112">The router then forwards the message to a UDP multicast endpoint.</span></span> <span data-ttu-id="3f761-113">El mensaje de sondeo sale al extremo de multidifusión y un servicio que realiza escuchas en una dirección de multidifusión UDP responde a ese enrutador de detección.</span><span class="sxs-lookup"><span data-stu-id="3f761-113">The probe message goes out to the multicast endpoint and a service listening on a UDP multicast address responds to that discovery router.</span></span> <span data-ttu-id="3f761-114">El enrutador de detección recopila las respuestas y las envía de nuevo al cliente.</span><span class="sxs-lookup"><span data-stu-id="3f761-114">The discovery router collects the responses and sends them back to the client.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="3f761-115">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="3f761-115">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="3f761-116">Compile el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="3f761-116">Build the sample.</span></span>  
  
2. <span data-ttu-id="3f761-117">Ejecute la aplicación ejecutable DiscoveryRouter.</span><span class="sxs-lookup"><span data-stu-id="3f761-117">Run the DiscoveryRouter executable.</span></span>  
  
3. <span data-ttu-id="3f761-118">Ejecute el ejecutable de servicio desde el directorio de compilación.</span><span class="sxs-lookup"><span data-stu-id="3f761-118">Run the service executable from the build directory.</span></span>  
  
4. <span data-ttu-id="3f761-119">Ejecute la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="3f761-119">Run the client executable.</span></span> <span data-ttu-id="3f761-120">Observe que el cliente busca el servicio.</span><span class="sxs-lookup"><span data-stu-id="3f761-120">Note that the client locates the service.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="3f761-121">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="3f761-121">The samples may already be installed on your machine.</span></span> <span data-ttu-id="3f761-122">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="3f761-122">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="3f761-123">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="3f761-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="3f761-124">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="3f761-124">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\DiscoveryRouter`
