---
title: Elemento &lt;security&gt; de &lt;wsDualHttpBinding&gt;
ms.date: 03/30/2017
ms.assetid: 869c05e7-4ebe-467d-95ab-c8f8de4e6b9e
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 734b6d0625cfda79b600a0920ab39bda25ee2e8b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltsecuritygt-of-ltwsdualhttpbindinggt"></a><span data-ttu-id="b03d5-102">Elemento &lt;security&gt; de &lt;wsDualHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="b03d5-102">&lt;security&gt; of &lt;wsDualHttpBinding&gt;</span></span>
<span data-ttu-id="b03d5-103">Define las capacidades de seguridad de la [ \<wsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="b03d5-103">Defines the security capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>  
  
 <span data-ttu-id="b03d5-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="b03d5-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="b03d5-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="b03d5-105">\<bindings></span></span>  
<span data-ttu-id="b03d5-106">\<wsDualHttpBinding></span><span class="sxs-lookup"><span data-stu-id="b03d5-106">\<wsDualHttpBinding></span></span>  
<span data-ttu-id="b03d5-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="b03d5-107">\<binding></span></span>  
<span data-ttu-id="b03d5-108">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="b03d5-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b03d5-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b03d5-109">Syntax</span></span>  
  
```xml  
<security mode="Message/None">  
   <message  
      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
      clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"  
      negotiateServiceCredential="Boolean"/>  
</security>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b03d5-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b03d5-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b03d5-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b03d5-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b03d5-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="b03d5-112">Attributes</span></span>  
  
|<span data-ttu-id="b03d5-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="b03d5-113">Attribute</span></span>|<span data-ttu-id="b03d5-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="b03d5-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b03d5-115">modo</span><span class="sxs-lookup"><span data-stu-id="b03d5-115">mode</span></span>|<span data-ttu-id="b03d5-116">-Opcional.</span><span class="sxs-lookup"><span data-stu-id="b03d5-116">-   Optional.</span></span> <span data-ttu-id="b03d5-117">Especifica el tipo de seguridad que se aplica.</span><span class="sxs-lookup"><span data-stu-id="b03d5-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="b03d5-118">El valor predeterminado es `Message`.</span><span class="sxs-lookup"><span data-stu-id="b03d5-118">The default value is `Message`.</span></span> <span data-ttu-id="b03d5-119">Este atributo es del tipo <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="b03d5-119">This attribute is of type <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="b03d5-120">Atributo de modo</span><span class="sxs-lookup"><span data-stu-id="b03d5-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="b03d5-121">Valor</span><span class="sxs-lookup"><span data-stu-id="b03d5-121">Value</span></span>|<span data-ttu-id="b03d5-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="b03d5-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b03d5-123">Ninguna</span><span class="sxs-lookup"><span data-stu-id="b03d5-123">None</span></span>|<span data-ttu-id="b03d5-124">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="b03d5-124">Security is disabled.</span></span>|  
|<span data-ttu-id="b03d5-125">Mensaje</span><span class="sxs-lookup"><span data-stu-id="b03d5-125">Message</span></span>|<span data-ttu-id="b03d5-126">La seguridad se proporciona mediante la seguridad del mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="b03d5-126">Security is provided using SOAP message security.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b03d5-127">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b03d5-127">Child Elements</span></span>  
  
|<span data-ttu-id="b03d5-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="b03d5-128">Element</span></span>|<span data-ttu-id="b03d5-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="b03d5-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b03d5-130">\<mensaje ></span><span class="sxs-lookup"><span data-stu-id="b03d5-130">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wsdualhttpbinding.md)|<span data-ttu-id="b03d5-131">Define la configuración de seguridad del nivel del mensaje.</span><span class="sxs-lookup"><span data-stu-id="b03d5-131">Defines the settings for the message-level security.</span></span> <span data-ttu-id="b03d5-132">Este elemento es del tipo <xref:System.ServiceModel.MessageSecurityOverHttp>.</span><span class="sxs-lookup"><span data-stu-id="b03d5-132">This element is of type <xref:System.ServiceModel.MessageSecurityOverHttp>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b03d5-133">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b03d5-133">Parent Elements</span></span>  
  
|<span data-ttu-id="b03d5-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="b03d5-134">Element</span></span>|<span data-ttu-id="b03d5-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="b03d5-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b03d5-136">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="b03d5-136">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="b03d5-137">Define todas las funcionalidades de enlace de la [ \<wsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="b03d5-137">Defines all binding capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b03d5-138">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b03d5-138">Remarks</span></span>  
 <span data-ttu-id="b03d5-139">Un enlace dual expone la dirección IP del cliente al servicio.</span><span class="sxs-lookup"><span data-stu-id="b03d5-139">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="b03d5-140">El cliente debería utilizar la seguridad para asegurarse de que sólo se conecta a servicios de confianza.</span><span class="sxs-lookup"><span data-stu-id="b03d5-140">The client should use security to ensure that it only connects to services it trusts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b03d5-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="b03d5-141">See Also</span></span>  
 <xref:System.ServiceModel.WSDualHttpSecurity>  
 <xref:System.ServiceModel.BasicHttpSecurity>  
 [<span data-ttu-id="b03d5-142">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="b03d5-142">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="b03d5-143">Enlaces</span><span class="sxs-lookup"><span data-stu-id="b03d5-143">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="b03d5-144">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="b03d5-144">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="b03d5-145">Utilización de enlaces para configurar los clientes y servicios de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="b03d5-145">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="b03d5-146">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="b03d5-146">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
