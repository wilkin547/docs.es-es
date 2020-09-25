---
title: Elemento <proxy> (configuración de red)
description: El <proxy> elemento de configuración de red define las opciones del servidor proxy en el .NET Framework. En este artículo se incluye un ejemplo.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/proxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#proxy
helpviewer_keywords:
- <proxy> element
- proxy element
ms.assetid: 37a548d8-fade-4ac5-82ec-b49b6c6cb22a
ms.openlocfilehash: 54b324dcd27d5827159bc2d773365e388a367d26
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91190220"
---
# <a name="proxy-element-network-settings"></a><span data-ttu-id="70200-104">Elemento \<proxy> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="70200-104">\<proxy> Element (Network Settings)</span></span>

<span data-ttu-id="70200-105">Define un servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="70200-105">Defines a proxy server.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<proxy>**

## <a name="syntax"></a><span data-ttu-id="70200-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="70200-106">Syntax</span></span>  
  
```xml  
<proxy
  autoDetect="True|False|Unspecified"
  bypassonlocal="True|False|Unspecified"
  proxyaddress="uriString"
  scriptLocation="uriString"
  usesystemdefault="True|False|Unspecified"
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="70200-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="70200-107">Attributes and Elements</span></span>  

 <span data-ttu-id="70200-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="70200-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="70200-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="70200-109">Attributes</span></span>  
  
|<span data-ttu-id="70200-110">**Atributo**</span><span class="sxs-lookup"><span data-stu-id="70200-110">**Attribute**</span></span>|<span data-ttu-id="70200-111">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="70200-111">**Description**</span></span>|  
|-------------------|---------------------|  
|`autoDetect`|<span data-ttu-id="70200-112">Especifica si el servidor proxy se detecta automáticamente.</span><span class="sxs-lookup"><span data-stu-id="70200-112">Specifies whether the proxy is automatically detected.</span></span> <span data-ttu-id="70200-113">El valor predeterminado es `Unspecified`.</span><span class="sxs-lookup"><span data-stu-id="70200-113">The default value is `Unspecified`.</span></span>|  
|`bypassonlocal`|<span data-ttu-id="70200-114">Especifica si el servidor proxy se omite para los recursos locales.</span><span class="sxs-lookup"><span data-stu-id="70200-114">Specifies whether the proxy is bypassed for local resources.</span></span> <span data-ttu-id="70200-115">Los recursos locales incluyen el servidor local ( `http://localhost` , `http://loopback` o `http://127.0.0.1` ) y un URI sin punto ( `http://webserver` ).</span><span class="sxs-lookup"><span data-stu-id="70200-115">Local resources include the local server (`http://localhost`, `http://loopback`, or `http://127.0.0.1`) and a URI without a period (`http://webserver`).</span></span> <span data-ttu-id="70200-116">El valor predeterminado es `Unspecified`.</span><span class="sxs-lookup"><span data-stu-id="70200-116">The default value is `Unspecified`.</span></span>|  
|`proxyaddress`|<span data-ttu-id="70200-117">Especifica el URI del proxy que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="70200-117">Specifies the proxy URI to use.</span></span>|  
|`scriptLocation`|<span data-ttu-id="70200-118">Especifica la ubicación del script de configuración.</span><span class="sxs-lookup"><span data-stu-id="70200-118">Specifies the location of the configuration script.</span></span> <span data-ttu-id="70200-119">No utilice el `bypassonlocal` atributo con este atributo.</span><span class="sxs-lookup"><span data-stu-id="70200-119">Do not use the `bypassonlocal` attribute with this attribute.</span></span> |  
|`usesystemdefault`|<span data-ttu-id="70200-120">Especifica si se va a usar la configuración de proxy de Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="70200-120">Specifies whether to use Internet Explorer proxy settings.</span></span> <span data-ttu-id="70200-121">Si se establece en `True` , los atributos subsiguientes invalidarán la configuración de proxy de Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="70200-121">If set to `True`, subsequent attributes will override Internet Explorer proxy settings.</span></span> <span data-ttu-id="70200-122">El valor predeterminado es `Unspecified`.</span><span class="sxs-lookup"><span data-stu-id="70200-122">The default value is `Unspecified`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="70200-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="70200-123">Child Elements</span></span>  

 <span data-ttu-id="70200-124">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="70200-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="70200-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="70200-125">Parent Elements</span></span>  
  
