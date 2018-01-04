---
title: "Credencial personalizada y validación de la credencial"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- credentials [WCF], custom
- credentials [WCF]
- custom credentials [WCF]
- credential validation [WCF]
- credentials [WCF], validation
ms.assetid: da831bec-e281-4d44-b343-437b5eef688e
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bdfd50253c71bfc9edd737964e771546cb797b9e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="custom-credential-and-credential-validation"></a><span data-ttu-id="3c6bf-102">Credencial personalizada y validación de la credencial</span><span class="sxs-lookup"><span data-stu-id="3c6bf-102">Custom Credential and Credential Validation</span></span>
<span data-ttu-id="3c6bf-103">La seguridad en [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] está basada en el intercambio de credenciales entre los servicios y clientes.</span><span class="sxs-lookup"><span data-stu-id="3c6bf-103">Security in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] is based on the exchange of credentials between services and clients.</span></span> <span data-ttu-id="3c6bf-104">La mayoría de los escenarios de seguridad se pueden cumplir utilizando tipos de credencial comunes, como Windows (Kerberos), el nombre de usuario y contraseñas y certificados.</span><span class="sxs-lookup"><span data-stu-id="3c6bf-104">Most security scenarios can be satisfied using common credential types, such as Windows (Kerberos), username and passwords, and certificates.</span></span> <span data-ttu-id="3c6bf-105">Sin embargo, si se exige un nuevo tipo de credencial, los temas en esta sección explican cómo administrar y validar los nuevos tipos.</span><span class="sxs-lookup"><span data-stu-id="3c6bf-105">However, if a new type of credential is required, the topics in this section explain how to handle and validate new types.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3c6bf-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="3c6bf-106">In This Section</span></span>  
 [<span data-ttu-id="3c6bf-107">Creación de un servicio que emplee un validador de certificado personalizado</span><span class="sxs-lookup"><span data-stu-id="3c6bf-107">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)  
 <span data-ttu-id="3c6bf-108">Explica cómo personalizar la validación [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] mediante la adquisición de la clase <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="3c6bf-108">Explains how to customize [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] validation by inheriting from the <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span>  
  
 [<span data-ttu-id="3c6bf-109">Tutorial: Creación de credenciales de cliente y servicio personalizadas</span><span class="sxs-lookup"><span data-stu-id="3c6bf-109">Walkthrough: Creating Custom Client and Service Credentials</span></span>](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md)  
 <span data-ttu-id="3c6bf-110">Muestra cómo extender el <xref:System.ServiceModel.Description.ClientCredentials> y <xref:System.ServiceModel.Description.ServiceCredentials> clases para alojar nuevos tipos de credencial.</span><span class="sxs-lookup"><span data-stu-id="3c6bf-110">Demonstrates how to extend the <xref:System.ServiceModel.Description.ClientCredentials> and <xref:System.ServiceModel.Description.ServiceCredentials> classes to accommodate new credential types.</span></span> <span data-ttu-id="3c6bf-111">Esto es lo primero en una serie de temas que habilitan la creación de tipos de credencial personalizados.</span><span class="sxs-lookup"><span data-stu-id="3c6bf-111">This is first in a series of topics that enable creation of custom credential types.</span></span>  
  
 [<span data-ttu-id="3c6bf-112">Creación de un proveedor de tokens de seguridad personalizado</span><span class="sxs-lookup"><span data-stu-id="3c6bf-112">How to: Create a Custom Security Token Provider</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-provider.md)  
 <span data-ttu-id="3c6bf-113">Explica cómo crear un proveedor de token de seguridad para administrar nuevos tipos de credencial y devolver nuevos tokens para la credencial.</span><span class="sxs-lookup"><span data-stu-id="3c6bf-113">Explains how to create a security token provider to handle new credential types and return new tokens for the credential.</span></span> <span data-ttu-id="3c6bf-114">Este es el segundo tema en la serie.</span><span class="sxs-lookup"><span data-stu-id="3c6bf-114">This is the second topic in the series.</span></span>  
  
 [<span data-ttu-id="3c6bf-115">Creación de un autenticador de tokens de seguridad personalizado</span><span class="sxs-lookup"><span data-stu-id="3c6bf-115">How to: Create a Custom Security Token Authenticator</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-authenticator.md)  
 <span data-ttu-id="3c6bf-116">Explica cómo crear un autenticador personalizado para autenticar un nuevo tipo de credencial.</span><span class="sxs-lookup"><span data-stu-id="3c6bf-116">Explains how to create a custom authenticator to authenticate a new credential type.</span></span> <span data-ttu-id="3c6bf-117">Este es el tercer tema en la serie.</span><span class="sxs-lookup"><span data-stu-id="3c6bf-117">This is the third topic in the series.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="3c6bf-118">Referencia</span><span class="sxs-lookup"><span data-stu-id="3c6bf-118">Reference</span></span>  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Selectors>  
  
 <xref:System.IdentityModel.Selectors.X509CertificateValidator>  
  
 <xref:System.ServiceModel.Description.ClientCredentials>  
  
 <xref:System.ServiceModel.Description.ServiceCredentials>  
  
## <a name="related-sections"></a><span data-ttu-id="3c6bf-119">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="3c6bf-119">Related Sections</span></span>  
 [<span data-ttu-id="3c6bf-120">Autenticación</span><span class="sxs-lookup"><span data-stu-id="3c6bf-120">Authentication</span></span>](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
  
 [<span data-ttu-id="3c6bf-121">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="3c6bf-121">Federation and Issued Tokens</span></span>](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
  
 [<span data-ttu-id="3c6bf-122">Autorización</span><span class="sxs-lookup"><span data-stu-id="3c6bf-122">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
## <a name="see-also"></a><span data-ttu-id="3c6bf-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="3c6bf-123">See Also</span></span>  
 [<span data-ttu-id="3c6bf-124">Seguridad</span><span class="sxs-lookup"><span data-stu-id="3c6bf-124">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)
