---
title: Elemento &lt;security&gt; de &lt;netNamedPipeBinding&gt;
ms.date: 03/30/2017
ms.assetid: bb3cb022-637e-49fd-92e8-6766038affa7
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 74bf0d14b0acfd8a5382575d2ee1e51174b6b6b8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32752798"
---
# <a name="ltsecuritygt-of-ltnetnamedpipebindinggt"></a><span data-ttu-id="e3a22-102">Elemento &lt;security&gt; de &lt;netNamedPipeBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="e3a22-102">&lt;security&gt; of &lt;netNamedPipeBinding&gt;</span></span>
<span data-ttu-id="e3a22-103">Define la configuración de seguridad de un enlace.</span><span class="sxs-lookup"><span data-stu-id="e3a22-103">Defines the security settings for a binding.</span></span>  
  
 <span data-ttu-id="e3a22-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e3a22-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e3a22-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="e3a22-105">\<bindings></span></span>  
<span data-ttu-id="e3a22-106">\<netNamedPipeBinding ></span><span class="sxs-lookup"><span data-stu-id="e3a22-106">\<netNamedPipeBinding></span></span>  
<span data-ttu-id="e3a22-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="e3a22-107">\<binding></span></span>  
<span data-ttu-id="e3a22-108">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="e3a22-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3a22-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e3a22-109">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>  
      <binding>  
            <security mode="None/Transport">  
                        <transport protectionLevel="None/Sign/EncryptAndSign" />  
            </security>  
      </binding>  
</netNamedPipeBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e3a22-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e3a22-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e3a22-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e3a22-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e3a22-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="e3a22-112">Attributes</span></span>  
  
|<span data-ttu-id="e3a22-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="e3a22-113">Attribute</span></span>|<span data-ttu-id="e3a22-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="e3a22-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e3a22-115">modo</span><span class="sxs-lookup"><span data-stu-id="e3a22-115">mode</span></span>|<span data-ttu-id="e3a22-116">Especifica el tipo de seguridad que se aplica a este enlace.</span><span class="sxs-lookup"><span data-stu-id="e3a22-116">Specifies the type of security that is applied to this binding.</span></span> <span data-ttu-id="e3a22-117">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="e3a22-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="e3a22-118">-Ninguno: Esto deshabilita la seguridad.</span><span class="sxs-lookup"><span data-stu-id="e3a22-118">-   None: This disables security.</span></span><br /><span data-ttu-id="e3a22-119">-Transport: Seguridad se proporciona utilizando seguridad basada en transporte subyacente.</span><span class="sxs-lookup"><span data-stu-id="e3a22-119">-   Transport: Security is provided using underlying transport based security.</span></span> <span data-ttu-id="e3a22-120">Es posible controlar el nivel de protección con este modo.</span><span class="sxs-lookup"><span data-stu-id="e3a22-120">It is possible to control the protection level with this mode.</span></span><br /><span data-ttu-id="e3a22-121">-El valor predeterminado es transporte.</span><span class="sxs-lookup"><span data-stu-id="e3a22-121">-   The default value is Transport.</span></span> <span data-ttu-id="e3a22-122">Este atributo es del tipo <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="e3a22-122">This attribute is of type <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e3a22-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e3a22-123">Child Elements</span></span>  
  
|<span data-ttu-id="e3a22-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="e3a22-124">Element</span></span>|<span data-ttu-id="e3a22-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="e3a22-125">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e3a22-126">transporte</span><span class="sxs-lookup"><span data-stu-id="e3a22-126">transport</span></span>|<span data-ttu-id="e3a22-127">Define la configuración de seguridad para el transporte.</span><span class="sxs-lookup"><span data-stu-id="e3a22-127">Defines the security settings for the transport.</span></span> <span data-ttu-id="e3a22-128">Este elemento es del tipo <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="e3a22-128">This element is of type <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e3a22-129">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e3a22-129">Parent Elements</span></span>  
  
|<span data-ttu-id="e3a22-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="e3a22-130">Element</span></span>|<span data-ttu-id="e3a22-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="e3a22-131">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e3a22-132">enlace</span><span class="sxs-lookup"><span data-stu-id="e3a22-132">binding</span></span>|<span data-ttu-id="e3a22-133">El elemento de enlace de la [ \<netNamedPipeBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netnamedpipebinding.md).</span><span class="sxs-lookup"><span data-stu-id="e3a22-133">The binding element of the [\<netNamedPipeBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netnamedpipebinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e3a22-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="e3a22-134">See Also</span></span>  
 <xref:System.ServiceModel.NetNamedPipeSecurity>  
 <xref:System.ServiceModel.NetNamedPipeBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement>  
 [<span data-ttu-id="e3a22-135">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="e3a22-135">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="e3a22-136">Selección de tipos de credenciales</span><span class="sxs-lookup"><span data-stu-id="e3a22-136">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="e3a22-137">Enlaces</span><span class="sxs-lookup"><span data-stu-id="e3a22-137">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="e3a22-138">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="e3a22-138">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="e3a22-139">Utilización de enlaces para configurar los clientes y servicios de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="e3a22-139">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="e3a22-140">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="e3a22-140">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
