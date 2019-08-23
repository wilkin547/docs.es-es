---
title: <security> de <wsDualHttpBinding>
ms.date: 03/30/2017
ms.assetid: 869c05e7-4ebe-467d-95ab-c8f8de4e6b9e
ms.openlocfilehash: bed7f4ce325e0d5e387e310ca15a3b72ac93f18e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936545"
---
# <a name="security-of-wsdualhttpbinding"></a><span data-ttu-id="60768-102">\<> de seguridad \<de wsDualHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="60768-102">\<security> of \<wsDualHttpBinding></span></span>
<span data-ttu-id="60768-103">Define las capacidades de seguridad de la [ \<> wsDualHttpBinding](wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="60768-103">Defines the security capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>  
  
 <span data-ttu-id="60768-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="60768-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="60768-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="60768-105">\<bindings></span></span>  
<span data-ttu-id="60768-106">\<wsDualHttpBinding></span><span class="sxs-lookup"><span data-stu-id="60768-106">\<wsDualHttpBinding></span></span>  
<span data-ttu-id="60768-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="60768-107">\<binding></span></span>  
<span data-ttu-id="60768-108">\<> de seguridad</span><span class="sxs-lookup"><span data-stu-id="60768-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60768-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="60768-109">Syntax</span></span>  
  
```xml  
<security mode="Message/None">
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"
           negotiateServiceCredential="Boolean"/>
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="60768-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="60768-110">Attributes and Elements</span></span>  
 <span data-ttu-id="60768-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="60768-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="60768-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="60768-112">Attributes</span></span>  
  
|<span data-ttu-id="60768-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="60768-113">Attribute</span></span>|<span data-ttu-id="60768-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="60768-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="60768-115">modo</span><span class="sxs-lookup"><span data-stu-id="60768-115">mode</span></span>|<span data-ttu-id="60768-116">Opta.</span><span class="sxs-lookup"><span data-stu-id="60768-116">-   Optional.</span></span> <span data-ttu-id="60768-117">Especifica el tipo de seguridad que se aplica.</span><span class="sxs-lookup"><span data-stu-id="60768-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="60768-118">El valor predeterminado es `Message`.</span><span class="sxs-lookup"><span data-stu-id="60768-118">The default value is `Message`.</span></span> <span data-ttu-id="60768-119">Este atributo es del tipo <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="60768-119">This attribute is of type <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="60768-120">Atributo de modo</span><span class="sxs-lookup"><span data-stu-id="60768-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="60768-121">Value</span><span class="sxs-lookup"><span data-stu-id="60768-121">Value</span></span>|<span data-ttu-id="60768-122">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="60768-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="60768-123">None</span><span class="sxs-lookup"><span data-stu-id="60768-123">None</span></span>|<span data-ttu-id="60768-124">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="60768-124">Security is disabled.</span></span>|  
|<span data-ttu-id="60768-125">Message</span><span class="sxs-lookup"><span data-stu-id="60768-125">Message</span></span>|<span data-ttu-id="60768-126">La seguridad se proporciona mediante la seguridad del mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="60768-126">Security is provided using SOAP message security.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="60768-127">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="60768-127">Child Elements</span></span>  
  
|<span data-ttu-id="60768-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="60768-128">Element</span></span>|<span data-ttu-id="60768-129">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="60768-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="60768-130">\<message></span><span class="sxs-lookup"><span data-stu-id="60768-130">\<message></span></span>](message-of-wsdualhttpbinding.md)|<span data-ttu-id="60768-131">Define la configuración de seguridad del nivel del mensaje.</span><span class="sxs-lookup"><span data-stu-id="60768-131">Defines the settings for the message-level security.</span></span> <span data-ttu-id="60768-132">Este elemento es del tipo <xref:System.ServiceModel.MessageSecurityOverHttp>.</span><span class="sxs-lookup"><span data-stu-id="60768-132">This element is of type <xref:System.ServiceModel.MessageSecurityOverHttp>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="60768-133">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="60768-133">Parent Elements</span></span>  
  
|<span data-ttu-id="60768-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="60768-134">Element</span></span>|<span data-ttu-id="60768-135">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="60768-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="60768-136">\<binding></span><span class="sxs-lookup"><span data-stu-id="60768-136">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="60768-137">Define todas las funciones de enlace del [ \<> wsDualHttpBinding](wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="60768-137">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="60768-138">Comentarios</span><span class="sxs-lookup"><span data-stu-id="60768-138">Remarks</span></span>  
 <span data-ttu-id="60768-139">Un enlace dual expone la dirección IP del cliente al servicio.</span><span class="sxs-lookup"><span data-stu-id="60768-139">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="60768-140">El cliente debería utilizar la seguridad para asegurarse de que sólo se conecta a servicios de confianza.</span><span class="sxs-lookup"><span data-stu-id="60768-140">The client should use security to ensure that it only connects to services it trusts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60768-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="60768-141">See also</span></span>

- <xref:System.ServiceModel.WSDualHttpSecurity>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [<span data-ttu-id="60768-142">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="60768-142">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="60768-143">Enlaces</span><span class="sxs-lookup"><span data-stu-id="60768-143">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="60768-144">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="60768-144">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="60768-145">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="60768-145">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="60768-146">\<binding></span><span class="sxs-lookup"><span data-stu-id="60768-146">\<binding></span></span>](../../../misc/binding.md)
