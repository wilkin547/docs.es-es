---
title: <specifiedPickupDirectory> (Elemento, Configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#specifiedPickupDirectory
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/specifiedPickupDirectory
helpviewer_keywords:
- specifiedPickupDirectory element
- <specifiedPickupDirectory> element
ms.assetid: 0121f49d-bff2-4bc6-af06-f1628dcd61f1
ms.openlocfilehash: 6abee1b01e690633dabfd225b30fcb9b8b408dad
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55270828"
---
# <a name="specifiedpickupdirectory-element-network-settings"></a><span data-ttu-id="4608f-102">\<specifiedPickupDirectory > elemento (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="4608f-102">\<specifiedPickupDirectory> Element (Network Settings)</span></span>
<span data-ttu-id="4608f-103">Configura el directorio local de un servidor SMTP (Protocolo simple de transferencia de correo).</span><span class="sxs-lookup"><span data-stu-id="4608f-103">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>  
  
 <span data-ttu-id="4608f-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="4608f-104">\<configuration></span></span>  
<span data-ttu-id="4608f-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="4608f-105">\<system.net></span></span>  
<span data-ttu-id="4608f-106">\<mailSettings></span><span class="sxs-lookup"><span data-stu-id="4608f-106">\<mailSettings></span></span>  
<span data-ttu-id="4608f-107">\<smtp></span><span class="sxs-lookup"><span data-stu-id="4608f-107">\<smtp></span></span>  
<span data-ttu-id="4608f-108">\<specifiedPickupDirectory></span><span class="sxs-lookup"><span data-stu-id="4608f-108">\<specifiedPickupDirectory></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4608f-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4608f-109">Syntax</span></span>  
  
```xml  
<specifiedPickupDirectory  
  pickupDirectoryLocation="directory"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4608f-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4608f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="4608f-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4608f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4608f-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="4608f-112">Attributes</span></span>  
  
|<span data-ttu-id="4608f-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="4608f-113">Attribute</span></span>|<span data-ttu-id="4608f-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="4608f-114">Description</span></span>|  
|---------------|-----------------|  
|`pickupDirectoryLocation`|<span data-ttu-id="4608f-115">El directorio donde las aplicaciones guardan el correo electrónico para su procesamiento posterior por el servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="4608f-115">The directory where applications save email for later processing by the SMTP server.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4608f-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4608f-116">Child Elements</span></span>  
 <span data-ttu-id="4608f-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="4608f-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4608f-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4608f-118">Parent Elements</span></span>  
  
|<span data-ttu-id="4608f-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="4608f-119">Element</span></span>|<span data-ttu-id="4608f-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="4608f-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4608f-121">\<SMTP > elemento (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="4608f-121">\<smtp> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|<span data-ttu-id="4608f-122">Configura las opciones de envío de correo de Protocolo Simple de transferencia de correo (SMTP).</span><span class="sxs-lookup"><span data-stu-id="4608f-122">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4608f-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4608f-123">Remarks</span></span>  
 <span data-ttu-id="4608f-124">El `specifiedPickupDirectory` atributo establece el directorio donde las aplicaciones guardan los mensajes de correo para ser procesados por el servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="4608f-124">The `specifiedPickupDirectory` attribute sets the directory where applications save mail messages to be processed by the SMTP server.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4608f-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4608f-125">Example</span></span>  
 <span data-ttu-id="4608f-126">El ejemplo siguiente especifica c:\maildrop como el directorio de recogida de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="4608f-126">The following example specifies c:\maildrop as the mail pickup directory.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4608f-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="4608f-127">See also</span></span>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSpecifiedPickupDirectoryElement?displayProperty=nameWithType>
- [<span data-ttu-id="4608f-128">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="4608f-128">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
