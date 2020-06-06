---
title: <xmlElement>
ms.date: 03/30/2017
ms.assetid: 395205c2-d8c0-4a5e-90f3-7ce3c085fccd
ms.openlocfilehash: 841331f233bb8c42c25c88ad8e9b4fb1a86faa76
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398998"
---
# \<xmlElement>
<span data-ttu-id="a7b93-101">Especifica un elemento XML que se envía en el cuerpo del mensaje al servicio de token de seguridad cuando se solicita un token.</span><span class="sxs-lookup"><span data-stu-id="a7b93-101">Specifies an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<tokenRequestParameters>**](tokenrequestparameters.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<xmlElement>**  
  
## <a name="syntax"></a><span data-ttu-id="a7b93-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a7b93-102">Syntax</span></span>  
  
```xml  
<tokenRequestParameters>
  <xmlElement xmlElement="String" />
</tokenRequestParameters>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a7b93-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a7b93-103">Attributes and Elements</span></span>  
 <span data-ttu-id="a7b93-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a7b93-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a7b93-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="a7b93-105">Attributes</span></span>  
  
|<span data-ttu-id="a7b93-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="a7b93-106">Attribute</span></span>|<span data-ttu-id="a7b93-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="a7b93-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a7b93-108">xmlElement</span><span class="sxs-lookup"><span data-stu-id="a7b93-108">xmlElement</span></span>|<span data-ttu-id="a7b93-109">Cadena que especifica un elemento XML que se envía en el cuerpo del mensaje al servicio de token de seguridad cuando se solicita un token.</span><span class="sxs-lookup"><span data-stu-id="a7b93-109">A string specifying an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a7b93-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a7b93-110">Child Elements</span></span>  
 <span data-ttu-id="a7b93-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a7b93-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a7b93-112">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a7b93-112">Parent Elements</span></span>  
  
|<span data-ttu-id="a7b93-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="a7b93-113">Element</span></span>|<span data-ttu-id="a7b93-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="a7b93-114">Description</span></span>|  
|-------------|-----------------|  
|[\<tokenRequestParameters>](tokenrequestparameters.md)|<span data-ttu-id="a7b93-115">Una colección de parámetros de solicitud de token.</span><span class="sxs-lookup"><span data-stu-id="a7b93-115">A collection of token request parameters.</span></span> <span data-ttu-id="a7b93-116">Cada parámetro es un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="a7b93-116">Each parameter is an XML element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a7b93-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a7b93-117">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.TokenRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.TokenRequestParameters%2A>
- [<span data-ttu-id="a7b93-118">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="a7b93-118">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="a7b93-119">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="a7b93-119">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="a7b93-120">Capacidades de seguridad con enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="a7b93-120">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="a7b93-121">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="a7b93-121">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="a7b93-122">Enlaces</span><span class="sxs-lookup"><span data-stu-id="a7b93-122">Bindings</span></span>](../../../wcf/bindings.md)
