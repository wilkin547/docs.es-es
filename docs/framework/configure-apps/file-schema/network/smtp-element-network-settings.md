---
title: Elemento <smtp> (configuración de red)
description: El <smtp> elemento configuración de red configura el formato de entrega, el método de entrega y la dirección de remitente para el envío de opciones de correo electrónico en el .NET Framework.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp
- http://schemas.microsoft.com/.NetConfiguration/v2.0#smtp
helpviewer_keywords:
- <smtp> element
- smtp element
ms.assetid: 220b0329-e384-4e0c-86b4-0945ad17efd9
ms.openlocfilehash: 58f496b4a07f7d5531df897dd54bb6176111f1c4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178325"
---
# <a name="smtp-element-network-settings"></a><span data-ttu-id="0948c-103">Elemento \<smtp> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="0948c-103">\<smtp> Element (Network Settings)</span></span>

<span data-ttu-id="0948c-104">Configura el formato de entrega, el método de entrega y la dirección de remitente para enviar correos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="0948c-104">Configures the delivery format, delivery method, and from address for sending emails.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<smtp>**
  
## <a name="syntax"></a><span data-ttu-id="0948c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0948c-105">Syntax</span></span>  
  
```xml  
<smtp  
  deliveryFormat="format"  
  deliveryMethod="method"  
  from="from address">
    <specifiedPickupDirectory>...</specifiedPickupDirectory>  
    <network>...</network>  
</smtp>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0948c-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0948c-106">Attributes and Elements</span></span>  

 <span data-ttu-id="0948c-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0948c-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0948c-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="0948c-108">Attributes</span></span>  
  
|<span data-ttu-id="0948c-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="0948c-109">Attribute</span></span>|<span data-ttu-id="0948c-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="0948c-110">Description</span></span>|  
|---------------|-----------------|  
|`deliveryFormat`|<span data-ttu-id="0948c-111">Especifica el formato de entrega para los mensajes de correo electrónico salientes.</span><span class="sxs-lookup"><span data-stu-id="0948c-111">Specifies the delivery format for outgoing emails.</span></span> <span data-ttu-id="0948c-112">Los valores aceptables son SevenBit e International.</span><span class="sxs-lookup"><span data-stu-id="0948c-112">Acceptable values are SevenBit and International.</span></span>|  
|`deliveryMethod`|<span data-ttu-id="0948c-113">Especifica el método de entrega para los mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="0948c-113">Specifies the delivery method for emails.</span></span> <span data-ttu-id="0948c-114">Los valores aceptables son Network, PickupDirectoryFromIis y SpecifiedPickupDirectory.</span><span class="sxs-lookup"><span data-stu-id="0948c-114">Acceptable values are Network, PickupDirectoryFromIis, and SpecifiedPickupDirectory.</span></span>|  
|`from`|<span data-ttu-id="0948c-115">Especifica la dirección de de los mensajes de correo electrónico salientes.</span><span class="sxs-lookup"><span data-stu-id="0948c-115">Specifies the from address for outgoing emails.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0948c-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0948c-116">Child Elements</span></span>  
  
|<span data-ttu-id="0948c-117">Atributo</span><span class="sxs-lookup"><span data-stu-id="0948c-117">Attribute</span></span>|<span data-ttu-id="0948c-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="0948c-118">Description</span></span>|  
|---------------|-----------------|  
|`specifiedPickupDirectory`|<span data-ttu-id="0948c-119">Configura el directorio local de un servidor SMTP (Protocolo simple de transferencia de correo).</span><span class="sxs-lookup"><span data-stu-id="0948c-119">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>|  
|`network`|<span data-ttu-id="0948c-120">Configura las opciones de red de un servidor SMTP externo.</span><span class="sxs-lookup"><span data-stu-id="0948c-120">Configures the network options for an external SMTP server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0948c-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0948c-121">Parent Elements</span></span>  
  
|<span data-ttu-id="0948c-122">**Element**</span><span class="sxs-lookup"><span data-stu-id="0948c-122">**Element**</span></span>|<span data-ttu-id="0948c-123">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="0948c-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="0948c-124">Elemento \<mailSettings> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="0948c-124">\<mailSettings> Element (Network Settings)</span></span>](mailsettings-element-network-settings.md)|<span data-ttu-id="0948c-125">Configura opciones de envío de correo.</span><span class="sxs-lookup"><span data-stu-id="0948c-125">Configures mail sending options.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="0948c-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0948c-126">Example</span></span>  

 <span data-ttu-id="0948c-127">En el ejemplo siguiente se especifican los parámetros SMTP adecuados para enviar correo electrónico con las credenciales de red predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="0948c-127">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0948c-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0948c-128">See also</span></span>

- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpDeliveryFormat>
- <xref:System.Net.Mail.SmtpDeliveryMethod>
- [<span data-ttu-id="0948c-129">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="0948c-129">Network Settings Schema</span></span>](index.md)
