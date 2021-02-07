---
description: 'Más información sobre: credenciales personalizadas y validación de credenciales'
title: Credencial personalizada y validación de la credencial
ms.date: 03/30/2017
helpviewer_keywords:
- credentials [WCF], custom
- credentials [WCF]
- custom credentials [WCF]
- credential validation [WCF]
- credentials [WCF], validation
ms.assetid: da831bec-e281-4d44-b343-437b5eef688e
ms.openlocfilehash: f1ceb8cf46cca01ac31faeb9485cbeb6c8663d31
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99735314"
---
# <a name="custom-credential-and-credential-validation"></a><span data-ttu-id="cc1d4-103">Credencial personalizada y validación de la credencial</span><span class="sxs-lookup"><span data-stu-id="cc1d4-103">Custom Credential and Credential Validation</span></span>

<span data-ttu-id="cc1d4-104">La seguridad en Windows Communication Foundation (WCF) se basa en el intercambio de credenciales entre servicios y clientes.</span><span class="sxs-lookup"><span data-stu-id="cc1d4-104">Security in Windows Communication Foundation (WCF) is based on the exchange of credentials between services and clients.</span></span> <span data-ttu-id="cc1d4-105">La mayoría de los escenarios de seguridad se pueden cumplir utilizando tipos de credencial comunes, como Windows (Kerberos), el nombre de usuario y contraseñas y certificados.</span><span class="sxs-lookup"><span data-stu-id="cc1d4-105">Most security scenarios can be satisfied using common credential types, such as Windows (Kerberos), username and passwords, and certificates.</span></span> <span data-ttu-id="cc1d4-106">Sin embargo, si se exige un nuevo tipo de credencial, los temas en esta sección explican cómo administrar y validar los nuevos tipos.</span><span class="sxs-lookup"><span data-stu-id="cc1d4-106">However, if a new type of credential is required, the topics in this section explain how to handle and validate new types.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cc1d4-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="cc1d4-107">In This Section</span></span>  

 [<span data-ttu-id="cc1d4-108">Procedimiento para crear un servicio que emplee un validador de certificado personalizado</span><span class="sxs-lookup"><span data-stu-id="cc1d4-108">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](how-to-create-a-service-that-employs-a-custom-certificate-validator.md)  
 <span data-ttu-id="cc1d4-109">Explica cómo personalizar la validación de WCF heredando de la <xref:System.IdentityModel.Selectors.X509CertificateValidator> clase.</span><span class="sxs-lookup"><span data-stu-id="cc1d4-109">Explains how to customize WCF validation by inheriting from the <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span>  
  
 [<span data-ttu-id="cc1d4-110">Tutorial: Crear credenciales de cliente y servicio personalizadas</span><span class="sxs-lookup"><span data-stu-id="cc1d4-110">Walkthrough: Creating Custom Client and Service Credentials</span></span>](walkthrough-creating-custom-client-and-service-credentials.md)  
 <span data-ttu-id="cc1d4-111">Muestra cómo extender las <xref:System.ServiceModel.Description.ClientCredentials> clases y <xref:System.ServiceModel.Description.ServiceCredentials> para alojar nuevos tipos de credenciales.</span><span class="sxs-lookup"><span data-stu-id="cc1d4-111">Demonstrates how to extend the <xref:System.ServiceModel.Description.ClientCredentials> and <xref:System.ServiceModel.Description.ServiceCredentials> classes to accommodate new credential types.</span></span> <span data-ttu-id="cc1d4-112">Esto es lo primero en una serie de temas que habilitan la creación de tipos de credencial personalizados.</span><span class="sxs-lookup"><span data-stu-id="cc1d4-112">This is first in a series of topics that enable creation of custom credential types.</span></span>  
  
 [<span data-ttu-id="cc1d4-113">Procedimiento para crear un proveedor de tokens de seguridad personalizado</span><span class="sxs-lookup"><span data-stu-id="cc1d4-113">How to: Create a Custom Security Token Provider</span></span>](how-to-create-a-custom-security-token-provider.md)  
 <span data-ttu-id="cc1d4-114">Explica cómo crear un proveedor de token de seguridad para administrar nuevos tipos de credencial y devolver nuevos tokens para la credencial.</span><span class="sxs-lookup"><span data-stu-id="cc1d4-114">Explains how to create a security token provider to handle new credential types and return new tokens for the credential.</span></span> <span data-ttu-id="cc1d4-115">Este es el segundo tema en la serie.</span><span class="sxs-lookup"><span data-stu-id="cc1d4-115">This is the second topic in the series.</span></span>  
  
 [<span data-ttu-id="cc1d4-116">Procedimiento para crear un autenticador de tokens de seguridad personalizado</span><span class="sxs-lookup"><span data-stu-id="cc1d4-116">How to: Create a Custom Security Token Authenticator</span></span>](how-to-create-a-custom-security-token-authenticator.md)  
 <span data-ttu-id="cc1d4-117">Explica cómo crear un autenticador personalizado para autenticar un nuevo tipo de credencial.</span><span class="sxs-lookup"><span data-stu-id="cc1d4-117">Explains how to create a custom authenticator to authenticate a new credential type.</span></span> <span data-ttu-id="cc1d4-118">Este es el tercer tema en la serie.</span><span class="sxs-lookup"><span data-stu-id="cc1d4-118">This is the third topic in the series.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="cc1d4-119">Referencia</span><span class="sxs-lookup"><span data-stu-id="cc1d4-119">Reference</span></span>  

 <xref:System.ServiceModel.Security>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Selectors>  
  
 <xref:System.IdentityModel.Selectors.X509CertificateValidator>  
  
 <xref:System.ServiceModel.Description.ClientCredentials>  
  
 <xref:System.ServiceModel.Description.ServiceCredentials>  
  
## <a name="related-sections"></a><span data-ttu-id="cc1d4-120">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="cc1d4-120">Related Sections</span></span>  

 [<span data-ttu-id="cc1d4-121">Autenticación</span><span class="sxs-lookup"><span data-stu-id="cc1d4-121">Authentication</span></span>](../feature-details/authentication-in-wcf.md)  
  
 [<span data-ttu-id="cc1d4-122">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="cc1d4-122">Federation and Issued Tokens</span></span>](../feature-details/federation-and-issued-tokens.md)  
  
 [<span data-ttu-id="cc1d4-123">Autorización</span><span class="sxs-lookup"><span data-stu-id="cc1d4-123">Authorization</span></span>](../feature-details/authorization-in-wcf.md)  
  
## <a name="see-also"></a><span data-ttu-id="cc1d4-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="cc1d4-124">See also</span></span>

- [<span data-ttu-id="cc1d4-125">Seguridad</span><span class="sxs-lookup"><span data-stu-id="cc1d4-125">Security</span></span>](../feature-details/security.md)
