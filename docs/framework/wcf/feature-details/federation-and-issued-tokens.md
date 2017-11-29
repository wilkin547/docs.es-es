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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: aa3ed1b68cab19b0464067a2dc8f52be03279f5c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="federation-and-issued-tokens"></a><span data-ttu-id="4b004-102">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="4b004-102">Federation and Issued Tokens</span></span>
<span data-ttu-id="4b004-103">Con [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], puede crear clientes que se comuniquen de manera segura con servicios que implementan las especificaciones WS-Federation y WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="4b004-103">With [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], you can create clients that communicate securely with services that implement the WS-Federation and WS-Trust specifications.</span></span> <span data-ttu-id="4b004-104">Las especificaciones utilizan XML, SOAP y lenguaje de descripción de servicios Web (WSDL) para proporcionar mecanismos que habilitan la autenticación y autorización en los diferentes dominios de confianza.</span><span class="sxs-lookup"><span data-stu-id="4b004-104">The specifications use XML, SOAP, and Web Services Description Language (WSDL) to provide mechanisms that enable authentication and authorization across different trust realms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4b004-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="4b004-105">In This Section</span></span>  
 [<span data-ttu-id="4b004-106">Federación</span><span class="sxs-lookup"><span data-stu-id="4b004-106">Federation</span></span>](../../../../docs/framework/wcf/feature-details/federation.md)  
 <span data-ttu-id="4b004-107">Proporciona información general sobre la federación.</span><span class="sxs-lookup"><span data-stu-id="4b004-107">Provides an overview of federation.</span></span>  
  
 [<span data-ttu-id="4b004-108">Federación y confianza</span><span class="sxs-lookup"><span data-stu-id="4b004-108">Federation and Trust</span></span>](../../../../docs/framework/wcf/feature-details/federation-and-trust.md)  
 <span data-ttu-id="4b004-109">Enumera los problemas de diseño a tener en cuenta al crear servicios o clientes federados.</span><span class="sxs-lookup"><span data-stu-id="4b004-109">Lists the design issues to be aware of when creating federated services or clients.</span></span>  
  
 [<span data-ttu-id="4b004-110">Cómo: crear un cliente federado</span><span class="sxs-lookup"><span data-stu-id="4b004-110">How to: Create a Federated Client</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 <span data-ttu-id="4b004-111">Describe los fundamentos de la creación de un cliente federado con [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4b004-111">Describes the basics of creating a federated client with [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 [<span data-ttu-id="4b004-112">Cómo: configurar las credenciales en un servicio de federación</span><span class="sxs-lookup"><span data-stu-id="4b004-112">How to: Configure Credentials on a Federation Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)  
 <span data-ttu-id="4b004-113">Describe los pasos de creación de un servicio federado.</span><span class="sxs-lookup"><span data-stu-id="4b004-113">Describes the steps of creating a federated service.</span></span>  
  
 [<span data-ttu-id="4b004-114">Cómo: crear un WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="4b004-114">How to: Create a WSFederationHttpBinding</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)  
 <span data-ttu-id="4b004-115">Describe cómo configurar los clientes y servicios que utilizan el `WSFederationHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="4b004-115">Describes how to configure clients and services that use the `WSFederationHttpBinding`.</span></span>  
  
 [<span data-ttu-id="4b004-116">Cómo: crear un servicio de Token de seguridad</span><span class="sxs-lookup"><span data-stu-id="4b004-116">How to: Create a Security Token Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-token-service.md)  
 <span data-ttu-id="4b004-117">Describe los pasos de creación de un servicio de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="4b004-117">Describes the steps of creating a security token service.</span></span>  
  
 [<span data-ttu-id="4b004-118">Notificaciones y Tokens de seguridad aserciones Markup Language (SAML)</span><span class="sxs-lookup"><span data-stu-id="4b004-118">Security Assertions Markup Language (SAML) Tokens and Claims</span></span>](../../../../docs/framework/wcf/feature-details/saml-tokens-and-claims.md)  
 <span data-ttu-id="4b004-119">Describe tokens del lenguaje de marcado de aserción de seguridad (SAML), que son extensibles y le permiten crear tipos de demanda eficaces.</span><span class="sxs-lookup"><span data-stu-id="4b004-119">Describes Security Assertions Markup Language (SAML) tokens, which are extensible and enable you to create rich claim types.</span></span>  
  
 [<span data-ttu-id="4b004-120">Cómo: configurar un emisor Local</span><span class="sxs-lookup"><span data-stu-id="4b004-120">How to: Configure a Local Issuer</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)  
 <span data-ttu-id="4b004-121">Describe cómo crear un emisor local de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="4b004-121">Describes how to create a local issuer of security tokens.</span></span>  
  
 [<span data-ttu-id="4b004-122">Cómo: deshabilitar sesiones seguras en un WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="4b004-122">How to: Disable Secure Sessions on a WSFederationHttpBinding</span></span>](../../../../docs/framework/wcf/feature-details/how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)  
 <span data-ttu-id="4b004-123">Describe cómo deshabilitar las sesiones seguras en un `WSFederationHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="4b004-123">Describes how to disable secure sessions on a `WSFederationHttpBinding`.</span></span> <span data-ttu-id="4b004-124">La deshabilitación de las sesiones seguras es necesaria al crear una granja de servidores web que requiere una sesión para cada cliente.</span><span class="sxs-lookup"><span data-stu-id="4b004-124">Disabling secure sessions is necessary when creating a Web farm that requires a session for each client.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="4b004-125">Referencia</span><span class="sxs-lookup"><span data-stu-id="4b004-125">Reference</span></span>  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
  
 <xref:System.IdentityModel.Tokens.SamlSecurityToken>  
  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential>  
  
 <xref:System.ServiceModel.Security.IssuedTokenServiceCredential>  
  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>  
  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenProvider>  
  
 <xref:System.ServiceModel.WSFederationHttpBinding>  
  
## <a name="see-also"></a><span data-ttu-id="4b004-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="4b004-126">See Also</span></span>  
 [<span data-ttu-id="4b004-127">Autorización</span><span class="sxs-lookup"><span data-stu-id="4b004-127">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
 [<span data-ttu-id="4b004-128">Tokens personalizados</span><span class="sxs-lookup"><span data-stu-id="4b004-128">Custom Tokens</span></span>](../../../../docs/framework/wcf/extending/custom-tokens.md)  
 [<span data-ttu-id="4b004-129">Modelo de seguridad de Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="4b004-129">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
