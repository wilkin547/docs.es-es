---
title: Credencial personalizada y validación de la credencial
ms.date: 03/30/2017
helpviewer_keywords:
- credentials [WCF], custom
- credentials [WCF]
- custom credentials [WCF]
- credential validation [WCF]
- credentials [WCF], validation
ms.assetid: da831bec-e281-4d44-b343-437b5eef688e
ms.openlocfilehash: 3b1ff700010f471a4d9be117f363083b6cbed493
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59210638"
---
# <a name="custom-credential-and-credential-validation"></a><span data-ttu-id="1a854-102">Credencial personalizada y validación de la credencial</span><span class="sxs-lookup"><span data-stu-id="1a854-102">Custom Credential and Credential Validation</span></span>
<span data-ttu-id="1a854-103">Seguridad en Windows Communication Foundation (WCF) se basa en el intercambio de credenciales entre servicios y clientes.</span><span class="sxs-lookup"><span data-stu-id="1a854-103">Security in Windows Communication Foundation (WCF) is based on the exchange of credentials between services and clients.</span></span> <span data-ttu-id="1a854-104">La mayoría de los escenarios de seguridad se pueden cumplir utilizando tipos de credencial comunes, como Windows (Kerberos), el nombre de usuario y contraseñas y certificados.</span><span class="sxs-lookup"><span data-stu-id="1a854-104">Most security scenarios can be satisfied using common credential types, such as Windows (Kerberos), username and passwords, and certificates.</span></span> <span data-ttu-id="1a854-105">Sin embargo, si se exige un nuevo tipo de credencial, los temas en esta sección explican cómo administrar y validar los nuevos tipos.</span><span class="sxs-lookup"><span data-stu-id="1a854-105">However, if a new type of credential is required, the topics in this section explain how to handle and validate new types.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1a854-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="1a854-106">In This Section</span></span>  
 [<span data-ttu-id="1a854-107">Filtrar para crear un servicio que emplee un validador de certificado personalizado</span><span class="sxs-lookup"><span data-stu-id="1a854-107">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)  
 <span data-ttu-id="1a854-108">Explica cómo personalizar la validación de WCF que se herede de la <xref:System.IdentityModel.Selectors.X509CertificateValidator> clase.</span><span class="sxs-lookup"><span data-stu-id="1a854-108">Explains how to customize WCF validation by inheriting from the <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span>  
  
 [<span data-ttu-id="1a854-109">Tutorial: Crear credenciales de cliente y servicio personalizadas</span><span class="sxs-lookup"><span data-stu-id="1a854-109">Walkthrough: Creating Custom Client and Service Credentials</span></span>](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md)  
 <span data-ttu-id="1a854-110">Muestra cómo extender el <xref:System.ServiceModel.Description.ClientCredentials> y <xref:System.ServiceModel.Description.ServiceCredentials> clases para alojar nuevos tipos de credencial.</span><span class="sxs-lookup"><span data-stu-id="1a854-110">Demonstrates how to extend the <xref:System.ServiceModel.Description.ClientCredentials> and <xref:System.ServiceModel.Description.ServiceCredentials> classes to accommodate new credential types.</span></span> <span data-ttu-id="1a854-111">Esto es lo primero en una serie de temas que habilitan la creación de tipos de credencial personalizados.</span><span class="sxs-lookup"><span data-stu-id="1a854-111">This is first in a series of topics that enable creation of custom credential types.</span></span>  
  
 [<span data-ttu-id="1a854-112">Filtrar para crear un proveedor de tokens de seguridad personalizado</span><span class="sxs-lookup"><span data-stu-id="1a854-112">How to: Create a Custom Security Token Provider</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-provider.md)  
 <span data-ttu-id="1a854-113">Explica cómo crear un proveedor de token de seguridad para administrar nuevos tipos de credencial y devolver nuevos tokens para la credencial.</span><span class="sxs-lookup"><span data-stu-id="1a854-113">Explains how to create a security token provider to handle new credential types and return new tokens for the credential.</span></span> <span data-ttu-id="1a854-114">Este es el segundo tema en la serie.</span><span class="sxs-lookup"><span data-stu-id="1a854-114">This is the second topic in the series.</span></span>  
  
 [<span data-ttu-id="1a854-115">Filtrar para crear un autenticador de tokens de seguridad personalizado</span><span class="sxs-lookup"><span data-stu-id="1a854-115">How to: Create a Custom Security Token Authenticator</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-authenticator.md)  
 <span data-ttu-id="1a854-116">Explica cómo crear un autenticador personalizado para autenticar un nuevo tipo de credencial.</span><span class="sxs-lookup"><span data-stu-id="1a854-116">Explains how to create a custom authenticator to authenticate a new credential type.</span></span> <span data-ttu-id="1a854-117">Este es el tercer tema en la serie.</span><span class="sxs-lookup"><span data-stu-id="1a854-117">This is the third topic in the series.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="1a854-118">Referencia</span><span class="sxs-lookup"><span data-stu-id="1a854-118">Reference</span></span>  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Selectors>  
  
 <xref:System.IdentityModel.Selectors.X509CertificateValidator>  
  
 <xref:System.ServiceModel.Description.ClientCredentials>  
  
 <xref:System.ServiceModel.Description.ServiceCredentials>  
  
## <a name="related-sections"></a><span data-ttu-id="1a854-119">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="1a854-119">Related Sections</span></span>  
 [<span data-ttu-id="1a854-120">Autenticación</span><span class="sxs-lookup"><span data-stu-id="1a854-120">Authentication</span></span>](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
  
 [<span data-ttu-id="1a854-121">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="1a854-121">Federation and Issued Tokens</span></span>](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
  
 [<span data-ttu-id="1a854-122">Autorización</span><span class="sxs-lookup"><span data-stu-id="1a854-122">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
## <a name="see-also"></a><span data-ttu-id="1a854-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="1a854-123">See also</span></span>

- [<span data-ttu-id="1a854-124">Seguridad</span><span class="sxs-lookup"><span data-stu-id="1a854-124">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)
