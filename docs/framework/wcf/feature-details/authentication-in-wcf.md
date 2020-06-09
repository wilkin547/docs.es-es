---
title: Autenticación en WCF
ms.date: 03/30/2017
helpviewer_keywords:
- authentication [WCF]
- security [WCF], authentication
ms.assetid: 9254d873-843d-4c6e-bea4-8184ac3e44f4
ms.openlocfilehash: b513c9713bd2c04e125915d1a0a87c86ce249666
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597649"
---
# <a name="authentication-in-wcf"></a><span data-ttu-id="d38a9-102">Autenticación en WCF</span><span class="sxs-lookup"><span data-stu-id="d38a9-102">Authentication in WCF</span></span>
<span data-ttu-id="d38a9-103">En los temas siguientes se muestran una serie de mecanismos diferentes en Windows Communication Foundation (WCF) que proporcionan autenticación, por ejemplo, la autenticación de Windows, los certificados X. 509 y el nombre de usuario y contraseñas.</span><span class="sxs-lookup"><span data-stu-id="d38a9-103">The following topics show a number of different mechanisms in Windows Communication Foundation (WCF) that provide authentication, for example, Windows authentication, X.509 certificates, and user name and passwords.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d38a9-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d38a9-104">In This Section</span></span>  
 [<span data-ttu-id="d38a9-105">Procedimiento para usar el proveedor de pertenencia de ASP.NET</span><span class="sxs-lookup"><span data-stu-id="d38a9-105">How to: Use the ASP.NET Membership Provider</span></span>](how-to-use-the-aspnet-membership-provider.md)  
 <span data-ttu-id="d38a9-106">Las características de ASP.NET incluyen una pertenencia y proveedor de funciones, una base de datos para almacenar pares de nombre de usuario/contraseña para la autenticación y funciones de usuario para la autorización.</span><span class="sxs-lookup"><span data-stu-id="d38a9-106">ASP.NET features include a membership and role provider, a database to store user name/password pairs for authentication, and user roles for authorization.</span></span> <span data-ttu-id="d38a9-107">En este tema se explica cómo los servicios WCF pueden usar la misma base de datos para autenticar y autorizar a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="d38a9-107">This topic explains how WCF services can use the same database to authenticate and authorize users.</span></span>  
  
 [<span data-ttu-id="d38a9-108">Procedimiento para usar un nombre de usuario personalizado y un validador de contraseñas</span><span class="sxs-lookup"><span data-stu-id="d38a9-108">How to: Use a Custom User Name and Password Validator</span></span>](how-to-use-a-custom-user-name-and-password-validator.md)  
 <span data-ttu-id="d38a9-109">Muestra cómo integrar un validador de nombre de usuario/contraseña personalizado.</span><span class="sxs-lookup"><span data-stu-id="d38a9-109">Demonstrates how to integrate a custom user name/password validator.</span></span>  
  
 [<span data-ttu-id="d38a9-110">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="d38a9-110">Service Identity and Authentication</span></span>](service-identity-and-authentication.md)  
 <span data-ttu-id="d38a9-111">Como medida de seguridad adicional, un cliente puede autenticar el servicio especificando la *identidad* esperada del servicio.</span><span class="sxs-lookup"><span data-stu-id="d38a9-111">As an extra safeguard, a client can authenticate the service by specifying the expected *identity* of the service.</span></span> <span data-ttu-id="d38a9-112">Si la identidad esperada y la identidad devuelta por el servicio no coinciden, se produce un error de autenticación.</span><span class="sxs-lookup"><span data-stu-id="d38a9-112">If the expected identity and the identity returned by the service do not match, authentication fails.</span></span>  
  
 [<span data-ttu-id="d38a9-113">Negociación de seguridad y tiempos de espera</span><span class="sxs-lookup"><span data-stu-id="d38a9-113">Security Negotiation and Timeouts</span></span>](security-negotiation-and-timeouts.md)  
 <span data-ttu-id="d38a9-114">Describe cómo se utiliza la propiedad <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> en la clase <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>.</span><span class="sxs-lookup"><span data-stu-id="d38a9-114">Describes how to use the <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> property in the <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings> class.</span></span>  
  
 [<span data-ttu-id="d38a9-115">Depuración de errores de autenticación de Windows</span><span class="sxs-lookup"><span data-stu-id="d38a9-115">Debugging Windows Authentication Errors</span></span>](debugging-windows-authentication-errors.md)  
 <span data-ttu-id="d38a9-116">Se centra en los problemas comunes que se producen cuando se usa la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="d38a9-116">Focuses on common problems encountered when using Windows authentication.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="d38a9-117">Referencia</span><span class="sxs-lookup"><span data-stu-id="d38a9-117">Reference</span></span>  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a><span data-ttu-id="d38a9-118">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="d38a9-118">Related Sections</span></span>  
 [<span data-ttu-id="d38a9-119">Escenarios de seguridad comunes</span><span class="sxs-lookup"><span data-stu-id="d38a9-119">Common Security Scenarios</span></span>](common-security-scenarios.md)  
  
## <a name="see-also"></a><span data-ttu-id="d38a9-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="d38a9-120">See also</span></span>

- [<span data-ttu-id="d38a9-121">Información general sobre seguridad</span><span class="sxs-lookup"><span data-stu-id="d38a9-121">Security Overview</span></span>](security-overview.md)
- <span data-ttu-id="d38a9-122">[Modelo de seguridad para Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="d38a9-122">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
