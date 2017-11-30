---
title: "Configuración de proxy"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Networking
- adaptive proxies
- static proxies
- Network Resources
- Internet, proxy configuration
- proxies
- network, proxy configuration
- proxies, configuring
ms.assetid: 353c0a8b-4cee-44f6-8e65-60e286743df9
caps.latest.revision: "14"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: b543097d0fc85c502bd36f22225958f9239ccd71
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="proxy-configuration"></a><span data-ttu-id="a7b01-102">Configuración de proxy</span><span class="sxs-lookup"><span data-stu-id="a7b01-102">Proxy Configuration</span></span>
<span data-ttu-id="a7b01-103">Un servidor proxy controla las solicitudes de cliente de recursos.</span><span class="sxs-lookup"><span data-stu-id="a7b01-103">A proxy server handles client requests for resources.</span></span> <span data-ttu-id="a7b01-104">Un proxy puede devolver un recurso solicitado de su caché o reenviar la solicitud al servidor donde reside el recurso.</span><span class="sxs-lookup"><span data-stu-id="a7b01-104">A proxy can return a requested resource from its cache or forward the request to the server where the resource resides.</span></span> <span data-ttu-id="a7b01-105">Los servidores proxy pueden mejorar el rendimiento de la red al reducir el número de solicitudes enviadas a servidores remotos.</span><span class="sxs-lookup"><span data-stu-id="a7b01-105">Proxies can improve network performance by reducing the number of requests sent to remote servers.</span></span> <span data-ttu-id="a7b01-106">Los servidores proxy también pueden usarse para restringir el acceso a los recursos.</span><span class="sxs-lookup"><span data-stu-id="a7b01-106">Proxies can also be used to restrict access to resources.</span></span>  
  
## <a name="adaptive-proxies"></a><span data-ttu-id="a7b01-107">Servidores proxy adaptables</span><span class="sxs-lookup"><span data-stu-id="a7b01-107">Adaptive Proxies</span></span>  
 <span data-ttu-id="a7b01-108">En .NET Framework, los servidores proxy son de dos tipos: adaptable y estático.</span><span class="sxs-lookup"><span data-stu-id="a7b01-108">In the .NET Framework, proxies come in two varieties: adaptive and static.</span></span> <span data-ttu-id="a7b01-109">Los servidores proxy adaptables ajustan su configuración cuando cambia la configuración de red.</span><span class="sxs-lookup"><span data-stu-id="a7b01-109">Adaptive proxies adjust their settings when the network configuration changes.</span></span> <span data-ttu-id="a7b01-110">Por ejemplo, si un usuario de un portátil inicia una conexión de red de acceso telefónico, un proxy adaptable podría reconocer este cambio, descubrir y ejecutar su nuevo script de configuración y ajustar su configuración de manera adecuada.</span><span class="sxs-lookup"><span data-stu-id="a7b01-110">For example, if a laptop user starts a dialup network connection, an adaptive proxy would recognize this change, discover and run its new configuration script, and adjust its settings appropriately.</span></span>  
  
 <span data-ttu-id="a7b01-111">Los servidores proxy adaptables se configuran por medio de un script de configuración (vea [Detección automática de proxy](../../../docs/framework/network-programming/automatic-proxy-detection.md)).</span><span class="sxs-lookup"><span data-stu-id="a7b01-111">Adaptive proxies are configured by a configuration script (see [Automatic Proxy Detection](../../../docs/framework/network-programming/automatic-proxy-detection.md)).</span></span> <span data-ttu-id="a7b01-112">El script genera un conjunto de protocolos de aplicación y un proxy para cada protocolo.</span><span class="sxs-lookup"><span data-stu-id="a7b01-112">The script generates a set of application protocols and a proxy for each protocol.</span></span>  
  
 <span data-ttu-id="a7b01-113">Varias opciones controlan cómo se ejecuta el script de configuración.</span><span class="sxs-lookup"><span data-stu-id="a7b01-113">Several options control how the configuration script is run.</span></span> <span data-ttu-id="a7b01-114">Puede especificar los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="a7b01-114">You can specify the following:</span></span>  
  
-   <span data-ttu-id="a7b01-115">Con qué frecuencia se descarga y se ejecuta el script de configuración.</span><span class="sxs-lookup"><span data-stu-id="a7b01-115">How often the configuration script is downloaded and run.</span></span>  
  
