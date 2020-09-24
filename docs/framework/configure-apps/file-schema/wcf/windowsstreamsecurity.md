---
title: <windowsStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 926bea29-90c7-4a26-9cf0-fb4aa44f6f70
ms.openlocfilehash: 3c82bd81bd0fabf10f2dd835188b346f62d038b5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91167085"
---
# \<windowsStreamSecurity>

<span data-ttu-id="ed996-101">Especifique configuración de seguridad de secuencia de Windows del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="ed996-101">Specify Windows stream security settings of the custom binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<windowsStreamSecurity>**  
  
## <a name="syntax"></a><span data-ttu-id="ed996-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ed996-102">Syntax</span></span>  
  
```xml  
<windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ed996-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ed996-103">Attributes and Elements</span></span>  

 <span data-ttu-id="ed996-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ed996-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ed996-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="ed996-105">Attributes</span></span>  
  
|<span data-ttu-id="ed996-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="ed996-106">Attribute</span></span>|<span data-ttu-id="ed996-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="ed996-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ed996-108">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="ed996-108">protectionLevel</span></span>|<span data-ttu-id="ed996-109">Define la seguridad del nivel de mensaje.</span><span class="sxs-lookup"><span data-stu-id="ed996-109">Defines message-level security.</span></span> <span data-ttu-id="ed996-110">Si se firman los mensajes, se reduce el riesgo de que manipulen el mensaje terceros mientras éste se transfiere.</span><span class="sxs-lookup"><span data-stu-id="ed996-110">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="ed996-111">El cifrado proporciona privacidad de nivel de datos durante el transporte.</span><span class="sxs-lookup"><span data-stu-id="ed996-111">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="ed996-112">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="ed996-112">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="ed996-113">-None: sin protección.</span><span class="sxs-lookup"><span data-stu-id="ed996-113">-   None: No protection.</span></span><br /><span data-ttu-id="ed996-114">-Sign: los mensajes se firman.</span><span class="sxs-lookup"><span data-stu-id="ed996-114">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="ed996-115">-EncryptAndSign: los mensajes se firman y cifran.</span><span class="sxs-lookup"><span data-stu-id="ed996-115">-   EncryptAndSign: Messages are signed and encrypted.</span></span><br /><br /> <span data-ttu-id="ed996-116">El valor predeterminado es EncryptAndSign.</span><span class="sxs-lookup"><span data-stu-id="ed996-116">The default is EncryptAndSign.</span></span><br /><br /> <span data-ttu-id="ed996-117">Este atributo es del tipo <xref:System.Net.Security.ProtectionLevel>.</span><span class="sxs-lookup"><span data-stu-id="ed996-117">This attribute is of type <xref:System.Net.Security.ProtectionLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ed996-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ed996-118">Child Elements</span></span>  

 <span data-ttu-id="ed996-119">None</span><span class="sxs-lookup"><span data-stu-id="ed996-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ed996-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ed996-120">Parent Elements</span></span>  
  
|<span data-ttu-id="ed996-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="ed996-121">Element</span></span>|<span data-ttu-id="ed996-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="ed996-122">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="ed996-123">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="ed996-123">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ed996-124">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ed996-124">Remarks</span></span>  

 <span data-ttu-id="ed996-125">Transportes que utilizan un protocolo orientado a secuencias como TCP y canalizaciones con nombre que admiten las actualizaciones de transporte basadas en secuencias.</span><span class="sxs-lookup"><span data-stu-id="ed996-125">Transports that use a stream-oriented protocol such as TCP and named pipes support stream-based transport upgrades.</span></span> <span data-ttu-id="ed996-126">Concretamente, WCF proporciona actualizaciones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="ed996-126">Specifically, WCF provides security upgrades.</span></span> <span data-ttu-id="ed996-127">La configuración de esta seguridad de transporte está encapsulada por este elemento de configuración, así como por [\<sslStreamSecurity>](sslstreamsecurity.md) , que se puede configurar y agregar a un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="ed996-127">The configuration of this transport security is encapsulated by this configuration element  as well as by [\<sslStreamSecurity>](sslstreamsecurity.md), which can be configured and added to a custom binding</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed996-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ed996-128">See also</span></span>

- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>
- <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>
- [<span data-ttu-id="ed996-129">Enlaces</span><span class="sxs-lookup"><span data-stu-id="ed996-129">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="ed996-130">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="ed996-130">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="ed996-131">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="ed996-131">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
