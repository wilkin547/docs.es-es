---
title: '&lt;windowsStreamSecurity&gt;'
ms.date: 03/30/2017
ms.assetid: 926bea29-90c7-4a26-9cf0-fb4aa44f6f70
ms.openlocfilehash: 4218072f63cabe511ca9d30c77395f734d961eca
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54745186"
---
# <a name="ltwindowsstreamsecuritygt"></a><span data-ttu-id="93fe1-102">&lt;windowsStreamSecurity&gt;</span><span class="sxs-lookup"><span data-stu-id="93fe1-102">&lt;windowsStreamSecurity&gt;</span></span>
<span data-ttu-id="93fe1-103">Especifique configuración de seguridad de secuencia de Windows del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="93fe1-103">Specify Windows stream security settings of the custom binding.</span></span>  
  
 <span data-ttu-id="93fe1-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="93fe1-104">\<system.serviceModel></span></span>  
<span data-ttu-id="93fe1-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="93fe1-105">\<bindings></span></span>  
<span data-ttu-id="93fe1-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="93fe1-106">\<customBinding></span></span>  
<span data-ttu-id="93fe1-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="93fe1-107">\<binding></span></span>  
<span data-ttu-id="93fe1-108">\<windowsStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="93fe1-108">\<windowsStreamSecurity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93fe1-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="93fe1-109">Syntax</span></span>  
  
```xml  
<windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="93fe1-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="93fe1-110">Attributes and Elements</span></span>  
 <span data-ttu-id="93fe1-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="93fe1-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="93fe1-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="93fe1-112">Attributes</span></span>  
  
|<span data-ttu-id="93fe1-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="93fe1-113">Attribute</span></span>|<span data-ttu-id="93fe1-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="93fe1-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="93fe1-115">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="93fe1-115">protectionLevel</span></span>|<span data-ttu-id="93fe1-116">Define la seguridad del nivel de mensaje.</span><span class="sxs-lookup"><span data-stu-id="93fe1-116">Defines message-level security.</span></span> <span data-ttu-id="93fe1-117">Al firmar los mensajes se reduce el riesgo de que un tercero manipule el mensaje mientras se transfiere.</span><span class="sxs-lookup"><span data-stu-id="93fe1-117">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="93fe1-118">El cifrado proporciona privacidad de nivel de datos durante el transporte.</span><span class="sxs-lookup"><span data-stu-id="93fe1-118">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="93fe1-119">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="93fe1-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="93fe1-120">-None: Ninguna protección</span><span class="sxs-lookup"><span data-stu-id="93fe1-120">-   None: No protection.</span></span><br /><span data-ttu-id="93fe1-121">-Inicio de sesión: Se firman los mensajes.</span><span class="sxs-lookup"><span data-stu-id="93fe1-121">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="93fe1-122">-   EncryptAndSign: Los mensajes se firman y cifran.</span><span class="sxs-lookup"><span data-stu-id="93fe1-122">-   EncryptAndSign: Messages are signed and encrypted.</span></span><br /><br /> <span data-ttu-id="93fe1-123">El valor predeterminado es EncryptAndSign.</span><span class="sxs-lookup"><span data-stu-id="93fe1-123">The default is EncryptAndSign.</span></span><br /><br /> <span data-ttu-id="93fe1-124">Este atributo es del tipo <xref:System.Net.Security.ProtectionLevel>.</span><span class="sxs-lookup"><span data-stu-id="93fe1-124">This attribute is of type <xref:System.Net.Security.ProtectionLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="93fe1-125">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="93fe1-125">Child Elements</span></span>  
 <span data-ttu-id="93fe1-126">Ninguna</span><span class="sxs-lookup"><span data-stu-id="93fe1-126">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="93fe1-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="93fe1-127">Parent Elements</span></span>  
  
|<span data-ttu-id="93fe1-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="93fe1-128">Element</span></span>|<span data-ttu-id="93fe1-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="93fe1-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="93fe1-130">\<binding></span><span class="sxs-lookup"><span data-stu-id="93fe1-130">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="93fe1-131">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="93fe1-131">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="93fe1-132">Comentarios</span><span class="sxs-lookup"><span data-stu-id="93fe1-132">Remarks</span></span>  
 <span data-ttu-id="93fe1-133">Transportes que utilizan un protocolo orientado a secuencias como TCP y canalizaciones con nombre que admiten las actualizaciones de transporte basadas en secuencias.</span><span class="sxs-lookup"><span data-stu-id="93fe1-133">Transports that use a stream-oriented protocol such as TCP and named pipes support stream-based transport upgrades.</span></span> <span data-ttu-id="93fe1-134">Concretamente, WCF proporciona actualizaciones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="93fe1-134">Specifically, WCF provides security upgrades.</span></span> <span data-ttu-id="93fe1-135">La configuración de seguridad de este transporte es encapsulada por este elemento de configuración así como por [ \<sslStreamSecurity >](../../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md), que se pueden configurar y agregar a un enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="93fe1-135">The configuration of this transport security is encapsulated by this configuration element  as well as by [\<sslStreamSecurity>](../../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md), which can be configured and added to a custom binding</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93fe1-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="93fe1-136">See also</span></span>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>
- <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>
- [<span data-ttu-id="93fe1-137">Enlaces</span><span class="sxs-lookup"><span data-stu-id="93fe1-137">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="93fe1-138">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="93fe1-138">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="93fe1-139">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="93fe1-139">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="93fe1-140">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="93fe1-140">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
