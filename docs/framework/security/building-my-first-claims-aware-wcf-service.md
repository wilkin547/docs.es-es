---
title: "Compilación del primer servicio WCF para notificaciones"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e0e6d091-9a97-4888-8f2c-cbcee42d90ee
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: a27420609a6bcb6e30a351e4b84a899da9583d5e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="building-my-first-claims-aware-wcf-service"></a><span data-ttu-id="e2fa0-102">Compilación del primer servicio WCF para notificaciones</span><span class="sxs-lookup"><span data-stu-id="e2fa0-102">Building My First Claims-Aware WCF Service</span></span>
## <a name="applies-to"></a><span data-ttu-id="e2fa0-103">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="e2fa0-103">Applies To</span></span>  
  
-   <span data-ttu-id="e2fa0-104">Windows Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="e2fa0-104">Windows Identity Foundation (WIF)</span></span>  
  
-   <span data-ttu-id="e2fa0-105">Windows Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="e2fa0-105">Windows Communication Foundation (WCF)</span></span>  
  
## <a name="overview"></a><span data-ttu-id="e2fa0-106">Información general</span><span class="sxs-lookup"><span data-stu-id="e2fa0-106">Overview</span></span>  
 <span data-ttu-id="e2fa0-107">En este tema se describe el escenario para compilar servicios WCF para notificaciones mediante WIF.</span><span class="sxs-lookup"><span data-stu-id="e2fa0-107">This topic outlines the scenario of building claims-aware WCF services using WIF.</span></span> <span data-ttu-id="e2fa0-108">En un escenario de servicio Web para notificaciones suele haber tres participantes: el propio servicio Web, el usuario final y el servicio de token de seguridad (STS).</span><span class="sxs-lookup"><span data-stu-id="e2fa0-108">There are usually three participants in a claims-aware web service scenario: the web service itself, the end user, and the Security Token Service (STS).</span></span> <span data-ttu-id="e2fa0-109">En la ilustración siguiente se describe este escenario:</span><span class="sxs-lookup"><span data-stu-id="e2fa0-109">The following figure describes this scenario:</span></span>  
  
 <span data-ttu-id="e2fa0-110">![Servicio WCF para notificaciones de WIF básico](../../../docs/framework/security/media/wifbasicclaimsawarewcfservice.gif "WIFBasicClaimsAwareWCFService")</span><span class="sxs-lookup"><span data-stu-id="e2fa0-110">![WIF Basic Claims Aware WCF Service](../../../docs/framework/security/media/wifbasicclaimsawarewcfservice.gif "WIFBasicClaimsAwareWCFService")</span></span>  
  
1.  <span data-ttu-id="e2fa0-111">El cliente de servicio WCF (a veces denominado agente) usa WIF para enviar credenciales al STS que a su vez, y tras llevarse la autenticación a cabo correctamente, emite un token para el agente.</span><span class="sxs-lookup"><span data-stu-id="e2fa0-111">The WCF service client (sometimes called agent) uses WIF to send credentials to the STS and upon successful authentication, the agent is issued a token by the STS.</span></span>  
  
2.  <span data-ttu-id="e2fa0-112">El agente envía este token emitido por el STS al servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="e2fa0-112">The agent sends this STS-issued token to the WCF service.</span></span>  
  
3.  <span data-ttu-id="e2fa0-113">El servicio WCF para notificaciones se configura de forma que confíe en el STS y en los token que emite.</span><span class="sxs-lookup"><span data-stu-id="e2fa0-113">The claims-aware WCF service is configured to trust the STS and the tokens it issues.</span></span> <span data-ttu-id="e2fa0-114">Asimismo, usa WIF para validar el token y analizarlo.</span><span class="sxs-lookup"><span data-stu-id="e2fa0-114">The claims-aware WCF service uses WIF to validate the token and to parse it.</span></span> <span data-ttu-id="e2fa0-115">Los desarrolladores usan la API y los tipos de WIF adecuados, por ejemplo, **ClaimsPrincipal**, para las necesidades de la aplicación, como la implementación de autorización correspondiente.</span><span class="sxs-lookup"><span data-stu-id="e2fa0-115">Developers use the appropriate WIF API and types, for example, **ClaimsPrincipal** for the application’s needs, such as implementing authorization for it.</span></span>  
  
 <span data-ttu-id="e2fa0-116">A partir de .NET 4.5, WIF forma parte del paquete de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e2fa0-116">Starting from .NET 4.5, WIF is part of the .NET Framework package.</span></span> <span data-ttu-id="e2fa0-117">Poder disponer de las clases de WIF directamente en el marco de trabajo permite una integración mucho más profunda de la identidad basada en notificaciones en .NET, lo que facilita el uso de notificaciones.</span><span class="sxs-lookup"><span data-stu-id="e2fa0-117">Having the WIF classes directly available in the framework allows a much deeper integration of claims-based identity in .NET, making it easier to use claims.</span></span> <span data-ttu-id="e2fa0-118">Con WIF 4.5, no es necesario instalar ningún componente fuera de banda para comenzar a desarrollar aplicaciones web compatibles con notificaciones.</span><span class="sxs-lookup"><span data-stu-id="e2fa0-118">With WIF 4.5, you do not need to install any out-of-band components in order to start developing claims-aware web applications.</span></span> <span data-ttu-id="e2fa0-119">Las clases de WIF se extienden ahora por diversos ensamblados; los principales son System.Security.Claims, System.IdentityModel y System.IdentityModel.Services.</span><span class="sxs-lookup"><span data-stu-id="e2fa0-119">WIF classes are now spread across various assemblies, the main ones being System.Security.Claims, System.IdentityModel and System.IdentityModel.Services.</span></span>  
  
 <span data-ttu-id="e2fa0-120">El STS es un servicio que emite tokens tras haberse realizado la autenticación correctamente.</span><span class="sxs-lookup"><span data-stu-id="e2fa0-120">STS is a service that issues tokens upon successful authentication.</span></span> <span data-ttu-id="e2fa0-121">Microsoft ofrece dos STS estándar del sector:</span><span class="sxs-lookup"><span data-stu-id="e2fa0-121">Microsoft offers two industry standard STS’s:</span></span>  
  
