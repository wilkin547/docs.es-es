---
title: Esquema de la configuración de red
description: Obtenga información acerca del esquema de la configuración de red que especifica cómo el .NET Framework se conecta a Internet y controla los URI.
ms.date: 03/30/2017
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
ms.openlocfilehash: 6a22d7f1608db2e8909d0ead11e9110ec8a8a2c5
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504581"
---
# <a name="network-settings-schema"></a><span data-ttu-id="15d8a-103">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="15d8a-103">Network Settings Schema</span></span>
<span data-ttu-id="15d8a-104">La configuración de red especifica cómo se conecta .NET Framework a Internet.</span><span class="sxs-lookup"><span data-stu-id="15d8a-104">Network settings specify how the .NET Framework connects to the Internet.</span></span>

<span data-ttu-id="15d8a-105">La \<system.net> configuración especifica cómo el .NET Framework se conecta a la red.</span><span class="sxs-lookup"><span data-stu-id="15d8a-105">The \<system.net> settings specify how the .NET Framework connects to the network.</span></span> <span data-ttu-id="15d8a-106">En la tabla siguiente se describe la función de cada elemento de configuración secundario bajo el [ \<system.Net> elemento (configuración de red)](system-net-element-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="15d8a-106">The following table describes the function of each child configuration element under the [\<system.Net> Element (Network Settings)](system-net-element-network-settings.md).</span></span>  
  
|<span data-ttu-id="15d8a-107">Elemento</span><span class="sxs-lookup"><span data-stu-id="15d8a-107">Element</span></span>|<span data-ttu-id="15d8a-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="15d8a-108">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="15d8a-109">\<authenticationModules>(Elemento, configuración de red)</span><span class="sxs-lookup"><span data-stu-id="15d8a-109">\<authenticationModules> Element (Network Settings)</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="15d8a-110">Especifica los módulos usados para autenticar solicitudes de Internet.</span><span class="sxs-lookup"><span data-stu-id="15d8a-110">Specifies the modules used to authenticate Internet requests.</span></span>|  
|[<span data-ttu-id="15d8a-111">\<connectionManagement>(Elemento, configuración de red)</span><span class="sxs-lookup"><span data-stu-id="15d8a-111">\<connectionManagement> Element (Network Settings)</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="15d8a-112">Especifica el número máximo de conexiones a hosts de Internet.</span><span class="sxs-lookup"><span data-stu-id="15d8a-112">Specifies the maximum number of connections to Internet hosts.</span></span>|  
|[<span data-ttu-id="15d8a-113">\<defaultProxy>(Elemento, configuración de red)</span><span class="sxs-lookup"><span data-stu-id="15d8a-113">\<defaultProxy> Element (Network Settings)</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="15d8a-114">Especifica el servidor proxy usado para las solicitudes HTTP a Internet.</span><span class="sxs-lookup"><span data-stu-id="15d8a-114">Specifies the proxy server used for HTTP requests to the Internet.</span></span>|  
|[<span data-ttu-id="15d8a-115">\<mailSettings>(Elemento, configuración de red)</span><span class="sxs-lookup"><span data-stu-id="15d8a-115">\<mailSettings> Element (Network Settings)</span></span>](mailsettings-element-network-settings.md)|<span data-ttu-id="15d8a-116">Contiene la configuración de opciones de envío de correo.</span><span class="sxs-lookup"><span data-stu-id="15d8a-116">Contains settings for mail sending options.</span></span>|  
|[<span data-ttu-id="15d8a-117">\<requestCaching>(Elemento, configuración de red)</span><span class="sxs-lookup"><span data-stu-id="15d8a-117">\<requestCaching> Element (Network Settings)</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="15d8a-118">Controla el mecanismo de almacenamiento en caché para las solicitudes de red.</span><span class="sxs-lookup"><span data-stu-id="15d8a-118">Controls the caching mechanism for network requests.</span></span>|  
|[<span data-ttu-id="15d8a-119">\<webRequestModules>(Elemento, configuración de red)</span><span class="sxs-lookup"><span data-stu-id="15d8a-119">\<webRequestModules> Element (Network Settings)</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="15d8a-120">Especifica los módulos usados para solicitar información de hosts de Internet.</span><span class="sxs-lookup"><span data-stu-id="15d8a-120">Specifies the modules used to request information from Internet hosts.</span></span>|  
  
<span data-ttu-id="15d8a-121">La \<uri> configuración especifica cómo el .NET Framework controla las direcciones web expresadas mediante identificadores uniformes de recursos (URI).</span><span class="sxs-lookup"><span data-stu-id="15d8a-121">The \<uri> settings specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span> <span data-ttu-id="15d8a-122">En la tabla siguiente se describe la función de cada elemento de configuración secundario bajo el [ \<uri> elemento (configuración de URI)](uri-element-uri-settings.md).</span><span class="sxs-lookup"><span data-stu-id="15d8a-122">The following table describes the function of each child configuration element under the [\<uri> Element (Uri Settings)](uri-element-uri-settings.md).</span></span>  
  
|<span data-ttu-id="15d8a-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="15d8a-123">Element</span></span>|<span data-ttu-id="15d8a-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="15d8a-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="15d8a-125">\<idn>Elemento (configuración de URI)</span><span class="sxs-lookup"><span data-stu-id="15d8a-125">\<idn> Element (Uri Settings)</span></span>](idn-element-uri-settings.md)|<span data-ttu-id="15d8a-126">Especifica si se aplica el análisis de nombres de dominio internacionalizados (IDN) a los nombres de dominio.</span><span class="sxs-lookup"><span data-stu-id="15d8a-126">Specifies if Internationalized Domain Name (IDN) parsing is applied to domain names.</span></span>|  
|[<span data-ttu-id="15d8a-127">\<iriParsing>Elemento (configuración de URI)</span><span class="sxs-lookup"><span data-stu-id="15d8a-127">\<iriParsing> Element (Uri Settings)</span></span>](iriparsing-element-uri-settings.md)|<span data-ttu-id="15d8a-128">Especifica si se aplica el análisis de identificadores de recursos internacionales (IRI) a un <xref:System.Uri> y si se deben aplicar reglas de análisis de IRI.</span><span class="sxs-lookup"><span data-stu-id="15d8a-128">Specifies if International Resource Identifier (IRI) parsing is applied to a <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>|  
|[<span data-ttu-id="15d8a-129">\<schemeSettings>Elemento (configuración de URI)</span><span class="sxs-lookup"><span data-stu-id="15d8a-129">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="15d8a-130">Especifica cómo se analizará un <xref:System.Uri> para esquemas concretos.</span><span class="sxs-lookup"><span data-stu-id="15d8a-130">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="15d8a-131">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="15d8a-131">See also</span></span>

- [<span data-ttu-id="15d8a-132">Configuración de aplicaciones de Internet</span><span class="sxs-lookup"><span data-stu-id="15d8a-132">Configuring Internet Applications</span></span>](../../../network-programming/configuring-internet-applications.md)
- [<span data-ttu-id="15d8a-133">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="15d8a-133">Configuration File Schema</span></span>](../index.md)
