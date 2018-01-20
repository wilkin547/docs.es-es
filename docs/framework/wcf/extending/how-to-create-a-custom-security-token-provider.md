---
title: "Cómo crear un proveedor de tokens de seguridad personalizado"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: security [WCF], providing credentials
ms.assetid: db8cb478-aa43-478b-bf97-c6489ad7c7fd
caps.latest.revision: "10"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 37e7f9541457c475bfe187485520df63a84f7555
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-create-a-custom-security-token-provider"></a><span data-ttu-id="b6734-102">Cómo crear un proveedor de tokens de seguridad personalizado</span><span class="sxs-lookup"><span data-stu-id="b6734-102">How to: Create a Custom Security Token Provider</span></span>
<span data-ttu-id="b6734-103">En este tema se muestra cómo crear nuevos tipos de token con un proveedor de tokens de seguridad personalizado y cómo integrar el proveedor con un administrador de tokens de seguridad personalizado.</span><span class="sxs-lookup"><span data-stu-id="b6734-103">This topic shows how to create new token types with a custom security token provider and how to integrate the provider with a custom security token manager.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b6734-104">Cree un proveedor de tokens personalizado si los tokens proporcionados por el sistema ubicados en el espacio de nombres <xref:System.IdentityModel.Tokens> no coinciden con sus requisitos.</span><span class="sxs-lookup"><span data-stu-id="b6734-104">Create a custom token provider if the system-provided tokens found in the <xref:System.IdentityModel.Tokens> namespace do not match your requirements.</span></span>  
  
 <span data-ttu-id="b6734-105">El proveedor de tokens de seguridad crea una representación de token de seguridad basada en información en el cliente o en las credenciales de servicio.</span><span class="sxs-lookup"><span data-stu-id="b6734-105">The security token provider creates a security token representation based on information in the client or service credentials.</span></span> <span data-ttu-id="b6734-106">Para usar el proveedor de tokens de seguridad personalizado en la seguridad [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], debe crear credenciales personalizadas e implementaciones de administrador de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="b6734-106">To use the custom security token provider in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] security, you must create custom credentials and security token manager implementations.</span></span>  
  
 <span data-ttu-id="b6734-107">Para obtener más información acerca de las credenciales personalizadas y Administrador de tokens de seguridad, consulte el [Tutorial: creación de cliente personalizada y las credenciales de servicio](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md).</span><span class="sxs-lookup"><span data-stu-id="b6734-107">For more information about custom credentials and security token manager see the [Walkthrough: Creating Custom Client and Service Credentials](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md).</span></span>  
  
 <span data-ttu-id="b6734-108">Para obtener más información acerca de las credenciales, vea clases token de administrador, el proveedor y el autenticador de seguridad, el [arquitectura de seguridad](http://msdn.microsoft.com/library/16593476-d36a-408d-808c-ae6fd483e28f).</span><span class="sxs-lookup"><span data-stu-id="b6734-108">For more information about credentials, security token manager, provider and authenticator classes, see the [Security Architecture](http://msdn.microsoft.com/library/16593476-d36a-408d-808c-ae6fd483e28f).</span></span>  
  
### <a name="to-create-a-custom-security-token-provider"></a><span data-ttu-id="b6734-109">Para crear un proveedor de tokens de seguridad personalizado</span><span class="sxs-lookup"><span data-stu-id="b6734-109">To create a custom security token provider</span></span>  
  
1.  <span data-ttu-id="b6734-110">Defina una clase nueva derivada de la clase <xref:System.IdentityModel.Selectors.SecurityTokenProvider>.</span><span class="sxs-lookup"><span data-stu-id="b6734-110">Define a new class derived from the <xref:System.IdentityModel.Selectors.SecurityTokenProvider> class.</span></span>  
  
2.  <span data-ttu-id="b6734-111">Implemente el método <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%28System.TimeSpan%29>.</span><span class="sxs-lookup"><span data-stu-id="b6734-111">Implement the <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%28System.TimeSpan%29> method.</span></span> <span data-ttu-id="b6734-112">El método es responsable de crear y devolver una instancia del token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="b6734-112">The method is responsible for creating and returning an instance of the security token.</span></span> <span data-ttu-id="b6734-113">El ejemplo siguiente crea una clase denominada `MySecurityTokenProvider`e invalida el método <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%28System.TimeSpan%29> para devolver una instancia de la clase <xref:System.IdentityModel.Tokens.X509SecurityToken>.</span><span class="sxs-lookup"><span data-stu-id="b6734-113">The following example creates a class named `MySecurityTokenProvider`, and overrides the <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%28System.TimeSpan%29> method to return an instance of the <xref:System.IdentityModel.Tokens.X509SecurityToken> class.</span></span> <span data-ttu-id="b6734-114">El constructor de clase necesita una instancia de la clase <xref:System.Security.Cryptography.X509Certificates.X509Certificate2>.</span><span class="sxs-lookup"><span data-stu-id="b6734-114">The class constructor requires an instance of the <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> class.</span></span>  
  
     [!code-csharp[c_CustomTokenProvider#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenprovider/cs/source.cs#1)]
     [!code-vb[c_CustomTokenProvider#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenprovider/vb/source.vb#1)]  
  
### <a name="to-integrate-a-custom-security-token-provider-with-a-custom-security-token-manager"></a><span data-ttu-id="b6734-115">Para integrar un proveedor de tokens de seguridad personalizado con un administrador de tokens de seguridad personalizado</span><span class="sxs-lookup"><span data-stu-id="b6734-115">To integrate a custom security token provider with a custom security token manager</span></span>  
  
1.  <span data-ttu-id="b6734-116">Defina una clase nueva derivada de la clase <xref:System.IdentityModel.Selectors.SecurityTokenManager>.</span><span class="sxs-lookup"><span data-stu-id="b6734-116">Define a new class derived from the <xref:System.IdentityModel.Selectors.SecurityTokenManager> class.</span></span> <span data-ttu-id="b6734-117">(El siguiente ejemplo se deriva de la clase <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager>, que se deriva de la clase <xref:System.IdentityModel.Selectors.SecurityTokenManager>).</span><span class="sxs-lookup"><span data-stu-id="b6734-117">(The example below derives from the <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> class, which derives from the <xref:System.IdentityModel.Selectors.SecurityTokenManager> class.)</span></span>  
  
2.  <span data-ttu-id="b6734-118">Si no está ya invalidado, invalide el método <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%28System.IdentityModel.Selectors.SecurityTokenRequirement%29>.</span><span class="sxs-lookup"><span data-stu-id="b6734-118">Override the <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%28System.IdentityModel.Selectors.SecurityTokenRequirement%29> method if is not already overridden.</span></span>  
  
     <span data-ttu-id="b6734-119">El método <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%28System.IdentityModel.Selectors.SecurityTokenRequirement%29> es responsable de devolver una instancia de la clase <xref:System.IdentityModel.Selectors.SecurityTokenProvider> adecuada al parámetro <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> que el marco de seguridad [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] pasó al método.</span><span class="sxs-lookup"><span data-stu-id="b6734-119">The <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%28System.IdentityModel.Selectors.SecurityTokenRequirement%29> method is responsible for returning an instance of the <xref:System.IdentityModel.Selectors.SecurityTokenProvider> class appropriate to the <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> parameter passed to the method by the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] security framework.</span></span> <span data-ttu-id="b6734-120">Modifique el método para devolver la implementación de proveedor de tokens de seguridad personalizado (creada en el procedimiento anterior) cuando se llama al método con un parámetro de token de seguridad adecuado.</span><span class="sxs-lookup"><span data-stu-id="b6734-120">Modify the method to return the custom security token provider implementation (created in the previous procedure) when the method is called with an appropriate security token parameter.</span></span> <span data-ttu-id="b6734-121">Para obtener más información sobre el Administrador de tokens de seguridad, consulte el [Tutorial: creación personalizada credenciales de cliente y servicio](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md).</span><span class="sxs-lookup"><span data-stu-id="b6734-121">For more information about the security token manager, see the [Walkthrough: Creating Custom Client and Service Credentials](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md).</span></span>  
  
3.  <span data-ttu-id="b6734-122">Agregue la lógica personalizada al método para permitirle que devuelva su proveedor de tokens de seguridad personalizado basado en el parámetro <xref:System.IdentityModel.Selectors.SecurityTokenRequirement>.</span><span class="sxs-lookup"><span data-stu-id="b6734-122">Add custom logic to the method to enable it to return your custom security token provider based on the <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> parameter.</span></span> <span data-ttu-id="b6734-123">El ejemplo siguiente devuelve el proveedor de tokens de seguridad personalizado si se cumplen los requisitos del token.</span><span class="sxs-lookup"><span data-stu-id="b6734-123">The following sample returns the custom security token provider if the token requirements are met.</span></span> <span data-ttu-id="b6734-124">Los requisitos incluyen un token de seguridad X.509 y la dirección del mensaje (que el token se utiliza para la salida del mensaje).</span><span class="sxs-lookup"><span data-stu-id="b6734-124">The requirements include an X.509 security token and the message direction (that the token is used for message output).</span></span> <span data-ttu-id="b6734-125">Para todos los casos restantes, el código llama a la clase base para mantener el comportamiento proporcionado por el sistema para otros requisitos de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="b6734-125">For all other cases, the code calls the base class to maintain the system-provided behavior for other security token requirements.</span></span>  
  
 [!code-csharp[c_CustomTokenProvider#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenprovider/cs/source.cs#2)]
 [!code-vb[c_CustomTokenProvider#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenprovider/vb/source.vb#2)]  
  
## <a name="example"></a><span data-ttu-id="b6734-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b6734-126">Example</span></span>  
 <span data-ttu-id="b6734-127">A continuación se presenta una implementación <xref:System.IdentityModel.Selectors.SecurityTokenProvider> completa junto con una implementación <xref:System.IdentityModel.Selectors.SecurityTokenManager> correspondiente.</span><span class="sxs-lookup"><span data-stu-id="b6734-127">The following shows a complete <xref:System.IdentityModel.Selectors.SecurityTokenProvider> implementation along with a corresponding <xref:System.IdentityModel.Selectors.SecurityTokenManager> implementation.</span></span>  
  
 [!code-csharp[c_CustomTokenProvider#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenprovider/cs/source.cs#0)]
 [!code-vb[c_CustomTokenProvider#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenprovider/vb/source.vb#0)]  
  
## <a name="see-also"></a><span data-ttu-id="b6734-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="b6734-128">See Also</span></span>  
 <xref:System.IdentityModel.Selectors.SecurityTokenProvider>  
 <xref:System.IdentityModel.Selectors.SecurityTokenRequirement>  
 <xref:System.IdentityModel.Selectors.SecurityTokenManager>  
 <xref:System.IdentityModel.Tokens.X509SecurityToken>  
 [<span data-ttu-id="b6734-129">Tutorial: Creación de credenciales de cliente y servicio personalizadas</span><span class="sxs-lookup"><span data-stu-id="b6734-129">Walkthrough: Creating Custom Client and Service Credentials</span></span>](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md)  
 [<span data-ttu-id="b6734-130">Creación de un autenticador de tokens de seguridad personalizado</span><span class="sxs-lookup"><span data-stu-id="b6734-130">How to: Create a Custom Security Token Authenticator</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-authenticator.md)  
 [<span data-ttu-id="b6734-131">Arquitectura de seguridad</span><span class="sxs-lookup"><span data-stu-id="b6734-131">Security Architecture</span></span>](http://msdn.microsoft.com/library/16593476-d36a-408d-808c-ae6fd483e28f)
