---
title: <issuerMetadata> de <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: 1a85ca37-496d-4fa3-8d44-d6c9383d735c
ms.openlocfilehash: fcdd66ecd162dff5be86a1d4ab1b196f50dbd445
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400342"
---
# <a name="issuermetadata-of-issuedtokenparameters"></a><span data-ttu-id="555f5-102">\<issuerMetadata > \<issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="555f5-102">\<issuerMetadata> of \<issuedTokenParameters></span></span>

<span data-ttu-id="555f5-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="555f5-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="555f5-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="555f5-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="555f5-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de enlaces**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="555f5-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="555f5-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="555f5-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="555f5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de enlace**</span><span class="sxs-lookup"><span data-stu-id="555f5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="555f5-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de seguridad**](security-of-custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="555f5-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)</span></span>\
<span data-ttu-id="555f5-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> issuedTokenParameters**](issuedtokenparameters.md)</span><span class="sxs-lookup"><span data-stu-id="555f5-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenParameters>**](issuedtokenparameters.md)</span></span>\
<span data-ttu-id="555f5-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> issuerMetadata**</span><span class="sxs-lookup"><span data-stu-id="555f5-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerMetadata>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="555f5-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="555f5-111">Syntax</span></span>  
  
```xml  
<issuerMetaData address="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="555f5-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="555f5-112">Attributes and Elements</span></span>  
 <span data-ttu-id="555f5-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="555f5-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="555f5-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="555f5-114">Attributes</span></span>  
  
|<span data-ttu-id="555f5-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="555f5-115">Attribute</span></span>|<span data-ttu-id="555f5-116">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="555f5-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="555f5-117">dirección</span><span class="sxs-lookup"><span data-stu-id="555f5-117">address</span></span>|<span data-ttu-id="555f5-118">Necesario.</span><span class="sxs-lookup"><span data-stu-id="555f5-118">Required.</span></span> <span data-ttu-id="555f5-119">Cadena que especifica la dirección del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="555f5-119">A string that specifies the address of the endpoint.</span></span> <span data-ttu-id="555f5-120">La dirección debe ser un URI absoluto.</span><span class="sxs-lookup"><span data-stu-id="555f5-120">The address must be an absolute URI.</span></span> <span data-ttu-id="555f5-121">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="555f5-121">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="555f5-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="555f5-122">Child Elements</span></span>  
  
|<span data-ttu-id="555f5-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="555f5-123">Element</span></span>|<span data-ttu-id="555f5-124">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="555f5-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="555f5-125">\<headers></span><span class="sxs-lookup"><span data-stu-id="555f5-125">\<headers></span></span>](headers-element.md)|<span data-ttu-id="555f5-126">Una colección de encabezados de dirección.</span><span class="sxs-lookup"><span data-stu-id="555f5-126">A collection of address headers.</span></span>|  
|[<span data-ttu-id="555f5-127">\<identity></span><span class="sxs-lookup"><span data-stu-id="555f5-127">\<identity></span></span>](identity.md)|<span data-ttu-id="555f5-128">Una identidad que habilita la autenticación de un punto de conexión por otros puntos de conexión que intercambian mensajes con él.</span><span class="sxs-lookup"><span data-stu-id="555f5-128">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="555f5-129">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="555f5-129">Parent Elements</span></span>  
  
|<span data-ttu-id="555f5-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="555f5-130">Element</span></span>|<span data-ttu-id="555f5-131">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="555f5-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="555f5-132">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="555f5-132">\<issuedTokenParameters></span></span>](issuedtokenparameters.md)|<span data-ttu-id="555f5-133">Especifica los parámetros para un símbolo (token) de seguridad emitido en un escenario de seguridad aliado.</span><span class="sxs-lookup"><span data-stu-id="555f5-133">Specifies the parameters for an security token issued in a Federated security scenario.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="555f5-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="555f5-134">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="555f5-135">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="555f5-135">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="555f5-136">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="555f5-136">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="555f5-137">Funcionalidades de seguridad con enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="555f5-137">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="555f5-138">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="555f5-138">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="555f5-139">Enlaces</span><span class="sxs-lookup"><span data-stu-id="555f5-139">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="555f5-140">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="555f5-140">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="555f5-141">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="555f5-141">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="555f5-142">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="555f5-142">\<customBinding></span></span>](custombinding.md)
- [<span data-ttu-id="555f5-143">Procedimientos: Crear un enlace personalizado mediante SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="555f5-143">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="555f5-144">Seguridad de enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="555f5-144">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
