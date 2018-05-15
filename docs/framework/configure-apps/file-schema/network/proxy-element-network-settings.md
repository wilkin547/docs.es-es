---
title: '&lt;proxy&gt; Element (Network Settings)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/proxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#proxy
helpviewer_keywords:
- <proxy> element
- proxy element
ms.assetid: 37a548d8-fade-4ac5-82ec-b49b6c6cb22a
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: b5ae716994f9b8222a633699367c94480179c97b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltproxygt-element-network-settings"></a><span data-ttu-id="8ed51-102">&lt;proxy&gt; Element (Network Settings)</span><span class="sxs-lookup"><span data-stu-id="8ed51-102">&lt;proxy&gt; Element (Network Settings)</span></span>
<span data-ttu-id="8ed51-103">Define un servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="8ed51-103">Defines a proxy server.</span></span>  
  
 <span data-ttu-id="8ed51-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="8ed51-104">\<configuration></span></span>  
<span data-ttu-id="8ed51-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="8ed51-105">\<system.net></span></span>  
<span data-ttu-id="8ed51-106">\<defaultProxy ></span><span class="sxs-lookup"><span data-stu-id="8ed51-106">\<defaultProxy></span></span>  
<span data-ttu-id="8ed51-107">\<proxy ></span><span class="sxs-lookup"><span data-stu-id="8ed51-107">\<proxy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ed51-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8ed51-108">Syntax</span></span>  
  
