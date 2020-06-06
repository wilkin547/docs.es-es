---
title: <security> de <netNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: bb3cb022-637e-49fd-92e8-6766038affa7
ms.openlocfilehash: 31ea31ce6880a770c966350cd931e487396c4d63
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "73736438"
---
# <a name="security-of-netnamedpipebinding"></a><span data-ttu-id="c3ffa-102">\<security> de \<netNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="c3ffa-102">\<security> of \<netNamedPipeBinding></span></span>
<span data-ttu-id="c3ffa-103">Define la configuración de seguridad de un enlace.</span><span class="sxs-lookup"><span data-stu-id="c3ffa-103">Defines the security settings for a binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netNamedPipeBinding>**](netnamedpipebinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="c3ffa-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c3ffa-104">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c3ffa-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c3ffa-105">Attributes and Elements</span></span>  
 <span data-ttu-id="c3ffa-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c3ffa-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c3ffa-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="c3ffa-107">Attributes</span></span>  
  
|<span data-ttu-id="c3ffa-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="c3ffa-108">Attribute</span></span>|<span data-ttu-id="c3ffa-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="c3ffa-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c3ffa-110">mode</span><span class="sxs-lookup"><span data-stu-id="c3ffa-110">mode</span></span>|<span data-ttu-id="c3ffa-111">Especifica el tipo de seguridad que se aplica a este enlace.</span><span class="sxs-lookup"><span data-stu-id="c3ffa-111">Specifies the type of security that is applied to this binding.</span></span> <span data-ttu-id="c3ffa-112">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="c3ffa-112">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="c3ffa-113">-None: Esto deshabilita la seguridad.</span><span class="sxs-lookup"><span data-stu-id="c3ffa-113">-   None: This disables security.</span></span><br /><span data-ttu-id="c3ffa-114">-Transport: la seguridad se proporciona mediante la seguridad basada en transporte subyacente.</span><span class="sxs-lookup"><span data-stu-id="c3ffa-114">-   Transport: Security is provided using underlying transport based security.</span></span> <span data-ttu-id="c3ffa-115">Con este modo es posible controlar el nivel de protección.</span><span class="sxs-lookup"><span data-stu-id="c3ffa-115">It is possible to control the protection level with this mode.</span></span><br /><span data-ttu-id="c3ffa-116">-El valor predeterminado es Transport.</span><span class="sxs-lookup"><span data-stu-id="c3ffa-116">-   The default value is Transport.</span></span> <span data-ttu-id="c3ffa-117">Este atributo es del tipo <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="c3ffa-117">This attribute is of type <xref:System.ServiceModel.NetNamedPipeSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c3ffa-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c3ffa-118">Child Elements</span></span>  
  
|<span data-ttu-id="c3ffa-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="c3ffa-119">Element</span></span>|<span data-ttu-id="c3ffa-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="c3ffa-120">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c3ffa-121">transporte</span><span class="sxs-lookup"><span data-stu-id="c3ffa-121">transport</span></span>|<span data-ttu-id="c3ffa-122">Define la configuración de seguridad para el transporte.</span><span class="sxs-lookup"><span data-stu-id="c3ffa-122">Defines the security settings for the transport.</span></span> <span data-ttu-id="c3ffa-123">Este elemento es del tipo <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="c3ffa-123">This element is of type <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c3ffa-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c3ffa-124">Parent Elements</span></span>  
  
|<span data-ttu-id="c3ffa-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="c3ffa-125">Element</span></span>|<span data-ttu-id="c3ffa-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="c3ffa-126">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c3ffa-127">binding</span><span class="sxs-lookup"><span data-stu-id="c3ffa-127">binding</span></span>|<span data-ttu-id="c3ffa-128">Elemento de enlace de [\<netNamedPipeBinding>](netnamedpipebinding.md) .</span><span class="sxs-lookup"><span data-stu-id="c3ffa-128">The binding element of the [\<netNamedPipeBinding>](netnamedpipebinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c3ffa-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c3ffa-129">See also</span></span>

- <xref:System.ServiceModel.NetNamedPipeSecurity>
- <xref:System.ServiceModel.NetNamedPipeBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement>
- [<span data-ttu-id="c3ffa-130">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="c3ffa-130">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="c3ffa-131">Selección de tipos de credenciales</span><span class="sxs-lookup"><span data-stu-id="c3ffa-131">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="c3ffa-132">Enlaces</span><span class="sxs-lookup"><span data-stu-id="c3ffa-132">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="c3ffa-133">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="c3ffa-133">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="c3ffa-134">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="c3ffa-134">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
