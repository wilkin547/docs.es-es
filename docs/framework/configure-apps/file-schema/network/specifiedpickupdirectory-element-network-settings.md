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
ms.sourcegitcommit: 0a798a7e9680e2d0a5a81a3eaa203870ea782883
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2020
ms.locfileid: "79154613"
---
# <a name="specifiedpickupdirectory-element-network-settings"></a><span data-ttu-id="86c97-102">Elemento \<specifiedPickupDirectory> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="86c97-102">\<specifiedPickupDirectory> Element (Network Settings)</span></span>
<span data-ttu-id="86c97-103">Configura el directorio local de un servidor SMTP (Protocolo simple de transferencia de correo).</span><span class="sxs-lookup"><span data-stu-id="86c97-103">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<smtp>**](smtp-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<specifiedPickupDirectory>**  
  
## <a name="syntax"></a><span data-ttu-id="86c97-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="86c97-104">Syntax</span></span>  
  
```xml  
<specifiedPickupDirectory  
  pickupDirectoryLocation="directory"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="86c97-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="86c97-105">Attributes and Elements</span></span>  
 <span data-ttu-id="86c97-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="86c97-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="86c97-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="86c97-107">Attributes</span></span>  
  
|<span data-ttu-id="86c97-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="86c97-108">Attribute</span></span>|<span data-ttu-id="86c97-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="86c97-109">Description</span></span>|  
|---------------|-----------------|  
|`pickupDirectoryLocation`|<span data-ttu-id="86c97-110">Directorio en el que las aplicaciones guardan el correo electrónico para su procesamiento posterior por parte del servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="86c97-110">The directory where applications save email for later processing by the SMTP server.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="86c97-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="86c97-111">Child Elements</span></span>  
 <span data-ttu-id="86c97-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="86c97-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="86c97-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="86c97-113">Parent Elements</span></span>  
  
|<span data-ttu-id="86c97-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="86c97-114">Element</span></span>|<span data-ttu-id="86c97-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="86c97-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="86c97-116">\<smtp>(Elemento, configuración de red)</span><span class="sxs-lookup"><span data-stu-id="86c97-116">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="86c97-117">Configura las opciones de envío de correo del Protocolo simple de transferencia de correo (SMTP).</span><span class="sxs-lookup"><span data-stu-id="86c97-117">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="86c97-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="86c97-118">Remarks</span></span>  
 <span data-ttu-id="86c97-119">El `specifiedPickupDirectory` atributo establece el directorio en el que las aplicaciones guardan los mensajes de correo que el servidor SMTP va a procesar.</span><span class="sxs-lookup"><span data-stu-id="86c97-119">The `specifiedPickupDirectory` attribute sets the directory where applications save mail messages to be processed by the SMTP server.</span></span>  
  
## <a name="example"></a><span data-ttu-id="86c97-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="86c97-120">Example</span></span>  
 <span data-ttu-id="86c97-121">En el ejemplo siguiente se especifica c:\maildrop como directorio de recogida de correo.</span><span class="sxs-lookup"><span data-stu-id="86c97-121">The following example specifies c:\maildrop as the mail pickup directory.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="86c97-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="86c97-122">See also</span></span>

- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSpecifiedPickupDirectoryElement?displayProperty=nameWithType>
- [<span data-ttu-id="86c97-123">Esquema de configuración de red</span><span class="sxs-lookup"><span data-stu-id="86c97-123">Network Settings Schema</span></span>](index.md)
