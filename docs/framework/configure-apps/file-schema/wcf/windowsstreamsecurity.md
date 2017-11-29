---
title: '&lt;inicial de windowsStreamSecurity&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 926bea29-90c7-4a26-9cf0-fb4aa44f6f70
caps.latest.revision: "10"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 5a0d3b61f473b49abdb2470a9fa5381dc9929274
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltwindowsstreamsecuritygt"></a><span data-ttu-id="1dec5-102">&lt;inicial de windowsStreamSecurity&gt;</span><span class="sxs-lookup"><span data-stu-id="1dec5-102">&lt;windowsStreamSecurity&gt;</span></span>
<span data-ttu-id="1dec5-103">Especifique configuración de seguridad de secuencia de Windows del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="1dec5-103">Specify Windows stream security settings of the custom binding.</span></span>  
  
 <span data-ttu-id="1dec5-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="1dec5-104">\<system.serviceModel></span></span>  
<span data-ttu-id="1dec5-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="1dec5-105">\<bindings></span></span>  
<span data-ttu-id="1dec5-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="1dec5-106">\<customBinding></span></span>  
<span data-ttu-id="1dec5-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="1dec5-107">\<binding></span></span>  
<span data-ttu-id="1dec5-108">\<inicial de windowsStreamSecurity ></span><span class="sxs-lookup"><span data-stu-id="1dec5-108">\<windowsStreamSecurity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1dec5-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1dec5-109">Syntax</span></span>  
  
```xml  
<windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1dec5-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="1dec5-110">Attributes and Elements</span></span>  
 <span data-ttu-id="1dec5-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="1dec5-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1dec5-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="1dec5-112">Attributes</span></span>  
  
|<span data-ttu-id="1dec5-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="1dec5-113">Attribute</span></span>|<span data-ttu-id="1dec5-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="1dec5-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1dec5-115">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="1dec5-115">protectionLevel</span></span>|<span data-ttu-id="1dec5-116">Define la seguridad del nivel de mensaje.</span><span class="sxs-lookup"><span data-stu-id="1dec5-116">Defines message-level security.</span></span> <span data-ttu-id="1dec5-117">Al firmar los mensajes se reduce el riesgo de que un tercero manipule el mensaje mientras se transfiere.</span><span class="sxs-lookup"><span data-stu-id="1dec5-117">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="1dec5-118">El cifrado proporciona privacidad de nivel de datos durante el transporte.</span><span class="sxs-lookup"><span data-stu-id="1dec5-118">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="1dec5-119">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="1dec5-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="1dec5-120">-None: Sin protección.</span><span class="sxs-lookup"><span data-stu-id="1dec5-120">-   None: No protection.</span></span><br /><span data-ttu-id="1dec5-121">-Sign: Se firman los mensajes.</span><span class="sxs-lookup"><span data-stu-id="1dec5-121">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="1dec5-122">-EncryptAndSign: Los mensajes firmados y cifrados.</span><span class="sxs-lookup"><span data-stu-id="1dec5-122">-   EncryptAndSign: Messages are signed and encrypted.</span></span><br /><br /> <span data-ttu-id="1dec5-123">El valor predeterminado es EncryptAndSign.</span><span class="sxs-lookup"><span data-stu-id="1dec5-123">The default is EncryptAndSign.</span></span><br /><br /> <span data-ttu-id="1dec5-124">Este atributo es del tipo <xref:System.Net.Security.ProtectionLevel>.</span><span class="sxs-lookup"><span data-stu-id="1dec5-124">This attribute is of type <xref:System.Net.Security.ProtectionLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1dec5-125">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1dec5-125">Child Elements</span></span>  
 <span data-ttu-id="1dec5-126">Ninguna</span><span class="sxs-lookup"><span data-stu-id="1dec5-126">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1dec5-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1dec5-127">Parent Elements</span></span>  
  
|<span data-ttu-id="1dec5-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="1dec5-128">Element</span></span>|<span data-ttu-id="1dec5-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="1dec5-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1dec5-130">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="1dec5-130">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="1dec5-131">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="1dec5-131">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1dec5-132">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1dec5-132">Remarks</span></span>  
 <span data-ttu-id="1dec5-133">Transportes que utilizan un protocolo orientado a secuencias como TCP y canalizaciones con nombre que admiten las actualizaciones de transporte basadas en secuencias.</span><span class="sxs-lookup"><span data-stu-id="1dec5-133">Transports that use a stream-oriented protocol such as TCP and named pipes support stream-based transport upgrades.</span></span> <span data-ttu-id="1dec5-134">Concretamente, WCF proporciona actualizaciones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="1dec5-134">Specifically, WCF provides security upgrades.</span></span> <span data-ttu-id="1dec5-135">La configuración de esta seguridad de transporte es encapsulada por este elemento de configuración, así como por [ \<sslStreamSecurity >](../../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md), que se pueden configurar y agregar a un enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="1dec5-135">The configuration of this transport security is encapsulated by this configuration element  as well as by [\<sslStreamSecurity>](../../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md), which can be configured and added to a custom binding</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1dec5-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="1dec5-136">See Also</span></span>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>  
 <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>  
 [<span data-ttu-id="1dec5-137">Enlaces</span><span class="sxs-lookup"><span data-stu-id="1dec5-137">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="1dec5-138">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="1dec5-138">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="1dec5-139">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="1dec5-139">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="1dec5-140">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="1dec5-140">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
