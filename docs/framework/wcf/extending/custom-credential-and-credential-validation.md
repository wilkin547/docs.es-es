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
ms.openlocfilehash: 1418d4155bc7f2fefc9f3e6caf4d3a264747a667
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795806"
---
# <a name="custom-credential-and-credential-validation"></a><span data-ttu-id="d276d-102">Credencial personalizada y validación de la credencial</span><span class="sxs-lookup"><span data-stu-id="d276d-102">Custom Credential and Credential Validation</span></span>
<span data-ttu-id="d276d-103">La seguridad en Windows Communication Foundation (WCF) se basa en el intercambio de credenciales entre servicios y clientes.</span><span class="sxs-lookup"><span data-stu-id="d276d-103">Security in Windows Communication Foundation (WCF) is based on the exchange of credentials between services and clients.</span></span> <span data-ttu-id="d276d-104">La mayoría de los escenarios de seguridad se pueden cumplir utilizando tipos de credencial comunes, como Windows (Kerberos), el nombre de usuario y contraseñas y certificados.</span><span class="sxs-lookup"><span data-stu-id="d276d-104">Most security scenarios can be satisfied using common credential types, such as Windows (Kerberos), username and passwords, and certificates.</span></span> <span data-ttu-id="d276d-105">Sin embargo, si se exige un nuevo tipo de credencial, los temas en esta sección explican cómo administrar y validar los nuevos tipos.</span><span class="sxs-lookup"><span data-stu-id="d276d-105">However, if a new type of credential is required, the topics in this section explain how to handle and validate new types.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d276d-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d276d-106">In This Section</span></span>  
 [<span data-ttu-id="d276d-107">Cómo: Crear un servicio que emplee un validador de certificado personalizado</span><span class="sxs-lookup"><span data-stu-id="d276d-107">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](how-to-create-a-service-that-employs-a-custom-certificate-validator.md)  
 <span data-ttu-id="d276d-108">Explica cómo personalizar la validación de WCF heredando de la <xref:System.IdentityModel.Selectors.X509CertificateValidator> clase.</span><span class="sxs-lookup"><span data-stu-id="d276d-108">Explains how to customize WCF validation by inheriting from the <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span>  
  
 [<span data-ttu-id="d276d-109">Tutorial: Creación de credenciales de cliente y servicio personalizadas</span><span class="sxs-lookup"><span data-stu-id="d276d-109">Walkthrough: Creating Custom Client and Service Credentials</span></span>](walkthrough-creating-custom-client-and-service-credentials.md)  
 <span data-ttu-id="d276d-110">Muestra cómo extender las <xref:System.ServiceModel.Description.ClientCredentials> clases y <xref:System.ServiceModel.Description.ServiceCredentials> para alojar nuevos tipos de credenciales.</span><span class="sxs-lookup"><span data-stu-id="d276d-110">Demonstrates how to extend the <xref:System.ServiceModel.Description.ClientCredentials> and <xref:System.ServiceModel.Description.ServiceCredentials> classes to accommodate new credential types.</span></span> <span data-ttu-id="d276d-111">Esto es lo primero en una serie de temas que habilitan la creación de tipos de credencial personalizados.</span><span class="sxs-lookup"><span data-stu-id="d276d-111">This is first in a series of topics that enable creation of custom credential types.</span></span>  
  
 [<span data-ttu-id="d276d-112">Procedimientos: Crear un proveedor de tokens de seguridad personalizado</span><span class="sxs-lookup"><span data-stu-id="d276d-112">How to: Create a Custom Security Token Provider</span></span>](how-to-create-a-custom-security-token-provider.md)  
 <span data-ttu-id="d276d-113">Explica cómo crear un proveedor de token de seguridad para administrar nuevos tipos de credencial y devolver nuevos tokens para la credencial.</span><span class="sxs-lookup"><span data-stu-id="d276d-113">Explains how to create a security token provider to handle new credential types and return new tokens for the credential.</span></span> <span data-ttu-id="d276d-114">Este es el segundo tema en la serie.</span><span class="sxs-lookup"><span data-stu-id="d276d-114">This is the second topic in the series.</span></span>  
  
 [<span data-ttu-id="d276d-115">Procedimientos: Crear un autenticador de tokens de seguridad personalizado</span><span class="sxs-lookup"><span data-stu-id="d276d-115">How to: Create a Custom Security Token Authenticator</span></span>](how-to-create-a-custom-security-token-authenticator.md)  
 <span data-ttu-id="d276d-116">Explica cómo crear un autenticador personalizado para autenticar un nuevo tipo de credencial.</span><span class="sxs-lookup"><span data-stu-id="d276d-116">Explains how to create a custom authenticator to authenticate a new credential type.</span></span> <span data-ttu-id="d276d-117">Este es el tercer tema en la serie.</span><span class="sxs-lookup"><span data-stu-id="d276d-117">This is the third topic in the series.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="d276d-118">Referencia</span><span class="sxs-lookup"><span data-stu-id="d276d-118">Reference</span></span>  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Selectors>  
  
 <xref:System.IdentityModel.Selectors.X509CertificateValidator>  
  
 <xref:System.ServiceModel.Description.ClientCredentials>  
  
 <xref:System.ServiceModel.Description.ServiceCredentials>  
  
## <a name="related-sections"></a><span data-ttu-id="d276d-119">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="d276d-119">Related Sections</span></span>  
 [<span data-ttu-id="d276d-120">Autenticación</span><span class="sxs-lookup"><span data-stu-id="d276d-120">Authentication</span></span>](../feature-details/authentication-in-wcf.md)  
  
 [<span data-ttu-id="d276d-121">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="d276d-121">Federation and Issued Tokens</span></span>](../feature-details/federation-and-issued-tokens.md)  
  
 [<span data-ttu-id="d276d-122">Autorización</span><span class="sxs-lookup"><span data-stu-id="d276d-122">Authorization</span></span>](../feature-details/authorization-in-wcf.md)  
  
## <a name="see-also"></a><span data-ttu-id="d276d-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="d276d-123">See also</span></span>

- [<span data-ttu-id="d276d-124">Seguridad</span><span class="sxs-lookup"><span data-stu-id="d276d-124">Security</span></span>](../feature-details/security.md)
