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
ms.openlocfilehash: b2e31dee4f5aff2bf6cedf5c4e9ca235695b0a53
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659093"
---
# <a name="specifiedpickupdirectory-element-network-settings"></a><span data-ttu-id="5d6de-102">\<specifiedPickupDirectory > elemento (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="5d6de-102">\<specifiedPickupDirectory> Element (Network Settings)</span></span>
<span data-ttu-id="5d6de-103">Configura el directorio local de un servidor SMTP (Protocolo simple de transferencia de correo).</span><span class="sxs-lookup"><span data-stu-id="5d6de-103">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>  
  
 <span data-ttu-id="5d6de-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="5d6de-104">\<configuration></span></span>  
<span data-ttu-id="5d6de-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="5d6de-105">\<system.net></span></span>  
<span data-ttu-id="5d6de-106">\<mailSettings></span><span class="sxs-lookup"><span data-stu-id="5d6de-106">\<mailSettings></span></span>  
<span data-ttu-id="5d6de-107">\<smtp></span><span class="sxs-lookup"><span data-stu-id="5d6de-107">\<smtp></span></span>  
<span data-ttu-id="5d6de-108">\<specifiedPickupDirectory></span><span class="sxs-lookup"><span data-stu-id="5d6de-108">\<specifiedPickupDirectory></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d6de-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5d6de-109">Syntax</span></span>  
  
```xml  
<specifiedPickupDirectory  
  pickupDirectoryLocation="directory"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5d6de-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5d6de-110">Attributes and Elements</span></span>  
 <span data-ttu-id="5d6de-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5d6de-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5d6de-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="5d6de-112">Attributes</span></span>  
  
|<span data-ttu-id="5d6de-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="5d6de-113">Attribute</span></span>|<span data-ttu-id="5d6de-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5d6de-114">Description</span></span>|  
|---------------|-----------------|  
|`pickupDirectoryLocation`|<span data-ttu-id="5d6de-115">Directorio en el que las aplicaciones guardan el correo electrónico para su procesamiento posterior por parte del servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="5d6de-115">The directory where applications save email for later processing by the SMTP server.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5d6de-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5d6de-116">Child Elements</span></span>  
 <span data-ttu-id="5d6de-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="5d6de-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5d6de-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5d6de-118">Parent Elements</span></span>  
  
|<span data-ttu-id="5d6de-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="5d6de-119">Element</span></span>|<span data-ttu-id="5d6de-120">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5d6de-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5d6de-121">\<Elemento > de SMTP (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="5d6de-121">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="5d6de-122">Configura las opciones de envío de correo del Protocolo simple de transferencia de correo (SMTP).</span><span class="sxs-lookup"><span data-stu-id="5d6de-122">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d6de-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5d6de-123">Remarks</span></span>  
 <span data-ttu-id="5d6de-124">El `specifiedPickupDirectory` atributo establece el directorio en el que las aplicaciones guardan los mensajes de correo que el servidor SMTP va a procesar.</span><span class="sxs-lookup"><span data-stu-id="5d6de-124">The `specifiedPickupDirectory` attribute sets the directory where applications save mail messages to be processed by the SMTP server.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d6de-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5d6de-125">Example</span></span>  
 <span data-ttu-id="5d6de-126">En el ejemplo siguiente se especifica c:\maildrop como directorio de recogida de correo.</span><span class="sxs-lookup"><span data-stu-id="5d6de-126">The following example specifies c:\maildrop as the mail pickup directory.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5d6de-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="5d6de-127">See also</span></span>

- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSpecifiedPickupDirectoryElement?displayProperty=nameWithType>
- [<span data-ttu-id="5d6de-128">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="5d6de-128">Network Settings Schema</span></span>](index.md)
