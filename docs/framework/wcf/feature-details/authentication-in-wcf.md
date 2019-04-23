---
title: Autenticación en WCF
ms.date: 03/30/2017
helpviewer_keywords:
- authentication [WCF]
- security [WCF], authentication
ms.assetid: 9254d873-843d-4c6e-bea4-8184ac3e44f4
ms.openlocfilehash: ebff66e185bdca75a0150b22a16392bfd08892d3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59165500"
---
# <a name="authentication-in-wcf"></a><span data-ttu-id="44537-102">Autenticación en WCF</span><span class="sxs-lookup"><span data-stu-id="44537-102">Authentication in WCF</span></span>
<span data-ttu-id="44537-103">Los temas siguientes muestran varios mecanismos diferentes en Windows Communication Foundation (WCF) que proporciona autenticación, por ejemplo, autenticación de Windows, los certificados X.509 y nombre de usuario y contraseñas.</span><span class="sxs-lookup"><span data-stu-id="44537-103">The following topics show a number of different mechanisms in Windows Communication Foundation (WCF) that provide authentication, for example, Windows authentication, X.509 certificates, and user name and passwords.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="44537-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="44537-104">In This Section</span></span>  
 [<span data-ttu-id="44537-105">Cómo: Usar el proveedor de pertenencia ASP.NET</span><span class="sxs-lookup"><span data-stu-id="44537-105">How to: Use the ASP.NET Membership Provider</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)  
 <span data-ttu-id="44537-106">Las características de ASP.NET incluyen una pertenencia y proveedor de funciones, una base de datos para almacenar pares de nombre de usuario/contraseña para la autenticación y funciones de usuario para la autorización.</span><span class="sxs-lookup"><span data-stu-id="44537-106">ASP.NET features include a membership and role provider, a database to store user name/password pairs for authentication, and user roles for authorization.</span></span> <span data-ttu-id="44537-107">En este tema se explica cómo los servicios de WCF pueden usar la misma base de datos para autenticar y autorizar a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="44537-107">This topic explains how WCF services can use the same database to authenticate and authorize users.</span></span>  
  
 [<span data-ttu-id="44537-108">Cómo: Usar un nombre de usuario personalizado y validador de contraseña</span><span class="sxs-lookup"><span data-stu-id="44537-108">How to: Use a Custom User Name and Password Validator</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-a-custom-user-name-and-password-validator.md)  
 <span data-ttu-id="44537-109">Muestra cómo integrar un validador de nombre de usuario/contraseña personalizado.</span><span class="sxs-lookup"><span data-stu-id="44537-109">Demonstrates how to integrate a custom user name/password validator.</span></span>  
  
 [<span data-ttu-id="44537-110">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="44537-110">Service Identity and Authentication</span></span>](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 <span data-ttu-id="44537-111">Como una medida de seguridad adicional, un cliente puede autenticar el servicio mediante la especificación de la esperada *identidad* del servicio.</span><span class="sxs-lookup"><span data-stu-id="44537-111">As an extra safeguard, a client can authenticate the service by specifying the expected *identity* of the service.</span></span> <span data-ttu-id="44537-112">Si la identidad esperada y la identidad devuelta por el servicio no coinciden, se produce un error de autenticación.</span><span class="sxs-lookup"><span data-stu-id="44537-112">If the expected identity and the identity returned by the service do not match, authentication fails.</span></span>  
  
 [<span data-ttu-id="44537-113">Negociación de seguridad y tiempos de espera</span><span class="sxs-lookup"><span data-stu-id="44537-113">Security Negotiation and Timeouts</span></span>](../../../../docs/framework/wcf/feature-details/security-negotiation-and-timeouts.md)  
 <span data-ttu-id="44537-114">Describe cómo se utiliza la propiedad <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> en la clase <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>.</span><span class="sxs-lookup"><span data-stu-id="44537-114">Describes how to use the <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> property in the <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings> class.</span></span>  
  
 [<span data-ttu-id="44537-115">Depuración de errores de autenticación de Windows</span><span class="sxs-lookup"><span data-stu-id="44537-115">Debugging Windows Authentication Errors</span></span>](../../../../docs/framework/wcf/feature-details/debugging-windows-authentication-errors.md)  
 <span data-ttu-id="44537-116">Se centra en los problemas comunes que se producen cuando se usa la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="44537-116">Focuses on common problems encountered when using Windows authentication.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="44537-117">Referencia</span><span class="sxs-lookup"><span data-stu-id="44537-117">Reference</span></span>  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a><span data-ttu-id="44537-118">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="44537-118">Related Sections</span></span>  
 [<span data-ttu-id="44537-119">Escenarios de seguridad comunes</span><span class="sxs-lookup"><span data-stu-id="44537-119">Common Security Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
  
## <a name="see-also"></a><span data-ttu-id="44537-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="44537-120">See also</span></span>

- [<span data-ttu-id="44537-121">Información general sobre seguridad</span><span class="sxs-lookup"><span data-stu-id="44537-121">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [<span data-ttu-id="44537-122">Modelo de seguridad de Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="44537-122">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