```xml  
<proxy
  autoDetect="true|false|unspecified" 
  bypassonlocal="true|false|unspecified"
  proxyaddress="uriString"
  scriptLocation="uriString"
  usesystemdefault="true|false|unspecified"
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8ed51-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="8ed51-109">Attributes and Elements</span></span>  
 <span data-ttu-id="8ed51-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="8ed51-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8ed51-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="8ed51-111">Attributes</span></span>  
  
|<span data-ttu-id="8ed51-112">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="8ed51-112">**Attribute**</span></span>|<span data-ttu-id="8ed51-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="8ed51-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`autoDetect`|<span data-ttu-id="8ed51-114">Especifica si el proxy se detecta automáticamente.</span><span class="sxs-lookup"><span data-stu-id="8ed51-114">Specifies whether the proxy is automatically detected.</span></span> <span data-ttu-id="8ed51-115">El valor predeterminado es `unspecified`.</span><span class="sxs-lookup"><span data-stu-id="8ed51-115">The default value is `unspecified`.</span></span>|  
|`bypassonlocal`|<span data-ttu-id="8ed51-116">Especifica si se omite el proxy para los recursos locales.</span><span class="sxs-lookup"><span data-stu-id="8ed51-116">Specifies whether the proxy is bypassed for local resources.</span></span> <span data-ttu-id="8ed51-117">Los recursos locales incluyen el servidor local (http://localhost, http://loopback, o http://127.0.0.1) y un URI sin un período (http://webserver).</span><span class="sxs-lookup"><span data-stu-id="8ed51-117">Local resources include the local server (http://localhost, http://loopback, or http://127.0.0.1) and a URI without a period (http://webserver).</span></span> <span data-ttu-id="8ed51-118">El valor predeterminado es `unspecified`.</span><span class="sxs-lookup"><span data-stu-id="8ed51-118">The default value is `unspecified`.</span></span>|  
|`proxyaddress`|<span data-ttu-id="8ed51-119">Especifica al proxy de URI que se utiliza.</span><span class="sxs-lookup"><span data-stu-id="8ed51-119">Specifies the proxy URI to use.</span></span>|  
|`scriptLocation`|<span data-ttu-id="8ed51-120">Especifica la ubicación de la secuencia de comandos de configuración.</span><span class="sxs-lookup"><span data-stu-id="8ed51-120">Specifies the location of the configuration script.</span></span>|  
|`usesystemdefault`|<span data-ttu-id="8ed51-121">Especifica si se debe usar la configuración de proxy de Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="8ed51-121">Specifies whether to use Internet Explorer proxy settings.</span></span> <span data-ttu-id="8ed51-122">Si establece en `true`, los atributos subsiguientes invalidarán la configuración de proxy de Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="8ed51-122">If set to `true`, subsequent attributes will override Internet Explorer proxy settings.</span></span> <span data-ttu-id="8ed51-123">El valor predeterminado es `unspecified`.</span><span class="sxs-lookup"><span data-stu-id="8ed51-123">The default value is `unspecified`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8ed51-124">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8ed51-124">Child Elements</span></span>  
 <span data-ttu-id="8ed51-125">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="8ed51-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8ed51-126">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8ed51-126">Parent Elements</span></span>  
  
|<span data-ttu-id="8ed51-127">**Element**</span><span class="sxs-lookup"><span data-stu-id="8ed51-127">**Element**</span></span>|<span data-ttu-id="8ed51-128">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="8ed51-128">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="8ed51-129">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="8ed51-129">defaultProxy</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|<span data-ttu-id="8ed51-130">Configura el servidor proxy de Protocolo de transferencia de hipertexto (HTTP).</span><span class="sxs-lookup"><span data-stu-id="8ed51-130">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="text-value"></a><span data-ttu-id="8ed51-131">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="8ed51-131">Text Value</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8ed51-132">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8ed51-132">Remarks</span></span>  
 <span data-ttu-id="8ed51-133">El `proxy` elemento define un servidor proxy para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="8ed51-133">The `proxy` element defines a proxy server for an application.</span></span> <span data-ttu-id="8ed51-134">Si falta este elemento en el archivo de configuración, .NET Framework utilizará la configuración del proxy en Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="8ed51-134">If this element is missing from the configuration file, then the .NET Framework will use the proxy settings in Internet Explorer.</span></span>  
  
 <span data-ttu-id="8ed51-135">El valor de la `proxyaddress` atributo debe ser un indicador de recursos uniforme (URI) correcto.</span><span class="sxs-lookup"><span data-stu-id="8ed51-135">The value for the `proxyaddress` attribute should be a well-formed Uniform Resource Indicator (URI).</span></span>  
  
 <span data-ttu-id="8ed51-136">El `scriptLocation` atributo hace referencia a la detección automática de scripts de configuración de proxy.</span><span class="sxs-lookup"><span data-stu-id="8ed51-136">The `scriptLocation` attribute refers to the automatic detection of proxy configuration scripts.</span></span> <span data-ttu-id="8ed51-137">El <xref:System.Net.WebProxy> clase intentará encontrar un script de configuración (generalmente denominado Wpad.dat) cuando la **usar scripts de configuración automática** opción está seleccionada en el Explorador de Internet.</span><span class="sxs-lookup"><span data-stu-id="8ed51-137">The <xref:System.Net.WebProxy> class will attempt to locate a configuration script (usually named Wpad.dat) when the **Use automatic configuration script** option is selected in Internet Explorer.</span></span>  
  
 <span data-ttu-id="8ed51-138">Use la `usesystemdefault` atributo para las aplicaciones de la versión 1.1 de .NET Framework que va a migrar a la versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="8ed51-138">Use the `usesystemdefault` attribute for .NET Framework version 1.1 applications that are migrating to version 2.0.</span></span>  
  
 <span data-ttu-id="8ed51-139">Se produce una excepción si el `proxyaddress` atributo especifica un proxy predeterminado no válido.</span><span class="sxs-lookup"><span data-stu-id="8ed51-139">An exception is thrown if the `proxyaddress` attribute specifies an invalid default proxy.</span></span> <span data-ttu-id="8ed51-140">La propiedad <xref:System.Exception.InnerException%2A> en la excepción debería tener más información acerca de la causa del error.</span><span class="sxs-lookup"><span data-stu-id="8ed51-140">The <xref:System.Exception.InnerException%2A> property on the exception should have more information about the root cause of the error.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="8ed51-141">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="8ed51-141">Configuration Files</span></span>  
 <span data-ttu-id="8ed51-142">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="8ed51-142">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ed51-143">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8ed51-143">Example</span></span>  
 <span data-ttu-id="8ed51-144">En el siguiente ejemplo utiliza los valores predeterminados del proxy de Internet Explorer, especifica la dirección del proxy y omite al proxy para el acceso local.</span><span class="sxs-lookup"><span data-stu-id="8ed51-144">The following example uses the defaults from the Internet Explorer proxy, specifies the proxy address, and bypasses the proxy for local access.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="true"  
        proxyaddress="http://192.168.1.10:3128"  
        bypassonlocal="true"  
      />  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8ed51-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="8ed51-145">See Also</span></span>  
 <xref:System.Net.WebProxy?displayProperty=nameWithType>  
 [<span data-ttu-id="8ed51-146">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="8ed51-146">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
