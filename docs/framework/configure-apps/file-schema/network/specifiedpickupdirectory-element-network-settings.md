---
title: Elemento <specifiedPickupDirectory> (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#specifiedPickupDirectory
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/specifiedPickupDirectory
helpviewer_keywords:
- specifiedPickupDirectory element
- <specifiedPickupDirectory> element
ms.assetid: 0121f49d-bff2-4bc6-af06-f1628dcd61f1
ms.openlocfilehash: 4b0cbaf9a7bfe2a9b1610811f4201253d219a6b2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154613"
---
# <a name="specifiedpickupdirectory-element-network-settings"></a><span data-ttu-id="80dff-102">\<elemento de> de PickupDirectory especificado (Configuración de red)</span><span class="sxs-lookup"><span data-stu-id="80dff-102">\<specifiedPickupDirectory> Element (Network Settings)</span></span>
<span data-ttu-id="80dff-103">Configura el directorio local de un servidor SMTP (Protocolo simple de transferencia de correo).</span><span class="sxs-lookup"><span data-stu-id="80dff-103">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>  
  
<span data-ttu-id="80dff-104">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="80dff-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="80dff-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="80dff-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="80dff-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="80dff-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)</span></span>\
<span data-ttu-id="80dff-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>smtp**](smtp-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="80dff-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<smtp>**](smtp-element-network-settings.md)</span></span>\
<span data-ttu-id="80dff-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<especificadoPickupDirectory>**</span><span class="sxs-lookup"><span data-stu-id="80dff-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<specifiedPickupDirectory>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80dff-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="80dff-109">Syntax</span></span>  
  
```xml  
<specifiedPickupDirectory  
  pickupDirectoryLocation="directory"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="80dff-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="80dff-110">Attributes and Elements</span></span>  
 <span data-ttu-id="80dff-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="80dff-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="80dff-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="80dff-112">Attributes</span></span>  
  
|<span data-ttu-id="80dff-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="80dff-113">Attribute</span></span>|<span data-ttu-id="80dff-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="80dff-114">Description</span></span>|  
|---------------|-----------------|  
|`pickupDirectoryLocation`|<span data-ttu-id="80dff-115">Directorio donde las aplicaciones guardan el correo electrónico para su posterior procesamiento por el servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="80dff-115">The directory where applications save email for later processing by the SMTP server.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="80dff-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="80dff-116">Child Elements</span></span>  
 <span data-ttu-id="80dff-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="80dff-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="80dff-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="80dff-118">Parent Elements</span></span>  
  
|<span data-ttu-id="80dff-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="80dff-119">Element</span></span>|<span data-ttu-id="80dff-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="80dff-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="80dff-121">\<Elemento> smtp (Configuración de red)</span><span class="sxs-lookup"><span data-stu-id="80dff-121">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="80dff-122">Configura las opciones de envío de correo del Protocolo simple de transporte de correo (SMTP).</span><span class="sxs-lookup"><span data-stu-id="80dff-122">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="80dff-123">Observaciones</span><span class="sxs-lookup"><span data-stu-id="80dff-123">Remarks</span></span>  
 <span data-ttu-id="80dff-124">El `specifiedPickupDirectory` atributo establece el directorio donde las aplicaciones guardan los mensajes de correo para que los procese el servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="80dff-124">The `specifiedPickupDirectory` attribute sets the directory where applications save mail messages to be processed by the SMTP server.</span></span>  
  
## <a name="example"></a><span data-ttu-id="80dff-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="80dff-125">Example</span></span>  
 <span data-ttu-id="80dff-126">En el ejemplo siguiente se especifica c:-maildrop como el directorio de recogida de correo.</span><span class="sxs-lookup"><span data-stu-id="80dff-126">The following example specifies c:\maildrop as the mail pickup directory.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="SpecifiedPickupDirectory">  
        <specifiedPickupDirectory  
          pickupDirectoryLocation="c:\maildrop"  
        />  
      </smtp>  
    </mailSettings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="80dff-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="80dff-127">See also</span></span>

- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSpecifiedPickupDirectoryElement?displayProperty=nameWithType>
- [<span data-ttu-id="80dff-128">Esquema de configuración de red</span><span class="sxs-lookup"><span data-stu-id="80dff-128">Network Settings Schema</span></span>](index.md)
