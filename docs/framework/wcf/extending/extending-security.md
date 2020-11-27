---
title: Extensión de la seguridad
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF], extending
ms.assetid: a015a040-9fdf-4147-9ea9-f83b570be1d4
ms.openlocfilehash: d91f4812dbccb7807be2e0780cccd1d0c38b1f40
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273066"
---
# <a name="extending-security"></a><span data-ttu-id="7730e-102">Extensión de la seguridad</span><span class="sxs-lookup"><span data-stu-id="7730e-102">Extending Security</span></span>

<span data-ttu-id="7730e-103">Para dar cabida a nuevos tipos de notificaciones y tokens personalizados, puede extender la infraestructura de seguridad de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="7730e-103">To accommodate new claim types and custom tokens, you can extend the security infrastructure of Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="7730e-104">Los temas de esta sección le muestran cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="7730e-104">The topics in this section show you how this is done.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7730e-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="7730e-105">In This Section</span></span>  
  
 [<span data-ttu-id="7730e-106">Credencial personalizada y validación de la credencial</span><span class="sxs-lookup"><span data-stu-id="7730e-106">Custom Credential and Credential Validation</span></span>](custom-credential-and-credential-validation.md)  
 <span data-ttu-id="7730e-107">Explica cómo se utiliza el modelo de identidad al validar las credenciales personalizadas.</span><span class="sxs-lookup"><span data-stu-id="7730e-107">Explains how the Identity Model is used when validating custom credentials.</span></span>  
  
 [<span data-ttu-id="7730e-108">Tokens personalizados</span><span class="sxs-lookup"><span data-stu-id="7730e-108">Custom Tokens</span></span>](custom-tokens.md)  
 <span data-ttu-id="7730e-109">Los tokens emitidos por un servicio de token de seguridad (STS) normalmente son tokens de SAML.</span><span class="sxs-lookup"><span data-stu-id="7730e-109">Issued tokens from a Security Token Service (STS) are typically SAML tokens.</span></span> <span data-ttu-id="7730e-110">En este tema se explica cómo crear un tipo de token personalizado.</span><span class="sxs-lookup"><span data-stu-id="7730e-110">This topic explains how to create a custom token type.</span></span>  
  
 [<span data-ttu-id="7730e-111">Autorización personalizada</span><span class="sxs-lookup"><span data-stu-id="7730e-111">Custom Authorization</span></span>](custom-authorization.md)  
 <span data-ttu-id="7730e-112">Explica cómo implementar la autorización personalizada.</span><span class="sxs-lookup"><span data-stu-id="7730e-112">Explains how to implement custom authorization.</span></span>  
  
 [<span data-ttu-id="7730e-113">Invalidación de la identidad de un servicio para la autenticación</span><span class="sxs-lookup"><span data-stu-id="7730e-113">Overriding the Identity of a Service for Authentication</span></span>](overriding-the-identity-of-a-service-for-authentication.md)  
 <span data-ttu-id="7730e-114">Describe cómo invalidar la identidad de un servicio para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="7730e-114">Describes how to override the identity of a service for authentication.</span></span>  
  
 [<span data-ttu-id="7730e-115">Procedimiento para crear un comprobador de identidad de cliente personalizado</span><span class="sxs-lookup"><span data-stu-id="7730e-115">How to: Create a Custom Client Identity Verifier</span></span>](how-to-create-a-custom-client-identity-verifier.md)  
 <span data-ttu-id="7730e-116">Muestra cómo validar una identidad del extremo personalizada.</span><span class="sxs-lookup"><span data-stu-id="7730e-116">Demonstrates how to validate a custom endpoint identity.</span></span>  
  
 [<span data-ttu-id="7730e-117">Procedimiento para usar diferentes certificados X.509 para la firma y el cifrado</span><span class="sxs-lookup"><span data-stu-id="7730e-117">How to: Use Separate X.509 Certificates for Signing and Encryption</span></span>](how-to-use-separate-x-509-certificates-for-signing-and-encryption.md)  
 <span data-ttu-id="7730e-118">Los mensajes normalmente se firman y cifran con un certificado único.</span><span class="sxs-lookup"><span data-stu-id="7730e-118">Messages are typically signed and encrypted with a single certificate.</span></span> <span data-ttu-id="7730e-119">En este tema se explica cómo se pueden utilizar dos certificados, cuando se requiere.</span><span class="sxs-lookup"><span data-stu-id="7730e-119">This topic explains how two certificates can be used, when required.</span></span>  
  
 [<span data-ttu-id="7730e-120">Procedimiento para cambiar el proveedor criptográfico para la clave privada de un certificado X.509</span><span class="sxs-lookup"><span data-stu-id="7730e-120">How to: Change the Cryptographic Provider for an X.509 Certificate's Private Key</span></span>](change-cryptographic-provider-x509-certificate-private-key.md)  
 <span data-ttu-id="7730e-121">Explica cómo cambiar el proveedor de servicios criptográficos que se usa para proporcionar la clave privada de un certificado X. 509 y cómo integrar el proveedor en el marco de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="7730e-121">Explains how to change the cryptographic provider used to provide an X.509 certificate's private key and how to integrate the provider into the Windows Communication Foundation (WCF) framework.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="7730e-122">Referencia</span><span class="sxs-lookup"><span data-stu-id="7730e-122">Reference</span></span>  

 <xref:System.ServiceModel.ServiceAuthorizationManager>  
  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Selectors>  
  
## <a name="related-sections"></a><span data-ttu-id="7730e-123">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="7730e-123">Related Sections</span></span>  

 [<span data-ttu-id="7730e-124">Seguridad</span><span class="sxs-lookup"><span data-stu-id="7730e-124">Security</span></span>](../feature-details/security.md)  
  
 [<span data-ttu-id="7730e-125">Programación básica de WCF</span><span class="sxs-lookup"><span data-stu-id="7730e-125">Basic WCF Programming</span></span>](../basic-wcf-programming.md)  
  
## <a name="see-also"></a><span data-ttu-id="7730e-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="7730e-126">See also</span></span>

- [<span data-ttu-id="7730e-127">Información general sobre seguridad</span><span class="sxs-lookup"><span data-stu-id="7730e-127">Security Overview</span></span>](../feature-details/security-overview.md)
