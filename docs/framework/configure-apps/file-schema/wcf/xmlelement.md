---
description: 'Más información acerca de: <xmlElement>'
title: <xmlElement>
ms.date: 03/30/2017
ms.assetid: 395205c2-d8c0-4a5e-90f3-7ce3c085fccd
ms.openlocfilehash: 891f1a95c1f6a79127d48a1572bc805574225530
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99682012"
---
# \<xmlElement>

<span data-ttu-id="08df6-102">Especifica un elemento XML que se envía en el cuerpo del mensaje al servicio de token de seguridad cuando se solicita un token.</span><span class="sxs-lookup"><span data-stu-id="08df6-102">Specifies an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<tokenRequestParameters>**](tokenrequestparameters.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<xmlElement>**  
  
## <a name="syntax"></a><span data-ttu-id="08df6-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="08df6-103">Syntax</span></span>  
  
```xml  
<tokenRequestParameters>
  <xmlElement xmlElement="String" />
</tokenRequestParameters>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="08df6-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="08df6-104">Attributes and Elements</span></span>  

 <span data-ttu-id="08df6-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="08df6-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="08df6-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="08df6-106">Attributes</span></span>  
  
|<span data-ttu-id="08df6-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="08df6-107">Attribute</span></span>|<span data-ttu-id="08df6-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="08df6-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="08df6-109">xmlElement</span><span class="sxs-lookup"><span data-stu-id="08df6-109">xmlElement</span></span>|<span data-ttu-id="08df6-110">Cadena que especifica un elemento XML que se envía en el cuerpo del mensaje al servicio de token de seguridad cuando se solicita un token.</span><span class="sxs-lookup"><span data-stu-id="08df6-110">A string specifying an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="08df6-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="08df6-111">Child Elements</span></span>  

 <span data-ttu-id="08df6-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="08df6-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="08df6-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="08df6-113">Parent Elements</span></span>  
  
|<span data-ttu-id="08df6-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="08df6-114">Element</span></span>|<span data-ttu-id="08df6-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="08df6-115">Description</span></span>|  
|-------------|-----------------|  
|[\<tokenRequestParameters>](tokenrequestparameters.md)|<span data-ttu-id="08df6-116">Una colección de parámetros de solicitud de token.</span><span class="sxs-lookup"><span data-stu-id="08df6-116">A collection of token request parameters.</span></span> <span data-ttu-id="08df6-117">Cada parámetro es un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="08df6-117">Each parameter is an XML element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="08df6-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="08df6-118">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.TokenRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.TokenRequestParameters%2A>
- [<span data-ttu-id="08df6-119">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="08df6-119">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="08df6-120">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="08df6-120">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="08df6-121">Capacidades de seguridad con enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="08df6-121">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="08df6-122">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="08df6-122">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="08df6-123">Enlaces</span><span class="sxs-lookup"><span data-stu-id="08df6-123">Bindings</span></span>](../../../wcf/bindings.md)
