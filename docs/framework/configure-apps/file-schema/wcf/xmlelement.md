---
title: '&lt;xmlElement&gt;'
ms.date: 03/30/2017
ms.assetid: 395205c2-d8c0-4a5e-90f3-7ce3c085fccd
ms.openlocfilehash: 40703bdf62e8c69ac7e09a0d715e2a2f99408680
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54612286"
---
# <a name="ltxmlelementgt"></a><span data-ttu-id="fb6a9-102">&lt;xmlElement&gt;</span><span class="sxs-lookup"><span data-stu-id="fb6a9-102">&lt;xmlElement&gt;</span></span>
<span data-ttu-id="fb6a9-103">Especifica un elemento XML que se envía en el cuerpo del mensaje al servicio de token de seguridad cuando se solicita un token.</span><span class="sxs-lookup"><span data-stu-id="fb6a9-103">Specifies an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>  
  
 <span data-ttu-id="fb6a9-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="fb6a9-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="fb6a9-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="fb6a9-105">\<bindings></span></span>  
<span data-ttu-id="fb6a9-106">\<wsFederatedBinding></span><span class="sxs-lookup"><span data-stu-id="fb6a9-106">\<wsFederatedBinding></span></span>  
<span data-ttu-id="fb6a9-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="fb6a9-107">\<binding></span></span>  
<span data-ttu-id="fb6a9-108">\<security></span><span class="sxs-lookup"><span data-stu-id="fb6a9-108">\<security></span></span>  
<span data-ttu-id="fb6a9-109">\<message></span><span class="sxs-lookup"><span data-stu-id="fb6a9-109">\<message></span></span>  
<span data-ttu-id="fb6a9-110">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="fb6a9-110">\<tokenRequestParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb6a9-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fb6a9-111">Syntax</span></span>  
  
```xml  
<tokenRequestParameters>
  <xmlElement xmlElement="String" />
</tokenRequestParameters>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fb6a9-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="fb6a9-112">Attributes and Elements</span></span>  
 <span data-ttu-id="fb6a9-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="fb6a9-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fb6a9-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="fb6a9-114">Attributes</span></span>  
  
|<span data-ttu-id="fb6a9-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="fb6a9-115">Attribute</span></span>|<span data-ttu-id="fb6a9-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="fb6a9-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fb6a9-117">xmlElement</span><span class="sxs-lookup"><span data-stu-id="fb6a9-117">xmlElement</span></span>|<span data-ttu-id="fb6a9-118">Cadena que especifica un elemento XML que se envía en el cuerpo del mensaje al servicio de token de seguridad cuando se solicita un token.</span><span class="sxs-lookup"><span data-stu-id="fb6a9-118">A string specifying an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fb6a9-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="fb6a9-119">Child Elements</span></span>  
 <span data-ttu-id="fb6a9-120">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="fb6a9-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fb6a9-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="fb6a9-121">Parent Elements</span></span>  
  
|<span data-ttu-id="fb6a9-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="fb6a9-122">Element</span></span>|<span data-ttu-id="fb6a9-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="fb6a9-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fb6a9-124">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="fb6a9-124">\<tokenRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/tokenrequestparameters.md)|<span data-ttu-id="fb6a9-125">Una colección de parámetros de solicitud de token.</span><span class="sxs-lookup"><span data-stu-id="fb6a9-125">A collection of token request parameters.</span></span> <span data-ttu-id="fb6a9-126">Cada parámetro es un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="fb6a9-126">Each parameter is an XML element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fb6a9-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="fb6a9-127">See also</span></span>
- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.TokenRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.TokenRequestParameters%2A>
- [<span data-ttu-id="fb6a9-128">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="fb6a9-128">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="fb6a9-129">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="fb6a9-129">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="fb6a9-130">Funcionalidades de seguridad con enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="fb6a9-130">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="fb6a9-131">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="fb6a9-131">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="fb6a9-132">Enlaces</span><span class="sxs-lookup"><span data-stu-id="fb6a9-132">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
