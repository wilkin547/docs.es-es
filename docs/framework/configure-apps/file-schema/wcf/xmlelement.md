---
title: <xmlElement>
ms.date: 03/30/2017
ms.assetid: 395205c2-d8c0-4a5e-90f3-7ce3c085fccd
ms.openlocfilehash: 841331f233bb8c42c25c88ad8e9b4fb1a86faa76
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398998"
---
# <a name="xmlelement"></a><span data-ttu-id="8a2c4-101">\<xmlElement></span><span class="sxs-lookup"><span data-stu-id="8a2c4-101">\<xmlElement></span></span>
<span data-ttu-id="8a2c4-102">Especifica un elemento XML que se envía en el cuerpo del mensaje al servicio de token de seguridad cuando se solicita un token.</span><span class="sxs-lookup"><span data-stu-id="8a2c4-102">Specifies an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>  
  
<span data-ttu-id="8a2c4-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8a2c4-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8a2c4-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="8a2c4-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="8a2c4-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de enlaces**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="8a2c4-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="8a2c4-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> wsFederationHttpBinding**](wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="8a2c4-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="8a2c4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de enlace**</span><span class="sxs-lookup"><span data-stu-id="8a2c4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="8a2c4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de seguridad**](security-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="8a2c4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="8a2c4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de mensajes**](message-element-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="8a2c4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="8a2c4-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> tokenRequestParameters**](tokenrequestparameters.md)</span><span class="sxs-lookup"><span data-stu-id="8a2c4-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<tokenRequestParameters>**](tokenrequestparameters.md)</span></span>\
<span data-ttu-id="8a2c4-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> xmlElement**</span><span class="sxs-lookup"><span data-stu-id="8a2c4-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<xmlElement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a2c4-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8a2c4-112">Syntax</span></span>  
  
```xml  
<tokenRequestParameters>
  <xmlElement xmlElement="String" />
</tokenRequestParameters>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8a2c4-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="8a2c4-113">Attributes and Elements</span></span>  
 <span data-ttu-id="8a2c4-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="8a2c4-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8a2c4-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="8a2c4-115">Attributes</span></span>  
  
|<span data-ttu-id="8a2c4-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="8a2c4-116">Attribute</span></span>|<span data-ttu-id="8a2c4-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="8a2c4-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8a2c4-118">xmlElement</span><span class="sxs-lookup"><span data-stu-id="8a2c4-118">xmlElement</span></span>|<span data-ttu-id="8a2c4-119">Cadena que especifica un elemento XML que se envía en el cuerpo del mensaje al servicio de token de seguridad cuando se solicita un token.</span><span class="sxs-lookup"><span data-stu-id="8a2c4-119">A string specifying an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8a2c4-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8a2c4-120">Child Elements</span></span>  
 <span data-ttu-id="8a2c4-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="8a2c4-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8a2c4-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8a2c4-122">Parent Elements</span></span>  
  
|<span data-ttu-id="8a2c4-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="8a2c4-123">Element</span></span>|<span data-ttu-id="8a2c4-124">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="8a2c4-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8a2c4-125">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="8a2c4-125">\<tokenRequestParameters></span></span>](tokenrequestparameters.md)|<span data-ttu-id="8a2c4-126">Una colección de parámetros de solicitud de token.</span><span class="sxs-lookup"><span data-stu-id="8a2c4-126">A collection of token request parameters.</span></span> <span data-ttu-id="8a2c4-127">Cada parámetro es un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="8a2c4-127">Each parameter is an XML element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8a2c4-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="8a2c4-128">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.TokenRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.TokenRequestParameters%2A>
- [<span data-ttu-id="8a2c4-129">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="8a2c4-129">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="8a2c4-130">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="8a2c4-130">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="8a2c4-131">Funcionalidades de seguridad con enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="8a2c4-131">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="8a2c4-132">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="8a2c4-132">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="8a2c4-133">Enlaces</span><span class="sxs-lookup"><span data-stu-id="8a2c4-133">Bindings</span></span>](../../../wcf/bindings.md)
