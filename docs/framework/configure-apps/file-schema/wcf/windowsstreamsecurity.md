---
title: '&lt;inicial de windowsStreamSecurity&gt;'
ms.date: 03/30/2017
ms.assetid: 926bea29-90c7-4a26-9cf0-fb4aa44f6f70
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: a089a6fb61e8f7fac4116b2280a5c2fe0b703f94
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32755115"
---
# <a name="ltwindowsstreamsecuritygt"></a><span data-ttu-id="620e9-102">&lt;inicial de windowsStreamSecurity&gt;</span><span class="sxs-lookup"><span data-stu-id="620e9-102">&lt;windowsStreamSecurity&gt;</span></span>
<span data-ttu-id="620e9-103">Especifique configuración de seguridad de secuencia de Windows del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="620e9-103">Specify Windows stream security settings of the custom binding.</span></span>  
  
 <span data-ttu-id="620e9-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="620e9-104">\<system.serviceModel></span></span>  
<span data-ttu-id="620e9-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="620e9-105">\<bindings></span></span>  
<span data-ttu-id="620e9-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="620e9-106">\<customBinding></span></span>  
<span data-ttu-id="620e9-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="620e9-107">\<binding></span></span>  
<span data-ttu-id="620e9-108">\<inicial de windowsStreamSecurity ></span><span class="sxs-lookup"><span data-stu-id="620e9-108">\<windowsStreamSecurity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="620e9-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="620e9-109">Syntax</span></span>  
  
```xml  
<windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="620e9-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="620e9-110">Attributes and Elements</span></span>  
 <span data-ttu-id="620e9-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="620e9-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="620e9-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="620e9-112">Attributes</span></span>  
  
|<span data-ttu-id="620e9-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="620e9-113">Attribute</span></span>|<span data-ttu-id="620e9-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="620e9-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="620e9-115">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="620e9-115">protectionLevel</span></span>|<span data-ttu-id="620e9-116">Define la seguridad del nivel de mensaje.</span><span class="sxs-lookup"><span data-stu-id="620e9-116">Defines message-level security.</span></span> <span data-ttu-id="620e9-117">Al firmar los mensajes se reduce el riesgo de que un tercero manipule el mensaje mientras se transfiere.</span><span class="sxs-lookup"><span data-stu-id="620e9-117">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="620e9-118">El cifrado proporciona privacidad de nivel de datos durante el transporte.</span><span class="sxs-lookup"><span data-stu-id="620e9-118">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="620e9-119">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="620e9-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="620e9-120">-None: Sin protección.</span><span class="sxs-lookup"><span data-stu-id="620e9-120">-   None: No protection.</span></span><br /><span data-ttu-id="620e9-121">-Sign: Se firman los mensajes.</span><span class="sxs-lookup"><span data-stu-id="620e9-121">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="620e9-122">-EncryptAndSign: Los mensajes firmados y cifrados.</span><span class="sxs-lookup"><span data-stu-id="620e9-122">-   EncryptAndSign: Messages are signed and encrypted.</span></span><br /><br /> <span data-ttu-id="620e9-123">El valor predeterminado es EncryptAndSign.</span><span class="sxs-lookup"><span data-stu-id="620e9-123">The default is EncryptAndSign.</span></span><br /><br /> <span data-ttu-id="620e9-124">Este atributo es del tipo <xref:System.Net.Security.ProtectionLevel>.</span><span class="sxs-lookup"><span data-stu-id="620e9-124">This attribute is of type <xref:System.Net.Security.ProtectionLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="620e9-125">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="620e9-125">Child Elements</span></span>  
 <span data-ttu-id="620e9-126">Ninguna</span><span class="sxs-lookup"><span data-stu-id="620e9-126">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="620e9-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="620e9-127">Parent Elements</span></span>  
  
|<span data-ttu-id="620e9-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="620e9-128">Element</span></span>|<span data-ttu-id="620e9-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="620e9-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="620e9-130">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="620e9-130">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="620e9-131">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="620e9-131">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="620e9-132">Comentarios</span><span class="sxs-lookup"><span data-stu-id="620e9-132">Remarks</span></span>  
 <span data-ttu-id="620e9-133">Transportes que utilizan un protocolo orientado a secuencias como TCP y canalizaciones con nombre que admiten las actualizaciones de transporte basadas en secuencias.</span><span class="sxs-lookup"><span data-stu-id="620e9-133">Transports that use a stream-oriented protocol such as TCP and named pipes support stream-based transport upgrades.</span></span> <span data-ttu-id="620e9-134">Concretamente, WCF proporciona actualizaciones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="620e9-134">Specifically, WCF provides security upgrades.</span></span> <span data-ttu-id="620e9-135">La configuración de esta seguridad de transporte es encapsulada por este elemento de configuración, así como por [ \<sslStreamSecurity >](../../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md), que se pueden configurar y agregar a un enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="620e9-135">The configuration of this transport security is encapsulated by this configuration element  as well as by [\<sslStreamSecurity>](../../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md), which can be configured and added to a custom binding</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="620e9-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="620e9-136">See Also</span></span>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>  
 <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>  
 [<span data-ttu-id="620e9-137">Enlaces</span><span class="sxs-lookup"><span data-stu-id="620e9-137">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="620e9-138">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="620e9-138">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="620e9-139">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="620e9-139">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="620e9-140">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="620e9-140">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
