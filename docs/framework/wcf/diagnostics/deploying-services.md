---
title: Desarrollo de servicios
ms.date: 03/30/2017
ms.assetid: ac361bfb-017d-4da9-a2d7-fc0fb72d65bb
ms.openlocfilehash: 07bd2a3938f238336dc00fa2e0826a28a9363a4a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294812"
---
# <a name="deploying-services"></a><span data-ttu-id="53e6b-102">Desarrollo de servicios</span><span class="sxs-lookup"><span data-stu-id="53e6b-102">Deploying Services</span></span>

<span data-ttu-id="53e6b-103">En este tema se describe cómo puede implementar una aplicación Windows Communication Foundation (WCF) en un entorno de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="53e6b-103">This topic describes how you can deploy a Windows Communication Foundation (WCF) application to a run-time environment.</span></span>  
  
## <a name="choosing-the-hosting-environment-for-your-application"></a><span data-ttu-id="53e6b-104">Elegir el entorno de alojamiento para su aplicación</span><span class="sxs-lookup"><span data-stu-id="53e6b-104">Choosing the Hosting Environment for Your Application</span></span>  

 <span data-ttu-id="53e6b-105">Los servicios WCF están diseñados para ejecutarse en cualquier proceso de Windows que admita código administrado.</span><span class="sxs-lookup"><span data-stu-id="53e6b-105">WCF services are designed to run in any Windows process that supports managed code.</span></span> <span data-ttu-id="53e6b-106">Para activarse, se debe hospedar un servicio dentro de un entorno de tiempo en ejecución que lo crea y controla su contexto y duración.</span><span class="sxs-lookup"><span data-stu-id="53e6b-106">To become active, a service must be hosted within a run-time environment that creates it and controls its context and lifetime.</span></span> <span data-ttu-id="53e6b-107">Las opciones de alojamiento son ejecutarse dentro de la aplicación de consola más simple a entornos de servidor como un servicio de Windows, Internet Information Server (IIS), o dentro de un proceso de trabajo administrado por el Servicio de Activación de Windows (WAS).</span><span class="sxs-lookup"><span data-stu-id="53e6b-107">Hosting options range from running inside the simplest console application to server environments like a Windows service, Internet Information Services (IIS), or within a worker process managed by the Windows Activation Service (WAS).</span></span> <span data-ttu-id="53e6b-108">Para revisar las distintas opciones de hospedaje de la aplicación WCF, vea [servicios de hospedaje](../hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="53e6b-108">To review the different hosting options for your WCF application, see [Hosting Services](../hosting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53e6b-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="53e6b-109">See also</span></span>

- [<span data-ttu-id="53e6b-110">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="53e6b-110">Hosting</span></span>](../feature-details/hosting.md)
- [<span data-ttu-id="53e6b-111">Servicios de hospedaje</span><span class="sxs-lookup"><span data-stu-id="53e6b-111">Hosting Services</span></span>](../hosting-services.md)
