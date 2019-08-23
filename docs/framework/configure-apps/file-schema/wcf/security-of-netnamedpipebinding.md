---
title: <security> de <netNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: bb3cb022-637e-49fd-92e8-6766038affa7
ms.openlocfilehash: 0996a98438dc344d96d640abced52ac99709adbf
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936672"
---
# <a name="security-of-netnamedpipebinding"></a><span data-ttu-id="5e483-102">\<> de seguridad \<de netNamedPipeBinding ></span><span class="sxs-lookup"><span data-stu-id="5e483-102">\<security> of \<netNamedPipeBinding></span></span>
<span data-ttu-id="5e483-103">Define la configuración de seguridad de un enlace.</span><span class="sxs-lookup"><span data-stu-id="5e483-103">Defines the security settings for a binding.</span></span>  
  
 <span data-ttu-id="5e483-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="5e483-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="5e483-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="5e483-105">\<bindings></span></span>  
<span data-ttu-id="5e483-106">\<netNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="5e483-106">\<netNamedPipeBinding></span></span>  
<span data-ttu-id="5e483-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="5e483-107">\<binding></span></span>  
<span data-ttu-id="5e483-108">\<> de seguridad</span><span class="sxs-lookup"><span data-stu-id="5e483-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e483-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5e483-109">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5e483-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5e483-110">Attributes and Elements</span></span>  
 <span data-ttu-id="5e483-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5e483-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5e483-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="5e483-112">Attributes</span></span>  
  
|<span data-ttu-id="5e483-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="5e483-113">Attribute</span></span>|<span data-ttu-id="5e483-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5e483-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5e483-115">modo</span><span class="sxs-lookup"><span data-stu-id="5e483-115">mode</span></span>|<span data-ttu-id="5e483-116">Especifica el tipo de seguridad que se aplica a este enlace.</span><span class="sxs-lookup"><span data-stu-id="5e483-116">Specifies the type of security that is applied to this binding.</span></span> <span data-ttu-id="5e483-117">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="5e483-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="5e483-118">Ninguna Esto deshabilita la seguridad.</span><span class="sxs-lookup"><span data-stu-id="5e483-118">-   None: This disables security.</span></span><br /><span data-ttu-id="5e483-119">Porta La seguridad se proporciona mediante la seguridad basada en transporte subyacente.</span><span class="sxs-lookup"><span data-stu-id="5e483-119">-   Transport: Security is provided using underlying transport based security.</span></span> <span data-ttu-id="5e483-120">Es posible controlar el nivel de protección con este modo.</span><span class="sxs-lookup"><span data-stu-id="5e483-120">It is possible to control the protection level with this mode.</span></span><br /><span data-ttu-id="5e483-121">-El valor predeterminado es Transport.</span><span class="sxs-lookup"><span data-stu-id="5e483-121">-   The default value is Transport.</span></span> <span data-ttu-id="5e483-122">Este atributo es del tipo <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="5e483-122">This attribute is of type <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5e483-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5e483-123">Child Elements</span></span>  
  
|<span data-ttu-id="5e483-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="5e483-124">Element</span></span>|<span data-ttu-id="5e483-125">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5e483-125">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5e483-126">transporte</span><span class="sxs-lookup"><span data-stu-id="5e483-126">transport</span></span>|<span data-ttu-id="5e483-127">Define la configuración de seguridad para el transporte.</span><span class="sxs-lookup"><span data-stu-id="5e483-127">Defines the security settings for the transport.</span></span> <span data-ttu-id="5e483-128">Este elemento es del tipo <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="5e483-128">This element is of type <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5e483-129">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5e483-129">Parent Elements</span></span>  
  
|<span data-ttu-id="5e483-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="5e483-130">Element</span></span>|<span data-ttu-id="5e483-131">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5e483-131">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5e483-132">enlace</span><span class="sxs-lookup"><span data-stu-id="5e483-132">binding</span></span>|<span data-ttu-id="5e483-133">Elemento de enlace del [ \<> netNamedPipeBinding](netnamedpipebinding.md).</span><span class="sxs-lookup"><span data-stu-id="5e483-133">The binding element of the [\<netNamedPipeBinding>](netnamedpipebinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5e483-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e483-134">See also</span></span>

- <xref:System.ServiceModel.NetNamedPipeSecurity>
- <xref:System.ServiceModel.NetNamedPipeBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement>
- [<span data-ttu-id="5e483-135">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="5e483-135">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="5e483-136">Selección de tipos de credenciales</span><span class="sxs-lookup"><span data-stu-id="5e483-136">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="5e483-137">Enlaces</span><span class="sxs-lookup"><span data-stu-id="5e483-137">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="5e483-138">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="5e483-138">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="5e483-139">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="5e483-139">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="5e483-140">\<binding></span><span class="sxs-lookup"><span data-stu-id="5e483-140">\<binding></span></span>](../../../misc/binding.md)
