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
ms.openlocfilehash: 1b5f7406f995a86f0a192dbf3249c067dff570ea
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59140379"
---
# <a name="smtp-element-network-settings"></a><span data-ttu-id="75d1f-102">\<SMTP > elemento (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="75d1f-102">\<smtp> Element (Network Settings)</span></span>
<span data-ttu-id="75d1f-103">Configura el formato de entrega, el método de entrega y de dirección para el envío de mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="75d1f-103">Configures the delivery format, delivery method, and from address for sending emails.</span></span>  
  
 <span data-ttu-id="75d1f-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="75d1f-104">\<configuration></span></span>  
<span data-ttu-id="75d1f-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="75d1f-105">\<system.net></span></span>  
<span data-ttu-id="75d1f-106">\<mailSettings></span><span class="sxs-lookup"><span data-stu-id="75d1f-106">\<mailSettings></span></span>  
<span data-ttu-id="75d1f-107">\<smtp></span><span class="sxs-lookup"><span data-stu-id="75d1f-107">\<smtp></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75d1f-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="75d1f-108">Syntax</span></span>  
  
```xml  
<smtp  
  deliveryFormat="format"  
  deliveryMethod="method"  
  from="from address">
    <specifiedPickupDirectory>...</specifiedPickupDirectory>  
    <network>...</network>  
</smtp>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="75d1f-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="75d1f-109">Attributes and Elements</span></span>  
 <span data-ttu-id="75d1f-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="75d1f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="75d1f-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="75d1f-111">Attributes</span></span>  
  
|<span data-ttu-id="75d1f-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="75d1f-112">Attribute</span></span>|<span data-ttu-id="75d1f-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="75d1f-113">Description</span></span>|  
|---------------|-----------------|  
|`deliveryFormat`|<span data-ttu-id="75d1f-114">Especifica el formato de entrega de mensajes de correo electrónico salientes.</span><span class="sxs-lookup"><span data-stu-id="75d1f-114">Specifies the delivery format for outgoing emails.</span></span> <span data-ttu-id="75d1f-115">Los valores aceptables son SevenBit e International.</span><span class="sxs-lookup"><span data-stu-id="75d1f-115">Acceptable values are SevenBit and International.</span></span>|  
|`deliveryMethod`|<span data-ttu-id="75d1f-116">Especifica el método de entrega de mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="75d1f-116">Specifies the delivery method for emails.</span></span> <span data-ttu-id="75d1f-117">Los valores aceptables son Network, PickupDirectoryFromIis y SpecifiedPickupDirectory.</span><span class="sxs-lookup"><span data-stu-id="75d1f-117">Acceptable values are Network, PickupDirectoryFromIis, and SpecifiedPickupDirectory.</span></span>|  
|`from`|<span data-ttu-id="75d1f-118">Especifica la desde la dirección de correo saliente.</span><span class="sxs-lookup"><span data-stu-id="75d1f-118">Specifies the from address for outgoing emails.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="75d1f-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="75d1f-119">Child Elements</span></span>  
  
|<span data-ttu-id="75d1f-120">Atributo</span><span class="sxs-lookup"><span data-stu-id="75d1f-120">Attribute</span></span>|<span data-ttu-id="75d1f-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="75d1f-121">Description</span></span>|  
|---------------|-----------------|  
|`specifiedPickupDirectory`|<span data-ttu-id="75d1f-122">Configura el directorio local de un servidor SMTP (Protocolo simple de transferencia de correo).</span><span class="sxs-lookup"><span data-stu-id="75d1f-122">Configures the local directory for a Simple Mail Transport Protocol (SMTP) server.</span></span>|  
|`network`|<span data-ttu-id="75d1f-123">Configura las opciones de red de un servidor SMTP externo.</span><span class="sxs-lookup"><span data-stu-id="75d1f-123">Configures the network options for an external SMTP server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="75d1f-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="75d1f-124">Parent Elements</span></span>  
  
|<span data-ttu-id="75d1f-125">**Element**</span><span class="sxs-lookup"><span data-stu-id="75d1f-125">**Element**</span></span>|<span data-ttu-id="75d1f-126">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="75d1f-126">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="75d1f-127">Elemento \<mailSettings> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="75d1f-127">\<mailSettings> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/mailsettings-element-network-settings.md)|<span data-ttu-id="75d1f-128">Configura opciones de envío de correo.</span><span class="sxs-lookup"><span data-stu-id="75d1f-128">Configures mail sending options.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="75d1f-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="75d1f-129">Example</span></span>  
 <span data-ttu-id="75d1f-130">El ejemplo siguiente especifica los parámetros SMTP adecuados para enviar correo electrónico utilizando las credenciales de red predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="75d1f-130">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="75d1f-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="75d1f-131">See also</span></span>

- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpDeliveryFormat>
- <xref:System.Net.Mail.SmtpDeliveryMethod>
- [<span data-ttu-id="75d1f-132">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="75d1f-132">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
