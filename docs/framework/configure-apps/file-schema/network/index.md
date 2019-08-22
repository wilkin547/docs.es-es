---
title: Esquema de la configuración de red
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
ms.openlocfilehash: 0f5d762a2b688bebcb7c027be6c639b6d64c069d
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664115"
---
# <a name="network-settings-schema"></a><span data-ttu-id="eadbd-102">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="eadbd-102">Network Settings Schema</span></span>
<span data-ttu-id="eadbd-103">La configuración de red especifica cómo se conecta .NET Framework a Internet.</span><span class="sxs-lookup"><span data-stu-id="eadbd-103">Network settings specify how the .NET Framework connects to the Internet.</span></span> <span data-ttu-id="eadbd-104">En la tabla siguiente se describe la función de cada elemento de configuración secundario bajo el [elemento \<system.Net> (configuración de red)](system-net-element-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="eadbd-104">The following table describes the function of each child configuration element under the [\<system.Net> Element (Network Settings)](system-net-element-network-settings.md).</span></span>  
  
|<span data-ttu-id="eadbd-105">Elemento</span><span class="sxs-lookup"><span data-stu-id="eadbd-105">Element</span></span>|<span data-ttu-id="eadbd-106">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="eadbd-106">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eadbd-107">Elemento \<authenticationModules> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="eadbd-107">\<authenticationModules> Element (Network Settings)</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="eadbd-108">Especifica los módulos usados para autenticar solicitudes de Internet.</span><span class="sxs-lookup"><span data-stu-id="eadbd-108">Specifies the modules used to authenticate Internet requests.</span></span>|  
|[<span data-ttu-id="eadbd-109">Elemento \<connectionManagement> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="eadbd-109">\<connectionManagement> Element (Network Settings)</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="eadbd-110">Especifica el número máximo de conexiones a hosts de Internet.</span><span class="sxs-lookup"><span data-stu-id="eadbd-110">Specifies the maximum number of connections to Internet hosts.</span></span>|  
|[<span data-ttu-id="eadbd-111">Elemento \<defaultProxy> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="eadbd-111">\<defaultProxy> Element (Network Settings)</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="eadbd-112">Especifica el servidor proxy usado para las solicitudes HTTP a Internet.</span><span class="sxs-lookup"><span data-stu-id="eadbd-112">Specifies the proxy server used for HTTP requests to the Internet.</span></span>|  
|[<span data-ttu-id="eadbd-113">Elemento \<mailSettings> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="eadbd-113">\<mailSettings> Element (Network Settings)</span></span>](mailsettings-element-network-settings.md)|<span data-ttu-id="eadbd-114">Contiene la configuración de opciones de envío de correo.</span><span class="sxs-lookup"><span data-stu-id="eadbd-114">Contains settings for mail sending options.</span></span>|  
|[<span data-ttu-id="eadbd-115">Elemento \<requestCaching> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="eadbd-115">\<requestCaching> Element (Network Settings)</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="eadbd-116">Controla el mecanismo de almacenamiento en caché para las solicitudes de red.</span><span class="sxs-lookup"><span data-stu-id="eadbd-116">Controls the caching mechanism for network requests.</span></span>|  
|[<span data-ttu-id="eadbd-117">Elemento \<webRequestModules> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="eadbd-117">\<webRequestModules> Element (Network Settings)</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="eadbd-118">Especifica los módulos usados para solicitar información de hosts de Internet.</span><span class="sxs-lookup"><span data-stu-id="eadbd-118">Specifies the modules used to request information from Internet hosts.</span></span>|  
  
 <span data-ttu-id="eadbd-119">La configuración de URI especifica la manera en que .NET Framework controla las direcciones web expresadas mediante identificadores uniformes de recursos (URI).</span><span class="sxs-lookup"><span data-stu-id="eadbd-119">Uri settings specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span> <span data-ttu-id="eadbd-120">En la tabla siguiente se describe la función de cada elemento de configuración secundario bajo el [elemento \<Uri> (configuración de URI)](uri-element-uri-settings.md).</span><span class="sxs-lookup"><span data-stu-id="eadbd-120">The following table describes the function of each child configuration element under the [\<Uri> Element (Uri Settings)](uri-element-uri-settings.md).</span></span>  
  
|<span data-ttu-id="eadbd-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="eadbd-121">Element</span></span>|<span data-ttu-id="eadbd-122">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="eadbd-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eadbd-123">Elemento \<idn> (Configuración de URI)</span><span class="sxs-lookup"><span data-stu-id="eadbd-123">\<idn> Element (Uri Settings)</span></span>](idn-element-uri-settings.md)|<span data-ttu-id="eadbd-124">Especifica si se aplica el análisis de nombres de dominio internacionalizados (IDN) a los nombres de dominio.</span><span class="sxs-lookup"><span data-stu-id="eadbd-124">Specifies if Internationalized Domain Name (IDN) parsing is applied to domain names.</span></span>|  
|[<span data-ttu-id="eadbd-125">Elemento \<iriParsing> (Configuración de URI)</span><span class="sxs-lookup"><span data-stu-id="eadbd-125">\<iriParsing> Element (Uri Settings)</span></span>](iriparsing-element-uri-settings.md)|<span data-ttu-id="eadbd-126">Especifica si se aplica el análisis de identificadores de recursos internacionales (IRI) a un <xref:System.Uri> y si se deben aplicar reglas de análisis de IRI.</span><span class="sxs-lookup"><span data-stu-id="eadbd-126">Specifies if International Resource Identifier (IRI) parsing is applied to a <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>|  
|[<span data-ttu-id="eadbd-127">Elemento \<schemeSettings> (configuración de URI)</span><span class="sxs-lookup"><span data-stu-id="eadbd-127">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="eadbd-128">Especifica cómo se analizará un <xref:System.Uri> para esquemas concretos.</span><span class="sxs-lookup"><span data-stu-id="eadbd-128">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="eadbd-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="eadbd-129">See also</span></span>

- [<span data-ttu-id="eadbd-130">Configuración de aplicaciones de Internet</span><span class="sxs-lookup"><span data-stu-id="eadbd-130">Configuring Internet Applications</span></span>](../../../network-programming/configuring-internet-applications.md)
- [<span data-ttu-id="eadbd-131">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="eadbd-131">Configuration File Schema</span></span>](../index.md)
