---
title: Elemento &lt;security&gt; de &lt;netNamedPipeBinding&gt;
ms.date: 03/30/2017
ms.assetid: bb3cb022-637e-49fd-92e8-6766038affa7
ms.openlocfilehash: 0079cb9e62abed42a36b67fed935f883473ebbb8
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54147829"
---
# <a name="ltsecuritygt-of-ltnetnamedpipebindinggt"></a><span data-ttu-id="78a81-102">Elemento &lt;security&gt; de &lt;netNamedPipeBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="78a81-102">&lt;security&gt; of &lt;netNamedPipeBinding&gt;</span></span>
<span data-ttu-id="78a81-103">Define la configuración de seguridad de un enlace.</span><span class="sxs-lookup"><span data-stu-id="78a81-103">Defines the security settings for a binding.</span></span>  
  
 <span data-ttu-id="78a81-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="78a81-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="78a81-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="78a81-105">\<bindings></span></span>  
<span data-ttu-id="78a81-106">\<netNamedPipeBinding ></span><span class="sxs-lookup"><span data-stu-id="78a81-106">\<netNamedPipeBinding></span></span>  
<span data-ttu-id="78a81-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="78a81-107">\<binding></span></span>  
<span data-ttu-id="78a81-108">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="78a81-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78a81-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="78a81-109">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="78a81-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="78a81-110">Attributes and Elements</span></span>  
 <span data-ttu-id="78a81-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="78a81-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="78a81-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="78a81-112">Attributes</span></span>  
  
|<span data-ttu-id="78a81-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="78a81-113">Attribute</span></span>|<span data-ttu-id="78a81-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="78a81-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="78a81-115">modo</span><span class="sxs-lookup"><span data-stu-id="78a81-115">mode</span></span>|<span data-ttu-id="78a81-116">Especifica el tipo de seguridad que se aplica a este enlace.</span><span class="sxs-lookup"><span data-stu-id="78a81-116">Specifies the type of security that is applied to this binding.</span></span> <span data-ttu-id="78a81-117">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="78a81-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="78a81-118">-None: Esto deshabilita la seguridad.</span><span class="sxs-lookup"><span data-stu-id="78a81-118">-   None: This disables security.</span></span><br /><span data-ttu-id="78a81-119">-Transporte: Se proporciona seguridad mediante seguridad basada en transporte subyacente.</span><span class="sxs-lookup"><span data-stu-id="78a81-119">-   Transport: Security is provided using underlying transport based security.</span></span> <span data-ttu-id="78a81-120">Es posible controlar el nivel de protección con este modo.</span><span class="sxs-lookup"><span data-stu-id="78a81-120">It is possible to control the protection level with this mode.</span></span><br /><span data-ttu-id="78a81-121">-El valor predeterminado es transporte.</span><span class="sxs-lookup"><span data-stu-id="78a81-121">-   The default value is Transport.</span></span> <span data-ttu-id="78a81-122">Este atributo es del tipo <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="78a81-122">This attribute is of type <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="78a81-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="78a81-123">Child Elements</span></span>  
  
|<span data-ttu-id="78a81-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="78a81-124">Element</span></span>|<span data-ttu-id="78a81-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="78a81-125">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="78a81-126">transporte</span><span class="sxs-lookup"><span data-stu-id="78a81-126">transport</span></span>|<span data-ttu-id="78a81-127">Define la configuración de seguridad para el transporte.</span><span class="sxs-lookup"><span data-stu-id="78a81-127">Defines the security settings for the transport.</span></span> <span data-ttu-id="78a81-128">Este elemento es del tipo <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="78a81-128">This element is of type <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="78a81-129">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="78a81-129">Parent Elements</span></span>  
  
|<span data-ttu-id="78a81-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="78a81-130">Element</span></span>|<span data-ttu-id="78a81-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="78a81-131">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="78a81-132">enlace</span><span class="sxs-lookup"><span data-stu-id="78a81-132">binding</span></span>|<span data-ttu-id="78a81-133">El elemento de enlace de la [ \<netNamedPipeBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netnamedpipebinding.md).</span><span class="sxs-lookup"><span data-stu-id="78a81-133">The binding element of the [\<netNamedPipeBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netnamedpipebinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="78a81-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="78a81-134">See Also</span></span>  
 <xref:System.ServiceModel.NetNamedPipeSecurity>  
 <xref:System.ServiceModel.NetNamedPipeBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement>  
 [<span data-ttu-id="78a81-135">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="78a81-135">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="78a81-136">Selección de tipos de credenciales</span><span class="sxs-lookup"><span data-stu-id="78a81-136">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="78a81-137">Enlaces</span><span class="sxs-lookup"><span data-stu-id="78a81-137">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="78a81-138">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="78a81-138">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="78a81-139">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="78a81-139">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="78a81-140">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="78a81-140">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
