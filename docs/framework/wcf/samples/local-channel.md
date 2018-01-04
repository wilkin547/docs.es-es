---
title: Canal local
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fa1917a4-f701-4e82-a439-14a16282c7cc
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1298b4b96006837f0634040c5c615adfa3a1a11b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="local-channel"></a><span data-ttu-id="a88b9-102">Canal local</span><span class="sxs-lookup"><span data-stu-id="a88b9-102">Local Channel</span></span>
<span data-ttu-id="a88b9-103">El canal local es un canal de transporte de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] que se utiliza para la comunicación dentro del mismo dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="a88b9-103">Local Channel is a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] transport channel that is used for communication within the same application domain.</span></span> <span data-ttu-id="a88b9-104">Esto es útil para los escenarios donde el cliente y el servicio se están ejecutando en el mismo dominio de aplicación y la sobrecarga de la pila del canal WCF típica (la serialización y deserialización de mensajes) se debe evitar.</span><span class="sxs-lookup"><span data-stu-id="a88b9-104">This is useful for scenarios where the client and the service are running in the same application domain and the overhead of the typical WCF channel stack (serialization and deserialization of messages) must be avoided.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="a88b9-105">Demostraciones</span><span class="sxs-lookup"><span data-stu-id="a88b9-105">Demonstrates</span></span>  
 <span data-ttu-id="a88b9-106">Canal local</span><span class="sxs-lookup"><span data-stu-id="a88b9-106">Local Channel</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="a88b9-107">Explicación</span><span class="sxs-lookup"><span data-stu-id="a88b9-107">Discussion</span></span>  
 <span data-ttu-id="a88b9-108">El ejemplo consta de dos archivos de proyecto:</span><span class="sxs-lookup"><span data-stu-id="a88b9-108">The sample consists of two project files:</span></span>  
  
-   <span data-ttu-id="a88b9-109">**LocalChannel**: la representación mediante programación del canal local dentro del dominio de aplicación actual.</span><span class="sxs-lookup"><span data-stu-id="a88b9-109">**LocalChannel**: The programmatic representation of the local channel within the current application domain.</span></span> <span data-ttu-id="a88b9-110">En este proyecto, el componente de envío coloca el mensaje en una cola en memoria y el componente receptor saca el mensaje de la cola para recibirlo.</span><span class="sxs-lookup"><span data-stu-id="a88b9-110">In this project, the sending component places the message in an in-memory queue and the receiving component de-queues the message to receive it.</span></span>  
  
-   <span data-ttu-id="a88b9-111">**ClientAndService**: este proyecto hospeda un servicio en una aplicación de consola y, a continuación, ejecuta un cliente para llamar al servicio desde dentro del mismo dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="a88b9-111">**ClientAndService**: This project hosts a service in a console application and then runs a client to call the service from within the same application domain.</span></span>  
  
 <span data-ttu-id="a88b9-112">El diseño del canal local omite la pila del canal y el proceso de serialización para aumentar la velocidad.</span><span class="sxs-lookup"><span data-stu-id="a88b9-112">The local channel design skips both the channel stack and the serialization process to increase speed.</span></span> <span data-ttu-id="a88b9-113">El canal de transporte local se implementa utilizando una cola para las llamadas del servicio de transporte desde el cliente al servicio y para devolver el valor al cliente.</span><span class="sxs-lookup"><span data-stu-id="a88b9-113">The local transport channel is implemented using a queue to transport service calls from the client to the service and to return back the value to the client.</span></span> <span data-ttu-id="a88b9-114">En lugar de serializar los parámetros y los valores devueltos, en el ejemplo se copian los objetos.</span><span class="sxs-lookup"><span data-stu-id="a88b9-114">Rather than serializing parameters and return values, the sample copies the objects.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="a88b9-115">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="a88b9-115">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="a88b9-116">Compile y ejecute la solución LocalChannel.</span><span class="sxs-lookup"><span data-stu-id="a88b9-116">Build and run the LocalChannel solution.</span></span>  
  
2.  <span data-ttu-id="a88b9-117">El host del servicio se inicia y el cliente llama al servicio utilizando el canal local.</span><span class="sxs-lookup"><span data-stu-id="a88b9-117">The service host is started and the client calls the service using the local channel.</span></span> <span data-ttu-id="a88b9-118">Una ventana de la consola aparece para mostrar los resultados de la llamada del servicio.</span><span class="sxs-lookup"><span data-stu-id="a88b9-118">A console window appears to display the results of the service call.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a88b9-119">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="a88b9-119">The samples may already be installed on your machine.</span></span> <span data-ttu-id="a88b9-120">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="a88b9-120">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="a88b9-121">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a88b9-121">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a88b9-122">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="a88b9-122">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\LocalChannel`
