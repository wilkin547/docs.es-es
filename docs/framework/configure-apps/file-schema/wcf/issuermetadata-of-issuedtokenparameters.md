---
title: <issuerMetadata> de <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: 1a85ca37-496d-4fa3-8d44-d6c9383d735c
ms.openlocfilehash: fcdd66ecd162dff5be86a1d4ab1b196f50dbd445
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400342"
---
# <a name="issuermetadata-of-issuedtokenparameters"></a><span data-ttu-id="ca283-102">\<issuerMetadata> de \<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="ca283-102">\<issuerMetadata> of \<issuedTokenParameters></span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenParameters>**](issuedtokenparameters.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerMetadata>**  
  
## <a name="syntax"></a><span data-ttu-id="ca283-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ca283-103">Syntax</span></span>  
  
```xml  
<issuerMetaData address="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ca283-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ca283-104">Attributes and Elements</span></span>  
 <span data-ttu-id="ca283-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ca283-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ca283-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="ca283-106">Attributes</span></span>  
  
|<span data-ttu-id="ca283-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="ca283-107">Attribute</span></span>|<span data-ttu-id="ca283-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="ca283-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ca283-109">address</span><span class="sxs-lookup"><span data-stu-id="ca283-109">address</span></span>|<span data-ttu-id="ca283-110">Necesario.</span><span class="sxs-lookup"><span data-stu-id="ca283-110">Required.</span></span> <span data-ttu-id="ca283-111">Cadena que especifica la dirección del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="ca283-111">A string that specifies the address of the endpoint.</span></span> <span data-ttu-id="ca283-112">La dirección debe ser un URI absoluto.</span><span class="sxs-lookup"><span data-stu-id="ca283-112">The address must be an absolute URI.</span></span> <span data-ttu-id="ca283-113">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="ca283-113">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ca283-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ca283-114">Child Elements</span></span>  
  
|<span data-ttu-id="ca283-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="ca283-115">Element</span></span>|<span data-ttu-id="ca283-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="ca283-116">Description</span></span>|  
|-------------|-----------------|  
|[\<headers>](headers-element.md)|<span data-ttu-id="ca283-117">Una colección de encabezados de dirección.</span><span class="sxs-lookup"><span data-stu-id="ca283-117">A collection of address headers.</span></span>|  
|[\<identity>](identity.md)|<span data-ttu-id="ca283-118">Una identidad que habilita la autenticación de un punto de conexión por otros puntos de conexión que intercambian mensajes con él.</span><span class="sxs-lookup"><span data-stu-id="ca283-118">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ca283-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ca283-119">Parent Elements</span></span>  
  
|<span data-ttu-id="ca283-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="ca283-120">Element</span></span>|<span data-ttu-id="ca283-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="ca283-121">Description</span></span>|  
|-------------|-----------------|  
|[\<issuedTokenParameters>](issuedtokenparameters.md)|<span data-ttu-id="ca283-122">Especifica los parámetros para un símbolo (token) de seguridad emitido en un escenario de seguridad aliado.</span><span class="sxs-lookup"><span data-stu-id="ca283-122">Specifies the parameters for an security token issued in a Federated security scenario.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ca283-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ca283-123">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="ca283-124">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="ca283-124">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="ca283-125">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="ca283-125">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="ca283-126">Capacidades de seguridad con enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="ca283-126">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="ca283-127">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="ca283-127">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="ca283-128">Enlaces</span><span class="sxs-lookup"><span data-stu-id="ca283-128">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="ca283-129">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="ca283-129">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="ca283-130">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="ca283-130">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="ca283-131">Procedimiento para crear un enlace personalizado mediante SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="ca283-131">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="ca283-132">Seguridad de enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="ca283-132">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
