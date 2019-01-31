---
title: <xmlElement>
ms.date: 03/30/2017
ms.assetid: 395205c2-d8c0-4a5e-90f3-7ce3c085fccd
ms.openlocfilehash: 648147a7e3977648ac3c26c9dfc469629f3b70c3
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55278296"
---
# <a name="xmlelement"></a><span data-ttu-id="f2cd4-101">\<xmlElement></span><span class="sxs-lookup"><span data-stu-id="f2cd4-101">\<xmlElement></span></span>
<span data-ttu-id="f2cd4-102">Especifica un elemento XML que se envía en el cuerpo del mensaje al servicio de token de seguridad cuando se solicita un token.</span><span class="sxs-lookup"><span data-stu-id="f2cd4-102">Specifies an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>  
  
 <span data-ttu-id="f2cd4-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="f2cd4-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="f2cd4-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="f2cd4-104">\<bindings></span></span>  
<span data-ttu-id="f2cd4-105">\<wsFederatedBinding></span><span class="sxs-lookup"><span data-stu-id="f2cd4-105">\<wsFederatedBinding></span></span>  
<span data-ttu-id="f2cd4-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="f2cd4-106">\<binding></span></span>  
<span data-ttu-id="f2cd4-107">\<security></span><span class="sxs-lookup"><span data-stu-id="f2cd4-107">\<security></span></span>  
<span data-ttu-id="f2cd4-108">\<message></span><span class="sxs-lookup"><span data-stu-id="f2cd4-108">\<message></span></span>  
<span data-ttu-id="f2cd4-109">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="f2cd4-109">\<tokenRequestParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2cd4-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f2cd4-110">Syntax</span></span>  
  
```xml  
<tokenRequestParameters>
  <xmlElement xmlElement="String" />
</tokenRequestParameters>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f2cd4-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f2cd4-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f2cd4-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f2cd4-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f2cd4-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="f2cd4-113">Attributes</span></span>  
  
|<span data-ttu-id="f2cd4-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="f2cd4-114">Attribute</span></span>|<span data-ttu-id="f2cd4-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="f2cd4-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f2cd4-116">xmlElement</span><span class="sxs-lookup"><span data-stu-id="f2cd4-116">xmlElement</span></span>|<span data-ttu-id="f2cd4-117">Cadena que especifica un elemento XML que se envía en el cuerpo del mensaje al servicio de token de seguridad cuando se solicita un token.</span><span class="sxs-lookup"><span data-stu-id="f2cd4-117">A string specifying an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f2cd4-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f2cd4-118">Child Elements</span></span>  
 <span data-ttu-id="f2cd4-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f2cd4-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f2cd4-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f2cd4-120">Parent Elements</span></span>  
  
|<span data-ttu-id="f2cd4-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="f2cd4-121">Element</span></span>|<span data-ttu-id="f2cd4-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="f2cd4-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f2cd4-123">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="f2cd4-123">\<tokenRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/tokenrequestparameters.md)|<span data-ttu-id="f2cd4-124">Una colección de parámetros de solicitud de token.</span><span class="sxs-lookup"><span data-stu-id="f2cd4-124">A collection of token request parameters.</span></span> <span data-ttu-id="f2cd4-125">Cada parámetro es un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="f2cd4-125">Each parameter is an XML element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f2cd4-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="f2cd4-126">See also</span></span>
- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.TokenRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.TokenRequestParameters%2A>
- [<span data-ttu-id="f2cd4-127">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="f2cd4-127">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="f2cd4-128">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="f2cd4-128">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="f2cd4-129">Funcionalidades de seguridad con enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="f2cd4-129">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="f2cd4-130">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="f2cd4-130">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="f2cd4-131">Enlaces</span><span class="sxs-lookup"><span data-stu-id="f2cd4-131">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
