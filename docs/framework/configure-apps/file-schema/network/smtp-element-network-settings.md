---
title: '&lt;SMTP&gt; elemento (configuración de red)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp
- http://schemas.microsoft.com/.NetConfiguration/v2.0#smtp
helpviewer_keywords:
- <smtp> element
- smtp element
ms.assetid: 220b0329-e384-4e0c-86b4-0945ad17efd9
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 56912e09d24fc83e93a91cc42b1d96dcc68210f2
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32741898"
---
# <a name="ltsmtpgt-element-network-settings"></a><span data-ttu-id="e03df-102">&lt;SMTP&gt; elemento (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="e03df-102">&lt;smtp&gt; Element (Network Settings)</span></span>
<span data-ttu-id="e03df-103">Configura el formato de entrega, el método de entrega y de dirección para el envío de mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="e03df-103">Configures the delivery format, delivery method, and from address for sending emails.</span></span>  
  
 <span data-ttu-id="e03df-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="e03df-104">\<configuration></span></span>  
<span data-ttu-id="e03df-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="e03df-105">\<system.net></span></span>  
<span data-ttu-id="e03df-106">\<mailSettings ></span><span class="sxs-lookup"><span data-stu-id="e03df-106">\<mailSettings></span></span>  
<span data-ttu-id="e03df-107">\<SMTP ></span><span class="sxs-lookup"><span data-stu-id="e03df-107">\<smtp></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e03df-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e03df-108">Syntax</span></span>  
  
```xml  
      <smtp  
        deliveryFormat="format"   
        deliveryMethod="method"   
        from="from address">
          <specifiedPickupDirectory> … </ specifiedPickupDirectory >  
          <network> … </network>  
      </smtp>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e03df-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e03df-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e03df-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e03df-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e03df-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="e03df-111">Attributes</span></span>  
  
|<span data-ttu-id="e03df-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="e03df-112">Attribute</span></span>|<span data-ttu-id="e03df-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="e03df-113">Description</span></span>|  
|---------------|-----------------|  
|`deliveryFormat`|<span data-ttu-id="e03df-114">Especifica el formato de entrega de correos electrónicos de salida.</span><span class="sxs-lookup"><span data-stu-id="e03df-114">Specifies the delivery format for outgoing emails.</span></span> <span data-ttu-id="e03df-115">Los valores aceptables son SevenBit e International.</span><span class="sxs-lookup"><span data-stu-id="e03df-115">Acceptable values are SevenBit and International.</span></span>|  
|`deliveryMethod`|<span data-ttu-id="e03df-116">Especifica el método de entrega de mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="e03df-116">Specifies the delivery method for emails.</span></span> <span data-ttu-id="e03df-117">Los valores aceptables son network, pickupDirectoryFromIis y specifiedPickupDirectory.</span><span class="sxs-lookup"><span data-stu-id="e03df-117">Acceptable values are network, pickupDirectoryFromIis, and specifiedPickupDirectory.</span></span>|  
|`from`|<span data-ttu-id="e03df-118">Especifica el de la dirección de correo electrónico saliente.</span><span class="sxs-lookup"><span data-stu-id="e03df-118">Specifies the from address for outgoing emails.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e03df-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e03df-119">Child Elements</span></span>  
  
|<span data-ttu-id="e03df-120">Atributo</span><span class="sxs-lookup"><span data-stu-id="e03df-120">Attribute</span></span>|<span data-ttu-id="e03df-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="e03df-121">Description</span></span>|  
|---------------|-----------------|  
|`specifiedPickupDirectory`|<span data-ttu-id="e03df-122">Configura el directorio local de un servidor SMTP (Protocolo simple de transferencia de correo).</span><span class="sxs-lookup"><span data-stu-id="e03df-122">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>|  
|`network`|<span data-ttu-id="e03df-123">Configura las opciones de red de un servidor SMTP externo.</span><span class="sxs-lookup"><span data-stu-id="e03df-123">Configures the network options for an external SMTP server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e03df-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e03df-124">Parent Elements</span></span>  
  
|<span data-ttu-id="e03df-125">**Element**</span><span class="sxs-lookup"><span data-stu-id="e03df-125">**Element**</span></span>|<span data-ttu-id="e03df-126">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="e03df-126">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="e03df-127">Elemento \<mailSettings> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="e03df-127">\<mailSettings> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/mailsettings-element-network-settings.md)|<span data-ttu-id="e03df-128">Configura opciones de envío de correo.</span><span class="sxs-lookup"><span data-stu-id="e03df-128">Configures mail sending options.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e03df-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e03df-129">Example</span></span>  
 <span data-ttu-id="e03df-130">En el ejemplo siguiente se especifica los parámetros SMTP adecuados para enviar correo electrónico mediante las credenciales de red predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="e03df-130">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="network" deliveryFormat="SevenBit"  from="ben@contoso.com">  
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
  
## <a name="see-also"></a><span data-ttu-id="e03df-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="e03df-131">See Also</span></span>  
 <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>  
 <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>  
 <xref:System.Net.Mail.SmtpDeliveryFormat>  
 <xref:System.Net.Mail.SmtpDeliveryMethod>  
 [<span data-ttu-id="e03df-132">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="e03df-132">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