-   <span data-ttu-id="a7b01-116">Cuánto tiempo debe esperar a que se descargue el script.</span><span class="sxs-lookup"><span data-stu-id="a7b01-116">How long to wait for the script to download.</span></span>  
  
-   <span data-ttu-id="a7b01-117">Qué credenciales debe usar el sistema deben para tener acceso al proxy.</span><span class="sxs-lookup"><span data-stu-id="a7b01-117">Which credentials your system should use to access the proxy.</span></span>  
  
-   <span data-ttu-id="a7b01-118">Qué credenciales debe usar el sistema para descargar el script de configuración.</span><span class="sxs-lookup"><span data-stu-id="a7b01-118">Which credentials your system should use to download the configuration script.</span></span>  
  
 <span data-ttu-id="a7b01-119">Los cambios en el entorno de red pueden requerir que el sistema use un nuevo conjunto de servidores proxy.</span><span class="sxs-lookup"><span data-stu-id="a7b01-119">Changes in the network environment may require that the system use a new set of proxies.</span></span> <span data-ttu-id="a7b01-120">Si una conexión de red deja de funcionar o se inicializa una nueva conexión de red, el sistema debe descubrir el origen adecuado del script de configuración en el nuevo entorno y ejecutar el script nuevo.</span><span class="sxs-lookup"><span data-stu-id="a7b01-120">If a network connection goes down or a new network connection is initialized, the system must discover the appropriate source of the configuration script in the new environment and run the new script.</span></span>  
  
 <span data-ttu-id="a7b01-121">La siguiente tabla muestra las opciones de configuración para un proxy adaptable.</span><span class="sxs-lookup"><span data-stu-id="a7b01-121">The following table shows configuration options for an adaptive proxy.</span></span>  
  
|<span data-ttu-id="a7b01-122">Parámetro, atributo o propiedad del archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="a7b01-122">Attribute, property, or configuration file setting</span></span>|<span data-ttu-id="a7b01-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="a7b01-123">Description</span></span>|  
|--------------------------------------------------------|-----------------|  
|`scriptDownloadInterval`|<span data-ttu-id="a7b01-124">Tiempo transcurrido en segundos entre las descargas de scripts.</span><span class="sxs-lookup"><span data-stu-id="a7b01-124">Elapsed time in seconds between script downloads.</span></span>|  
|`scriptDownloadTimeout`|<span data-ttu-id="a7b01-125">Tiempo de espera (en segundos) para que se descargue el script.</span><span class="sxs-lookup"><span data-stu-id="a7b01-125">Time to wait (in seconds) for the script to download.</span></span>|  
|<span data-ttu-id="a7b01-126">`useDefaultCredentials` o <xref:System.Net.WebProxy.UseDefaultCredentials></span><span class="sxs-lookup"><span data-stu-id="a7b01-126">`useDefaultCredentials` or <xref:System.Net.WebProxy.UseDefaultCredentials></span></span>|<span data-ttu-id="a7b01-127">Controla si el sistema usa las credenciales de red predeterminadas para tener acceso a un proxy.</span><span class="sxs-lookup"><span data-stu-id="a7b01-127">Controls whether the system uses the default network credentials to access a proxy.</span></span>|  
|`useDefaultCredentialForScriptDownload`|<span data-ttu-id="a7b01-128">Controla si el sistema usa las credenciales de red predeterminadas para descargar el script de configuración.</span><span class="sxs-lookup"><span data-stu-id="a7b01-128">Controls whether the system uses the default network credentials to download the configuration script.</span></span>|  
|`usesystemdefaults`|<span data-ttu-id="a7b01-129">Controla si la configuración de proxy estática (dirección de proxy, lista de omisión y omitir para las direcciones locales) debe leerse de la configuración de proxy de Internet Explorer para el usuario.</span><span class="sxs-lookup"><span data-stu-id="a7b01-129">Controls whether the static proxy settings (proxy address, bypass list, and bypass on local) should be read from the Internet Explorer proxy settings for the user.</span></span> <span data-ttu-id="a7b01-130">Si este valor se establece en "true", se usará la configuración de proxy estática de Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="a7b01-130">If this value is set to "true", then the static proxy settings from Internet Explorer will be used.</span></span><br /><br /> <span data-ttu-id="a7b01-131">Si este valor es "false" o no se establece, la configuración de proxy estática se pueden especificar en la configuración y reemplazará la configuración de proxy de Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="a7b01-131">If this value is "false" or not set, then the static proxy settings can be specified in the configuration and will override the Internet Explorer proxy settings.</span></span> <span data-ttu-id="a7b01-132">Este valor debe establecerse en "false" o no establecerse para que se habiliten los servidores proxy adaptables.</span><span class="sxs-lookup"><span data-stu-id="a7b01-132">This value must also be set to "false" or not set for adaptive proxies to be enabled.</span></span>|  
  
 <span data-ttu-id="a7b01-133">En el ejemplo siguiente se muestra una configuración típica de proxy adaptable.</span><span class="sxs-lookup"><span data-stu-id="a7b01-133">The following example shows a typical adaptive proxy configuration.</span></span>  
  
