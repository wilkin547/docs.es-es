---
title: Desarrollo de servicios
ms.date: 03/30/2017
ms.assetid: ac361bfb-017d-4da9-a2d7-fc0fb72d65bb
ms.openlocfilehash: 684b781c568518cfb321d8021e4f7062e855e6aa
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798145"
---
# <a name="deploying-services"></a><span data-ttu-id="b1283-102">Desarrollo de servicios</span><span class="sxs-lookup"><span data-stu-id="b1283-102">Deploying Services</span></span>
<span data-ttu-id="b1283-103">En este tema se describe cómo puede implementar una aplicación Windows Communication Foundation (WCF) en un entorno de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b1283-103">This topic describes how you can deploy a Windows Communication Foundation (WCF) application to a run-time environment.</span></span>  
  
## <a name="choosing-the-hosting-environment-for-your-application"></a><span data-ttu-id="b1283-104">Elegir el entorno de alojamiento para su aplicación</span><span class="sxs-lookup"><span data-stu-id="b1283-104">Choosing the Hosting Environment for Your Application</span></span>  
 <span data-ttu-id="b1283-105">Los servicios WCF están diseñados para ejecutarse en cualquier proceso de Windows que admita código administrado.</span><span class="sxs-lookup"><span data-stu-id="b1283-105">WCF services are designed to run in any Windows process that supports managed code.</span></span> <span data-ttu-id="b1283-106">Para activarse, se debe hospedar un servicio dentro de un entorno de tiempo en ejecución que lo crea y controla su contexto y duración.</span><span class="sxs-lookup"><span data-stu-id="b1283-106">To become active, a service must be hosted within a run-time environment that creates it and controls its context and lifetime.</span></span> <span data-ttu-id="b1283-107">Las opciones de alojamiento son ejecutarse dentro de la aplicación de consola más simple a entornos de servidor como un servicio de Windows, Internet Information Server (IIS), o dentro de un proceso de trabajo administrado por el Servicio de Activación de Windows (WAS).</span><span class="sxs-lookup"><span data-stu-id="b1283-107">Hosting options range from running inside the simplest console application to server environments like a Windows service, Internet Information Services (IIS), or within a worker process managed by the Windows Activation Service (WAS).</span></span> <span data-ttu-id="b1283-108">Para revisar las distintas opciones de hospedaje de la aplicación WCF, vea [servicios de hospedaje](../hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="b1283-108">To review the different hosting options for your WCF application, see [Hosting Services](../hosting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1283-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="b1283-109">See also</span></span>

- [<span data-ttu-id="b1283-110">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="b1283-110">Hosting</span></span>](../feature-details/hosting.md)
- [<span data-ttu-id="b1283-111">Servicios de hospedaje</span><span class="sxs-lookup"><span data-stu-id="b1283-111">Hosting Services</span></span>](../hosting-services.md)
