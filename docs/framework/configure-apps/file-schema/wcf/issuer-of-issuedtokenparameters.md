---
description: 'Más información sobre: <issuer> de <issuedTokenParameters>'
title: <issuer> de <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: d6a95f32-d58c-40fc-8658-dd92564d3c90
ms.openlocfilehash: 7d67583eda22414750631b6dff40f6e6ea8831e4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99725654"
---
# <a name="issuer-of-issuedtokenparameters"></a><span data-ttu-id="5a2bc-103">\<issuer> de \<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="5a2bc-103">\<issuer> of \<issuedTokenParameters></span></span>

<span data-ttu-id="5a2bc-104">Especifica el servicio de token de seguridad (STS) que emite los tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="5a2bc-104">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenParameters>**](issuedtokenparameters.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuer>**  
  
## <a name="syntax"></a><span data-ttu-id="5a2bc-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5a2bc-105">Syntax</span></span>  
  
```xml  
<issuer address="Uri" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5a2bc-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5a2bc-106">Attributes and Elements</span></span>  

 <span data-ttu-id="5a2bc-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5a2bc-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5a2bc-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="5a2bc-108">Attributes</span></span>  
  
|<span data-ttu-id="5a2bc-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="5a2bc-109">Attribute</span></span>|<span data-ttu-id="5a2bc-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="5a2bc-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5a2bc-111">address</span><span class="sxs-lookup"><span data-stu-id="5a2bc-111">address</span></span>|<span data-ttu-id="5a2bc-112">Cadena necesaria.</span><span class="sxs-lookup"><span data-stu-id="5a2bc-112">Required string.</span></span> <span data-ttu-id="5a2bc-113">La dirección URL del STS.</span><span class="sxs-lookup"><span data-stu-id="5a2bc-113">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5a2bc-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5a2bc-114">Child Elements</span></span>  
  
|<span data-ttu-id="5a2bc-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="5a2bc-115">Element</span></span>|<span data-ttu-id="5a2bc-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="5a2bc-116">Description</span></span>|  
|-------------|-----------------|  
|[\<headers>](headers-element.md)|<span data-ttu-id="5a2bc-117">Una colección de encabezados de dirección para los puntos de conexión que el generador puede crear.</span><span class="sxs-lookup"><span data-stu-id="5a2bc-117">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[\<identity>](identity.md)|<span data-ttu-id="5a2bc-118">Al utilizar un token emitido, especifica valores que permiten al cliente autenticar el servidor.</span><span class="sxs-lookup"><span data-stu-id="5a2bc-118">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5a2bc-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5a2bc-119">Parent Elements</span></span>  
  
|<span data-ttu-id="5a2bc-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="5a2bc-120">Element</span></span>|<span data-ttu-id="5a2bc-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="5a2bc-121">Description</span></span>|  
|-------------|-----------------|  
|[\<issuedTokenParameters>](issuedtokenparameters.md)|<span data-ttu-id="5a2bc-122">Especifica el token emitido actual.</span><span class="sxs-lookup"><span data-stu-id="5a2bc-122">Specifies the current issued token.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5a2bc-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="5a2bc-123">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.AdditionalRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.AdditionalRequestParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="5a2bc-124">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="5a2bc-124">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="5a2bc-125">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="5a2bc-125">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="5a2bc-126">Capacidades de seguridad con enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="5a2bc-126">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="5a2bc-127">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="5a2bc-127">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="5a2bc-128">Enlaces</span><span class="sxs-lookup"><span data-stu-id="5a2bc-128">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="5a2bc-129">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="5a2bc-129">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="5a2bc-130">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="5a2bc-130">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="5a2bc-131">Procedimiento para crear un enlace personalizado mediante SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="5a2bc-131">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="5a2bc-132">Seguridad de enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="5a2bc-132">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
