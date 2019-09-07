---
title: <issuer> de <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: d6a95f32-d58c-40fc-8658-dd92564d3c90
ms.openlocfilehash: bdd5ad45984fae7b39defe82c4af75845dfda1b6
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397946"
---
# <a name="issuer-of-issuedtokenparameters"></a><span data-ttu-id="24c56-102">\<> del emisor de \<issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="24c56-102">\<issuer> of \<issuedTokenParameters></span></span>
<span data-ttu-id="24c56-103">Especifica el servicio de token de seguridad (STS) que emite los tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="24c56-103">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
<span data-ttu-id="24c56-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="24c56-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="24c56-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="24c56-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="24c56-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de enlaces**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="24c56-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="24c56-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="24c56-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="24c56-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de enlace**</span><span class="sxs-lookup"><span data-stu-id="24c56-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="24c56-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de seguridad**](security-of-custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="24c56-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)</span></span>\
<span data-ttu-id="24c56-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> issuedTokenParameters**](issuedtokenparameters.md)</span><span class="sxs-lookup"><span data-stu-id="24c56-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenParameters>**](issuedtokenparameters.md)</span></span>\
<span data-ttu-id="24c56-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> del emisor**</span><span class="sxs-lookup"><span data-stu-id="24c56-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuer>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24c56-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="24c56-112">Syntax</span></span>  
  
```xml  
<issuer address="Uri" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="24c56-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="24c56-113">Attributes and Elements</span></span>  
 <span data-ttu-id="24c56-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="24c56-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="24c56-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="24c56-115">Attributes</span></span>  
  
|<span data-ttu-id="24c56-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="24c56-116">Attribute</span></span>|<span data-ttu-id="24c56-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="24c56-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="24c56-118">dirección</span><span class="sxs-lookup"><span data-stu-id="24c56-118">address</span></span>|<span data-ttu-id="24c56-119">Cadena necesaria.</span><span class="sxs-lookup"><span data-stu-id="24c56-119">Required string.</span></span> <span data-ttu-id="24c56-120">La dirección URL del STS.</span><span class="sxs-lookup"><span data-stu-id="24c56-120">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="24c56-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="24c56-121">Child Elements</span></span>  
  
|<span data-ttu-id="24c56-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="24c56-122">Element</span></span>|<span data-ttu-id="24c56-123">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="24c56-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="24c56-124">\<headers></span><span class="sxs-lookup"><span data-stu-id="24c56-124">\<headers></span></span>](headers-element.md)|<span data-ttu-id="24c56-125">Una colección de encabezados de dirección para los puntos de conexión que el generador puede crear.</span><span class="sxs-lookup"><span data-stu-id="24c56-125">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="24c56-126">\<identity></span><span class="sxs-lookup"><span data-stu-id="24c56-126">\<identity></span></span>](identity.md)|<span data-ttu-id="24c56-127">Al utilizar un token emitido, especifica valores que permiten al cliente autenticar el servidor.</span><span class="sxs-lookup"><span data-stu-id="24c56-127">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="24c56-128">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="24c56-128">Parent Elements</span></span>  
  
|<span data-ttu-id="24c56-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="24c56-129">Element</span></span>|<span data-ttu-id="24c56-130">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="24c56-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="24c56-131">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="24c56-131">\<issuedTokenParameters></span></span>](issuedtokenparameters.md)|<span data-ttu-id="24c56-132">Especifica el token emitido actual.</span><span class="sxs-lookup"><span data-stu-id="24c56-132">Specifies the current issued token.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="24c56-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="24c56-133">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.AdditionalRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.AdditionalRequestParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="24c56-134">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="24c56-134">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="24c56-135">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="24c56-135">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="24c56-136">Funcionalidades de seguridad con enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="24c56-136">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="24c56-137">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="24c56-137">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="24c56-138">Enlaces</span><span class="sxs-lookup"><span data-stu-id="24c56-138">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="24c56-139">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="24c56-139">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="24c56-140">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="24c56-140">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="24c56-141">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="24c56-141">\<customBinding></span></span>](custombinding.md)
- [<span data-ttu-id="24c56-142">Cómo: Crear un enlace personalizado mediante SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="24c56-142">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="24c56-143">Seguridad de enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="24c56-143">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
