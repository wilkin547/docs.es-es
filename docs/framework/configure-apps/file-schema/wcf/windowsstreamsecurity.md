---
title: <windowsStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 926bea29-90c7-4a26-9cf0-fb4aa44f6f70
ms.openlocfilehash: cddd9f0c1dda982c1795500723c21546bd58c92b
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399097"
---
# <a name="windowsstreamsecurity"></a><span data-ttu-id="188df-101">\<windowsStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="188df-101">\<windowsStreamSecurity></span></span>
<span data-ttu-id="188df-102">Especifique configuración de seguridad de secuencia de Windows del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="188df-102">Specify Windows stream security settings of the custom binding.</span></span>  
  
<span data-ttu-id="188df-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="188df-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="188df-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="188df-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="188df-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de enlaces**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="188df-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="188df-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="188df-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="188df-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de enlace**</span><span class="sxs-lookup"><span data-stu-id="188df-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="188df-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> windowsStreamSecurity**</span><span class="sxs-lookup"><span data-stu-id="188df-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<windowsStreamSecurity>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="188df-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="188df-109">Syntax</span></span>  
  
```xml  
<windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="188df-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="188df-110">Attributes and Elements</span></span>  
 <span data-ttu-id="188df-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="188df-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="188df-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="188df-112">Attributes</span></span>  
  
|<span data-ttu-id="188df-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="188df-113">Attribute</span></span>|<span data-ttu-id="188df-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="188df-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="188df-115">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="188df-115">protectionLevel</span></span>|<span data-ttu-id="188df-116">Define la seguridad del nivel de mensaje.</span><span class="sxs-lookup"><span data-stu-id="188df-116">Defines message-level security.</span></span> <span data-ttu-id="188df-117">Al firmar los mensajes se reduce el riesgo de que un tercero manipule el mensaje mientras se transfiere.</span><span class="sxs-lookup"><span data-stu-id="188df-117">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="188df-118">El cifrado proporciona privacidad de nivel de datos durante el transporte.</span><span class="sxs-lookup"><span data-stu-id="188df-118">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="188df-119">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="188df-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="188df-120">Ninguna Ninguna protección</span><span class="sxs-lookup"><span data-stu-id="188df-120">-   None: No protection.</span></span><br /><span data-ttu-id="188df-121">Sesión Se firman los mensajes.</span><span class="sxs-lookup"><span data-stu-id="188df-121">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="188df-122">-   EncryptAndSign: Los mensajes se firman y cifran.</span><span class="sxs-lookup"><span data-stu-id="188df-122">-   EncryptAndSign: Messages are signed and encrypted.</span></span><br /><br /> <span data-ttu-id="188df-123">El valor predeterminado es EncryptAndSign.</span><span class="sxs-lookup"><span data-stu-id="188df-123">The default is EncryptAndSign.</span></span><br /><br /> <span data-ttu-id="188df-124">Este atributo es del tipo <xref:System.Net.Security.ProtectionLevel>.</span><span class="sxs-lookup"><span data-stu-id="188df-124">This attribute is of type <xref:System.Net.Security.ProtectionLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="188df-125">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="188df-125">Child Elements</span></span>  
 <span data-ttu-id="188df-126">None</span><span class="sxs-lookup"><span data-stu-id="188df-126">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="188df-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="188df-127">Parent Elements</span></span>  
  
|<span data-ttu-id="188df-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="188df-128">Element</span></span>|<span data-ttu-id="188df-129">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="188df-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="188df-130">\<binding></span><span class="sxs-lookup"><span data-stu-id="188df-130">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="188df-131">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="188df-131">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="188df-132">Comentarios</span><span class="sxs-lookup"><span data-stu-id="188df-132">Remarks</span></span>  
 <span data-ttu-id="188df-133">Transportes que utilizan un protocolo orientado a secuencias como TCP y canalizaciones con nombre que admiten las actualizaciones de transporte basadas en secuencias.</span><span class="sxs-lookup"><span data-stu-id="188df-133">Transports that use a stream-oriented protocol such as TCP and named pipes support stream-based transport upgrades.</span></span> <span data-ttu-id="188df-134">Concretamente, WCF proporciona actualizaciones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="188df-134">Specifically, WCF provides security upgrades.</span></span> <span data-ttu-id="188df-135">La configuración de esta seguridad de transporte está encapsulada por este elemento de configuración, así como por [ \<sección sslstreamsecurity >](sslstreamsecurity.md), que se puede configurar y agregar a un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="188df-135">The configuration of this transport security is encapsulated by this configuration element  as well as by [\<sslStreamSecurity>](sslstreamsecurity.md), which can be configured and added to a custom binding</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="188df-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="188df-136">See also</span></span>

- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>
- <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>
- [<span data-ttu-id="188df-137">Enlaces</span><span class="sxs-lookup"><span data-stu-id="188df-137">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="188df-138">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="188df-138">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="188df-139">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="188df-139">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="188df-140">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="188df-140">\<customBinding></span></span>](custombinding.md)