-   <span data-ttu-id="e2fa0-122">[Servicios de federación de Active Directory (AD FS) 2.0](http://go.microsoft.com/fwlink/?LinkID=247516) (http://go.microsoft.com/fwlink/?LinkID=247516)</span><span class="sxs-lookup"><span data-stu-id="e2fa0-122">[Active Directory Federation Services (AD FS) 2.0](http://go.microsoft.com/fwlink/?LinkID=247516) (http://go.microsoft.com/fwlink/?LinkID=247516)</span></span>  
  
-   <span data-ttu-id="e2fa0-123">[Windows Azure Access Control Service (ACS)](http://go.microsoft.com/fwlink/?LinkID=247517) (http://go.microsoft.com/fwlink/?LinkID=247517).</span><span class="sxs-lookup"><span data-stu-id="e2fa0-123">[Windows Azure Access Control Service (ACS)](http://go.microsoft.com/fwlink/?LinkID=247517) (http://go.microsoft.com/fwlink/?LinkID=247517).</span></span>  
  
 <span data-ttu-id="e2fa0-124">AD FS 2.0 forma parte de Windows Server R2 y se puede usar como STS para escenarios locales.</span><span class="sxs-lookup"><span data-stu-id="e2fa0-124">AD FS 2.0 is part of the Windows Server R2 and can be used as an STS for on-premise scenarios.</span></span> <span data-ttu-id="e2fa0-125">El control de acceso de Active Directory de Azure (también conocido como Servicio de control de acceso o ACS) es un servicio en la nube que se ofrece como parte de Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="e2fa0-125">Azure Active Directory Access Control (also known as Access Control Service or ACS) is a cloud service, offered as part of Microsoft Azure.</span></span> <span data-ttu-id="e2fa0-126">Con fines de pruebas o educativos, también pueden usarse otros STS para compilar las aplicaciones compatibles con notificaciones.</span><span class="sxs-lookup"><span data-stu-id="e2fa0-126">For testing or educational purposes, you can also use other STS’s in order to build your claims-aware applications.</span></span> <span data-ttu-id="e2fa0-127">Por ejemplo, puede usar el STS de desarrollo local que forma parte de la [Herramienta de identidad y acceso para Visual Studio](http://go.microsoft.com/fwlink/?LinkID=245849) (http://go.microsoft.com/fwlink/?LinkID=245849), disponible en línea de forma gratuita.</span><span class="sxs-lookup"><span data-stu-id="e2fa0-127">For example, you can use the Local Development STS that is part of the [Identity and Access Tool for Visual Studio](http://go.microsoft.com/fwlink/?LinkID=245849) (http://go.microsoft.com/fwlink/?LinkID=245849) which is freely available online.</span></span>  
  
 <span data-ttu-id="e2fa0-128">Para compilar el primer servicio WCF para notificaciones mediante WIF, vea [How To: Build Claims-Aware WCF Service Using WIF (Cómo: Compilar un servicio WCF para notificaciones mediante WIF)](http://msdn.microsoft.com/en-us/431e6415-62ed-4a9f-af03-f14d2b4dfe6d).</span><span class="sxs-lookup"><span data-stu-id="e2fa0-128">To build your first claims-aware WCF service using WIF, see [How To: Build Claims-Aware WCF Service Using WIF](http://msdn.microsoft.com/en-us/431e6415-62ed-4a9f-af03-f14d2b4dfe6d).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2fa0-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="e2fa0-129">See Also</span></span>  
 [<span data-ttu-id="e2fa0-130">Introducción a WIF</span><span class="sxs-lookup"><span data-stu-id="e2fa0-130">Getting Started With WIF</span></span>](../../../docs/framework/security/getting-started-with-wif.md)
