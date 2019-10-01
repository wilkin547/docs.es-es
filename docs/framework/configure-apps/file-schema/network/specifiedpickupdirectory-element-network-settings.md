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
ms.openlocfilehash: 47aa357dac8b6bf71ce8c391004af16f8c98e347
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697592"
---
# <a name="specifiedpickupdirectory-element-network-settings"></a><span data-ttu-id="dc722-102">\<specifiedPickupDirectory (elemento >) (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="dc722-102">\<specifiedPickupDirectory> Element (Network Settings)</span></span>
<span data-ttu-id="dc722-103">Configura el directorio local de un servidor SMTP (Protocolo simple de transferencia de correo).</span><span class="sxs-lookup"><span data-stu-id="dc722-103">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>  
  
[<span data-ttu-id="dc722-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="dc722-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="dc722-105">&nbsp; @ no__t-1[ **@no__t -4System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="dc722-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="dc722-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<mailSettings >** ](mailsettings-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="dc722-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)</span></span>  
<span data-ttu-id="dc722-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5[ **\<smtp >** ](smtp-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="dc722-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<smtp>**](smtp-element-network-settings.md)</span></span>  
<span data-ttu-id="dc722-108">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7 **\<specifiedPickupDirectory >**</span><span class="sxs-lookup"><span data-stu-id="dc722-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<specifiedPickupDirectory>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc722-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dc722-109">Syntax</span></span>  
  
```xml  
<specifiedPickupDirectory  
  pickupDirectoryLocation="directory"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dc722-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="dc722-110">Attributes and Elements</span></span>  
 <span data-ttu-id="dc722-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="dc722-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dc722-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="dc722-112">Attributes</span></span>  
  
|<span data-ttu-id="dc722-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="dc722-113">Attribute</span></span>|<span data-ttu-id="dc722-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="dc722-114">Description</span></span>|  
|---------------|-----------------|  
|`pickupDirectoryLocation`|<span data-ttu-id="dc722-115">Directorio en el que las aplicaciones guardan el correo electrónico para su procesamiento posterior por parte del servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="dc722-115">The directory where applications save email for later processing by the SMTP server.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dc722-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="dc722-116">Child Elements</span></span>  
 <span data-ttu-id="dc722-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="dc722-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dc722-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="dc722-118">Parent Elements</span></span>  
  
|<span data-ttu-id="dc722-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="dc722-119">Element</span></span>|<span data-ttu-id="dc722-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="dc722-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dc722-121">\<SMTP (elemento >) (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="dc722-121">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="dc722-122">Configura las opciones de envío de correo del Protocolo simple de transferencia de correo (SMTP).</span><span class="sxs-lookup"><span data-stu-id="dc722-122">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dc722-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dc722-123">Remarks</span></span>  
 <span data-ttu-id="dc722-124">El atributo `specifiedPickupDirectory` establece el directorio en el que las aplicaciones guardan los mensajes de correo que el servidor SMTP va a procesar.</span><span class="sxs-lookup"><span data-stu-id="dc722-124">The `specifiedPickupDirectory` attribute sets the directory where applications save mail messages to be processed by the SMTP server.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dc722-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dc722-125">Example</span></span>  
 <span data-ttu-id="dc722-126">En el ejemplo siguiente se especifica c:\maildrop como directorio de recogida de correo.</span><span class="sxs-lookup"><span data-stu-id="dc722-126">The following example specifies c:\maildrop as the mail pickup directory.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="dc722-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="dc722-127">See also</span></span>

- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSpecifiedPickupDirectoryElement?displayProperty=nameWithType>
- [<span data-ttu-id="dc722-128">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="dc722-128">Network Settings Schema</span></span>](index.md)
