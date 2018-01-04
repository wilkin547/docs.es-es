---
title: "Federación y tokens emitidos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF, federation
- issued tokens [WCF]
- federation [WCF], issued tokens
ms.assetid: 4c31ee7d-a820-4067-8b84-a83049021bb6
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 017d3e51022ad9980dc8f058415697c80a2a6b35
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="federation-and-issued-tokens"></a><span data-ttu-id="ef1c3-102">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="ef1c3-102">Federation and Issued Tokens</span></span>
<span data-ttu-id="ef1c3-103">Con [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], puede crear clientes que se comuniquen de manera segura con servicios que implementan las especificaciones WS-Federation y WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="ef1c3-103">With [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], you can create clients that communicate securely with services that implement the WS-Federation and WS-Trust specifications.</span></span> <span data-ttu-id="ef1c3-104">Las especificaciones utilizan XML, SOAP y lenguaje de descripción de servicios Web (WSDL) para proporcionar mecanismos que habilitan la autenticación y autorización en los diferentes dominios de confianza.</span><span class="sxs-lookup"><span data-stu-id="ef1c3-104">The specifications use XML, SOAP, and Web Services Description Language (WSDL) to provide mechanisms that enable authentication and authorization across different trust realms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ef1c3-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="ef1c3-105">In This Section</span></span>  
 [<span data-ttu-id="ef1c3-106">Federación</span><span class="sxs-lookup"><span data-stu-id="ef1c3-106">Federation</span></span>](../../../../docs/framework/wcf/feature-details/federation.md)  
 <span data-ttu-id="ef1c3-107">Proporciona información general sobre la federación.</span><span class="sxs-lookup"><span data-stu-id="ef1c3-107">Provides an overview of federation.</span></span>  
  
 [<span data-ttu-id="ef1c3-108">Federación y confianza</span><span class="sxs-lookup"><span data-stu-id="ef1c3-108">Federation and Trust</span></span>](../../../../docs/framework/wcf/feature-details/federation-and-trust.md)  
 <span data-ttu-id="ef1c3-109">Enumera los problemas de diseño a tener en cuenta al crear servicios o clientes federados.</span><span class="sxs-lookup"><span data-stu-id="ef1c3-109">Lists the design issues to be aware of when creating federated services or clients.</span></span>  
  
 [<span data-ttu-id="ef1c3-110">Creación de un cliente federado</span><span class="sxs-lookup"><span data-stu-id="ef1c3-110">How to: Create a Federated Client</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 <span data-ttu-id="ef1c3-111">Describe los fundamentos de la creación de un cliente federado con [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ef1c3-111">Describes the basics of creating a federated client with [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 [<span data-ttu-id="ef1c3-112">Configuración de las credenciales en un servicio de federación</span><span class="sxs-lookup"><span data-stu-id="ef1c3-112">How to: Configure Credentials on a Federation Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)  
 <span data-ttu-id="ef1c3-113">Describe los pasos de creación de un servicio federado.</span><span class="sxs-lookup"><span data-stu-id="ef1c3-113">Describes the steps of creating a federated service.</span></span>  
  
 [<span data-ttu-id="ef1c3-114">Creación de un WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="ef1c3-114">How to: Create a WSFederationHttpBinding</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)  
 <span data-ttu-id="ef1c3-115">Describe cómo configurar los clientes y servicios que utilizan el `WSFederationHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="ef1c3-115">Describes how to configure clients and services that use the `WSFederationHttpBinding`.</span></span>  
  
 [<span data-ttu-id="ef1c3-116">Creación de un servicio de token de seguridad</span><span class="sxs-lookup"><span data-stu-id="ef1c3-116">How to: Create a Security Token Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-token-service.md)  
 <span data-ttu-id="ef1c3-117">Describe los pasos de creación de un servicio de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="ef1c3-117">Describes the steps of creating a security token service.</span></span>  
  
 [<span data-ttu-id="ef1c3-118">Tokens y notificaciones del Lenguaje de marcado de aserción de seguridad (SAML)</span><span class="sxs-lookup"><span data-stu-id="ef1c3-118">Security Assertions Markup Language (SAML) Tokens and Claims</span></span>](../../../../docs/framework/wcf/feature-details/saml-tokens-and-claims.md)  
 <span data-ttu-id="ef1c3-119">Describe tokens del lenguaje de marcado de aserción de seguridad (SAML), que son extensibles y le permiten crear tipos de demanda eficaces.</span><span class="sxs-lookup"><span data-stu-id="ef1c3-119">Describes Security Assertions Markup Language (SAML) tokens, which are extensible and enable you to create rich claim types.</span></span>  
  
 [<span data-ttu-id="ef1c3-120">Configuración de un emisor local</span><span class="sxs-lookup"><span data-stu-id="ef1c3-120">How to: Configure a Local Issuer</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)  
 <span data-ttu-id="ef1c3-121">Describe cómo crear un emisor local de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="ef1c3-121">Describes how to create a local issuer of security tokens.</span></span>  
  
 [<span data-ttu-id="ef1c3-122">Deshabilitar sesiones seguras en WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="ef1c3-122">How to: Disable Secure Sessions on a WSFederationHttpBinding</span></span>](../../../../docs/framework/wcf/feature-details/how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)  
 <span data-ttu-id="ef1c3-123">Describe cómo deshabilitar las sesiones seguras en un `WSFederationHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="ef1c3-123">Describes how to disable secure sessions on a `WSFederationHttpBinding`.</span></span> <span data-ttu-id="ef1c3-124">La deshabilitación de las sesiones seguras es necesaria al crear una granja de servidores web que requiere una sesión para cada cliente.</span><span class="sxs-lookup"><span data-stu-id="ef1c3-124">Disabling secure sessions is necessary when creating a Web farm that requires a session for each client.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="ef1c3-125">Referencia</span><span class="sxs-lookup"><span data-stu-id="ef1c3-125">Reference</span></span>  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
  
 <xref:System.IdentityModel.Tokens.SamlSecurityToken>  
  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential>  
  
 <xref:System.ServiceModel.Security.IssuedTokenServiceCredential>  
  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>  
  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenProvider>  
  
 <xref:System.ServiceModel.WSFederationHttpBinding>  
  
## <a name="see-also"></a><span data-ttu-id="ef1c3-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="ef1c3-126">See Also</span></span>  
 [<span data-ttu-id="ef1c3-127">Autorización</span><span class="sxs-lookup"><span data-stu-id="ef1c3-127">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
 [<span data-ttu-id="ef1c3-128">Tokens personalizados</span><span class="sxs-lookup"><span data-stu-id="ef1c3-128">Custom Tokens</span></span>](../../../../docs/framework/wcf/extending/custom-tokens.md)  
 [<span data-ttu-id="ef1c3-129">Modelo de seguridad de Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="ef1c3-129">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
