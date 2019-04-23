---
title: Extensión de la seguridad
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF], extending
ms.assetid: a015a040-9fdf-4147-9ea9-f83b570be1d4
ms.openlocfilehash: 95dacf3ef975be1ddd56db747936cca35db50625
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59099643"
---
# <a name="extending-security"></a><span data-ttu-id="9ce85-102">Extensión de la seguridad</span><span class="sxs-lookup"><span data-stu-id="9ce85-102">Extending Security</span></span>
<span data-ttu-id="9ce85-103">Para dar cabida a nuevos tipos de notificaciones y tokens personalizados, puede ampliar la infraestructura de seguridad de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="9ce85-103">To accommodate new claim types and custom tokens, you can extend the security infrastructure of Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="9ce85-104">Los temas de esta sección le muestran cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="9ce85-104">The topics in this section show you how this is done.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9ce85-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="9ce85-105">In This Section</span></span>  
  
 [<span data-ttu-id="9ce85-106">Credencial personalizada y validación de la credencial</span><span class="sxs-lookup"><span data-stu-id="9ce85-106">Custom Credential and Credential Validation</span></span>](../../../../docs/framework/wcf/extending/custom-credential-and-credential-validation.md)  
 <span data-ttu-id="9ce85-107">Explica cómo se utiliza el modelo de identidad al validar las credenciales personalizadas.</span><span class="sxs-lookup"><span data-stu-id="9ce85-107">Explains how the Identity Model is used when validating custom credentials.</span></span>  
  
 [<span data-ttu-id="9ce85-108">Tokens personalizados</span><span class="sxs-lookup"><span data-stu-id="9ce85-108">Custom Tokens</span></span>](../../../../docs/framework/wcf/extending/custom-tokens.md)  
 <span data-ttu-id="9ce85-109">Los tokens emitidos por un servicio de token de seguridad (STS) normalmente son tokens de SAML.</span><span class="sxs-lookup"><span data-stu-id="9ce85-109">Issued tokens from a Security Token Service (STS) are typically SAML tokens.</span></span> <span data-ttu-id="9ce85-110">En este tema se explica cómo crear un tipo de token personalizado.</span><span class="sxs-lookup"><span data-stu-id="9ce85-110">This topic explains how to create a custom token type.</span></span>  
  
 [<span data-ttu-id="9ce85-111">Autorización personalizada</span><span class="sxs-lookup"><span data-stu-id="9ce85-111">Custom Authorization</span></span>](../../../../docs/framework/wcf/extending/custom-authorization.md)  
 <span data-ttu-id="9ce85-112">Explica cómo implementar la autorización personalizada.</span><span class="sxs-lookup"><span data-stu-id="9ce85-112">Explains how to implement custom authorization.</span></span>  
  
 [<span data-ttu-id="9ce85-113">Invalidación de la identidad de un servicio para la autenticación</span><span class="sxs-lookup"><span data-stu-id="9ce85-113">Overriding the Identity of a Service for Authentication</span></span>](../../../../docs/framework/wcf/extending/overriding-the-identity-of-a-service-for-authentication.md)  
 <span data-ttu-id="9ce85-114">Describe cómo invalidar la identidad de un servicio para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="9ce85-114">Describes how to override the identity of a service for authentication.</span></span>  
  
 [<span data-ttu-id="9ce85-115">Cómo: Crear un comprobador de identidad de cliente personalizada</span><span class="sxs-lookup"><span data-stu-id="9ce85-115">How to: Create a Custom Client Identity Verifier</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-custom-client-identity-verifier.md)  
 <span data-ttu-id="9ce85-116">Muestra cómo validar una identidad del extremo personalizada.</span><span class="sxs-lookup"><span data-stu-id="9ce85-116">Demonstrates how to validate a custom endpoint identity.</span></span>  
  
 [<span data-ttu-id="9ce85-117">Cómo: Usar diferentes certificados X.509 para la firma y cifrado</span><span class="sxs-lookup"><span data-stu-id="9ce85-117">How to: Use Separate X.509 Certificates for Signing and Encryption</span></span>](../../../../docs/framework/wcf/extending/how-to-use-separate-x-509-certificates-for-signing-and-encryption.md)  
 <span data-ttu-id="9ce85-118">Los mensajes normalmente se firman y cifran con un certificado único.</span><span class="sxs-lookup"><span data-stu-id="9ce85-118">Messages are typically signed and encrypted with a single certificate.</span></span> <span data-ttu-id="9ce85-119">En este tema se explica cómo se pueden utilizar dos certificados, cuando se requiere.</span><span class="sxs-lookup"><span data-stu-id="9ce85-119">This topic explains how two certificates can be used, when required.</span></span>  
  
 [<span data-ttu-id="9ce85-120">Cómo: Cambiar el proveedor de servicios criptográficos de clave privada de un certificado X.509</span><span class="sxs-lookup"><span data-stu-id="9ce85-120">How to: Change the Cryptographic Provider for an X.509 Certificate's Private Key</span></span>](../../../../docs/framework/wcf/extending/change-cryptographic-provider-x509-certificate-private-key.md)  
 <span data-ttu-id="9ce85-121">Explica cómo cambiar el proveedor criptográfico utilizado para proporcionar la clave privada de un certificado X.509 y cómo integrar el proveedor en el marco de trabajo de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="9ce85-121">Explains how to change the cryptographic provider used to provide an X.509 certificate's private key and how to integrate the provider into the Windows Communication Foundation (WCF) framework.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="9ce85-122">Referencia</span><span class="sxs-lookup"><span data-stu-id="9ce85-122">Reference</span></span>  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Selectors>  
  
## <a name="related-sections"></a><span data-ttu-id="9ce85-123">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="9ce85-123">Related Sections</span></span>  
 [<span data-ttu-id="9ce85-124">Seguridad</span><span class="sxs-lookup"><span data-stu-id="9ce85-124">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)  
  
 [<span data-ttu-id="9ce85-125">Programación básica de WCF</span><span class="sxs-lookup"><span data-stu-id="9ce85-125">Basic WCF Programming</span></span>](../../../../docs/framework/wcf/basic-wcf-programming.md)  
  
## <a name="see-also"></a><span data-ttu-id="9ce85-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="9ce85-126">See also</span></span>

- [<span data-ttu-id="9ce85-127">Información general sobre seguridad</span><span class="sxs-lookup"><span data-stu-id="9ce85-127">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
