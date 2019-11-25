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
ms.openlocfilehash: 1acc724bb14c3610f14d06452c30b3d5dac42e13
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089074"
---
# <a name="specifiedpickupdirectory-element-network-settings"></a><span data-ttu-id="c8b5b-102">\<elemento > specifiedPickupDirectory (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="c8b5b-102">\<specifiedPickupDirectory> Element (Network Settings)</span></span>
<span data-ttu-id="c8b5b-103">Configura el directorio local de un servidor SMTP (Protocolo simple de transferencia de correo).</span><span class="sxs-lookup"><span data-stu-id="c8b5b-103">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>  
  
<span data-ttu-id="c8b5b-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c8b5b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c8b5b-105">&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="c8b5b-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="c8b5b-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<mailSettings >** ](mailsettings-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="c8b5b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)</span></span>\
<span data-ttu-id="c8b5b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**SMTP**](smtp-element-network-settings.md) ></span><span class="sxs-lookup"><span data-stu-id="c8b5b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<smtp>**](smtp-element-network-settings.md)</span></span>\
<span data-ttu-id="c8b5b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<specifiedPickupDirectory >**</span><span class="sxs-lookup"><span data-stu-id="c8b5b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<specifiedPickupDirectory>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8b5b-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c8b5b-109">Syntax</span></span>  
  
```xml  
<specifiedPickupDirectory  
  pickupDirectoryLocation="directory"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c8b5b-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c8b5b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c8b5b-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c8b5b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c8b5b-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="c8b5b-112">Attributes</span></span>  
  
|<span data-ttu-id="c8b5b-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="c8b5b-113">Attribute</span></span>|<span data-ttu-id="c8b5b-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="c8b5b-114">Description</span></span>|  
|---------------|-----------------|  
|`pickupDirectoryLocation`|<span data-ttu-id="c8b5b-115">Directorio en el que las aplicaciones guardan el correo electrónico para su procesamiento posterior por parte del servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="c8b5b-115">The directory where applications save email for later processing by the SMTP server.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c8b5b-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c8b5b-116">Child Elements</span></span>  
 <span data-ttu-id="c8b5b-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c8b5b-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c8b5b-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c8b5b-118">Parent Elements</span></span>  
  
|<span data-ttu-id="c8b5b-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="c8b5b-119">Element</span></span>|<span data-ttu-id="c8b5b-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="c8b5b-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c8b5b-121">\<elemento > de SMTP (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="c8b5b-121">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="c8b5b-122">Configura las opciones de envío de correo del Protocolo simple de transferencia de correo (SMTP).</span><span class="sxs-lookup"><span data-stu-id="c8b5b-122">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c8b5b-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c8b5b-123">Remarks</span></span>  
 <span data-ttu-id="c8b5b-124">El atributo `specifiedPickupDirectory` establece el directorio en el que las aplicaciones guardan los mensajes de correo que el servidor SMTP va a procesar.</span><span class="sxs-lookup"><span data-stu-id="c8b5b-124">The `specifiedPickupDirectory` attribute sets the directory where applications save mail messages to be processed by the SMTP server.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8b5b-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c8b5b-125">Example</span></span>  
 <span data-ttu-id="c8b5b-126">En el ejemplo siguiente se especifica c:\maildrop como directorio de recogida de correo.</span><span class="sxs-lookup"><span data-stu-id="c8b5b-126">The following example specifies c:\maildrop as the mail pickup directory.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c8b5b-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="c8b5b-127">See also</span></span>

- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSpecifiedPickupDirectoryElement?displayProperty=nameWithType>
- [<span data-ttu-id="c8b5b-128">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="c8b5b-128">Network Settings Schema</span></span>](index.md)
