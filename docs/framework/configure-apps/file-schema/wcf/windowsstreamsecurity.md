---
title: <windowsStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 926bea29-90c7-4a26-9cf0-fb4aa44f6f70
ms.openlocfilehash: 0f1dfd523e593c82727354db7ce39ffc992bdfb4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69932802"
---
# <a name="windowsstreamsecurity"></a><span data-ttu-id="c3940-101">\<windowsStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="c3940-101">\<windowsStreamSecurity></span></span>
<span data-ttu-id="c3940-102">Especifique configuración de seguridad de secuencia de Windows del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="c3940-102">Specify Windows stream security settings of the custom binding.</span></span>  
  
 <span data-ttu-id="c3940-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="c3940-103">\<system.serviceModel></span></span>  
<span data-ttu-id="c3940-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="c3940-104">\<bindings></span></span>  
<span data-ttu-id="c3940-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="c3940-105">\<customBinding></span></span>  
<span data-ttu-id="c3940-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="c3940-106">\<binding></span></span>  
<span data-ttu-id="c3940-107">\<windowsStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="c3940-107">\<windowsStreamSecurity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3940-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c3940-108">Syntax</span></span>  
  
```xml  
<windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c3940-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c3940-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c3940-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c3940-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c3940-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="c3940-111">Attributes</span></span>  
  
|<span data-ttu-id="c3940-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="c3940-112">Attribute</span></span>|<span data-ttu-id="c3940-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="c3940-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c3940-114">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="c3940-114">protectionLevel</span></span>|<span data-ttu-id="c3940-115">Define la seguridad del nivel de mensaje.</span><span class="sxs-lookup"><span data-stu-id="c3940-115">Defines message-level security.</span></span> <span data-ttu-id="c3940-116">Al firmar los mensajes se reduce el riesgo de que un tercero manipule el mensaje mientras se transfiere.</span><span class="sxs-lookup"><span data-stu-id="c3940-116">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="c3940-117">El cifrado proporciona privacidad de nivel de datos durante el transporte.</span><span class="sxs-lookup"><span data-stu-id="c3940-117">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="c3940-118">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="c3940-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="c3940-119">Ninguna Ninguna protección</span><span class="sxs-lookup"><span data-stu-id="c3940-119">-   None: No protection.</span></span><br /><span data-ttu-id="c3940-120">Sesión Se firman los mensajes.</span><span class="sxs-lookup"><span data-stu-id="c3940-120">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="c3940-121">-   EncryptAndSign: Los mensajes se firman y cifran.</span><span class="sxs-lookup"><span data-stu-id="c3940-121">-   EncryptAndSign: Messages are signed and encrypted.</span></span><br /><br /> <span data-ttu-id="c3940-122">El valor predeterminado es EncryptAndSign.</span><span class="sxs-lookup"><span data-stu-id="c3940-122">The default is EncryptAndSign.</span></span><br /><br /> <span data-ttu-id="c3940-123">Este atributo es del tipo <xref:System.Net.Security.ProtectionLevel>.</span><span class="sxs-lookup"><span data-stu-id="c3940-123">This attribute is of type <xref:System.Net.Security.ProtectionLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c3940-124">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c3940-124">Child Elements</span></span>  
 <span data-ttu-id="c3940-125">None</span><span class="sxs-lookup"><span data-stu-id="c3940-125">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c3940-126">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c3940-126">Parent Elements</span></span>  
  
|<span data-ttu-id="c3940-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="c3940-127">Element</span></span>|<span data-ttu-id="c3940-128">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="c3940-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c3940-129">\<binding></span><span class="sxs-lookup"><span data-stu-id="c3940-129">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="c3940-130">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="c3940-130">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c3940-131">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c3940-131">Remarks</span></span>  
 <span data-ttu-id="c3940-132">Transportes que utilizan un protocolo orientado a secuencias como TCP y canalizaciones con nombre que admiten las actualizaciones de transporte basadas en secuencias.</span><span class="sxs-lookup"><span data-stu-id="c3940-132">Transports that use a stream-oriented protocol such as TCP and named pipes support stream-based transport upgrades.</span></span> <span data-ttu-id="c3940-133">Concretamente, WCF proporciona actualizaciones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="c3940-133">Specifically, WCF provides security upgrades.</span></span> <span data-ttu-id="c3940-134">La configuración de esta seguridad de transporte está encapsulada por este elemento de configuración, así como por [ \<sección sslstreamsecurity >](sslstreamsecurity.md), que se puede configurar y agregar a un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="c3940-134">The configuration of this transport security is encapsulated by this configuration element  as well as by [\<sslStreamSecurity>](sslstreamsecurity.md), which can be configured and added to a custom binding</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3940-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="c3940-135">See also</span></span>

- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>
- <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>
- [<span data-ttu-id="c3940-136">Enlaces</span><span class="sxs-lookup"><span data-stu-id="c3940-136">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="c3940-137">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="c3940-137">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="c3940-138">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="c3940-138">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="c3940-139">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="c3940-139">\<customBinding></span></span>](custombinding.md)