|<span data-ttu-id="70200-126">**Element**</span><span class="sxs-lookup"><span data-stu-id="70200-126">**Element**</span></span>|<span data-ttu-id="70200-127">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="70200-127">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="70200-128">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="70200-128">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="70200-129">Configura el servidor proxy de Protocolo de transferencia de hipertexto (HTTP).</span><span class="sxs-lookup"><span data-stu-id="70200-129">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="text-value"></a><span data-ttu-id="70200-130">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="70200-130">Text Value</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="70200-131">Observaciones</span><span class="sxs-lookup"><span data-stu-id="70200-131">Remarks</span></span>  

 <span data-ttu-id="70200-132">El `proxy` elemento define un servidor proxy para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="70200-132">The `proxy` element defines a proxy server for an application.</span></span> <span data-ttu-id="70200-133">Si este elemento no se encuentra en el archivo de configuración, el .NET Framework utilizará la configuración de proxy en Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="70200-133">If this element is missing from the configuration file, then the .NET Framework will use the proxy settings in Internet Explorer.</span></span>  
  
 <span data-ttu-id="70200-134">El valor del `proxyaddress` atributo debe ser un indicador uniforme de recursos (URI) correcto.</span><span class="sxs-lookup"><span data-stu-id="70200-134">The value for the `proxyaddress` attribute should be a well-formed Uniform Resource Indicator (URI).</span></span>  
  
 <span data-ttu-id="70200-135">El `scriptLocation` atributo hace referencia a la detección automática de scripts de configuración de proxy.</span><span class="sxs-lookup"><span data-stu-id="70200-135">The `scriptLocation` attribute refers to the automatic detection of proxy configuration scripts.</span></span> <span data-ttu-id="70200-136">La <xref:System.Net.WebProxy> clase intentará localizar un script de configuración (normalmente denominado WPAD. dat) cuando se selecciona la opción **usar script de configuración automática** en Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="70200-136">The <xref:System.Net.WebProxy> class will attempt to locate a configuration script (usually named Wpad.dat) when the **Use automatic configuration script** option is selected in Internet Explorer.</span></span> <span data-ttu-id="70200-137">Si `bypassonlocal` se establece en cualquier valor, `scriptLocation` se omite.</span><span class="sxs-lookup"><span data-stu-id="70200-137">If `bypassonlocal` is set to any value, `scriptLocation` is ignored.</span></span>
  
 <span data-ttu-id="70200-138">Use el `usesystemdefault` atributo para las aplicaciones de .NET Framework versión 1,1 que migran a la versión 2,0.</span><span class="sxs-lookup"><span data-stu-id="70200-138">Use the `usesystemdefault` attribute for .NET Framework version 1.1 applications that are migrating to version 2.0.</span></span>  
  
 <span data-ttu-id="70200-139">Se produce una excepción si el `proxyaddress` atributo especifica un proxy predeterminado no válido.</span><span class="sxs-lookup"><span data-stu-id="70200-139">An exception is thrown if the `proxyaddress` attribute specifies an invalid default proxy.</span></span> <span data-ttu-id="70200-140">La propiedad <xref:System.Exception.InnerException%2A> en la excepción debería tener más información acerca de la causa principal del error.</span><span class="sxs-lookup"><span data-stu-id="70200-140">The <xref:System.Exception.InnerException%2A> property on the exception should have more information about the root cause of the error.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="70200-141">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="70200-141">Configuration Files</span></span>  

 <span data-ttu-id="70200-142">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="70200-142">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="70200-143">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="70200-143">Example</span></span>  

 <span data-ttu-id="70200-144">En el ejemplo siguiente se usan los valores predeterminados del proxy de Internet Explorer, se especifica la dirección del proxy y se omite el proxy para el acceso local.</span><span class="sxs-lookup"><span data-stu-id="70200-144">The following example uses the defaults from the Internet Explorer proxy, specifies the proxy address, and bypasses the proxy for local access.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="True"  
        proxyaddress="http://192.168.1.10:3128"  
        bypassonlocal="True"  
      />  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="70200-145">Consulte también</span><span class="sxs-lookup"><span data-stu-id="70200-145">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="70200-146">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="70200-146">Network Settings Schema</span></span>](index.md)
