---
title: Elemento &lt;security&gt; de &lt;wsDualHttpBinding&gt;
ms.date: 03/30/2017
ms.assetid: 869c05e7-4ebe-467d-95ab-c8f8de4e6b9e
author: BrucePerlerMS
ms.openlocfilehash: 761eb9d111630d64d0fe4450c7a8950a8181366d
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2018
ms.locfileid: "48838293"
---
# <a name="ltsecuritygt-of-ltwsdualhttpbindinggt"></a><span data-ttu-id="c22cc-102">Elemento &lt;security&gt; de &lt;wsDualHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="c22cc-102">&lt;security&gt; of &lt;wsDualHttpBinding&gt;</span></span>
<span data-ttu-id="c22cc-103">Define las funciones de seguridad de la [ \<wsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="c22cc-103">Defines the security capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>  
  
 <span data-ttu-id="c22cc-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="c22cc-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="c22cc-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="c22cc-105">\<bindings></span></span>  
<span data-ttu-id="c22cc-106">\<wsDualHttpBinding></span><span class="sxs-lookup"><span data-stu-id="c22cc-106">\<wsDualHttpBinding></span></span>  
<span data-ttu-id="c22cc-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="c22cc-107">\<binding></span></span>  
<span data-ttu-id="c22cc-108">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="c22cc-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c22cc-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c22cc-109">Syntax</span></span>  
  
```xml  
<security mode="Message/None">  
   <message  
      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
      clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"  
      negotiateServiceCredential="Boolean"/>  
</security>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c22cc-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c22cc-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c22cc-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c22cc-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c22cc-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="c22cc-112">Attributes</span></span>  
  
|<span data-ttu-id="c22cc-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="c22cc-113">Attribute</span></span>|<span data-ttu-id="c22cc-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="c22cc-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c22cc-115">modo</span><span class="sxs-lookup"><span data-stu-id="c22cc-115">mode</span></span>|<span data-ttu-id="c22cc-116">-Opcional.</span><span class="sxs-lookup"><span data-stu-id="c22cc-116">-   Optional.</span></span> <span data-ttu-id="c22cc-117">Especifica el tipo de seguridad que se aplica.</span><span class="sxs-lookup"><span data-stu-id="c22cc-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="c22cc-118">El valor predeterminado es `Message`.</span><span class="sxs-lookup"><span data-stu-id="c22cc-118">The default value is `Message`.</span></span> <span data-ttu-id="c22cc-119">Este atributo es del tipo <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="c22cc-119">This attribute is of type <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="c22cc-120">Atributo de modo</span><span class="sxs-lookup"><span data-stu-id="c22cc-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="c22cc-121">Valor</span><span class="sxs-lookup"><span data-stu-id="c22cc-121">Value</span></span>|<span data-ttu-id="c22cc-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="c22cc-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c22cc-123">Ninguna</span><span class="sxs-lookup"><span data-stu-id="c22cc-123">None</span></span>|<span data-ttu-id="c22cc-124">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="c22cc-124">Security is disabled.</span></span>|  
|<span data-ttu-id="c22cc-125">Mensaje</span><span class="sxs-lookup"><span data-stu-id="c22cc-125">Message</span></span>|<span data-ttu-id="c22cc-126">La seguridad se proporciona mediante la seguridad del mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="c22cc-126">Security is provided using SOAP message security.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c22cc-127">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c22cc-127">Child Elements</span></span>  
  
|<span data-ttu-id="c22cc-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="c22cc-128">Element</span></span>|<span data-ttu-id="c22cc-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="c22cc-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c22cc-130">\<mensaje ></span><span class="sxs-lookup"><span data-stu-id="c22cc-130">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wsdualhttpbinding.md)|<span data-ttu-id="c22cc-131">Define la configuración de seguridad del nivel del mensaje.</span><span class="sxs-lookup"><span data-stu-id="c22cc-131">Defines the settings for the message-level security.</span></span> <span data-ttu-id="c22cc-132">Este elemento es del tipo <xref:System.ServiceModel.MessageSecurityOverHttp>.</span><span class="sxs-lookup"><span data-stu-id="c22cc-132">This element is of type <xref:System.ServiceModel.MessageSecurityOverHttp>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c22cc-133">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c22cc-133">Parent Elements</span></span>  
  
|<span data-ttu-id="c22cc-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="c22cc-134">Element</span></span>|<span data-ttu-id="c22cc-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="c22cc-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c22cc-136">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="c22cc-136">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="c22cc-137">Define todas las capacidades de enlace de la [ \<wsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="c22cc-137">Defines all binding capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c22cc-138">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c22cc-138">Remarks</span></span>  
 <span data-ttu-id="c22cc-139">Un enlace dual expone la dirección IP del cliente al servicio.</span><span class="sxs-lookup"><span data-stu-id="c22cc-139">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="c22cc-140">El cliente debería utilizar la seguridad para asegurarse de que sólo se conecta a servicios de confianza.</span><span class="sxs-lookup"><span data-stu-id="c22cc-140">The client should use security to ensure that it only connects to services it trusts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c22cc-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="c22cc-141">See Also</span></span>  
 <xref:System.ServiceModel.WSDualHttpSecurity>  
 <xref:System.ServiceModel.BasicHttpSecurity>  
 [<span data-ttu-id="c22cc-142">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="c22cc-142">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="c22cc-143">Enlaces</span><span class="sxs-lookup"><span data-stu-id="c22cc-143">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="c22cc-144">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="c22cc-144">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="c22cc-145">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="c22cc-145">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="c22cc-146">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="c22cc-146">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
