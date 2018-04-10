---
title: Esquema de la configuración de red
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- elements [.NET Framework], network configuration elements
- sending data, network configuration elements
- receiving data, network configuration elements
- configuration settings [.NET Framework], networks
- Internet, network configuration elements
- network configuration elements
- network settings
- connections [.NET Framework], network configuration elements
- network resources, network configuration elements
ms.assetid: f1de5a0f-76c5-4833-819f-5222b8146340
caps.latest.revision: 14
author: mcleblanc
ms.author: markl
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: d8f13b75d0558c002fd29938ce98d85f358acc9a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="network-settings-schema"></a><span data-ttu-id="20d34-102">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="20d34-102">Network Settings Schema</span></span>
<span data-ttu-id="20d34-103">La configuración de red especifica cómo se conecta .NET Framework a Internet.</span><span class="sxs-lookup"><span data-stu-id="20d34-103">Network settings specify how the .NET Framework connects to the Internet.</span></span> <span data-ttu-id="20d34-104">En la tabla siguiente se describe la función de cada elemento de configuración secundario bajo el [elemento \<system.Net> (configuración de red)](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="20d34-104">The following table describes the function of each child configuration element under the [\<system.Net> Element (Network Settings)](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md).</span></span>  
  
|<span data-ttu-id="20d34-105">Elemento</span><span class="sxs-lookup"><span data-stu-id="20d34-105">Element</span></span>|<span data-ttu-id="20d34-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="20d34-106">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="20d34-107">Elemento \<authenticationModules> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="20d34-107">\<authenticationModules> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|<span data-ttu-id="20d34-108">Especifica los módulos usados para autenticar solicitudes de Internet.</span><span class="sxs-lookup"><span data-stu-id="20d34-108">Specifies the modules used to authenticate Internet requests.</span></span>|  
|[<span data-ttu-id="20d34-109">Elemento \<connectionManagement> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="20d34-109">\<connectionManagement> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|<span data-ttu-id="20d34-110">Especifica el número máximo de conexiones a hosts de Internet.</span><span class="sxs-lookup"><span data-stu-id="20d34-110">Specifies the maximum number of connections to Internet hosts.</span></span>|  
|[<span data-ttu-id="20d34-111">Elemento \<defaultProxy> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="20d34-111">\<defaultProxy> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|<span data-ttu-id="20d34-112">Especifica el servidor proxy usado para las solicitudes HTTP a Internet.</span><span class="sxs-lookup"><span data-stu-id="20d34-112">Specifies the proxy server used for HTTP requests to the Internet.</span></span>|  
|[<span data-ttu-id="20d34-113">Elemento \<mailSettings> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="20d34-113">\<mailSettings> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/mailsettings-element-network-settings.md)|<span data-ttu-id="20d34-114">Contiene la configuración de opciones de envío de correo.</span><span class="sxs-lookup"><span data-stu-id="20d34-114">Contains settings for mail sending options.</span></span>|  
|[<span data-ttu-id="20d34-115">Elemento \<requestCaching> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="20d34-115">\<requestCaching> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|<span data-ttu-id="20d34-116">Especifica los módulos usados para solicitar información de hosts de Internet.</span><span class="sxs-lookup"><span data-stu-id="20d34-116">Specifies the modules used to request information from Internet hosts.</span></span>|  
|[<span data-ttu-id="20d34-117">Elemento \<requestCaching> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="20d34-117">\<requestCaching> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|<span data-ttu-id="20d34-118">Configura opciones de red básicas para el espacio de nombres <xref:System.Net?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="20d34-118">Configures basic network options for the <xref:System.Net?displayProperty=nameWithType> namespace.</span></span>|  
|[<span data-ttu-id="20d34-119">Elemento \<webRequestModules> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="20d34-119">\<webRequestModules> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|<span data-ttu-id="20d34-120">Especifica los módulos usados para solicitar información de hosts de Internet.</span><span class="sxs-lookup"><span data-stu-id="20d34-120">Specifies the modules used to request information from Internet hosts.</span></span>|  
  
 <span data-ttu-id="20d34-121">La configuración de URI especifica la manera en que .NET Framework controla las direcciones web expresadas mediante identificadores uniformes de recursos (URI).</span><span class="sxs-lookup"><span data-stu-id="20d34-121">Uri settings specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span> <span data-ttu-id="20d34-122">En la tabla siguiente se describe la función de cada elemento de configuración secundario bajo el [elemento \<Uri> (configuración de URI)](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md).</span><span class="sxs-lookup"><span data-stu-id="20d34-122">The following table describes the function of each child configuration element under the [\<Uri> Element (Uri Settings)](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md).</span></span>  
  
|<span data-ttu-id="20d34-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="20d34-123">Element</span></span>|<span data-ttu-id="20d34-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="20d34-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="20d34-125">Elemento \<idn> (Configuración de URI)</span><span class="sxs-lookup"><span data-stu-id="20d34-125">\<idn> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/idn-element-uri-settings.md)|<span data-ttu-id="20d34-126">Especifica si se aplica el análisis de nombres de dominio internacionalizados (IDN) a los nombres de dominio.</span><span class="sxs-lookup"><span data-stu-id="20d34-126">Specifies if Internationalized Domain Name (IDN) parsing is applied to domain names.</span></span>|  
|[<span data-ttu-id="20d34-127">Elemento \<iriParsing> (Configuración de URI)</span><span class="sxs-lookup"><span data-stu-id="20d34-127">\<iriParsing> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/iriparsing-element-uri-settings.md)|<span data-ttu-id="20d34-128">Especifica si se aplica el análisis de identificadores de recursos internacionales (IRI) a un <xref:System.Uri> y si se deben aplicar reglas de análisis de IRI.</span><span class="sxs-lookup"><span data-stu-id="20d34-128">Specifies if International Resource Identifier (IRI) parsing is applied to a <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>|  
|[<span data-ttu-id="20d34-129">Elemento \<schemeSettings> (configuración de URI)</span><span class="sxs-lookup"><span data-stu-id="20d34-129">\<schemeSettings> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|<span data-ttu-id="20d34-130">Especifica cómo se analizará un <xref:System.Uri> para esquemas concretos.</span><span class="sxs-lookup"><span data-stu-id="20d34-130">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="20d34-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="20d34-131">See Also</span></span>  
 [<span data-ttu-id="20d34-132">Configuración de aplicaciones de Internet</span><span class="sxs-lookup"><span data-stu-id="20d34-132">Configuring Internet Applications</span></span>](../../../../../docs/framework/network-programming/configuring-internet-applications.md)  
 [<span data-ttu-id="20d34-133">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="20d34-133">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