```xml  
<system.net>  
    <defaultProxy>  
      <proxy  scriptDownloadInterval="600"  
              scriptDownloadTimeout="30"  
              useDefaultCredentials="true"  
              usesystemdefaults="true"  
      />  
    </defaultProxy>  
</system.net>  
```  
  
## <a name="static-proxies"></a><span data-ttu-id="a7b01-134">Servidores proxy estáticos</span><span class="sxs-lookup"><span data-stu-id="a7b01-134">Static Proxies</span></span>  
 <span data-ttu-id="a7b01-135">Los servidores proxy estáticos se suelen configurar explícitamente por medio de una aplicación o cuando una aplicación o el sistema invoca un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="a7b01-135">Static proxies are usually configured explicitly by an application, or when a configuration file is invoked by an application or the system.</span></span> <span data-ttu-id="a7b01-136">Los servidores proxy estáticos son útiles en las redes en las que la topología cambia con poca frecuencia, como un equipo de escritorio conectado a una red corporativa.</span><span class="sxs-lookup"><span data-stu-id="a7b01-136">Static proxies are useful in networks in which the topology changes infrequently, such as a desktop computer connected to a corporate network.</span></span>  
  
 <span data-ttu-id="a7b01-137">Varias opciones controlan el funcionamiento de un proxy estático.</span><span class="sxs-lookup"><span data-stu-id="a7b01-137">Several options control how a static proxy operates.</span></span> <span data-ttu-id="a7b01-138">Puede especificar los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="a7b01-138">You can specify the following:</span></span>  
  
-   <span data-ttu-id="a7b01-139">La dirección del proxy.</span><span class="sxs-lookup"><span data-stu-id="a7b01-139">The address of the proxy.</span></span>  
  
-   <span data-ttu-id="a7b01-140">Si debe omitirse el proxy para direcciones locales.</span><span class="sxs-lookup"><span data-stu-id="a7b01-140">Whether the proxy should be bypassed for local addresses.</span></span>  
  
-   <span data-ttu-id="a7b01-141">Si debe omitirse el proxy para un conjunto de direcciones.</span><span class="sxs-lookup"><span data-stu-id="a7b01-141">Whether the proxy should be bypassed for a set of addresses.</span></span>  
  
 <span data-ttu-id="a7b01-142">En la siguiente tabla se muestran las opciones de configuración de un proxy estático.</span><span class="sxs-lookup"><span data-stu-id="a7b01-142">The following table shows the configuration options for a static proxy.</span></span>  
  
