---
title: <security> de <wsDualHttpBinding>
ms.date: 03/30/2017
ms.assetid: 869c05e7-4ebe-467d-95ab-c8f8de4e6b9e
ms.openlocfilehash: b6a1c952b1ae65c8fb6f17237b5c15f3a8d4844a
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399749"
---
# <a name="security-of-wsdualhttpbinding"></a><span data-ttu-id="ac314-102">\<> de seguridad \<de wsDualHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="ac314-102">\<security> of \<wsDualHttpBinding></span></span>
<span data-ttu-id="ac314-103">Define las capacidades de seguridad de la [ \<> wsDualHttpBinding](wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="ac314-103">Defines the security capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>  
  
<span data-ttu-id="ac314-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ac314-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ac314-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="ac314-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="ac314-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de enlaces**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="ac314-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="ac314-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> wsDualHttpBinding**](wsdualhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="ac314-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsDualHttpBinding>**](wsdualhttpbinding.md)</span></span>\
<span data-ttu-id="ac314-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de enlace**</span><span class="sxs-lookup"><span data-stu-id="ac314-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="ac314-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de seguridad**</span><span class="sxs-lookup"><span data-stu-id="ac314-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac314-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ac314-110">Syntax</span></span>  
  
```xml  
<security mode="Message/None">
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"
           negotiateServiceCredential="Boolean"/>
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ac314-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ac314-111">Attributes and Elements</span></span>  
 <span data-ttu-id="ac314-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ac314-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ac314-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="ac314-113">Attributes</span></span>  
  
|<span data-ttu-id="ac314-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="ac314-114">Attribute</span></span>|<span data-ttu-id="ac314-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="ac314-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ac314-116">modo</span><span class="sxs-lookup"><span data-stu-id="ac314-116">mode</span></span>|<span data-ttu-id="ac314-117">Opta.</span><span class="sxs-lookup"><span data-stu-id="ac314-117">-   Optional.</span></span> <span data-ttu-id="ac314-118">Especifica el tipo de seguridad que se aplica.</span><span class="sxs-lookup"><span data-stu-id="ac314-118">Specifies the type of security that is applied.</span></span> <span data-ttu-id="ac314-119">El valor predeterminado es `Message`.</span><span class="sxs-lookup"><span data-stu-id="ac314-119">The default value is `Message`.</span></span> <span data-ttu-id="ac314-120">Este atributo es del tipo <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="ac314-120">This attribute is of type <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="ac314-121">Atributo de modo</span><span class="sxs-lookup"><span data-stu-id="ac314-121">Mode Attribute</span></span>  
  
|<span data-ttu-id="ac314-122">Valor</span><span class="sxs-lookup"><span data-stu-id="ac314-122">Value</span></span>|<span data-ttu-id="ac314-123">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="ac314-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ac314-124">None</span><span class="sxs-lookup"><span data-stu-id="ac314-124">None</span></span>|<span data-ttu-id="ac314-125">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="ac314-125">Security is disabled.</span></span>|  
|<span data-ttu-id="ac314-126">Message</span><span class="sxs-lookup"><span data-stu-id="ac314-126">Message</span></span>|<span data-ttu-id="ac314-127">La seguridad se proporciona mediante la seguridad del mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="ac314-127">Security is provided using SOAP message security.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ac314-128">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ac314-128">Child Elements</span></span>  
  
|<span data-ttu-id="ac314-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="ac314-129">Element</span></span>|<span data-ttu-id="ac314-130">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="ac314-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ac314-131">\<message></span><span class="sxs-lookup"><span data-stu-id="ac314-131">\<message></span></span>](message-of-wsdualhttpbinding.md)|<span data-ttu-id="ac314-132">Define la configuración de seguridad del nivel del mensaje.</span><span class="sxs-lookup"><span data-stu-id="ac314-132">Defines the settings for the message-level security.</span></span> <span data-ttu-id="ac314-133">Este elemento es del tipo <xref:System.ServiceModel.MessageSecurityOverHttp>.</span><span class="sxs-lookup"><span data-stu-id="ac314-133">This element is of type <xref:System.ServiceModel.MessageSecurityOverHttp>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ac314-134">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ac314-134">Parent Elements</span></span>  
  
|<span data-ttu-id="ac314-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="ac314-135">Element</span></span>|<span data-ttu-id="ac314-136">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="ac314-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ac314-137">\<binding></span><span class="sxs-lookup"><span data-stu-id="ac314-137">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="ac314-138">Define todas las funciones de enlace del [ \<> wsDualHttpBinding](wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="ac314-138">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ac314-139">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ac314-139">Remarks</span></span>  
 <span data-ttu-id="ac314-140">Un enlace dual expone la dirección IP del cliente al servicio.</span><span class="sxs-lookup"><span data-stu-id="ac314-140">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="ac314-141">El cliente debería utilizar la seguridad para asegurarse de que sólo se conecta a servicios de confianza.</span><span class="sxs-lookup"><span data-stu-id="ac314-141">The client should use security to ensure that it only connects to services it trusts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac314-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="ac314-142">See also</span></span>

- <xref:System.ServiceModel.WSDualHttpSecurity>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [<span data-ttu-id="ac314-143">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="ac314-143">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="ac314-144">Enlaces</span><span class="sxs-lookup"><span data-stu-id="ac314-144">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="ac314-145">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="ac314-145">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="ac314-146">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="ac314-146">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="ac314-147">\<binding></span><span class="sxs-lookup"><span data-stu-id="ac314-147">\<binding></span></span>](../../../misc/binding.md)
