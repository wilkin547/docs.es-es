---
title: Servicio de enrutador de detección
ms.date: 03/30/2017
ms.assetid: 3d30af47-b24f-40e5-833a-24d77125c9e6
ms.openlocfilehash: 9c0c409eb6cf3146a198b9f4bcd6d76660f5da36
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43409119"
---
# <a name="discovery-router-service"></a><span data-ttu-id="bc997-102">Servicio de enrutador de detección</span><span class="sxs-lookup"><span data-stu-id="bc997-102">Discovery Router Service</span></span>
<span data-ttu-id="bc997-103">En este ejemplo se muestra cómo reenviar los mensajes de detección a otro punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="bc997-103">This sample demonstrates how to forward discovery messages to another endpoint.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="bc997-104">Demostraciones</span><span class="sxs-lookup"><span data-stu-id="bc997-104">Demonstrates</span></span>  
 <span data-ttu-id="bc997-105">Enrutamiento de la detección</span><span class="sxs-lookup"><span data-stu-id="bc997-105">Discovery Routing</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="bc997-106">Explicación</span><span class="sxs-lookup"><span data-stu-id="bc997-106">Discussion</span></span>  
 <span data-ttu-id="bc997-107">El enrutamiento de la detección es útil en un escenario en el que un cliente busca un servicio mediante un proxy y el proxy no conoce dicho servicio, pero conoce otro proxy.</span><span class="sxs-lookup"><span data-stu-id="bc997-107">Discovery routing is useful in a scenario in which a client is looking for a service using a proxy and the proxy is unaware of such a service, but knows of another proxy.</span></span> <span data-ttu-id="bc997-108">Este proxy puede reenviar el paquete de detección desde este cliente al segundo proxy.</span><span class="sxs-lookup"><span data-stu-id="bc997-108">This proxy can forward the discovery packet from this client to the second proxy.</span></span> <span data-ttu-id="bc997-109">El segundo proxy puede buscar el servicio y devolver las respuestas al cliente original.</span><span class="sxs-lookup"><span data-stu-id="bc997-109">The second proxy can look for the service and return the responses to the original client.</span></span>  
  
 <span data-ttu-id="bc997-110">En este ejemplo, un cliente envía un mensaje a un componente de enrutamiento de la detección.</span><span class="sxs-lookup"><span data-stu-id="bc997-110">In this sample, a client sends a message to a discovery routing component.</span></span> <span data-ttu-id="bc997-111">Este mensaje se envía a un extremo concreto en el enrutador de detección.</span><span class="sxs-lookup"><span data-stu-id="bc997-111">This message is sent to a specific endpoint on the discovery router.</span></span> <span data-ttu-id="bc997-112">A continuación, el enrutador reenvía el mensaje a un extremo de multidifusión UDP.</span><span class="sxs-lookup"><span data-stu-id="bc997-112">The router then forwards the message to a UDP multicast endpoint.</span></span> <span data-ttu-id="bc997-113">El mensaje de sondeo sale al extremo de multidifusión y un servicio que realiza escuchas en una dirección de multidifusión UDP responde a ese enrutador de detección.</span><span class="sxs-lookup"><span data-stu-id="bc997-113">The probe message goes out to the multicast endpoint and a service listening on a UDP multicast address responds to that discovery router.</span></span> <span data-ttu-id="bc997-114">El enrutador de detección recopila las respuestas y las envía de nuevo al cliente.</span><span class="sxs-lookup"><span data-stu-id="bc997-114">The discovery router collects the responses and sends them back to the client.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="bc997-115">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="bc997-115">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="bc997-116">Compilar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="bc997-116">Build the sample.</span></span>  
  
2.  <span data-ttu-id="bc997-117">Ejecute la aplicación ejecutable DiscoveryRouter.</span><span class="sxs-lookup"><span data-stu-id="bc997-117">Run the DiscoveryRouter executable.</span></span>  
  
3.  <span data-ttu-id="bc997-118">Ejecute el ejecutable de servicio desde el directorio de compilación.</span><span class="sxs-lookup"><span data-stu-id="bc997-118">Run the service executable from the build directory.</span></span>  
  
4.  <span data-ttu-id="bc997-119">Ejecute la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="bc997-119">Run the client executable.</span></span> <span data-ttu-id="bc997-120">Observe que el cliente busca el servicio.</span><span class="sxs-lookup"><span data-stu-id="bc997-120">Note that the client locates the service.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="bc997-121">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="bc997-121">The samples may already be installed on your machine.</span></span> <span data-ttu-id="bc997-122">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="bc997-122">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="bc997-123">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="bc997-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="bc997-124">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="bc997-124">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\DiscoveryRouter`
