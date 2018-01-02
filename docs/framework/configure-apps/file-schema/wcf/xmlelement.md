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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 702b5ea1331aa0ac284d62809367a90e200a8ba3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltxmlelementgt"></a><span data-ttu-id="4836a-102">&lt;xmlElement&gt;</span><span class="sxs-lookup"><span data-stu-id="4836a-102">&lt;xmlElement&gt;</span></span>
<span data-ttu-id="4836a-103">Especifica un elemento XML que se envía en el cuerpo del mensaje al servicio de token de seguridad cuando se solicita un token.</span><span class="sxs-lookup"><span data-stu-id="4836a-103">Specifies an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>  
  
 <span data-ttu-id="4836a-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="4836a-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="4836a-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="4836a-105">\<bindings></span></span>  
<span data-ttu-id="4836a-106">\<wsFederatedBinding ></span><span class="sxs-lookup"><span data-stu-id="4836a-106">\<wsFederatedBinding></span></span>  
<span data-ttu-id="4836a-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="4836a-107">\<binding></span></span>  
<span data-ttu-id="4836a-108">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="4836a-108">\<security></span></span>  
<span data-ttu-id="4836a-109">\<mensaje ></span><span class="sxs-lookup"><span data-stu-id="4836a-109">\<message></span></span>  
<span data-ttu-id="4836a-110">\<tokenRequestParameters ></span><span class="sxs-lookup"><span data-stu-id="4836a-110">\<tokenRequestParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4836a-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4836a-111">Syntax</span></span>  
  
```xml  
<tokenRequestParameters>  
      <xmlElement xmlElement="String" />  
</tokenRequestParameters>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4836a-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4836a-112">Attributes and Elements</span></span>  
 <span data-ttu-id="4836a-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4836a-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4836a-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="4836a-114">Attributes</span></span>  
  
|<span data-ttu-id="4836a-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="4836a-115">Attribute</span></span>|<span data-ttu-id="4836a-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="4836a-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4836a-117">xmlElement</span><span class="sxs-lookup"><span data-stu-id="4836a-117">xmlElement</span></span>|<span data-ttu-id="4836a-118">Cadena que especifica un elemento XML que se envía en el cuerpo del mensaje al servicio de token de seguridad cuando se solicita un token.</span><span class="sxs-lookup"><span data-stu-id="4836a-118">A string specifying an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4836a-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4836a-119">Child Elements</span></span>  
 <span data-ttu-id="4836a-120">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="4836a-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4836a-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4836a-121">Parent Elements</span></span>  
  
|<span data-ttu-id="4836a-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="4836a-122">Element</span></span>|<span data-ttu-id="4836a-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="4836a-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4836a-124">\<tokenRequestParameters ></span><span class="sxs-lookup"><span data-stu-id="4836a-124">\<tokenRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/tokenrequestparameters.md)|<span data-ttu-id="4836a-125">Una colección de parámetros de solicitud de token.</span><span class="sxs-lookup"><span data-stu-id="4836a-125">A collection of token request parameters.</span></span> <span data-ttu-id="4836a-126">Cada parámetro es un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="4836a-126">Each parameter is an XML element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4836a-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="4836a-127">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.TokenRequestParameters%2A>  
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.TokenRequestParameters%2A>  
 [<span data-ttu-id="4836a-128">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="4836a-128">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="4836a-129">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="4836a-129">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="4836a-130">Funcionalidades de seguridad con enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="4836a-130">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="4836a-131">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="4836a-131">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="4836a-132">Enlaces</span><span class="sxs-lookup"><span data-stu-id="4836a-132">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
