---
title: Desarrollo de servicios
ms.date: 03/30/2017
ms.assetid: ac361bfb-017d-4da9-a2d7-fc0fb72d65bb
ms.openlocfilehash: 4d9efcb4da064021d93345285982c0cbd29dde2e
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2018
ms.locfileid: "33803587"
---
# <a name="deploying-services"></a><span data-ttu-id="5f3e4-102">Desarrollo de servicios</span><span class="sxs-lookup"><span data-stu-id="5f3e4-102">Deploying Services</span></span>
<span data-ttu-id="5f3e4-103">Este tema describe cómo puede implementar una aplicación de Windows Communication Foundation (WCF) en un entorno de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="5f3e4-103">This topic describes how you can deploy a Windows Communication Foundation (WCF) application to a run-time environment.</span></span>  
  
## <a name="choosing-the-hosting-environment-for-your-application"></a><span data-ttu-id="5f3e4-104">Elegir el entorno de alojamiento para su aplicación</span><span class="sxs-lookup"><span data-stu-id="5f3e4-104">Choosing the Hosting Environment for Your Application</span></span>  
 <span data-ttu-id="5f3e4-105">Servicios WCF están diseñados para ejecutarse en cualquier proceso de Windows que admite código administrado.</span><span class="sxs-lookup"><span data-stu-id="5f3e4-105">WCF services are designed to run in any Windows process that supports managed code.</span></span> <span data-ttu-id="5f3e4-106">Para activarse, se debe hospedar un servicio dentro de un entorno de tiempo en ejecución que lo crea y controla su contexto y duración.</span><span class="sxs-lookup"><span data-stu-id="5f3e4-106">To become active, a service must be hosted within a run-time environment that creates it and controls its context and lifetime.</span></span> <span data-ttu-id="5f3e4-107">Las opciones de alojamiento son ejecutarse dentro de la aplicación de consola más simple a entornos de servidor como un servicio de Windows, Internet Information Server (IIS), o dentro de un proceso de trabajo administrado por el Servicio de Activación de Windows (WAS).</span><span class="sxs-lookup"><span data-stu-id="5f3e4-107">Hosting options range from running inside the simplest console application to server environments like a Windows service, Internet Information Services (IIS), or within a worker process managed by the Windows Activation Service (WAS).</span></span> <span data-ttu-id="5f3e4-108">Para revisar las opciones de hospedaje diferentes para la aplicación de WCF, vea [servicios de hospedaje](../../../../docs/framework/wcf/hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="5f3e4-108">To review the different hosting options for your WCF application, see [Hosting Services](../../../../docs/framework/wcf/hosting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f3e4-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="5f3e4-109">See Also</span></span>  
 [<span data-ttu-id="5f3e4-110">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="5f3e4-110">Hosting</span></span>](../../../../docs/framework/wcf/feature-details/hosting.md)  
 [<span data-ttu-id="5f3e4-111">Servicios de hospedaje</span><span class="sxs-lookup"><span data-stu-id="5f3e4-111">Hosting Services</span></span>](../../../../docs/framework/wcf/hosting-services.md)
