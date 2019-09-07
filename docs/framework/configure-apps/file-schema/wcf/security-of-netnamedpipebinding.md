---
title: <security> de <netNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: bb3cb022-637e-49fd-92e8-6766038affa7
ms.openlocfilehash: cd3ff5d3983283f9b4783912b4b9525c5000df61
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399829"
---
# <a name="security-of-netnamedpipebinding"></a><span data-ttu-id="a3171-102">\<> de seguridad \<de netNamedPipeBinding ></span><span class="sxs-lookup"><span data-stu-id="a3171-102">\<security> of \<netNamedPipeBinding></span></span>
<span data-ttu-id="a3171-103">Define la configuración de seguridad de un enlace.</span><span class="sxs-lookup"><span data-stu-id="a3171-103">Defines the security settings for a binding.</span></span>  
  
<span data-ttu-id="a3171-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a3171-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a3171-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="a3171-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="a3171-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de enlaces**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="a3171-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="a3171-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> netNamedPipeBinding**](netnamedpipebinding.md)</span><span class="sxs-lookup"><span data-stu-id="a3171-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netNamedPipeBinding>**](netnamedpipebinding.md)</span></span>\
<span data-ttu-id="a3171-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de enlace**</span><span class="sxs-lookup"><span data-stu-id="a3171-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="a3171-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de seguridad**</span><span class="sxs-lookup"><span data-stu-id="a3171-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3171-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a3171-110">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a3171-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a3171-111">Attributes and Elements</span></span>  
 <span data-ttu-id="a3171-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a3171-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a3171-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="a3171-113">Attributes</span></span>  
  
|<span data-ttu-id="a3171-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="a3171-114">Attribute</span></span>|<span data-ttu-id="a3171-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="a3171-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a3171-116">modo</span><span class="sxs-lookup"><span data-stu-id="a3171-116">mode</span></span>|<span data-ttu-id="a3171-117">Especifica el tipo de seguridad que se aplica a este enlace.</span><span class="sxs-lookup"><span data-stu-id="a3171-117">Specifies the type of security that is applied to this binding.</span></span> <span data-ttu-id="a3171-118">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="a3171-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="a3171-119">Ninguna Esto deshabilita la seguridad.</span><span class="sxs-lookup"><span data-stu-id="a3171-119">-   None: This disables security.</span></span><br /><span data-ttu-id="a3171-120">Porta La seguridad se proporciona mediante la seguridad basada en transporte subyacente.</span><span class="sxs-lookup"><span data-stu-id="a3171-120">-   Transport: Security is provided using underlying transport based security.</span></span> <span data-ttu-id="a3171-121">Es posible controlar el nivel de protección con este modo.</span><span class="sxs-lookup"><span data-stu-id="a3171-121">It is possible to control the protection level with this mode.</span></span><br /><span data-ttu-id="a3171-122">-El valor predeterminado es Transport.</span><span class="sxs-lookup"><span data-stu-id="a3171-122">-   The default value is Transport.</span></span> <span data-ttu-id="a3171-123">Este atributo es del tipo <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="a3171-123">This attribute is of type <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a3171-124">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a3171-124">Child Elements</span></span>  
  
|<span data-ttu-id="a3171-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="a3171-125">Element</span></span>|<span data-ttu-id="a3171-126">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="a3171-126">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a3171-127">transporte</span><span class="sxs-lookup"><span data-stu-id="a3171-127">transport</span></span>|<span data-ttu-id="a3171-128">Define la configuración de seguridad para el transporte.</span><span class="sxs-lookup"><span data-stu-id="a3171-128">Defines the security settings for the transport.</span></span> <span data-ttu-id="a3171-129">Este elemento es del tipo <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="a3171-129">This element is of type <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a3171-130">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a3171-130">Parent Elements</span></span>  
  
|<span data-ttu-id="a3171-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="a3171-131">Element</span></span>|<span data-ttu-id="a3171-132">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="a3171-132">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a3171-133">enlace</span><span class="sxs-lookup"><span data-stu-id="a3171-133">binding</span></span>|<span data-ttu-id="a3171-134">Elemento de enlace del [ \<> netNamedPipeBinding](netnamedpipebinding.md).</span><span class="sxs-lookup"><span data-stu-id="a3171-134">The binding element of the [\<netNamedPipeBinding>](netnamedpipebinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a3171-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="a3171-135">See also</span></span>

- <xref:System.ServiceModel.NetNamedPipeSecurity>
- <xref:System.ServiceModel.NetNamedPipeBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement>
- [<span data-ttu-id="a3171-136">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="a3171-136">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="a3171-137">Selección de tipos de credenciales</span><span class="sxs-lookup"><span data-stu-id="a3171-137">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="a3171-138">Enlaces</span><span class="sxs-lookup"><span data-stu-id="a3171-138">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="a3171-139">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="a3171-139">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="a3171-140">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="a3171-140">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="a3171-141">\<binding></span><span class="sxs-lookup"><span data-stu-id="a3171-141">\<binding></span></span>](../../../misc/binding.md)
