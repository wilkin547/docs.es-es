---
title: "Ejemplo de búsqueda asincrónica"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7a713a25-c1f4-42e1-8c4a-93d64ca45a3b
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4b0b21e9d75c0145c9bd3fa5edf13913cf43f461
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="asynchronous-find-sample"></a><span data-ttu-id="c84e7-102">Ejemplo de búsqueda asincrónica</span><span class="sxs-lookup"><span data-stu-id="c84e7-102">Asynchronous Find Sample</span></span>
<span data-ttu-id="c84e7-103">En este ejemplo se muestra cómo utilizar la operación de búsqueda asincrónica desde una aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="c84e7-103">This sample shows how to use the asynchronous find operation from a client application.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="c84e7-104">Detalles del ejemplo</span><span class="sxs-lookup"><span data-stu-id="c84e7-104">Sample Details</span></span>  
 <span data-ttu-id="c84e7-105">La ventaja de seguir este patrón de diseño es que se notifica al cliente de forma asincrónica los extremos situados como resultado de la solicitud de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="c84e7-105">The benefit of following this design pattern is that the client is notified asynchronously of the endpoints located as a result of the find request.</span></span> <span data-ttu-id="c84e7-106">Para ver cómo funciona, abra el archivo Client.cs.</span><span class="sxs-lookup"><span data-stu-id="c84e7-106">To see how this works, open the Client.cs file.</span></span> <span data-ttu-id="c84e7-107">Observe que el objeto <xref:System.ServiceModel.Discovery.DiscoveryClient> tiene dos delegados adjuntados a sus controladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="c84e7-107">Note the <xref:System.ServiceModel.Discovery.DiscoveryClient> object has two delegates attached to its event handlers.</span></span> <span data-ttu-id="c84e7-108">Se llama a un delegado cuando se genera un evento <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted> y a otro cada vez que se provoca un evento <xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged>.</span><span class="sxs-lookup"><span data-stu-id="c84e7-108">One delegate is called when a <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted> event is raised and another is called each time a <xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged> event is raised.</span></span> <span data-ttu-id="c84e7-109">El ejemplo muestra cómo puede utilizar este patrón en su aplicación.</span><span class="sxs-lookup"><span data-stu-id="c84e7-109">The sample shows how you can utilize this pattern in your application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c84e7-110">Este ejemplo utiliza los puntos de conexión HTTP y, para ejecutarlo, se deben agregar las ACL de dirección URL apropiadas.</span><span class="sxs-lookup"><span data-stu-id="c84e7-110">This sample uses HTTP endpoints and to run, proper URL ACLs must be added.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="c84e7-111">[Configurar HTTP y HTTPS](../../../../docs/framework/wcf/feature-details/configuring-http-and-https.md).</span><span class="sxs-lookup"><span data-stu-id="c84e7-111"> [Configuring HTTP and HTTPS](../../../../docs/framework/wcf/feature-details/configuring-http-and-https.md).</span></span> <span data-ttu-id="c84e7-112">Al ejecutar el siguiente comando con privilegios elevados, se deberían agregar las ACL adecuadas.</span><span class="sxs-lookup"><span data-stu-id="c84e7-112">Executing the following command at an elevated privilege should add the appropriate ACLs.</span></span> <span data-ttu-id="c84e7-113">Puede que desee sustituir su dominio y nombre de usuario para los siguientes argumentos si el comando no funciona como debería.</span><span class="sxs-lookup"><span data-stu-id="c84e7-113">You may want to substitute your domain and username for the following arguments if the command does not work as is.</span></span> `netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="c84e7-114">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="c84e7-114">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="c84e7-115">Con [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], abra AsyncFind.sln.</span><span class="sxs-lookup"><span data-stu-id="c84e7-115">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the AsyncFind.sln.</span></span>  
  
2.  <span data-ttu-id="c84e7-116">Presione Ctrl+MAYÚS+B para compilar la solución.</span><span class="sxs-lookup"><span data-stu-id="c84e7-116">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
3.  <span data-ttu-id="c84e7-117">Abra un símbolo del sistema de [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], navegue hasta el directorio \WCF\Basic\Discovery\AsyncFind\CS\service\bin\Debug o \WCF\Basic\Discovery\AsyncFind\VB\service\bin\Debug, y ejecute Service.exe.</span><span class="sxs-lookup"><span data-stu-id="c84e7-117">Open a [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] command prompt and navigate to the \WCF\Basic\Discovery\AsyncFind\CS\service\bin\Debug or \WCF\Basic\Discovery\AsyncFind\VB\service\bin\Debug directory and run Service.exe.</span></span>  
  
4.  <span data-ttu-id="c84e7-118">Una vez iniciado el servicio, navegue al directorio \WCF\Basic\Discovery\AsyncFind\CS\client\bin\Debug o WCF\Basic\Discovery\AsyncFind\VB\client\bin\Debug, y ejecute Client.exe.</span><span class="sxs-lookup"><span data-stu-id="c84e7-118">After the service has started, navigate to the \WCF\Basic\Discovery\AsyncFind\CS\client\bin\Debug or WCF\Basic\Discovery\AsyncFind\VB\client\bin\Debug directory and run Client.exe.</span></span>  
  
5.  <span data-ttu-id="c84e7-119">Observe que el cliente puede localizar y llamar al servicio.</span><span class="sxs-lookup"><span data-stu-id="c84e7-119">Observe the client is able to locate and call the service.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c84e7-120">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="c84e7-120">The samples may already be installed on your machine.</span></span> <span data-ttu-id="c84e7-121">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="c84e7-121">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="c84e7-122">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c84e7-122">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c84e7-123">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="c84e7-123">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\AsyncFind`  
  
## <a name="see-also"></a><span data-ttu-id="c84e7-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="c84e7-124">See Also</span></span>
