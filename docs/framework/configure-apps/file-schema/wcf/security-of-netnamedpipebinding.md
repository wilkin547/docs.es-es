---
description: 'Más información sobre: <security> de <netNamedPipeBinding>'
title: <security> de <netNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: bb3cb022-637e-49fd-92e8-6766038affa7
ms.openlocfilehash: d64917c53390cade00d9e104c8581ce45355ac34
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99683104"
---
# <a name="security-of-netnamedpipebinding"></a><span data-ttu-id="2b913-103">\<security> de \<netNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="2b913-103">\<security> of \<netNamedPipeBinding></span></span>

<span data-ttu-id="2b913-104">Define la configuración de seguridad de un enlace.</span><span class="sxs-lookup"><span data-stu-id="2b913-104">Defines the security settings for a binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netNamedPipeBinding>**](netnamedpipebinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="2b913-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2b913-105">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2b913-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="2b913-106">Attributes and Elements</span></span>  

 <span data-ttu-id="2b913-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="2b913-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2b913-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="2b913-108">Attributes</span></span>  
  
|<span data-ttu-id="2b913-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="2b913-109">Attribute</span></span>|<span data-ttu-id="2b913-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="2b913-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2b913-111">mode</span><span class="sxs-lookup"><span data-stu-id="2b913-111">mode</span></span>|<span data-ttu-id="2b913-112">Especifica el tipo de seguridad que se aplica a este enlace.</span><span class="sxs-lookup"><span data-stu-id="2b913-112">Specifies the type of security that is applied to this binding.</span></span> <span data-ttu-id="2b913-113">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="2b913-113">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="2b913-114">-None: Esto deshabilita la seguridad.</span><span class="sxs-lookup"><span data-stu-id="2b913-114">-   None: This disables security.</span></span><br /><span data-ttu-id="2b913-115">-Transport: la seguridad se proporciona mediante la seguridad basada en transporte subyacente.</span><span class="sxs-lookup"><span data-stu-id="2b913-115">-   Transport: Security is provided using underlying transport based security.</span></span> <span data-ttu-id="2b913-116">Con este modo es posible controlar el nivel de protección.</span><span class="sxs-lookup"><span data-stu-id="2b913-116">It is possible to control the protection level with this mode.</span></span><br /><span data-ttu-id="2b913-117">-El valor predeterminado es Transport.</span><span class="sxs-lookup"><span data-stu-id="2b913-117">-   The default value is Transport.</span></span> <span data-ttu-id="2b913-118">Este atributo es del tipo <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="2b913-118">This attribute is of type <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2b913-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="2b913-119">Child Elements</span></span>  
  
|<span data-ttu-id="2b913-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="2b913-120">Element</span></span>|<span data-ttu-id="2b913-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="2b913-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2b913-122">transporte</span><span class="sxs-lookup"><span data-stu-id="2b913-122">transport</span></span>|<span data-ttu-id="2b913-123">Define la configuración de seguridad para el transporte.</span><span class="sxs-lookup"><span data-stu-id="2b913-123">Defines the security settings for the transport.</span></span> <span data-ttu-id="2b913-124">Este elemento es del tipo <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="2b913-124">This element is of type <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2b913-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="2b913-125">Parent Elements</span></span>  
  
|<span data-ttu-id="2b913-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="2b913-126">Element</span></span>|<span data-ttu-id="2b913-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="2b913-127">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2b913-128">binding</span><span class="sxs-lookup"><span data-stu-id="2b913-128">binding</span></span>|<span data-ttu-id="2b913-129">Elemento de enlace de [\<netNamedPipeBinding>](netnamedpipebinding.md) .</span><span class="sxs-lookup"><span data-stu-id="2b913-129">The binding element of the [\<netNamedPipeBinding>](netnamedpipebinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2b913-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="2b913-130">See also</span></span>

- <xref:System.ServiceModel.NetNamedPipeSecurity>
- <xref:System.ServiceModel.NetNamedPipeBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement>
- [<span data-ttu-id="2b913-131">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="2b913-131">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="2b913-132">Selección de tipos de credenciales</span><span class="sxs-lookup"><span data-stu-id="2b913-132">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="2b913-133">Enlaces</span><span class="sxs-lookup"><span data-stu-id="2b913-133">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="2b913-134">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="2b913-134">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="2b913-135">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="2b913-135">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
