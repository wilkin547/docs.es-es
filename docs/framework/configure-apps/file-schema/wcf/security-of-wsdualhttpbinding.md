---
title: <security> de <wsDualHttpBinding>
ms.date: 03/30/2017
ms.assetid: 869c05e7-4ebe-467d-95ab-c8f8de4e6b9e
ms.openlocfilehash: 4969c041678bbf3490975bc0ec53507b6cf762bb
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738610"
---
# <a name="security-of-wsdualhttpbinding"></a><span data-ttu-id="0e90f-102">\<security> de \<wsDualHttpBinding></span><span class="sxs-lookup"><span data-stu-id="0e90f-102">\<security> of \<wsDualHttpBinding></span></span>
<span data-ttu-id="0e90f-103">Define las capacidades de seguridad de [\<wsDualHttpBinding>](wsdualhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="0e90f-103">Defines the security capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsDualHttpBinding>**](wsdualhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="0e90f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0e90f-104">Syntax</span></span>  
  
```xml  
<security mode="Message/None">
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"
           negotiateServiceCredential="Boolean"/>
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0e90f-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0e90f-105">Attributes and Elements</span></span>  
 <span data-ttu-id="0e90f-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0e90f-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0e90f-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="0e90f-107">Attributes</span></span>  
  
|<span data-ttu-id="0e90f-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="0e90f-108">Attribute</span></span>|<span data-ttu-id="0e90f-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="0e90f-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0e90f-110">mode</span><span class="sxs-lookup"><span data-stu-id="0e90f-110">mode</span></span>|<span data-ttu-id="0e90f-111">Opta.</span><span class="sxs-lookup"><span data-stu-id="0e90f-111">-   Optional.</span></span> <span data-ttu-id="0e90f-112">Especifica el tipo de seguridad que se aplica.</span><span class="sxs-lookup"><span data-stu-id="0e90f-112">Specifies the type of security that is applied.</span></span> <span data-ttu-id="0e90f-113">El valor predeterminado es `Message`.</span><span class="sxs-lookup"><span data-stu-id="0e90f-113">The default value is `Message`.</span></span> <span data-ttu-id="0e90f-114">Este atributo es del tipo <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="0e90f-114">This attribute is of type <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="0e90f-115">Atributo mode</span><span class="sxs-lookup"><span data-stu-id="0e90f-115">Mode Attribute</span></span>  
  
|<span data-ttu-id="0e90f-116">Value</span><span class="sxs-lookup"><span data-stu-id="0e90f-116">Value</span></span>|<span data-ttu-id="0e90f-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="0e90f-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0e90f-118">None</span><span class="sxs-lookup"><span data-stu-id="0e90f-118">None</span></span>|<span data-ttu-id="0e90f-119">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="0e90f-119">Security is disabled.</span></span>|  
|<span data-ttu-id="0e90f-120">Message</span><span class="sxs-lookup"><span data-stu-id="0e90f-120">Message</span></span>|<span data-ttu-id="0e90f-121">La seguridad se proporciona mediante la seguridad del mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="0e90f-121">Security is provided using SOAP message security.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0e90f-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0e90f-122">Child Elements</span></span>  
  
|<span data-ttu-id="0e90f-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="0e90f-123">Element</span></span>|<span data-ttu-id="0e90f-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="0e90f-124">Description</span></span>|  
|-------------|-----------------|  
|[\<message>](message-of-wsdualhttpbinding.md)|<span data-ttu-id="0e90f-125">Define la configuración de seguridad del nivel del mensaje.</span><span class="sxs-lookup"><span data-stu-id="0e90f-125">Defines the settings for the message-level security.</span></span> <span data-ttu-id="0e90f-126">Este elemento es del tipo <xref:System.ServiceModel.MessageSecurityOverHttp>.</span><span class="sxs-lookup"><span data-stu-id="0e90f-126">This element is of type <xref:System.ServiceModel.MessageSecurityOverHttp>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0e90f-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0e90f-127">Parent Elements</span></span>  
  
|<span data-ttu-id="0e90f-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="0e90f-128">Element</span></span>|<span data-ttu-id="0e90f-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="0e90f-129">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="0e90f-130">Define todas las funciones de enlace de [\<wsDualHttpBinding>](wsdualhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="0e90f-130">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0e90f-131">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0e90f-131">Remarks</span></span>  
 <span data-ttu-id="0e90f-132">Un enlace dual expone la dirección IP del cliente al servicio.</span><span class="sxs-lookup"><span data-stu-id="0e90f-132">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="0e90f-133">El cliente debería utilizar la seguridad para asegurarse de que sólo se conecta a servicios de confianza.</span><span class="sxs-lookup"><span data-stu-id="0e90f-133">The client should use security to ensure that it only connects to services it trusts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e90f-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0e90f-134">See also</span></span>

- <xref:System.ServiceModel.WSDualHttpSecurity>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [<span data-ttu-id="0e90f-135">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="0e90f-135">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="0e90f-136">Enlaces</span><span class="sxs-lookup"><span data-stu-id="0e90f-136">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="0e90f-137">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="0e90f-137">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="0e90f-138">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="0e90f-138">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
