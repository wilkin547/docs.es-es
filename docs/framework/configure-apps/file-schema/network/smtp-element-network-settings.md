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
ms.openlocfilehash: 625c3cb82a8659c742b540724e5cf31be65a705e
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089100"
---
# <a name="smtp-element-network-settings"></a><span data-ttu-id="0deec-102">\<elemento > de SMTP (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="0deec-102">\<smtp> Element (Network Settings)</span></span>
<span data-ttu-id="0deec-103">Configura el formato de entrega, el método de entrega y la dirección de remitente para enviar correos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="0deec-103">Configures the delivery format, delivery method, and from address for sending emails.</span></span>  
  
<span data-ttu-id="0deec-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0deec-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0deec-105">&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="0deec-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="0deec-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<mailSettings >** ](mailsettings-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="0deec-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)</span></span>\
<span data-ttu-id="0deec-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**SMTP** ></span><span class="sxs-lookup"><span data-stu-id="0deec-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<smtp>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="0deec-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0deec-108">Syntax</span></span>  
  
```xml  
<smtp  
  deliveryFormat="format"  
  deliveryMethod="method"  
  from="from address">
    <specifiedPickupDirectory>...</specifiedPickupDirectory>  
    <network>...</network>  
</smtp>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0deec-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0deec-109">Attributes and Elements</span></span>  
 <span data-ttu-id="0deec-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0deec-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0deec-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="0deec-111">Attributes</span></span>  
  
|<span data-ttu-id="0deec-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="0deec-112">Attribute</span></span>|<span data-ttu-id="0deec-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="0deec-113">Description</span></span>|  
|---------------|-----------------|  
|`deliveryFormat`|<span data-ttu-id="0deec-114">Especifica el formato de entrega para los mensajes de correo electrónico salientes.</span><span class="sxs-lookup"><span data-stu-id="0deec-114">Specifies the delivery format for outgoing emails.</span></span> <span data-ttu-id="0deec-115">Los valores aceptables son SevenBit e International.</span><span class="sxs-lookup"><span data-stu-id="0deec-115">Acceptable values are SevenBit and International.</span></span>|  
|`deliveryMethod`|<span data-ttu-id="0deec-116">Especifica el método de entrega para los mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="0deec-116">Specifies the delivery method for emails.</span></span> <span data-ttu-id="0deec-117">Los valores aceptables son Network, PickupDirectoryFromIis y SpecifiedPickupDirectory.</span><span class="sxs-lookup"><span data-stu-id="0deec-117">Acceptable values are Network, PickupDirectoryFromIis, and SpecifiedPickupDirectory.</span></span>|  
|`from`|<span data-ttu-id="0deec-118">Especifica la dirección de de los mensajes de correo electrónico salientes.</span><span class="sxs-lookup"><span data-stu-id="0deec-118">Specifies the from address for outgoing emails.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0deec-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0deec-119">Child Elements</span></span>  
  
|<span data-ttu-id="0deec-120">Atributo</span><span class="sxs-lookup"><span data-stu-id="0deec-120">Attribute</span></span>|<span data-ttu-id="0deec-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="0deec-121">Description</span></span>|  
|---------------|-----------------|  
|`specifiedPickupDirectory`|<span data-ttu-id="0deec-122">Configura el directorio local de un servidor SMTP (Protocolo simple de transferencia de correo).</span><span class="sxs-lookup"><span data-stu-id="0deec-122">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>|  
|`network`|<span data-ttu-id="0deec-123">Configura las opciones de red de un servidor SMTP externo.</span><span class="sxs-lookup"><span data-stu-id="0deec-123">Configures the network options for an external SMTP server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0deec-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0deec-124">Parent Elements</span></span>  
  
|<span data-ttu-id="0deec-125">**Element**</span><span class="sxs-lookup"><span data-stu-id="0deec-125">**Element**</span></span>|<span data-ttu-id="0deec-126">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="0deec-126">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="0deec-127">Elemento \<mailSettings> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="0deec-127">\<mailSettings> Element (Network Settings)</span></span>](mailsettings-element-network-settings.md)|<span data-ttu-id="0deec-128">Configura opciones de envío de correo.</span><span class="sxs-lookup"><span data-stu-id="0deec-128">Configures mail sending options.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="0deec-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0deec-129">Example</span></span>  
 <span data-ttu-id="0deec-130">En el ejemplo siguiente se especifican los parámetros SMTP adecuados para enviar correo electrónico con las credenciales de red predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="0deec-130">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0deec-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="0deec-131">See also</span></span>

- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpDeliveryFormat>
- <xref:System.Net.Mail.SmtpDeliveryMethod>
- [<span data-ttu-id="0deec-132">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="0deec-132">Network Settings Schema</span></span>](index.md)
