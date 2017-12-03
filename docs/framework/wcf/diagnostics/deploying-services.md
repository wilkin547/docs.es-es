---
title: Desarrollo de servicios
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ac361bfb-017d-4da9-a2d7-fc0fb72d65bb
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5e8a853ebfa84ab5517e34bd67ae38672fdacddf
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="deploying-services"></a><span data-ttu-id="9850b-102">Desarrollo de servicios</span><span class="sxs-lookup"><span data-stu-id="9850b-102">Deploying Services</span></span>
<span data-ttu-id="9850b-103">Este tema describe cómo puede implementar una aplicación [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] a un entorno en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9850b-103">This topic describes how you can deploy a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] application to a run-time environment.</span></span>  
  
## <a name="choosing-the-hosting-environment-for-your-application"></a><span data-ttu-id="9850b-104">Elegir el entorno de alojamiento para su aplicación</span><span class="sxs-lookup"><span data-stu-id="9850b-104">Choosing the Hosting Environment for Your Application</span></span>  
 <span data-ttu-id="9850b-105">Los servicios [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] están diseñados para ejecutarse en cualquier proceso de Windows que admite código administrado.</span><span class="sxs-lookup"><span data-stu-id="9850b-105">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services are designed to run in any Windows process that supports managed code.</span></span> <span data-ttu-id="9850b-106">Para activarse, se debe hospedar un servicio dentro de un entorno de tiempo en ejecución que lo crea y controla su contexto y duración.</span><span class="sxs-lookup"><span data-stu-id="9850b-106">To become active, a service must be hosted within a run-time environment that creates it and controls its context and lifetime.</span></span> <span data-ttu-id="9850b-107">Las opciones de alojamiento son ejecutarse dentro de la aplicación de consola más simple a entornos de servidor como un servicio de Windows, Internet Information Server (IIS), o dentro de un proceso de trabajo administrado por el Servicio de Activación de Windows (WAS).</span><span class="sxs-lookup"><span data-stu-id="9850b-107">Hosting options range from running inside the simplest console application to server environments like a Windows service, Internet Information Services (IIS), or within a worker process managed by the Windows Activation Service (WAS).</span></span> <span data-ttu-id="9850b-108">Para revisar las opciones de hospedaje diferentes para su [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] aplicación, consulte [servicios de hospedaje](../../../../docs/framework/wcf/hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="9850b-108">To review the different hosting options for your [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] application, see [Hosting Services](../../../../docs/framework/wcf/hosting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9850b-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="9850b-109">See Also</span></span>  
 [<span data-ttu-id="9850b-110">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="9850b-110">Hosting</span></span>](../../../../docs/framework/wcf/feature-details/hosting.md)  
 [<span data-ttu-id="9850b-111">Servicios de hospedaje</span><span class="sxs-lookup"><span data-stu-id="9850b-111">Hosting Services</span></span>](../../../../docs/framework/wcf/hosting-services.md)
