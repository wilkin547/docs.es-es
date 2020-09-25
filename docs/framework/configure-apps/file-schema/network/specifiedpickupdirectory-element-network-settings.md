---
title: Elemento <specifiedPickupDirectory> (configuración de red)
description: El <specifiedPickupDirectory> elemento configuración de red configura el directorio local para las opciones del servidor SMTP en el .NET Framework.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#specifiedPickupDirectory
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/specifiedPickupDirectory
helpviewer_keywords:
- specifiedPickupDirectory element
- <specifiedPickupDirectory> element
ms.assetid: 0121f49d-bff2-4bc6-af06-f1628dcd61f1
ms.openlocfilehash: 5bb7fc5405b1ee2f0f054bc6e9f043a3f9fcd1ec
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176167"
---
# <a name="specifiedpickupdirectory-element-network-settings"></a><span data-ttu-id="236db-103">Elemento \<specifiedPickupDirectory> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="236db-103">\<specifiedPickupDirectory> Element (Network Settings)</span></span>

<span data-ttu-id="236db-104">Configura el directorio local de un servidor SMTP (Protocolo simple de transferencia de correo).</span><span class="sxs-lookup"><span data-stu-id="236db-104">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<smtp>**](smtp-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<specifiedPickupDirectory>**  
  
## <a name="syntax"></a><span data-ttu-id="236db-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="236db-105">Syntax</span></span>  
  
```xml  
<specifiedPickupDirectory  
  pickupDirectoryLocation="directory"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="236db-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="236db-106">Attributes and Elements</span></span>  

 <span data-ttu-id="236db-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="236db-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="236db-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="236db-108">Attributes</span></span>  
  
|<span data-ttu-id="236db-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="236db-109">Attribute</span></span>|<span data-ttu-id="236db-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="236db-110">Description</span></span>|  
|---------------|-----------------|  
|`pickupDirectoryLocation`|<span data-ttu-id="236db-111">Directorio en el que las aplicaciones guardan el correo electrónico para su procesamiento posterior por parte del servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="236db-111">The directory where applications save email for later processing by the SMTP server.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="236db-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="236db-112">Child Elements</span></span>  

 <span data-ttu-id="236db-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="236db-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="236db-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="236db-114">Parent Elements</span></span>  
  
|<span data-ttu-id="236db-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="236db-115">Element</span></span>|<span data-ttu-id="236db-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="236db-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="236db-117">Elemento \<smtp> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="236db-117">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="236db-118">Configura las opciones de envío de correo del Protocolo simple de transferencia de correo (SMTP).</span><span class="sxs-lookup"><span data-stu-id="236db-118">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="236db-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="236db-119">Remarks</span></span>  

 <span data-ttu-id="236db-120">El `specifiedPickupDirectory` atributo establece el directorio en el que las aplicaciones guardan los mensajes de correo que el servidor SMTP va a procesar.</span><span class="sxs-lookup"><span data-stu-id="236db-120">The `specifiedPickupDirectory` attribute sets the directory where applications save mail messages to be processed by the SMTP server.</span></span>  
  
## <a name="example"></a><span data-ttu-id="236db-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="236db-121">Example</span></span>  

 <span data-ttu-id="236db-122">En el ejemplo siguiente se especifica c:\maildrop como directorio de recogida de correo.</span><span class="sxs-lookup"><span data-stu-id="236db-122">The following example specifies c:\maildrop as the mail pickup directory.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="236db-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="236db-123">See also</span></span>

- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSpecifiedPickupDirectoryElement?displayProperty=nameWithType>
- [<span data-ttu-id="236db-124">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="236db-124">Network Settings Schema</span></span>](index.md)
