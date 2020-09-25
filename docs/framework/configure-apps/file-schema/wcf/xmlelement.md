---
title: <xmlElement>
ms.date: 03/30/2017
ms.assetid: 395205c2-d8c0-4a5e-90f3-7ce3c085fccd
ms.openlocfilehash: 0ab7fbd64cc92e940617f5334eeb16fcb3a50c4a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91181237"
---
# \<xmlElement>

<span data-ttu-id="77834-101">Especifica un elemento XML que se envía en el cuerpo del mensaje al servicio de token de seguridad cuando se solicita un token.</span><span class="sxs-lookup"><span data-stu-id="77834-101">Specifies an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<tokenRequestParameters>**](tokenrequestparameters.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<xmlElement>**  
  
## <a name="syntax"></a><span data-ttu-id="77834-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="77834-102">Syntax</span></span>  
  
```xml  
<tokenRequestParameters>
  <xmlElement xmlElement="String" />
</tokenRequestParameters>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="77834-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="77834-103">Attributes and Elements</span></span>  

 <span data-ttu-id="77834-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="77834-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="77834-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="77834-105">Attributes</span></span>  
  
|<span data-ttu-id="77834-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="77834-106">Attribute</span></span>|<span data-ttu-id="77834-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="77834-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="77834-108">xmlElement</span><span class="sxs-lookup"><span data-stu-id="77834-108">xmlElement</span></span>|<span data-ttu-id="77834-109">Cadena que especifica un elemento XML que se envía en el cuerpo del mensaje al servicio de token de seguridad cuando se solicita un token.</span><span class="sxs-lookup"><span data-stu-id="77834-109">A string specifying an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="77834-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="77834-110">Child Elements</span></span>  

 <span data-ttu-id="77834-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="77834-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="77834-112">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="77834-112">Parent Elements</span></span>  
  
|<span data-ttu-id="77834-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="77834-113">Element</span></span>|<span data-ttu-id="77834-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="77834-114">Description</span></span>|  
|-------------|-----------------|  
|[\<tokenRequestParameters>](tokenrequestparameters.md)|<span data-ttu-id="77834-115">Una colección de parámetros de solicitud de token.</span><span class="sxs-lookup"><span data-stu-id="77834-115">A collection of token request parameters.</span></span> <span data-ttu-id="77834-116">Cada parámetro es un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="77834-116">Each parameter is an XML element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="77834-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="77834-117">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.TokenRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.TokenRequestParameters%2A>
- [<span data-ttu-id="77834-118">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="77834-118">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="77834-119">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="77834-119">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="77834-120">Capacidades de seguridad con enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="77834-120">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="77834-121">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="77834-121">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="77834-122">Enlaces</span><span class="sxs-lookup"><span data-stu-id="77834-122">Bindings</span></span>](../../../wcf/bindings.md)
