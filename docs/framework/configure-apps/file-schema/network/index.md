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
ms.openlocfilehash: 5e3bd1b1734fc7fba50b72785531a8b001d6d741
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698153"
---
# <a name="network-settings-schema"></a><span data-ttu-id="37f86-102">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="37f86-102">Network Settings Schema</span></span>
<span data-ttu-id="37f86-103">La configuración de red especifica cómo se conecta .NET Framework a Internet.</span><span class="sxs-lookup"><span data-stu-id="37f86-103">Network settings specify how the .NET Framework connects to the Internet.</span></span>

<span data-ttu-id="37f86-104">La configuración de \<System. net > especifica cómo el .NET Framework se conecta a la red.</span><span class="sxs-lookup"><span data-stu-id="37f86-104">The \<system.net> settings specify how the .NET Framework connects to the network.</span></span> <span data-ttu-id="37f86-105">En la tabla siguiente se describe la función de cada elemento de configuración secundario bajo el [elemento \<system.Net> (configuración de red)](system-net-element-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="37f86-105">The following table describes the function of each child configuration element under the [\<system.Net> Element (Network Settings)](system-net-element-network-settings.md).</span></span>  
  
|<span data-ttu-id="37f86-106">Elemento</span><span class="sxs-lookup"><span data-stu-id="37f86-106">Element</span></span>|<span data-ttu-id="37f86-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="37f86-107">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="37f86-108">Elemento \<authenticationModules> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="37f86-108">\<authenticationModules> Element (Network Settings)</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="37f86-109">Especifica los módulos usados para autenticar solicitudes de Internet.</span><span class="sxs-lookup"><span data-stu-id="37f86-109">Specifies the modules used to authenticate Internet requests.</span></span>|  
|[<span data-ttu-id="37f86-110">Elemento \<connectionManagement> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="37f86-110">\<connectionManagement> Element (Network Settings)</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="37f86-111">Especifica el número máximo de conexiones a hosts de Internet.</span><span class="sxs-lookup"><span data-stu-id="37f86-111">Specifies the maximum number of connections to Internet hosts.</span></span>|  
|[<span data-ttu-id="37f86-112">Elemento \<defaultProxy> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="37f86-112">\<defaultProxy> Element (Network Settings)</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="37f86-113">Especifica el servidor proxy usado para las solicitudes HTTP a Internet.</span><span class="sxs-lookup"><span data-stu-id="37f86-113">Specifies the proxy server used for HTTP requests to the Internet.</span></span>|  
|[<span data-ttu-id="37f86-114">Elemento \<mailSettings> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="37f86-114">\<mailSettings> Element (Network Settings)</span></span>](mailsettings-element-network-settings.md)|<span data-ttu-id="37f86-115">Contiene la configuración de opciones de envío de correo.</span><span class="sxs-lookup"><span data-stu-id="37f86-115">Contains settings for mail sending options.</span></span>|  
|[<span data-ttu-id="37f86-116">Elemento \<requestCaching> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="37f86-116">\<requestCaching> Element (Network Settings)</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="37f86-117">Controla el mecanismo de almacenamiento en caché para las solicitudes de red.</span><span class="sxs-lookup"><span data-stu-id="37f86-117">Controls the caching mechanism for network requests.</span></span>|  
|[<span data-ttu-id="37f86-118">Elemento \<webRequestModules> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="37f86-118">\<webRequestModules> Element (Network Settings)</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="37f86-119">Especifica los módulos usados para solicitar información de hosts de Internet.</span><span class="sxs-lookup"><span data-stu-id="37f86-119">Specifies the modules used to request information from Internet hosts.</span></span>|  
  
<span data-ttu-id="37f86-120">La configuración de URI de \<> especifica cómo el .NET Framework controla las direcciones web expresadas mediante identificadores uniformes de recursos (URI).</span><span class="sxs-lookup"><span data-stu-id="37f86-120">The \<uri> settings specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span> <span data-ttu-id="37f86-121">En la tabla siguiente se describe la función de cada elemento de configuración secundario en el [elemento\<uri > (configuración de URI)](uri-element-uri-settings.md).</span><span class="sxs-lookup"><span data-stu-id="37f86-121">The following table describes the function of each child configuration element under the [\<uri> Element (Uri Settings)](uri-element-uri-settings.md).</span></span>  
  
|<span data-ttu-id="37f86-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="37f86-122">Element</span></span>|<span data-ttu-id="37f86-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="37f86-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="37f86-124">Elemento \<idn> (Configuración de URI)</span><span class="sxs-lookup"><span data-stu-id="37f86-124">\<idn> Element (Uri Settings)</span></span>](idn-element-uri-settings.md)|<span data-ttu-id="37f86-125">Especifica si se aplica el análisis de nombres de dominio internacionalizados (IDN) a los nombres de dominio.</span><span class="sxs-lookup"><span data-stu-id="37f86-125">Specifies if Internationalized Domain Name (IDN) parsing is applied to domain names.</span></span>|  
|[<span data-ttu-id="37f86-126">Elemento \<iriParsing> (Configuración de URI)</span><span class="sxs-lookup"><span data-stu-id="37f86-126">\<iriParsing> Element (Uri Settings)</span></span>](iriparsing-element-uri-settings.md)|<span data-ttu-id="37f86-127">Especifica si se aplica el análisis de identificadores de recursos internacionales (IRI) a un <xref:System.Uri> y si se deben aplicar reglas de análisis de IRI.</span><span class="sxs-lookup"><span data-stu-id="37f86-127">Specifies if International Resource Identifier (IRI) parsing is applied to a <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>|  
|[<span data-ttu-id="37f86-128">Elemento \<schemeSettings> (configuración de URI)</span><span class="sxs-lookup"><span data-stu-id="37f86-128">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="37f86-129">Especifica cómo se analizará un <xref:System.Uri> para esquemas concretos.</span><span class="sxs-lookup"><span data-stu-id="37f86-129">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="37f86-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="37f86-130">See also</span></span>

- [<span data-ttu-id="37f86-131">Configuración de aplicaciones de Internet</span><span class="sxs-lookup"><span data-stu-id="37f86-131">Configuring Internet Applications</span></span>](../../../network-programming/configuring-internet-applications.md)
- [<span data-ttu-id="37f86-132">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="37f86-132">Configuration File Schema</span></span>](../index.md)
