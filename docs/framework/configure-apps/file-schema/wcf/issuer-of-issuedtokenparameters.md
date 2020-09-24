---
title: <issuer> de <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: d6a95f32-d58c-40fc-8658-dd92564d3c90
ms.openlocfilehash: bfe8163d2d6baba1d6e8053f7f6579673d8b4b21
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91157283"
---
# <a name="issuer-of-issuedtokenparameters"></a><span data-ttu-id="230a7-102">\<issuer> de \<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="230a7-102">\<issuer> of \<issuedTokenParameters></span></span>

<span data-ttu-id="230a7-103">Especifica el servicio de token de seguridad (STS) que emite los tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="230a7-103">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenParameters>**](issuedtokenparameters.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuer>**  
  
## <a name="syntax"></a><span data-ttu-id="230a7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="230a7-104">Syntax</span></span>  
  
```xml  
<issuer address="Uri" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="230a7-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="230a7-105">Attributes and Elements</span></span>  

 <span data-ttu-id="230a7-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="230a7-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="230a7-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="230a7-107">Attributes</span></span>  
  
|<span data-ttu-id="230a7-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="230a7-108">Attribute</span></span>|<span data-ttu-id="230a7-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="230a7-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="230a7-110">address</span><span class="sxs-lookup"><span data-stu-id="230a7-110">address</span></span>|<span data-ttu-id="230a7-111">Cadena necesaria.</span><span class="sxs-lookup"><span data-stu-id="230a7-111">Required string.</span></span> <span data-ttu-id="230a7-112">La dirección URL del STS.</span><span class="sxs-lookup"><span data-stu-id="230a7-112">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="230a7-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="230a7-113">Child Elements</span></span>  
  
|<span data-ttu-id="230a7-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="230a7-114">Element</span></span>|<span data-ttu-id="230a7-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="230a7-115">Description</span></span>|  
|-------------|-----------------|  
|[\<headers>](headers-element.md)|<span data-ttu-id="230a7-116">Una colección de encabezados de dirección para los puntos de conexión que el generador puede crear.</span><span class="sxs-lookup"><span data-stu-id="230a7-116">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[\<identity>](identity.md)|<span data-ttu-id="230a7-117">Al utilizar un token emitido, especifica valores que permiten al cliente autenticar el servidor.</span><span class="sxs-lookup"><span data-stu-id="230a7-117">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="230a7-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="230a7-118">Parent Elements</span></span>  
  
|<span data-ttu-id="230a7-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="230a7-119">Element</span></span>|<span data-ttu-id="230a7-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="230a7-120">Description</span></span>|  
|-------------|-----------------|  
|[\<issuedTokenParameters>](issuedtokenparameters.md)|<span data-ttu-id="230a7-121">Especifica el token emitido actual.</span><span class="sxs-lookup"><span data-stu-id="230a7-121">Specifies the current issued token.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="230a7-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="230a7-122">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.AdditionalRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.AdditionalRequestParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="230a7-123">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="230a7-123">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="230a7-124">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="230a7-124">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="230a7-125">Capacidades de seguridad con enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="230a7-125">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="230a7-126">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="230a7-126">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="230a7-127">Enlaces</span><span class="sxs-lookup"><span data-stu-id="230a7-127">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="230a7-128">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="230a7-128">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="230a7-129">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="230a7-129">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="230a7-130">Procedimiento para crear un enlace personalizado mediante SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="230a7-130">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="230a7-131">Seguridad de enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="230a7-131">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
