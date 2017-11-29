---
title: '&lt;xmlElement&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 395205c2-d8c0-4a5e-90f3-7ce3c085fccd
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d1efe32121bc5744c305ff8ef8eefabd8a9d19e7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltxmlelementgt"></a><span data-ttu-id="bfaf4-102">&lt;xmlElement&gt;</span><span class="sxs-lookup"><span data-stu-id="bfaf4-102">&lt;xmlElement&gt;</span></span>
<span data-ttu-id="bfaf4-103">Especifica un elemento XML que se envía en el cuerpo del mensaje al servicio de token de seguridad cuando se solicita un token.</span><span class="sxs-lookup"><span data-stu-id="bfaf4-103">Specifies an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>  
  
 <span data-ttu-id="bfaf4-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="bfaf4-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="bfaf4-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="bfaf4-105">\<bindings></span></span>  
<span data-ttu-id="bfaf4-106">\<wsFederatedBinding ></span><span class="sxs-lookup"><span data-stu-id="bfaf4-106">\<wsFederatedBinding></span></span>  
<span data-ttu-id="bfaf4-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="bfaf4-107">\<binding></span></span>  
<span data-ttu-id="bfaf4-108">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="bfaf4-108">\<security></span></span>  
<span data-ttu-id="bfaf4-109">\<mensaje ></span><span class="sxs-lookup"><span data-stu-id="bfaf4-109">\<message></span></span>  
<span data-ttu-id="bfaf4-110">\<tokenRequestParameters ></span><span class="sxs-lookup"><span data-stu-id="bfaf4-110">\<tokenRequestParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfaf4-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bfaf4-111">Syntax</span></span>  
  
```xml  
<tokenRequestParameters>  
      <xmlElement xmlElement="String" />  
</tokenRequestParameters>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bfaf4-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="bfaf4-112">Attributes and Elements</span></span>  
 <span data-ttu-id="bfaf4-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="bfaf4-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bfaf4-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="bfaf4-114">Attributes</span></span>  
  
|<span data-ttu-id="bfaf4-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="bfaf4-115">Attribute</span></span>|<span data-ttu-id="bfaf4-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="bfaf4-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bfaf4-117">xmlElement</span><span class="sxs-lookup"><span data-stu-id="bfaf4-117">xmlElement</span></span>|<span data-ttu-id="bfaf4-118">Cadena que especifica un elemento XML que se envía en el cuerpo del mensaje al servicio de token de seguridad cuando se solicita un token.</span><span class="sxs-lookup"><span data-stu-id="bfaf4-118">A string specifying an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bfaf4-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="bfaf4-119">Child Elements</span></span>  
 <span data-ttu-id="bfaf4-120">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="bfaf4-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bfaf4-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="bfaf4-121">Parent Elements</span></span>  
  
|<span data-ttu-id="bfaf4-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="bfaf4-122">Element</span></span>|<span data-ttu-id="bfaf4-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="bfaf4-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bfaf4-124">\<tokenRequestParameters ></span><span class="sxs-lookup"><span data-stu-id="bfaf4-124">\<tokenRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/tokenrequestparameters.md)|<span data-ttu-id="bfaf4-125">Una colección de parámetros de solicitud de token.</span><span class="sxs-lookup"><span data-stu-id="bfaf4-125">A collection of token request parameters.</span></span> <span data-ttu-id="bfaf4-126">Cada parámetro es un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="bfaf4-126">Each parameter is an XML element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bfaf4-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="bfaf4-127">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.TokenRequestParameters%2A>  
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.TokenRequestParameters%2A>  
 [<span data-ttu-id="bfaf4-128">Autenticación e identidad de servicio</span><span class="sxs-lookup"><span data-stu-id="bfaf4-128">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="bfaf4-129">Federación y Tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="bfaf4-129">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="bfaf4-130">Capacidades de seguridad con enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="bfaf4-130">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="bfaf4-131">Federación y Tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="bfaf4-131">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="bfaf4-132">Enlaces</span><span class="sxs-lookup"><span data-stu-id="bfaf4-132">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
