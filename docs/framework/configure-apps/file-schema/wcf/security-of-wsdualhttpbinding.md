---
title: Elemento &lt;security&gt; de &lt;wsDualHttpBinding&gt;
ms.date: 03/30/2017
ms.assetid: 869c05e7-4ebe-467d-95ab-c8f8de4e6b9e
author: BrucePerlerMS
ms.openlocfilehash: c817ea6faf5229a8d372a06b866c75e0f40af3b3
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "48033108"
---
# <a name="ltsecuritygt-of-ltwsdualhttpbindinggt"></a><span data-ttu-id="a6d06-102">Elemento &lt;security&gt; de &lt;wsDualHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="a6d06-102">&lt;security&gt; of &lt;wsDualHttpBinding&gt;</span></span>
<span data-ttu-id="a6d06-103">Define las funciones de seguridad de la [ \<wsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="a6d06-103">Defines the security capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>  
  
 <span data-ttu-id="a6d06-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="a6d06-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="a6d06-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="a6d06-105">\<bindings></span></span>  
<span data-ttu-id="a6d06-106">\<wsDualHttpBinding></span><span class="sxs-lookup"><span data-stu-id="a6d06-106">\<wsDualHttpBinding></span></span>  
<span data-ttu-id="a6d06-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="a6d06-107">\<binding></span></span>  
<span data-ttu-id="a6d06-108">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="a6d06-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6d06-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a6d06-109">Syntax</span></span>  
  
```xml  
<security mode="Message/None">  
   <message  
      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
      clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"  
      negotiateServiceCredential="Boolean"/>  
</security>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a6d06-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a6d06-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a6d06-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a6d06-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a6d06-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="a6d06-112">Attributes</span></span>  
  
|<span data-ttu-id="a6d06-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="a6d06-113">Attribute</span></span>|<span data-ttu-id="a6d06-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="a6d06-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a6d06-115">modo</span><span class="sxs-lookup"><span data-stu-id="a6d06-115">mode</span></span>|<span data-ttu-id="a6d06-116">-Opcional.</span><span class="sxs-lookup"><span data-stu-id="a6d06-116">-   Optional.</span></span> <span data-ttu-id="a6d06-117">Especifica el tipo de seguridad que se aplica.</span><span class="sxs-lookup"><span data-stu-id="a6d06-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="a6d06-118">El valor predeterminado es `Message`.</span><span class="sxs-lookup"><span data-stu-id="a6d06-118">The default value is `Message`.</span></span> <span data-ttu-id="a6d06-119">Este atributo es del tipo <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="a6d06-119">This attribute is of type <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="a6d06-120">Atributo de modo</span><span class="sxs-lookup"><span data-stu-id="a6d06-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="a6d06-121">Valor</span><span class="sxs-lookup"><span data-stu-id="a6d06-121">Value</span></span>|<span data-ttu-id="a6d06-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="a6d06-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a6d06-123">Ninguna</span><span class="sxs-lookup"><span data-stu-id="a6d06-123">None</span></span>|<span data-ttu-id="a6d06-124">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="a6d06-124">Security is disabled.</span></span>|  
|<span data-ttu-id="a6d06-125">Mensaje</span><span class="sxs-lookup"><span data-stu-id="a6d06-125">Message</span></span>|<span data-ttu-id="a6d06-126">La seguridad se proporciona mediante la seguridad del mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="a6d06-126">Security is provided using SOAP message security.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a6d06-127">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a6d06-127">Child Elements</span></span>  
  
|<span data-ttu-id="a6d06-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="a6d06-128">Element</span></span>|<span data-ttu-id="a6d06-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="a6d06-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a6d06-130">\<mensaje ></span><span class="sxs-lookup"><span data-stu-id="a6d06-130">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wsdualhttpbinding.md)|<span data-ttu-id="a6d06-131">Define la configuración de seguridad del nivel del mensaje.</span><span class="sxs-lookup"><span data-stu-id="a6d06-131">Defines the settings for the message-level security.</span></span> <span data-ttu-id="a6d06-132">Este elemento es del tipo <xref:System.ServiceModel.MessageSecurityOverHttp>.</span><span class="sxs-lookup"><span data-stu-id="a6d06-132">This element is of type <xref:System.ServiceModel.MessageSecurityOverHttp>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a6d06-133">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a6d06-133">Parent Elements</span></span>  
  
|<span data-ttu-id="a6d06-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="a6d06-134">Element</span></span>|<span data-ttu-id="a6d06-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="a6d06-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a6d06-136">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="a6d06-136">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="a6d06-137">Define todas las capacidades de enlace de la [ \<wsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="a6d06-137">Defines all binding capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a6d06-138">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a6d06-138">Remarks</span></span>  
 <span data-ttu-id="a6d06-139">Un enlace dual expone la dirección IP del cliente al servicio.</span><span class="sxs-lookup"><span data-stu-id="a6d06-139">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="a6d06-140">El cliente debería utilizar la seguridad para asegurarse de que sólo se conecta a servicios de confianza.</span><span class="sxs-lookup"><span data-stu-id="a6d06-140">The client should use security to ensure that it only connects to services it trusts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6d06-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="a6d06-141">See Also</span></span>  
 <xref:System.ServiceModel.WSDualHttpSecurity>  
 <xref:System.ServiceModel.BasicHttpSecurity>  
 [<span data-ttu-id="a6d06-142">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="a6d06-142">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="a6d06-143">Enlaces</span><span class="sxs-lookup"><span data-stu-id="a6d06-143">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="a6d06-144">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="a6d06-144">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="a6d06-145">Utilización de enlaces para configurar los clientes y servicios de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="a6d06-145">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="a6d06-146">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="a6d06-146">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
