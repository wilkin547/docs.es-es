---
title: Elemento <system.Net> (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.Net
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.Net
helpviewer_keywords:
- system.Net element
- <system.Net> element
ms.assetid: 52de4d6c-b24d-44aa-ba7d-6b5061f1357e
ms.openlocfilehash: 88098f2afaad9728e38c4f9935b45f45826a0ca9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154561"
---
# <a name="systemnet-element-network-settings"></a><span data-ttu-id="fa7dd-102">Elemento \<system.Net> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="fa7dd-102">\<system.Net> Element (Network Settings)</span></span>
<span data-ttu-id="fa7dd-103">Contiene valores que especifican cómo se conecta .NET Framework a la red.</span><span class="sxs-lookup"><span data-stu-id="fa7dd-103">Contains settings that specify how the .NET Framework connects to the network.</span></span>  
  
[<span data-ttu-id="fa7dd-104">**\<configuración>**</span><span class="sxs-lookup"><span data-stu-id="fa7dd-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="fa7dd-105">&nbsp;&nbsp;**\<system.net>**</span><span class="sxs-lookup"><span data-stu-id="fa7dd-105">&nbsp;&nbsp;**\<system.net>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa7dd-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fa7dd-106">Syntax</span></span>  
  
```xml  
<system.net>
</system.net>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fa7dd-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="fa7dd-107">Attributes and Elements</span></span>  
 <span data-ttu-id="fa7dd-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="fa7dd-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fa7dd-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="fa7dd-109">Attributes</span></span>  
 <span data-ttu-id="fa7dd-110">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="fa7dd-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="fa7dd-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="fa7dd-111">Child Elements</span></span>  
  
|<span data-ttu-id="fa7dd-112">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="fa7dd-112">**Element**</span></span>|<span data-ttu-id="fa7dd-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="fa7dd-113">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="fa7dd-114">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="fa7dd-114">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="fa7dd-115">Especifica los módulos utilizados para autenticar las solicitudes de Internet.</span><span class="sxs-lookup"><span data-stu-id="fa7dd-115">Specifies modules used to authenticate Internet requests.</span></span>|  
|[<span data-ttu-id="fa7dd-116">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="fa7dd-116">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="fa7dd-117">Especifica el número máximo de conexiones a un host de Internet.</span><span class="sxs-lookup"><span data-stu-id="fa7dd-117">Specifies the maximum number of connections to an Internet host.</span></span>|  
|[<span data-ttu-id="fa7dd-118">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="fa7dd-118">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="fa7dd-119">Configura el servidor proxy de Protocolo de transferencia de hipertexto (HTTP).</span><span class="sxs-lookup"><span data-stu-id="fa7dd-119">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
|[<span data-ttu-id="fa7dd-120">mailSettings</span><span class="sxs-lookup"><span data-stu-id="fa7dd-120">mailSettings</span></span>](mailsettings-element-network-settings.md)|<span data-ttu-id="fa7dd-121">Configura las opciones de envío de correo del Protocolo simple de transporte de correo (SMTP).</span><span class="sxs-lookup"><span data-stu-id="fa7dd-121">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
|[<span data-ttu-id="fa7dd-122">requestCaching</span><span class="sxs-lookup"><span data-stu-id="fa7dd-122">requestCaching</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="fa7dd-123">Controla el mecanismo de almacenamiento en caché para las solicitudes de red.</span><span class="sxs-lookup"><span data-stu-id="fa7dd-123">Controls the caching mechanism for network requests.</span></span>|  
|[<span data-ttu-id="fa7dd-124">origen de datos</span><span class="sxs-lookup"><span data-stu-id="fa7dd-124">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="fa7dd-125">Configura las opciones de red <xref:System.Net> básicas para las clases de los espacios de nombres secundarios y relacionados.</span><span class="sxs-lookup"><span data-stu-id="fa7dd-125">Configures basic network options for classes in the <xref:System.Net> and related child namespaces.</span></span>|  
|[<span data-ttu-id="fa7dd-126">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="fa7dd-126">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="fa7dd-127">Especifica los módulos que se utilizarán para solicitar información a los hosts de Internet.</span><span class="sxs-lookup"><span data-stu-id="fa7dd-127">Specifies modules to use to request information from Internet hosts.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fa7dd-128">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="fa7dd-128">Parent Elements</span></span>  
  
|<span data-ttu-id="fa7dd-129">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="fa7dd-129">**Element**</span></span>|<span data-ttu-id="fa7dd-130">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="fa7dd-130">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="fa7dd-131">configuración</span><span class="sxs-lookup"><span data-stu-id="fa7dd-131">configuration</span></span>](../configuration-element.md)|<span data-ttu-id="fa7dd-132">Contiene la configuración de todos los espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="fa7dd-132">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fa7dd-133">Observaciones</span><span class="sxs-lookup"><span data-stu-id="fa7dd-133">Remarks</span></span>  
 <span data-ttu-id="fa7dd-134">El [ \<elemento system.net>](system-net-element-network-settings.md) contiene <xref:System.Net> la configuración de las clases de los espacios de nombres secundarios relacionados.</span><span class="sxs-lookup"><span data-stu-id="fa7dd-134">The [\<system.net>](system-net-element-network-settings.md) element contains settings for classes in the <xref:System.Net> and related child namespaces.</span></span> <span data-ttu-id="fa7dd-135">La configuración configura los módulos de autenticación, la administración de conexiones, la configuración de correo, el servidor proxy y los módulos de solicitud de Internet para recibir información de hosts de Internet.</span><span class="sxs-lookup"><span data-stu-id="fa7dd-135">The settings configure authentication modules, connection management, mail settings, the proxy server, and Internet request modules for receiving information from Internet hosts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa7dd-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fa7dd-136">Example</span></span>  
 <span data-ttu-id="fa7dd-137">En el ejemplo siguiente se <xref:System.Net> muestra una configuración típica utilizada por las clases.</span><span class="sxs-lookup"><span data-stu-id="fa7dd-137">The following example shows a typical configuration used by <xref:System.Net> classes.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <add type="System.Net.DigestClient" />  
      <add type="System.Net.NegotiateClient" />  
      <add type="System.Net.KerberosClient" />  
      <add type="System.Net.NtlmClient" />  
      <add type="System.Net.BasicClient" />  
    </authenticationModules>  
    <connectionManagement>  
      <add address="*" maxconnection="2" />  
    </connectionManagement>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="true"  
        bypassonlocal="true"  
      />  
    </defaultProxy>  
    <webRequestModules>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator"  
      />  
      <add prefix="https"  
           type="System.Net.HttpRequestCreator"  
      />  
      <add prefix="file"  
           type="System.Net.FileWebRequestCreator"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fa7dd-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fa7dd-138">See also</span></span>

- [<span data-ttu-id="fa7dd-139">Esquema de configuración de red</span><span class="sxs-lookup"><span data-stu-id="fa7dd-139">Network Settings Schema</span></span>](index.md)
