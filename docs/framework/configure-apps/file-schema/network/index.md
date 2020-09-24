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
ms.openlocfilehash: 8071fcfcdb16b6e71d8d7af05a704d8842b3e963
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158921"
---
# <a name="network-settings-schema"></a><span data-ttu-id="99da6-103">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="99da6-103">Network Settings Schema</span></span>

<span data-ttu-id="99da6-104">La configuración de red especifica cómo se conecta .NET Framework a Internet.</span><span class="sxs-lookup"><span data-stu-id="99da6-104">Network settings specify how the .NET Framework connects to the Internet.</span></span>

<span data-ttu-id="99da6-105">La \<system.net> configuración especifica cómo el .NET Framework se conecta a la red.</span><span class="sxs-lookup"><span data-stu-id="99da6-105">The \<system.net> settings specify how the .NET Framework connects to the network.</span></span> <span data-ttu-id="99da6-106">En la tabla siguiente se describe la función de cada elemento de configuración secundario bajo el [ \<system.Net> elemento (configuración de red)](system-net-element-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="99da6-106">The following table describes the function of each child configuration element under the [\<system.Net> Element (Network Settings)](system-net-element-network-settings.md).</span></span>  
  
|<span data-ttu-id="99da6-107">Elemento</span><span class="sxs-lookup"><span data-stu-id="99da6-107">Element</span></span>|<span data-ttu-id="99da6-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="99da6-108">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="99da6-109">Elemento \<authenticationModules> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="99da6-109">\<authenticationModules> Element (Network Settings)</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="99da6-110">Especifica los módulos usados para autenticar solicitudes de Internet.</span><span class="sxs-lookup"><span data-stu-id="99da6-110">Specifies the modules used to authenticate Internet requests.</span></span>|  
|[<span data-ttu-id="99da6-111">Elemento \<connectionManagement> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="99da6-111">\<connectionManagement> Element (Network Settings)</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="99da6-112">Especifica el número máximo de conexiones a hosts de Internet.</span><span class="sxs-lookup"><span data-stu-id="99da6-112">Specifies the maximum number of connections to Internet hosts.</span></span>|  
|[<span data-ttu-id="99da6-113">Elemento \<defaultProxy> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="99da6-113">\<defaultProxy> Element (Network Settings)</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="99da6-114">Especifica el servidor proxy usado para las solicitudes HTTP a Internet.</span><span class="sxs-lookup"><span data-stu-id="99da6-114">Specifies the proxy server used for HTTP requests to the Internet.</span></span>|  
|[<span data-ttu-id="99da6-115">Elemento \<mailSettings> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="99da6-115">\<mailSettings> Element (Network Settings)</span></span>](mailsettings-element-network-settings.md)|<span data-ttu-id="99da6-116">Contiene la configuración de opciones de envío de correo.</span><span class="sxs-lookup"><span data-stu-id="99da6-116">Contains settings for mail sending options.</span></span>|  
|[<span data-ttu-id="99da6-117">Elemento \<requestCaching> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="99da6-117">\<requestCaching> Element (Network Settings)</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="99da6-118">Controla el mecanismo de almacenamiento en caché para las solicitudes de red.</span><span class="sxs-lookup"><span data-stu-id="99da6-118">Controls the caching mechanism for network requests.</span></span>|  
|[<span data-ttu-id="99da6-119">Elemento \<webRequestModules> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="99da6-119">\<webRequestModules> Element (Network Settings)</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="99da6-120">Especifica los módulos usados para solicitar información de hosts de Internet.</span><span class="sxs-lookup"><span data-stu-id="99da6-120">Specifies the modules used to request information from Internet hosts.</span></span>|  
  
<span data-ttu-id="99da6-121">La \<uri> configuración especifica cómo el .NET Framework controla las direcciones web expresadas mediante identificadores uniformes de recursos (URI).</span><span class="sxs-lookup"><span data-stu-id="99da6-121">The \<uri> settings specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span> <span data-ttu-id="99da6-122">En la tabla siguiente se describe la función de cada elemento de configuración secundario bajo el [ \<uri> elemento (configuración de URI)](uri-element-uri-settings.md).</span><span class="sxs-lookup"><span data-stu-id="99da6-122">The following table describes the function of each child configuration element under the [\<uri> Element (Uri Settings)](uri-element-uri-settings.md).</span></span>  
  
|<span data-ttu-id="99da6-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="99da6-123">Element</span></span>|<span data-ttu-id="99da6-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="99da6-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="99da6-125">\<idn> Elemento (configuración de URI)</span><span class="sxs-lookup"><span data-stu-id="99da6-125">\<idn> Element (Uri Settings)</span></span>](idn-element-uri-settings.md)|<span data-ttu-id="99da6-126">Especifica si se aplica el análisis de nombres de dominio internacionalizados (IDN) a los nombres de dominio.</span><span class="sxs-lookup"><span data-stu-id="99da6-126">Specifies if Internationalized Domain Name (IDN) parsing is applied to domain names.</span></span>|  
|[<span data-ttu-id="99da6-127">\<iriParsing> Elemento (configuración de URI)</span><span class="sxs-lookup"><span data-stu-id="99da6-127">\<iriParsing> Element (Uri Settings)</span></span>](iriparsing-element-uri-settings.md)|<span data-ttu-id="99da6-128">Especifica si se aplica el análisis de identificadores de recursos internacionales (IRI) a un <xref:System.Uri> y si se deben aplicar reglas de análisis de IRI.</span><span class="sxs-lookup"><span data-stu-id="99da6-128">Specifies if International Resource Identifier (IRI) parsing is applied to a <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>|  
|[<span data-ttu-id="99da6-129">\<schemeSettings> Elemento (configuración de URI)</span><span class="sxs-lookup"><span data-stu-id="99da6-129">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="99da6-130">Especifica cómo se analizará un <xref:System.Uri> para esquemas concretos.</span><span class="sxs-lookup"><span data-stu-id="99da6-130">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="99da6-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="99da6-131">See also</span></span>

- [<span data-ttu-id="99da6-132">Configuración de aplicaciones de Internet</span><span class="sxs-lookup"><span data-stu-id="99da6-132">Configuring Internet Applications</span></span>](../../../network-programming/configuring-internet-applications.md)
- [<span data-ttu-id="99da6-133">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="99da6-133">Configuration File Schema</span></span>](../index.md)
