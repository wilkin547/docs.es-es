---
title: "Autenticación en WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- authentication [WCF]
- security [WCF], authentication
ms.assetid: 9254d873-843d-4c6e-bea4-8184ac3e44f4
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9a08627e213196c2d5fb296f458a5d3a8c7bb1a0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="authentication-in-wcf"></a><span data-ttu-id="b0411-102">Autenticación en WCF</span><span class="sxs-lookup"><span data-stu-id="b0411-102">Authentication in WCF</span></span>
<span data-ttu-id="b0411-103">Los temas siguientes muestran varios mecanismos diferentes en [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] que proporciona autenticación, por ejemplo, autenticación de Windows, certificados X.509 y nombre de usuario y contraseñas.</span><span class="sxs-lookup"><span data-stu-id="b0411-103">The following topics show a number of different mechanisms in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] that provide authentication, for example, Windows authentication, X.509 certificates, and user name and passwords.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b0411-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="b0411-104">In This Section</span></span>  
 [<span data-ttu-id="b0411-105">Cómo: usar el proveedor de pertenencia ASP.NET</span><span class="sxs-lookup"><span data-stu-id="b0411-105">How to: Use the ASP.NET Membership Provider</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)  
 <span data-ttu-id="b0411-106">Las características de ASP.NET incluyen una pertenencia y proveedor de funciones, una base de datos para almacenar pares de nombre de usuario/contraseña para la autenticación y funciones de usuario para la autorización.</span><span class="sxs-lookup"><span data-stu-id="b0411-106">ASP.NET features include a membership and role provider, a database to store user name/password pairs for authentication, and user roles for authorization.</span></span> <span data-ttu-id="b0411-107">En este tema se explica cómo los servicios [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] pueden utilizar la misma base de datos para autenticar y autorizar a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="b0411-107">This topic explains how [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services can use the same database to authenticate and authorize users.</span></span>  
  
 [<span data-ttu-id="b0411-108">Cómo: utilizar un nombre de usuario personalizado y validador de contraseña</span><span class="sxs-lookup"><span data-stu-id="b0411-108">How to: Use a Custom User Name and Password Validator</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-a-custom-user-name-and-password-validator.md)  
 <span data-ttu-id="b0411-109">Muestra cómo integrar un validador de nombre de usuario/contraseña personalizado.</span><span class="sxs-lookup"><span data-stu-id="b0411-109">Demonstrates how to integrate a custom user name/password validator.</span></span>  
  
 [<span data-ttu-id="b0411-110">Autenticación e identidad de servicio</span><span class="sxs-lookup"><span data-stu-id="b0411-110">Service Identity and Authentication</span></span>](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 <span data-ttu-id="b0411-111">Como una medida de seguridad adicional, un cliente puede autenticar el servicio especificando el esperado *identidad* del servicio.</span><span class="sxs-lookup"><span data-stu-id="b0411-111">As an extra safeguard, a client can authenticate the service by specifying the expected *identity* of the service.</span></span> <span data-ttu-id="b0411-112">Si la identidad esperada y la identidad devuelta por el servicio no coinciden, se produce un error de autenticación.</span><span class="sxs-lookup"><span data-stu-id="b0411-112">If the expected identity and the identity returned by the service do not match, authentication fails.</span></span>  
  
 [<span data-ttu-id="b0411-113">Los tiempos de espera y la negociación de seguridad</span><span class="sxs-lookup"><span data-stu-id="b0411-113">Security Negotiation and Timeouts</span></span>](../../../../docs/framework/wcf/feature-details/security-negotiation-and-timeouts.md)  
 <span data-ttu-id="b0411-114">Describe cómo se utiliza la propiedad <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> en la clase <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>.</span><span class="sxs-lookup"><span data-stu-id="b0411-114">Describes how to use the <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> property in the <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings> class.</span></span>  
  
 [<span data-ttu-id="b0411-115">Depuración de errores de autenticación de Windows</span><span class="sxs-lookup"><span data-stu-id="b0411-115">Debugging Windows Authentication Errors</span></span>](../../../../docs/framework/wcf/feature-details/debugging-windows-authentication-errors.md)  
 <span data-ttu-id="b0411-116">Se centra en los problemas comunes que se producen cuando se usa la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="b0411-116">Focuses on common problems encountered when using Windows authentication.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="b0411-117">Referencia</span><span class="sxs-lookup"><span data-stu-id="b0411-117">Reference</span></span>  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a><span data-ttu-id="b0411-118">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="b0411-118">Related Sections</span></span>  
 [<span data-ttu-id="b0411-119">Escenarios comunes de seguridad</span><span class="sxs-lookup"><span data-stu-id="b0411-119">Common Security Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
  
## <a name="see-also"></a><span data-ttu-id="b0411-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="b0411-120">See Also</span></span>  
 [<span data-ttu-id="b0411-121">Información general sobre seguridad</span><span class="sxs-lookup"><span data-stu-id="b0411-121">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="b0411-122">Modelo de seguridad de Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="b0411-122">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