|<span data-ttu-id="a7b01-143">Parámetro, atributo o propiedad del archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="a7b01-143">Attribute, property, or configuration file setting</span></span>|<span data-ttu-id="a7b01-144">Descripción</span><span class="sxs-lookup"><span data-stu-id="a7b01-144">Description</span></span>|  
|--------------------------------------------------------|-----------------|  
|<span data-ttu-id="a7b01-145">`proxyaddress` o <xref:System.Net.WebProxy.Address></span><span class="sxs-lookup"><span data-stu-id="a7b01-145">`proxyaddress` or <xref:System.Net.WebProxy.Address></span></span>|<span data-ttu-id="a7b01-146">La dirección de proxy que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="a7b01-146">The address of the proxy to use.</span></span>|  
|<span data-ttu-id="a7b01-147">`bypassonlocal` o <xref:System.Net.WebProxy.BypassProxyOnLocal></span><span class="sxs-lookup"><span data-stu-id="a7b01-147">`bypassonlocal` or <xref:System.Net.WebProxy.BypassProxyOnLocal></span></span>|<span data-ttu-id="a7b01-148">Controla si se omite el proxy para direcciones locales.</span><span class="sxs-lookup"><span data-stu-id="a7b01-148">Controls whether the proxy is bypassed for local addresses.</span></span>|  
|<span data-ttu-id="a7b01-149">`bypasslist` o <xref:System.Net.WebProxy.BypassArrayList></span><span class="sxs-lookup"><span data-stu-id="a7b01-149">`bypasslist` or <xref:System.Net.WebProxy.BypassArrayList></span></span>|<span data-ttu-id="a7b01-150">Describe, con expresiones regulares, un conjunto de direcciones que omiten el proxy.</span><span class="sxs-lookup"><span data-stu-id="a7b01-150">Describes, with regular expressions, a set of addresses that bypass the proxy.</span></span>|  
|`usesystemdefaults`|<span data-ttu-id="a7b01-151">Controla si la configuración de proxy estática (dirección de proxy, lista de omisión y omitir para las direcciones locales) debe leerse de la configuración de proxy de Internet Explorer para el usuario.</span><span class="sxs-lookup"><span data-stu-id="a7b01-151">Controls whether the static proxy settings (proxy address, bypass list, and bypass on local) should be read from the Internet Explorer proxy settings for the user.</span></span> <span data-ttu-id="a7b01-152">Si este valor se establece en "true", se usará la configuración de proxy estática de Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="a7b01-152">If this value is set to "true", then the static proxy settings from Internet Explorer will be used.</span></span> <span data-ttu-id="a7b01-153">En .NET Framework 2.0, cuando este valor se establece en "true", la configuración de proxy de Internet Explorer no se reemplaza por otros parámetros de proxy del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="a7b01-153">On .NET Framework 2.0 when this value is set to "true", the Internet Explorer proxy settings are not overridden by other proxy settings in the configuration file.</span></span> <span data-ttu-id="a7b01-154">En .NET Framework 1.1, la configuración de proxy de Internet Explorer puede reemplazarse por otra configuración de proxy en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="a7b01-154">On .NET Framework 1.1, the Internet Explorer proxy settings can be overridden by other proxy settings in the configuration file.</span></span><br /><br /> <span data-ttu-id="a7b01-155">Si este valor es "false" o no se establece, la configuración de proxy estática se pueden especificar en la configuración y reemplazará la configuración de proxy de Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="a7b01-155">If this value is "false" or not set, then the static proxy settings can be specified in the configuration and will override the Internet Explorer proxy settings.</span></span> <span data-ttu-id="a7b01-156">Este valor debe establecerse en "false" o no establecerse para que se habiliten los servidores proxy adaptables.</span><span class="sxs-lookup"><span data-stu-id="a7b01-156">This value must also be set to "false" or not set for adaptive proxies to be enabled.</span></span>|  
  
 <span data-ttu-id="a7b01-157">En el ejemplo siguiente se muestra una configuración típica de proxy estático.</span><span class="sxs-lookup"><span data-stu-id="a7b01-157">The following example shows a typical static proxy configuration.</span></span>  
  
```xml  
<system.net>  
    <defaultProxy>  
        <proxy  proxyaddress="http://proxy.contoso.com:3128"  
                bypassonlocal="true"  
        />  
        <bypasslist>  
            <add address="[a-z]+.blueyonderairlines.com$" />  
        </bypasslist>  
    </defaultProxy>  
</system.net>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a7b01-158">Vea también</span><span class="sxs-lookup"><span data-stu-id="a7b01-158">See Also</span></span>  
 <xref:System.Net.WebProxy>  
 <xref:System.Net.GlobalProxySelection>  
 [<span data-ttu-id="a7b01-159">Detección automática de proxy</span><span class="sxs-lookup"><span data-stu-id="a7b01-159">Automatic Proxy Detection</span></span>](../../../docs/framework/network-programming/automatic-proxy-detection.md)
