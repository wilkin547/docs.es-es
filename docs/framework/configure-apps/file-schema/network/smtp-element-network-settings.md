---
title: Elemento <smtp> (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp
- http://schemas.microsoft.com/.NetConfiguration/v2.0#smtp
helpviewer_keywords:
- <smtp> element
- smtp element
ms.assetid: 220b0329-e384-4e0c-86b4-0945ad17efd9
ms.openlocfilehash: 2105a6dd25a7f6e5e4c1ce286be7f60beae1dca0
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697610"
---
# <a name="smtp-element-network-settings"></a><span data-ttu-id="9222c-102">\<smtp (elemento >) (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="9222c-102">\<smtp> Element (Network Settings)</span></span>
<span data-ttu-id="9222c-103">Configura el formato de entrega, el método de entrega y la dirección de remitente para enviar correos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="9222c-103">Configures the delivery format, delivery method, and from address for sending emails.</span></span>  
  
[<span data-ttu-id="9222c-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="9222c-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="9222c-105">&nbsp; @ no__t-1[ **@no__t -4System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="9222c-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="9222c-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<mailSettings >** ](mailsettings-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="9222c-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)</span></span>  
<span data-ttu-id="9222c-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<smtp >**</span><span class="sxs-lookup"><span data-stu-id="9222c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<smtp>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9222c-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9222c-108">Syntax</span></span>  
  
```xml  
<smtp  
  deliveryFormat="format"  
  deliveryMethod="method"  
  from="from address">
    <specifiedPickupDirectory>...</specifiedPickupDirectory>  
    <network>...</network>  
</smtp>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9222c-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9222c-109">Attributes and Elements</span></span>  
 <span data-ttu-id="9222c-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9222c-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9222c-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="9222c-111">Attributes</span></span>  
  
|<span data-ttu-id="9222c-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="9222c-112">Attribute</span></span>|<span data-ttu-id="9222c-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="9222c-113">Description</span></span>|  
|---------------|-----------------|  
|`deliveryFormat`|<span data-ttu-id="9222c-114">Especifica el formato de entrega para los mensajes de correo electrónico salientes.</span><span class="sxs-lookup"><span data-stu-id="9222c-114">Specifies the delivery format for outgoing emails.</span></span> <span data-ttu-id="9222c-115">Los valores aceptables son SevenBit e International.</span><span class="sxs-lookup"><span data-stu-id="9222c-115">Acceptable values are SevenBit and International.</span></span>|  
|`deliveryMethod`|<span data-ttu-id="9222c-116">Especifica el método de entrega para los mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="9222c-116">Specifies the delivery method for emails.</span></span> <span data-ttu-id="9222c-117">Los valores aceptables son Network, PickupDirectoryFromIis y SpecifiedPickupDirectory.</span><span class="sxs-lookup"><span data-stu-id="9222c-117">Acceptable values are Network, PickupDirectoryFromIis, and SpecifiedPickupDirectory.</span></span>|  
|`from`|<span data-ttu-id="9222c-118">Especifica la dirección de de los mensajes de correo electrónico salientes.</span><span class="sxs-lookup"><span data-stu-id="9222c-118">Specifies the from address for outgoing emails.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9222c-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9222c-119">Child Elements</span></span>  
  
|<span data-ttu-id="9222c-120">Atributo</span><span class="sxs-lookup"><span data-stu-id="9222c-120">Attribute</span></span>|<span data-ttu-id="9222c-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="9222c-121">Description</span></span>|  
|---------------|-----------------|  
|`specifiedPickupDirectory`|<span data-ttu-id="9222c-122">Configura el directorio local de un servidor SMTP (Protocolo simple de transferencia de correo).</span><span class="sxs-lookup"><span data-stu-id="9222c-122">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>|  
|`network`|<span data-ttu-id="9222c-123">Configura las opciones de red de un servidor SMTP externo.</span><span class="sxs-lookup"><span data-stu-id="9222c-123">Configures the network options for an external SMTP server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9222c-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9222c-124">Parent Elements</span></span>  
  
|<span data-ttu-id="9222c-125">**Element**</span><span class="sxs-lookup"><span data-stu-id="9222c-125">**Element**</span></span>|<span data-ttu-id="9222c-126">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="9222c-126">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="9222c-127">Elemento \<mailSettings> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="9222c-127">\<mailSettings> Element (Network Settings)</span></span>](mailsettings-element-network-settings.md)|<span data-ttu-id="9222c-128">Configura opciones de envío de correo.</span><span class="sxs-lookup"><span data-stu-id="9222c-128">Configures mail sending options.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="9222c-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9222c-129">Example</span></span>  
 <span data-ttu-id="9222c-130">En el ejemplo siguiente se especifican los parámetros SMTP adecuados para enviar correo electrónico con las credenciales de red predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="9222c-130">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="Network" deliveryFormat="SevenBit"  from="ben@contoso.com">  
        <network  
          host="localhost"  
          port="25"  
          defaultCredentials="true"  
        />  
      </smtp>  
    </mailSettings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9222c-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="9222c-131">See also</span></span>

- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpDeliveryFormat>
- <xref:System.Net.Mail.SmtpDeliveryMethod>
- [<span data-ttu-id="9222c-132">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="9222c-132">Network Settings Schema</span></span>](index.md)
