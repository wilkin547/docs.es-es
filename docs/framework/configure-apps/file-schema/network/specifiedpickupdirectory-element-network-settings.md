---
title: '&lt;specifiedPickupDirectory&gt; Element (Network Settings)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#specifiedPickupDirectory
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/specifiedPickupDirectory
helpviewer_keywords:
- specifiedPickupDirectory element
- <specifiedPickupDirectory> element
ms.assetid: 0121f49d-bff2-4bc6-af06-f1628dcd61f1
caps.latest.revision: "8"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 0df8cb46943862e3de66faa5551f550cb232f212
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltspecifiedpickupdirectorygt-element-network-settings"></a><span data-ttu-id="009be-102">&lt;specifiedPickupDirectory&gt; Element (Network Settings)</span><span class="sxs-lookup"><span data-stu-id="009be-102">&lt;specifiedPickupDirectory&gt; Element (Network Settings)</span></span>
<span data-ttu-id="009be-103">Configura el directorio local de un servidor SMTP (Protocolo simple de transferencia de correo).</span><span class="sxs-lookup"><span data-stu-id="009be-103">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>  
  
 <span data-ttu-id="009be-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="009be-104">\<configuration></span></span>  
<span data-ttu-id="009be-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="009be-105">\<system.net></span></span>  
<span data-ttu-id="009be-106">\<mailSettings ></span><span class="sxs-lookup"><span data-stu-id="009be-106">\<mailSettings></span></span>  
<span data-ttu-id="009be-107">\<SMTP ></span><span class="sxs-lookup"><span data-stu-id="009be-107">\<smtp></span></span>  
<span data-ttu-id="009be-108">\<specifiedPickupDirectory ></span><span class="sxs-lookup"><span data-stu-id="009be-108">\<specifiedPickupDirectory></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="009be-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="009be-109">Syntax</span></span>  
  
```xml  
<specifiedPickupDirectory  
  pickupDirectoryLocation="directory"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="009be-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="009be-110">Attributes and Elements</span></span>  
 <span data-ttu-id="009be-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="009be-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="009be-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="009be-112">Attributes</span></span>  
  
|<span data-ttu-id="009be-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="009be-113">Attribute</span></span>|<span data-ttu-id="009be-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="009be-114">Description</span></span>|  
|---------------|-----------------|  
|`pickupDirectoryLocation`|<span data-ttu-id="009be-115">El directorio donde las aplicaciones guardan el correo electrónico para ser procesado posteriormente por el servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="009be-115">The directory where applications save e-mail for later processing by the SMTP server.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="009be-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="009be-116">Child Elements</span></span>  
 <span data-ttu-id="009be-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="009be-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="009be-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="009be-118">Parent Elements</span></span>  
  
|<span data-ttu-id="009be-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="009be-119">Element</span></span>|<span data-ttu-id="009be-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="009be-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="009be-121">\<SMTP > elemento (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="009be-121">\<smtp> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|<span data-ttu-id="009be-122">Configura opciones de envío de correo de Protocolo Simple de transferencia de correo (SMTP).</span><span class="sxs-lookup"><span data-stu-id="009be-122">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="009be-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="009be-123">Remarks</span></span>  
 <span data-ttu-id="009be-124">El `specifiedPickupDirectory` atributo establece el directorio donde las aplicaciones guardan los mensajes de correo electrónico para ser procesados por el servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="009be-124">The `specifiedPickupDirectory` attribute sets the directory where applications save mail messages to be processed by the SMTP server.</span></span>  
  
## <a name="example"></a><span data-ttu-id="009be-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="009be-125">Example</span></span>  
 <span data-ttu-id="009be-126">En el ejemplo siguiente se especifica c:\maildrop como el directorio de recogida de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="009be-126">The following example specifies c:\maildrop as the mail pickup directory.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="specifiedPickupDirectory">  
        <specifiedPickupDirectory  
          pickupDirectoryLocation="c:\maildrop"  
        />  
      </smtp>  
    </mailSettings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="009be-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="009be-127">See Also</span></span>  
 <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>  
 <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>  
 <xref:System.Net.Configuration.SmtpSpecifiedPickupDirectoryElement?displayProperty=nameWithType>  
 [<span data-ttu-id="009be-128">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="009be-128">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
