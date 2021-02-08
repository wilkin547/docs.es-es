---
description: 'Más información sobre: <issuerMetadata> de <issuedTokenParameters>'
title: <issuerMetadata> de <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: 1a85ca37-496d-4fa3-8d44-d6c9383d735c
ms.openlocfilehash: 6b0b5064254caf1c6bcf72c2e6d3449402853b98
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802247"
---
# <a name="issuermetadata-of-issuedtokenparameters"></a><span data-ttu-id="f8cec-103">\<issuerMetadata> de \<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="f8cec-103">\<issuerMetadata> of \<issuedTokenParameters></span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenParameters>**](issuedtokenparameters.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerMetadata>**  
  
## <a name="syntax"></a><span data-ttu-id="f8cec-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f8cec-104">Syntax</span></span>  
  
```xml  
<issuerMetaData address="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f8cec-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f8cec-105">Attributes and Elements</span></span>  

 <span data-ttu-id="f8cec-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f8cec-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f8cec-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="f8cec-107">Attributes</span></span>  
  
|<span data-ttu-id="f8cec-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="f8cec-108">Attribute</span></span>|<span data-ttu-id="f8cec-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="f8cec-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f8cec-110">address</span><span class="sxs-lookup"><span data-stu-id="f8cec-110">address</span></span>|<span data-ttu-id="f8cec-111">Necesario.</span><span class="sxs-lookup"><span data-stu-id="f8cec-111">Required.</span></span> <span data-ttu-id="f8cec-112">Cadena que especifica la dirección del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="f8cec-112">A string that specifies the address of the endpoint.</span></span> <span data-ttu-id="f8cec-113">La dirección debe ser un URI absoluto.</span><span class="sxs-lookup"><span data-stu-id="f8cec-113">The address must be an absolute URI.</span></span> <span data-ttu-id="f8cec-114">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="f8cec-114">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f8cec-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f8cec-115">Child Elements</span></span>  
  
|<span data-ttu-id="f8cec-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="f8cec-116">Element</span></span>|<span data-ttu-id="f8cec-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="f8cec-117">Description</span></span>|  
|-------------|-----------------|  
|[\<headers>](headers-element.md)|<span data-ttu-id="f8cec-118">Una colección de encabezados de dirección.</span><span class="sxs-lookup"><span data-stu-id="f8cec-118">A collection of address headers.</span></span>|  
|[\<identity>](identity.md)|<span data-ttu-id="f8cec-119">Una identidad que habilita la autenticación de un punto de conexión por otros puntos de conexión que intercambian mensajes con él.</span><span class="sxs-lookup"><span data-stu-id="f8cec-119">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f8cec-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f8cec-120">Parent Elements</span></span>  
  
|<span data-ttu-id="f8cec-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="f8cec-121">Element</span></span>|<span data-ttu-id="f8cec-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="f8cec-122">Description</span></span>|  
|-------------|-----------------|  
|[\<issuedTokenParameters>](issuedtokenparameters.md)|<span data-ttu-id="f8cec-123">Especifica los parámetros para un símbolo (token) de seguridad emitido en un escenario de seguridad aliado.</span><span class="sxs-lookup"><span data-stu-id="f8cec-123">Specifies the parameters for an security token issued in a Federated security scenario.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f8cec-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="f8cec-124">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="f8cec-125">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="f8cec-125">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="f8cec-126">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="f8cec-126">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="f8cec-127">Capacidades de seguridad con enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="f8cec-127">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="f8cec-128">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="f8cec-128">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="f8cec-129">Enlaces</span><span class="sxs-lookup"><span data-stu-id="f8cec-129">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="f8cec-130">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="f8cec-130">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="f8cec-131">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="f8cec-131">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="f8cec-132">Procedimiento para crear un enlace personalizado mediante SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="f8cec-132">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="f8cec-133">Seguridad de enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="f8cec-133">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
