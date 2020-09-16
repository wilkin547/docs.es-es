---
title: Federación y tokens emitidos
ms.date: 03/30/2017
helpviewer_keywords:
- WCF, federation
- issued tokens [WCF]
- federation [WCF], issued tokens
ms.assetid: 4c31ee7d-a820-4067-8b84-a83049021bb6
ms.openlocfilehash: dffba51c1bf1aaffbed8725aafc96fd747cb31c6
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90559257"
---
# <a name="federation-and-issued-tokens"></a><span data-ttu-id="ff571-102">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="ff571-102">Federation and Issued Tokens</span></span>
<span data-ttu-id="ff571-103">Con Windows Communication Foundation (WCF), puede crear clientes que se comuniquen de forma segura con servicios que implementan las especificaciones de WS-Federation y WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="ff571-103">With Windows Communication Foundation (WCF), you can create clients that communicate securely with services that implement the WS-Federation and WS-Trust specifications.</span></span> <span data-ttu-id="ff571-104">Las especificaciones utilizan XML, SOAP y lenguaje de descripción de servicios Web (WSDL) para proporcionar mecanismos que habilitan la autenticación y autorización en los diferentes dominios de confianza.</span><span class="sxs-lookup"><span data-stu-id="ff571-104">The specifications use XML, SOAP, and Web Services Description Language (WSDL) to provide mechanisms that enable authentication and authorization across different trust realms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ff571-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="ff571-105">In This Section</span></span>  
 [<span data-ttu-id="ff571-106">Federación</span><span class="sxs-lookup"><span data-stu-id="ff571-106">Federation</span></span>](federation.md)  
 <span data-ttu-id="ff571-107">Proporciona información general sobre la federación.</span><span class="sxs-lookup"><span data-stu-id="ff571-107">Provides an overview of federation.</span></span>  
  
 [<span data-ttu-id="ff571-108">Federación y confianza</span><span class="sxs-lookup"><span data-stu-id="ff571-108">Federation and Trust</span></span>](federation-and-trust.md)  
 <span data-ttu-id="ff571-109">Enumera los problemas de diseño a tener en cuenta al crear servicios o clientes federados.</span><span class="sxs-lookup"><span data-stu-id="ff571-109">Lists the design issues to be aware of when creating federated services or clients.</span></span>  
  
 [<span data-ttu-id="ff571-110">Procedimiento para crear un cliente federado</span><span class="sxs-lookup"><span data-stu-id="ff571-110">How to: Create a Federated Client</span></span>](how-to-create-a-federated-client.md)  
 <span data-ttu-id="ff571-111">Describe los conceptos básicos de la creación de un cliente federado con WCF.</span><span class="sxs-lookup"><span data-stu-id="ff571-111">Describes the basics of creating a federated client with WCF.</span></span>  
  
 [<span data-ttu-id="ff571-112">Procedimiento para configurar las credenciales en un servicio de federación</span><span class="sxs-lookup"><span data-stu-id="ff571-112">How to: Configure Credentials on a Federation Service</span></span>](how-to-configure-credentials-on-a-federation-service.md)  
 <span data-ttu-id="ff571-113">Describe los pasos de creación de un servicio federado.</span><span class="sxs-lookup"><span data-stu-id="ff571-113">Describes the steps of creating a federated service.</span></span>  
  
 [<span data-ttu-id="ff571-114">Procedimiento para crear un WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="ff571-114">How to: Create a WSFederationHttpBinding</span></span>](how-to-create-a-wsfederationhttpbinding.md)  
 <span data-ttu-id="ff571-115">Describe cómo configurar los clientes y servicios que utilizan el `WSFederationHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="ff571-115">Describes how to configure clients and services that use the `WSFederationHttpBinding`.</span></span>  
  
 [<span data-ttu-id="ff571-116">Procedimiento para crear un servicio de token de seguridad</span><span class="sxs-lookup"><span data-stu-id="ff571-116">How to: Create a Security Token Service</span></span>](how-to-create-a-security-token-service.md)  
 <span data-ttu-id="ff571-117">Describe los pasos de creación de un servicio de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="ff571-117">Describes the steps of creating a security token service.</span></span>  
  
 [<span data-ttu-id="ff571-118">Tokens y notificaciones del Lenguaje de marcado de aserción de seguridad (SAML)</span><span class="sxs-lookup"><span data-stu-id="ff571-118">Security Assertions Markup Language (SAML) Tokens and Claims</span></span>](saml-tokens-and-claims.md)  
 <span data-ttu-id="ff571-119">Describe tokens del lenguaje de marcado de aserción de seguridad (SAML), que son extensibles y le permiten crear tipos de demanda eficaces.</span><span class="sxs-lookup"><span data-stu-id="ff571-119">Describes Security Assertions Markup Language (SAML) tokens, which are extensible and enable you to create rich claim types.</span></span>  
  
 [<span data-ttu-id="ff571-120">Procedimiento para configurar un emisor local</span><span class="sxs-lookup"><span data-stu-id="ff571-120">How to: Configure a Local Issuer</span></span>](how-to-configure-a-local-issuer.md)  
 <span data-ttu-id="ff571-121">Describe cómo crear un emisor local de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="ff571-121">Describes how to create a local issuer of security tokens.</span></span>  
  
 [<span data-ttu-id="ff571-122">Procedimiento para deshabilitar sesiones seguras en WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="ff571-122">How to: Disable Secure Sessions on a WSFederationHttpBinding</span></span>](how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)  
 <span data-ttu-id="ff571-123">Describe cómo deshabilitar las sesiones seguras en un `WSFederationHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="ff571-123">Describes how to disable secure sessions on a `WSFederationHttpBinding`.</span></span> <span data-ttu-id="ff571-124">La deshabilitación de las sesiones seguras es necesaria al crear una granja de servidores web que requiere una sesión para cada cliente.</span><span class="sxs-lookup"><span data-stu-id="ff571-124">Disabling secure sessions is necessary when creating a Web farm that requires a session for each client.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="ff571-125">Referencia</span><span class="sxs-lookup"><span data-stu-id="ff571-125">Reference</span></span>  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
  
 <xref:System.IdentityModel.Tokens.SamlSecurityToken>  
  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential>  
  
 <xref:System.ServiceModel.Security.IssuedTokenServiceCredential>  
  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>  
  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenProvider>  
  
 <xref:System.ServiceModel.WSFederationHttpBinding>  
  
## <a name="see-also"></a><span data-ttu-id="ff571-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="ff571-126">See also</span></span>

- [<span data-ttu-id="ff571-127">Autorización</span><span class="sxs-lookup"><span data-stu-id="ff571-127">Authorization</span></span>](authorization-in-wcf.md)
- [<span data-ttu-id="ff571-128">Tokens personalizados</span><span class="sxs-lookup"><span data-stu-id="ff571-128">Custom Tokens</span></span>](../extending/custom-tokens.md)
- <span data-ttu-id="ff571-129">[Modelo de seguridad para Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="ff571-129">[Security Model for Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
