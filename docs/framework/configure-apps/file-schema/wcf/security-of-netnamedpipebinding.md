---
title: Elemento &lt;security&gt; de &lt;netNamedPipeBinding&gt;
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bb3cb022-637e-49fd-92e8-6766038affa7
caps.latest.revision: "11"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 3a018c502aead84eb6936001acb5bc24c59188f8
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="ltsecuritygt-of-ltnetnamedpipebindinggt"></a><span data-ttu-id="bb3c7-102">Elemento &lt;security&gt; de &lt;netNamedPipeBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="bb3c7-102">&lt;security&gt; of &lt;netNamedPipeBinding&gt;</span></span>
<span data-ttu-id="bb3c7-103">Define la configuración de seguridad de un enlace.</span><span class="sxs-lookup"><span data-stu-id="bb3c7-103">Defines the security settings for a binding.</span></span>  
  
 <span data-ttu-id="bb3c7-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="bb3c7-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="bb3c7-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="bb3c7-105">\<bindings></span></span>  
<span data-ttu-id="bb3c7-106">\<netNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="bb3c7-106">\<netNamedPipeBinding></span></span>  
<span data-ttu-id="bb3c7-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="bb3c7-107">\<binding></span></span>  
<span data-ttu-id="bb3c7-108">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="bb3c7-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb3c7-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bb3c7-109">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>  
      <binding>  
            <security mode="None/Transport">  
                        <transport protectionLevel="None/Sign/EncryptAndSign" />  
            </security>  
      </binding>  
</netNamedPipeBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bb3c7-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="bb3c7-110">Attributes and Elements</span></span>  
 <span data-ttu-id="bb3c7-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="bb3c7-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bb3c7-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="bb3c7-112">Attributes</span></span>  
  
|<span data-ttu-id="bb3c7-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="bb3c7-113">Attribute</span></span>|<span data-ttu-id="bb3c7-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="bb3c7-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bb3c7-115">modo</span><span class="sxs-lookup"><span data-stu-id="bb3c7-115">mode</span></span>|<span data-ttu-id="bb3c7-116">Especifica el tipo de seguridad que se aplica a este enlace.</span><span class="sxs-lookup"><span data-stu-id="bb3c7-116">Specifies the type of security that is applied to this binding.</span></span> <span data-ttu-id="bb3c7-117">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="bb3c7-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="bb3c7-118">-Ninguno: Esto deshabilita la seguridad.</span><span class="sxs-lookup"><span data-stu-id="bb3c7-118">-   None: This disables security.</span></span><br /><span data-ttu-id="bb3c7-119">-Transport: Seguridad se proporciona utilizando seguridad basada en transporte subyacente.</span><span class="sxs-lookup"><span data-stu-id="bb3c7-119">-   Transport: Security is provided using underlying transport based security.</span></span> <span data-ttu-id="bb3c7-120">Es posible controlar el nivel de protección con este modo.</span><span class="sxs-lookup"><span data-stu-id="bb3c7-120">It is possible to control the protection level with this mode.</span></span><br /><span data-ttu-id="bb3c7-121">-El valor predeterminado es transporte.</span><span class="sxs-lookup"><span data-stu-id="bb3c7-121">-   The default value is Transport.</span></span> <span data-ttu-id="bb3c7-122">Este atributo es del tipo <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="bb3c7-122">This attribute is of type <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bb3c7-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="bb3c7-123">Child Elements</span></span>  
  
|<span data-ttu-id="bb3c7-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="bb3c7-124">Element</span></span>|<span data-ttu-id="bb3c7-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="bb3c7-125">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bb3c7-126">transporte</span><span class="sxs-lookup"><span data-stu-id="bb3c7-126">transport</span></span>|<span data-ttu-id="bb3c7-127">Define la configuración de seguridad para el transporte.</span><span class="sxs-lookup"><span data-stu-id="bb3c7-127">Defines the security settings for the transport.</span></span> <span data-ttu-id="bb3c7-128">Este elemento es del tipo <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="bb3c7-128">This element is of type <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bb3c7-129">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="bb3c7-129">Parent Elements</span></span>  
  
|<span data-ttu-id="bb3c7-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="bb3c7-130">Element</span></span>|<span data-ttu-id="bb3c7-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="bb3c7-131">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bb3c7-132">enlace</span><span class="sxs-lookup"><span data-stu-id="bb3c7-132">binding</span></span>|<span data-ttu-id="bb3c7-133">El elemento de enlace de la [ \<netNamedPipeBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netnamedpipebinding.md).</span><span class="sxs-lookup"><span data-stu-id="bb3c7-133">The binding element of the [\<netNamedPipeBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netnamedpipebinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bb3c7-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="bb3c7-134">See Also</span></span>  
 <xref:System.ServiceModel.NetNamedPipeSecurity>  
 <xref:System.ServiceModel.NetNamedPipeBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement>  
 [<span data-ttu-id="bb3c7-135">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="bb3c7-135">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="bb3c7-136">Selección de tipos de credenciales</span><span class="sxs-lookup"><span data-stu-id="bb3c7-136">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="bb3c7-137">Enlaces</span><span class="sxs-lookup"><span data-stu-id="bb3c7-137">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="bb3c7-138">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="bb3c7-138">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="bb3c7-139">Utilización de enlaces para configurar los clientes y servicios de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="bb3c7-139">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="bb3c7-140">\<binding></span><span class="sxs-lookup"><span data-stu-id="bb3c7-140">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
