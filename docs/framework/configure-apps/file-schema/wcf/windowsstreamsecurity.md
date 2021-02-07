---
description: 'Más información acerca de: <windowsStreamSecurity>'
title: <windowsStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 926bea29-90c7-4a26-9cf0-fb4aa44f6f70
ms.openlocfilehash: c623dc23ca67d0341b66a2a4d97de564be77dcc5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99682402"
---
# \<windowsStreamSecurity>

<span data-ttu-id="0c979-102">Especifique configuración de seguridad de secuencia de Windows del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="0c979-102">Specify Windows stream security settings of the custom binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<windowsStreamSecurity>**  
  
## <a name="syntax"></a><span data-ttu-id="0c979-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0c979-103">Syntax</span></span>  
  
```xml  
<windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0c979-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0c979-104">Attributes and Elements</span></span>  

 <span data-ttu-id="0c979-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0c979-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0c979-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="0c979-106">Attributes</span></span>  
  
|<span data-ttu-id="0c979-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="0c979-107">Attribute</span></span>|<span data-ttu-id="0c979-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="0c979-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0c979-109">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="0c979-109">protectionLevel</span></span>|<span data-ttu-id="0c979-110">Define la seguridad del nivel de mensaje.</span><span class="sxs-lookup"><span data-stu-id="0c979-110">Defines message-level security.</span></span> <span data-ttu-id="0c979-111">Si se firman los mensajes, se reduce el riesgo de que manipulen el mensaje terceros mientras éste se transfiere.</span><span class="sxs-lookup"><span data-stu-id="0c979-111">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="0c979-112">El cifrado proporciona privacidad de nivel de datos durante el transporte.</span><span class="sxs-lookup"><span data-stu-id="0c979-112">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="0c979-113">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="0c979-113">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="0c979-114">-None: sin protección.</span><span class="sxs-lookup"><span data-stu-id="0c979-114">-   None: No protection.</span></span><br /><span data-ttu-id="0c979-115">-Sign: los mensajes se firman.</span><span class="sxs-lookup"><span data-stu-id="0c979-115">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="0c979-116">-EncryptAndSign: los mensajes se firman y cifran.</span><span class="sxs-lookup"><span data-stu-id="0c979-116">-   EncryptAndSign: Messages are signed and encrypted.</span></span><br /><br /> <span data-ttu-id="0c979-117">El valor predeterminado es EncryptAndSign.</span><span class="sxs-lookup"><span data-stu-id="0c979-117">The default is EncryptAndSign.</span></span><br /><br /> <span data-ttu-id="0c979-118">Este atributo es del tipo <xref:System.Net.Security.ProtectionLevel>.</span><span class="sxs-lookup"><span data-stu-id="0c979-118">This attribute is of type <xref:System.Net.Security.ProtectionLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0c979-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0c979-119">Child Elements</span></span>  

 <span data-ttu-id="0c979-120">None</span><span class="sxs-lookup"><span data-stu-id="0c979-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0c979-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0c979-121">Parent Elements</span></span>  
  
|<span data-ttu-id="0c979-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="0c979-122">Element</span></span>|<span data-ttu-id="0c979-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="0c979-123">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="0c979-124">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="0c979-124">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0c979-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0c979-125">Remarks</span></span>  

 <span data-ttu-id="0c979-126">Transportes que utilizan un protocolo orientado a secuencias como TCP y canalizaciones con nombre que admiten las actualizaciones de transporte basadas en secuencias.</span><span class="sxs-lookup"><span data-stu-id="0c979-126">Transports that use a stream-oriented protocol such as TCP and named pipes support stream-based transport upgrades.</span></span> <span data-ttu-id="0c979-127">Concretamente, WCF proporciona actualizaciones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="0c979-127">Specifically, WCF provides security upgrades.</span></span> <span data-ttu-id="0c979-128">La configuración de esta seguridad de transporte está encapsulada por este elemento de configuración, así como por [\<sslStreamSecurity>](sslstreamsecurity.md) , que se puede configurar y agregar a un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="0c979-128">The configuration of this transport security is encapsulated by this configuration element  as well as by [\<sslStreamSecurity>](sslstreamsecurity.md), which can be configured and added to a custom binding</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c979-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="0c979-129">See also</span></span>

- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>
- <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>
- [<span data-ttu-id="0c979-130">Enlaces</span><span class="sxs-lookup"><span data-stu-id="0c979-130">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="0c979-131">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="0c979-131">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="0c979-132">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="0c979-132">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
