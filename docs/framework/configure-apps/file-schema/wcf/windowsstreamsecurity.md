---
title: <windowsStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 926bea29-90c7-4a26-9cf0-fb4aa44f6f70
ms.openlocfilehash: 32e8ed6b70a23462fac3c53d1bc353167ff67560
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59113638"
---
# <a name="windowsstreamsecurity"></a><span data-ttu-id="a7839-101">\<windowsStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="a7839-101">\<windowsStreamSecurity></span></span>
<span data-ttu-id="a7839-102">Especifique configuración de seguridad de secuencia de Windows del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="a7839-102">Specify Windows stream security settings of the custom binding.</span></span>  
  
 <span data-ttu-id="a7839-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="a7839-103">\<system.serviceModel></span></span>  
<span data-ttu-id="a7839-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="a7839-104">\<bindings></span></span>  
<span data-ttu-id="a7839-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="a7839-105">\<customBinding></span></span>  
<span data-ttu-id="a7839-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="a7839-106">\<binding></span></span>  
<span data-ttu-id="a7839-107">\<windowsStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="a7839-107">\<windowsStreamSecurity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7839-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a7839-108">Syntax</span></span>  
  
```xml  
<windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a7839-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a7839-109">Attributes and Elements</span></span>  
 <span data-ttu-id="a7839-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a7839-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a7839-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="a7839-111">Attributes</span></span>  
  
|<span data-ttu-id="a7839-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="a7839-112">Attribute</span></span>|<span data-ttu-id="a7839-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="a7839-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a7839-114">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="a7839-114">protectionLevel</span></span>|<span data-ttu-id="a7839-115">Define la seguridad del nivel de mensaje.</span><span class="sxs-lookup"><span data-stu-id="a7839-115">Defines message-level security.</span></span> <span data-ttu-id="a7839-116">Al firmar los mensajes se reduce el riesgo de que un tercero manipule el mensaje mientras se transfiere.</span><span class="sxs-lookup"><span data-stu-id="a7839-116">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="a7839-117">El cifrado proporciona privacidad de nivel de datos durante el transporte.</span><span class="sxs-lookup"><span data-stu-id="a7839-117">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="a7839-118">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="a7839-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="a7839-119">-None: Ninguna protección</span><span class="sxs-lookup"><span data-stu-id="a7839-119">-   None: No protection.</span></span><br /><span data-ttu-id="a7839-120">-Inicio de sesión: Se firman los mensajes.</span><span class="sxs-lookup"><span data-stu-id="a7839-120">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="a7839-121">-   EncryptAndSign: Los mensajes se firman y cifran.</span><span class="sxs-lookup"><span data-stu-id="a7839-121">-   EncryptAndSign: Messages are signed and encrypted.</span></span><br /><br /> <span data-ttu-id="a7839-122">El valor predeterminado es EncryptAndSign.</span><span class="sxs-lookup"><span data-stu-id="a7839-122">The default is EncryptAndSign.</span></span><br /><br /> <span data-ttu-id="a7839-123">Este atributo es del tipo <xref:System.Net.Security.ProtectionLevel>.</span><span class="sxs-lookup"><span data-stu-id="a7839-123">This attribute is of type <xref:System.Net.Security.ProtectionLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a7839-124">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a7839-124">Child Elements</span></span>  
 <span data-ttu-id="a7839-125">Ninguna</span><span class="sxs-lookup"><span data-stu-id="a7839-125">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a7839-126">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a7839-126">Parent Elements</span></span>  
  
|<span data-ttu-id="a7839-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="a7839-127">Element</span></span>|<span data-ttu-id="a7839-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="a7839-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a7839-129">\<binding></span><span class="sxs-lookup"><span data-stu-id="a7839-129">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="a7839-130">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="a7839-130">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a7839-131">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a7839-131">Remarks</span></span>  
 <span data-ttu-id="a7839-132">Transportes que utilizan un protocolo orientado a secuencias como TCP y canalizaciones con nombre que admiten las actualizaciones de transporte basadas en secuencias.</span><span class="sxs-lookup"><span data-stu-id="a7839-132">Transports that use a stream-oriented protocol such as TCP and named pipes support stream-based transport upgrades.</span></span> <span data-ttu-id="a7839-133">Concretamente, WCF proporciona actualizaciones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="a7839-133">Specifically, WCF provides security upgrades.</span></span> <span data-ttu-id="a7839-134">La configuración de seguridad de este transporte es encapsulada por este elemento de configuración así como por [ \<sslStreamSecurity >](../../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md), que se pueden configurar y agregar a un enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="a7839-134">The configuration of this transport security is encapsulated by this configuration element  as well as by [\<sslStreamSecurity>](../../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md), which can be configured and added to a custom binding</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7839-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="a7839-135">See also</span></span>

- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>
- <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>
- [<span data-ttu-id="a7839-136">Enlaces</span><span class="sxs-lookup"><span data-stu-id="a7839-136">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="a7839-137">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="a7839-137">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="a7839-138">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="a7839-138">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="a7839-139">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="a7839-139">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
