---
title: '&lt;mailSettings&gt; elemento (configuración de red)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#mailSettings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings
helpviewer_keywords:
- mailSettings element
- <mailSettings> element
ms.assetid: 54f0f153-17e5-4f49-afdc-deadb940c9c1
author: mcleblanc
ms.author: markl
ms.openlocfilehash: f3a706edaeba551139368568a7467e0cdab3524c
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2018
ms.locfileid: "47208600"
---
# <a name="ltmailsettingsgt-element-network-settings"></a><span data-ttu-id="3953d-102">&lt;mailSettings&gt; elemento (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="3953d-102">&lt;mailSettings&gt; Element (Network Settings)</span></span>
<span data-ttu-id="3953d-103">Configura opciones de envío de correo.</span><span class="sxs-lookup"><span data-stu-id="3953d-103">Configures mail sending options.</span></span>  

<span data-ttu-id="3953d-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="3953d-104">\<configuration></span></span>  
<span data-ttu-id="3953d-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="3953d-105">\<system.net></span></span>  
<span data-ttu-id="3953d-106">\<mailSettings ></span><span class="sxs-lookup"><span data-stu-id="3953d-106">\<mailSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3953d-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3953d-107">Syntax</span></span>  
  
```xml  
<mailSettings>
  <smtp> … </smtp>  
</mailSettings>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3953d-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3953d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="3953d-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3953d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3953d-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="3953d-110">Attributes</span></span>  
 <span data-ttu-id="3953d-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="3953d-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3953d-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3953d-112">Child Elements</span></span>  
  
|<span data-ttu-id="3953d-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="3953d-113">Attribute</span></span>|<span data-ttu-id="3953d-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="3953d-114">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="3953d-115">\<SMTP > elemento (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="3953d-115">\<smtp> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|<span data-ttu-id="3953d-116">Configura las opciones de Protocolo Simple de transferencia de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="3953d-116">Configures Simple Mail Transport Protocol options.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3953d-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3953d-117">Parent Elements</span></span>  
  
|<span data-ttu-id="3953d-118">**Element**</span><span class="sxs-lookup"><span data-stu-id="3953d-118">**Element**</span></span>|<span data-ttu-id="3953d-119">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="3953d-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="3953d-120">Elemento \<system.Net> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="3953d-120">\<system.Net> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="3953d-121">Contiene valores que especifican cómo se conecta .NET Framework a la red.</span><span class="sxs-lookup"><span data-stu-id="3953d-121">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="3953d-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3953d-122">Example</span></span>  
 <span data-ttu-id="3953d-123">El ejemplo siguiente especifica los parámetros SMTP adecuados para enviar correo electrónico utilizando las credenciales de red predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="3953d-123">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="Network">  
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
  
## <a name="see-also"></a><span data-ttu-id="3953d-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="3953d-124">See Also</span></span>  
 <xref:System.Net.Mail.SmtpClient>  
 [<span data-ttu-id="3953d-125">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="3953d-125">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
