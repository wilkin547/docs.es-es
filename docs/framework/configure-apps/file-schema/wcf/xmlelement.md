---
title: <xmlElement>
ms.date: 03/30/2017
ms.assetid: 395205c2-d8c0-4a5e-90f3-7ce3c085fccd
ms.openlocfilehash: cc178dcc3684ab338282acc369e0ab5c789c15e4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941436"
---
# <a name="xmlelement"></a><span data-ttu-id="1dcf5-101">\<xmlElement></span><span class="sxs-lookup"><span data-stu-id="1dcf5-101">\<xmlElement></span></span>
<span data-ttu-id="1dcf5-102">Especifica un elemento XML que se envía en el cuerpo del mensaje al servicio de token de seguridad cuando se solicita un token.</span><span class="sxs-lookup"><span data-stu-id="1dcf5-102">Specifies an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>  
  
 <span data-ttu-id="1dcf5-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="1dcf5-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="1dcf5-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="1dcf5-104">\<bindings></span></span>  
<span data-ttu-id="1dcf5-105">\<wsFederatedBinding></span><span class="sxs-lookup"><span data-stu-id="1dcf5-105">\<wsFederatedBinding></span></span>  
<span data-ttu-id="1dcf5-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="1dcf5-106">\<binding></span></span>  
<span data-ttu-id="1dcf5-107">\<> de seguridad</span><span class="sxs-lookup"><span data-stu-id="1dcf5-107">\<security></span></span>  
<span data-ttu-id="1dcf5-108">\<message></span><span class="sxs-lookup"><span data-stu-id="1dcf5-108">\<message></span></span>  
<span data-ttu-id="1dcf5-109">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="1dcf5-109">\<tokenRequestParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1dcf5-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1dcf5-110">Syntax</span></span>  
  
```xml  
<tokenRequestParameters>
  <xmlElement xmlElement="String" />
</tokenRequestParameters>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1dcf5-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="1dcf5-111">Attributes and Elements</span></span>  
 <span data-ttu-id="1dcf5-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="1dcf5-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1dcf5-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="1dcf5-113">Attributes</span></span>  
  
|<span data-ttu-id="1dcf5-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="1dcf5-114">Attribute</span></span>|<span data-ttu-id="1dcf5-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="1dcf5-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1dcf5-116">xmlElement</span><span class="sxs-lookup"><span data-stu-id="1dcf5-116">xmlElement</span></span>|<span data-ttu-id="1dcf5-117">Cadena que especifica un elemento XML que se envía en el cuerpo del mensaje al servicio de token de seguridad cuando se solicita un token.</span><span class="sxs-lookup"><span data-stu-id="1dcf5-117">A string specifying an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1dcf5-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1dcf5-118">Child Elements</span></span>  
 <span data-ttu-id="1dcf5-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="1dcf5-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1dcf5-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1dcf5-120">Parent Elements</span></span>  
  
|<span data-ttu-id="1dcf5-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="1dcf5-121">Element</span></span>|<span data-ttu-id="1dcf5-122">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="1dcf5-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1dcf5-123">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="1dcf5-123">\<tokenRequestParameters></span></span>](tokenrequestparameters.md)|<span data-ttu-id="1dcf5-124">Una colección de parámetros de solicitud de token.</span><span class="sxs-lookup"><span data-stu-id="1dcf5-124">A collection of token request parameters.</span></span> <span data-ttu-id="1dcf5-125">Cada parámetro es un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="1dcf5-125">Each parameter is an XML element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1dcf5-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="1dcf5-126">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.TokenRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.TokenRequestParameters%2A>
- [<span data-ttu-id="1dcf5-127">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="1dcf5-127">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="1dcf5-128">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="1dcf5-128">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="1dcf5-129">Funcionalidades de seguridad con enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="1dcf5-129">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="1dcf5-130">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="1dcf5-130">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="1dcf5-131">Enlaces</span><span class="sxs-lookup"><span data-stu-id="1dcf5-131">Bindings</span></span>](../../../wcf/bindings.md)
