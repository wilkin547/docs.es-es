---
title: Elemento <proxy> (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/proxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#proxy
helpviewer_keywords:
- <proxy> element
- proxy element
ms.assetid: 37a548d8-fade-4ac5-82ec-b49b6c6cb22a
ms.openlocfilehash: 590ea747c2fa9e5e85e5e9d05f6fb80fe60251d3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154795"
---
# <a name="proxy-element-network-settings"></a><span data-ttu-id="28316-102">\<Elemento de> proxy (Configuración de red)</span><span class="sxs-lookup"><span data-stu-id="28316-102">\<proxy> Element (Network Settings)</span></span>
<span data-ttu-id="28316-103">Define un servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="28316-103">Defines a proxy server.</span></span>  

<span data-ttu-id="28316-104">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="28316-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="28316-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="28316-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="28316-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="28316-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)</span></span>\
<span data-ttu-id="28316-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<proxy>**</span><span class="sxs-lookup"><span data-stu-id="28316-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<proxy>**</span></span>

## <a name="syntax"></a><span data-ttu-id="28316-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="28316-108">Syntax</span></span>  
  
```xml  
<proxy
  autoDetect="true|false|unspecified"
  bypassonlocal="true|false|unspecified"
  proxyaddress="uriString"
  scriptLocation="uriString"
  usesystemdefault="true|false|unspecified"
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="28316-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="28316-109">Attributes and Elements</span></span>  
 <span data-ttu-id="28316-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="28316-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="28316-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="28316-111">Attributes</span></span>  
  
|<span data-ttu-id="28316-112">**Atributo**</span><span class="sxs-lookup"><span data-stu-id="28316-112">**Attribute**</span></span>|<span data-ttu-id="28316-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="28316-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`autoDetect`|<span data-ttu-id="28316-114">Especifica si el servidor proxy se detecta automáticamente.</span><span class="sxs-lookup"><span data-stu-id="28316-114">Specifies whether the proxy is automatically detected.</span></span> <span data-ttu-id="28316-115">El valor predeterminado es `unspecified`.</span><span class="sxs-lookup"><span data-stu-id="28316-115">The default value is `unspecified`.</span></span>|  
|`bypassonlocal`|<span data-ttu-id="28316-116">Especifica si el servidor proxy se omite para los recursos locales.</span><span class="sxs-lookup"><span data-stu-id="28316-116">Specifies whether the proxy is bypassed for local resources.</span></span> <span data-ttu-id="28316-117">Los recursos locales`http://localhost`incluyen `http://loopback`el `http://127.0.0.1`servidor local ( ,`http://webserver`, o ) y un URI sin un punto ( ).</span><span class="sxs-lookup"><span data-stu-id="28316-117">Local resources include the local server (`http://localhost`, `http://loopback`, or `http://127.0.0.1`) and a URI without a period (`http://webserver`).</span></span> <span data-ttu-id="28316-118">El valor predeterminado es `unspecified`.</span><span class="sxs-lookup"><span data-stu-id="28316-118">The default value is `unspecified`.</span></span>|  
|`proxyaddress`|<span data-ttu-id="28316-119">Especifica el URI de proxy que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="28316-119">Specifies the proxy URI to use.</span></span>|  
|`scriptLocation`|<span data-ttu-id="28316-120">Especifica la ubicación del script de configuración.</span><span class="sxs-lookup"><span data-stu-id="28316-120">Specifies the location of the configuration script.</span></span> <span data-ttu-id="28316-121">No utilice `bypassonlocal` el atributo con este atributo.</span><span class="sxs-lookup"><span data-stu-id="28316-121">Do not use the `bypassonlocal` attribute with this attribute.</span></span> |  
|`usesystemdefault`|<span data-ttu-id="28316-122">Especifica si se debe utilizar la configuración de proxy de Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="28316-122">Specifies whether to use Internet Explorer proxy settings.</span></span> <span data-ttu-id="28316-123">Si se `true`establece en , los atributos subsiguientes invalidarán la configuración del proxy de Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="28316-123">If set to `true`, subsequent attributes will override Internet Explorer proxy settings.</span></span> <span data-ttu-id="28316-124">El valor predeterminado es `unspecified`.</span><span class="sxs-lookup"><span data-stu-id="28316-124">The default value is `unspecified`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="28316-125">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="28316-125">Child Elements</span></span>  
 <span data-ttu-id="28316-126">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="28316-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="28316-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="28316-127">Parent Elements</span></span>  
  
|<span data-ttu-id="28316-128">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="28316-128">**Element**</span></span>|<span data-ttu-id="28316-129">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="28316-129">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="28316-130">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="28316-130">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="28316-131">Configura el servidor proxy de Protocolo de transferencia de hipertexto (HTTP).</span><span class="sxs-lookup"><span data-stu-id="28316-131">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="text-value"></a><span data-ttu-id="28316-132">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="28316-132">Text Value</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="28316-133">Observaciones</span><span class="sxs-lookup"><span data-stu-id="28316-133">Remarks</span></span>  
 <span data-ttu-id="28316-134">El `proxy` elemento define un servidor proxy para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="28316-134">The `proxy` element defines a proxy server for an application.</span></span> <span data-ttu-id="28316-135">Si falta este elemento en el archivo de configuración, .NET Framework usará la configuración de proxy en Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="28316-135">If this element is missing from the configuration file, then the .NET Framework will use the proxy settings in Internet Explorer.</span></span>  
  
 <span data-ttu-id="28316-136">El valor `proxyaddress` del atributo debe ser un indicador uniforme de recursos (URI) bien formado.</span><span class="sxs-lookup"><span data-stu-id="28316-136">The value for the `proxyaddress` attribute should be a well-formed Uniform Resource Indicator (URI).</span></span>  
  
 <span data-ttu-id="28316-137">El `scriptLocation` atributo hace referencia a la detección automática de scripts de configuración de proxy.</span><span class="sxs-lookup"><span data-stu-id="28316-137">The `scriptLocation` attribute refers to the automatic detection of proxy configuration scripts.</span></span> <span data-ttu-id="28316-138">La <xref:System.Net.WebProxy> clase intentará localizar un script de configuración (normalmente denominado Wpad.dat) cuando se seleccione la opción Usar script de **configuración automática** en Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="28316-138">The <xref:System.Net.WebProxy> class will attempt to locate a configuration script (usually named Wpad.dat) when the **Use automatic configuration script** option is selected in Internet Explorer.</span></span> <span data-ttu-id="28316-139">Si `bypassonlocal` se establece en `scriptLocation` cualquier valor, se omite.</span><span class="sxs-lookup"><span data-stu-id="28316-139">If `bypassonlocal` is set to any value, `scriptLocation` is ignored.</span></span>
  
 <span data-ttu-id="28316-140">Use `usesystemdefault` el atributo para las aplicaciones de .NET Framework versión 1.1 que se migran a la versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="28316-140">Use the `usesystemdefault` attribute for .NET Framework version 1.1 applications that are migrating to version 2.0.</span></span>  
  
 <span data-ttu-id="28316-141">Se produce una excepción si el `proxyaddress` atributo especifica un proxy predeterminado no válido.</span><span class="sxs-lookup"><span data-stu-id="28316-141">An exception is thrown if the `proxyaddress` attribute specifies an invalid default proxy.</span></span> <span data-ttu-id="28316-142">La propiedad <xref:System.Exception.InnerException%2A> en la excepción debería tener más información acerca de la causa principal del error.</span><span class="sxs-lookup"><span data-stu-id="28316-142">The <xref:System.Exception.InnerException%2A> property on the exception should have more information about the root cause of the error.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="28316-143">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="28316-143">Configuration Files</span></span>  
 <span data-ttu-id="28316-144">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="28316-144">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="28316-145">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="28316-145">Example</span></span>  
 <span data-ttu-id="28316-146">En el ejemplo siguiente se usan los valores predeterminados del proxy de Internet Explorer, se especifica la dirección proxy y se omite el proxy para el acceso local.</span><span class="sxs-lookup"><span data-stu-id="28316-146">The following example uses the defaults from the Internet Explorer proxy, specifies the proxy address, and bypasses the proxy for local access.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="28316-147">Consulte también</span><span class="sxs-lookup"><span data-stu-id="28316-147">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="28316-148">Esquema de configuración de red</span><span class="sxs-lookup"><span data-stu-id="28316-148">Network Settings Schema</span></span>](index.md)
