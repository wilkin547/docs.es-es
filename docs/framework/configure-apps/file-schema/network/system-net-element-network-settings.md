---
title: Elemento <system.Net> (configuración de red)
description: El elemento de configuración de red <system.Net> contiene opciones que especifican cómo se conecta el .NET Framework a las opciones de red del .NET Framework.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.Net
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.Net
helpviewer_keywords:
- system.Net element
- <system.Net> element
ms.assetid: 52de4d6c-b24d-44aa-ba7d-6b5061f1357e
ms.openlocfilehash: 9f18c7a3586948c03391d609f437e216a91bc27f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504490"
---
# <a name="systemnet-element-network-settings"></a><span data-ttu-id="148f8-103">Elemento \<system.Net> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="148f8-103">\<system.Net> Element (Network Settings)</span></span>
<span data-ttu-id="148f8-104">Contiene valores que especifican cómo se conecta .NET Framework a la red.</span><span class="sxs-lookup"><span data-stu-id="148f8-104">Contains settings that specify how the .NET Framework connects to the network.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<system.net>**  
  
## <a name="syntax"></a><span data-ttu-id="148f8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="148f8-105">Syntax</span></span>  
  
```xml  
<system.net>
</system.net>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="148f8-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="148f8-106">Attributes and Elements</span></span>  
 <span data-ttu-id="148f8-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="148f8-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="148f8-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="148f8-108">Attributes</span></span>  
 <span data-ttu-id="148f8-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="148f8-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="148f8-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="148f8-110">Child Elements</span></span>  
  
|<span data-ttu-id="148f8-111">**Element**</span><span class="sxs-lookup"><span data-stu-id="148f8-111">**Element**</span></span>|<span data-ttu-id="148f8-112">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="148f8-112">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="148f8-113">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="148f8-113">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="148f8-114">Especifica los módulos que se usan para autenticar las solicitudes de Internet.</span><span class="sxs-lookup"><span data-stu-id="148f8-114">Specifies modules used to authenticate Internet requests.</span></span>|  
|[<span data-ttu-id="148f8-115">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="148f8-115">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="148f8-116">Especifica el número máximo de conexiones a un host de Internet.</span><span class="sxs-lookup"><span data-stu-id="148f8-116">Specifies the maximum number of connections to an Internet host.</span></span>|  
|[<span data-ttu-id="148f8-117">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="148f8-117">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="148f8-118">Configura el servidor proxy de Protocolo de transferencia de hipertexto (HTTP).</span><span class="sxs-lookup"><span data-stu-id="148f8-118">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
|[<span data-ttu-id="148f8-119">mailSettings</span><span class="sxs-lookup"><span data-stu-id="148f8-119">mailSettings</span></span>](mailsettings-element-network-settings.md)|<span data-ttu-id="148f8-120">Configura las opciones de envío de correo del Protocolo simple de transferencia de correo (SMTP).</span><span class="sxs-lookup"><span data-stu-id="148f8-120">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
|[<span data-ttu-id="148f8-121">requestCaching</span><span class="sxs-lookup"><span data-stu-id="148f8-121">requestCaching</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="148f8-122">Controla el mecanismo de almacenamiento en caché para las solicitudes de red.</span><span class="sxs-lookup"><span data-stu-id="148f8-122">Controls the caching mechanism for network requests.</span></span>|  
|[<span data-ttu-id="148f8-123">settings</span><span class="sxs-lookup"><span data-stu-id="148f8-123">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="148f8-124">Configura las opciones de red básicas para las clases de <xref:System.Net> y los espacios de nombres secundarios relacionados.</span><span class="sxs-lookup"><span data-stu-id="148f8-124">Configures basic network options for classes in the <xref:System.Net> and related child namespaces.</span></span>|  
|[<span data-ttu-id="148f8-125">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="148f8-125">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="148f8-126">Especifica los módulos que se van a usar para solicitar información de los hosts de Internet.</span><span class="sxs-lookup"><span data-stu-id="148f8-126">Specifies modules to use to request information from Internet hosts.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="148f8-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="148f8-127">Parent Elements</span></span>  
  
|<span data-ttu-id="148f8-128">**Element**</span><span class="sxs-lookup"><span data-stu-id="148f8-128">**Element**</span></span>|<span data-ttu-id="148f8-129">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="148f8-129">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="148f8-130">configuration</span><span class="sxs-lookup"><span data-stu-id="148f8-130">configuration</span></span>](../configuration-element.md)|<span data-ttu-id="148f8-131">Contiene la configuración de todos los espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="148f8-131">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="148f8-132">Comentarios</span><span class="sxs-lookup"><span data-stu-id="148f8-132">Remarks</span></span>  
 <span data-ttu-id="148f8-133">El [\<system.net>](system-net-element-network-settings.md) elemento contiene la configuración para las clases en <xref:System.Net> y los espacios de nombres secundarios relacionados.</span><span class="sxs-lookup"><span data-stu-id="148f8-133">The [\<system.net>](system-net-element-network-settings.md) element contains settings for classes in the <xref:System.Net> and related child namespaces.</span></span> <span data-ttu-id="148f8-134">La configuración configura los módulos de autenticación, la administración de conexiones, la configuración de correo, el servidor proxy y los módulos de solicitud de Internet para recibir información de los hosts de Internet.</span><span class="sxs-lookup"><span data-stu-id="148f8-134">The settings configure authentication modules, connection management, mail settings, the proxy server, and Internet request modules for receiving information from Internet hosts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="148f8-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="148f8-135">Example</span></span>  
 <span data-ttu-id="148f8-136">En el ejemplo siguiente se muestra una configuración típica utilizada por <xref:System.Net> las clases.</span><span class="sxs-lookup"><span data-stu-id="148f8-136">The following example shows a typical configuration used by <xref:System.Net> classes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="148f8-137">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="148f8-137">See also</span></span>

- [<span data-ttu-id="148f8-138">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="148f8-138">Network Settings Schema</span></span>](index.md)
