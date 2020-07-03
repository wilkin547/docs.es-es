---
title: Configuración de proxy
description: Obtenga información sobre cómo configurar servidores proxy adaptables y estáticos. La configuración del proxy controla la manera en que un servidor proxy administra las solicitudes de recursos por parte de los clientes.
ms.date: 06/18/2018
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
ms.openlocfilehash: 4d62f5736e9aa469be49d101e85851bc01b7c159
ms.sourcegitcommit: 6219b1e1feccb16d88656444210fed3297f5611e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/22/2020
ms.locfileid: "85141610"
---
# <a name="proxy-configuration"></a><span data-ttu-id="241eb-104">Configuración de proxy</span><span class="sxs-lookup"><span data-stu-id="241eb-104">Proxy Configuration</span></span>
<span data-ttu-id="241eb-105">Un servidor proxy controla las solicitudes de cliente de recursos.</span><span class="sxs-lookup"><span data-stu-id="241eb-105">A proxy server handles client requests for resources.</span></span> <span data-ttu-id="241eb-106">Un proxy puede devolver un recurso solicitado de su caché o reenviar la solicitud al servidor donde reside el recurso.</span><span class="sxs-lookup"><span data-stu-id="241eb-106">A proxy can return a requested resource from its cache or forward the request to the server where the resource resides.</span></span> <span data-ttu-id="241eb-107">Los servidores proxy pueden mejorar el rendimiento de la red al reducir el número de solicitudes enviadas a servidores remotos.</span><span class="sxs-lookup"><span data-stu-id="241eb-107">Proxies can improve network performance by reducing the number of requests sent to remote servers.</span></span> <span data-ttu-id="241eb-108">Los servidores proxy también pueden usarse para restringir el acceso a los recursos.</span><span class="sxs-lookup"><span data-stu-id="241eb-108">Proxies can also be used to restrict access to resources.</span></span>  
  
## <a name="adaptive-proxies"></a><span data-ttu-id="241eb-109">Servidores proxy adaptables</span><span class="sxs-lookup"><span data-stu-id="241eb-109">Adaptive Proxies</span></span>  
 <span data-ttu-id="241eb-110">En .NET Framework, los servidores proxy son de dos tipos: adaptable y estático.</span><span class="sxs-lookup"><span data-stu-id="241eb-110">In the .NET Framework, proxies come in two varieties: adaptive and static.</span></span> <span data-ttu-id="241eb-111">Los servidores proxy adaptables ajustan su configuración cuando cambia la configuración de red.</span><span class="sxs-lookup"><span data-stu-id="241eb-111">Adaptive proxies adjust their settings when the network configuration changes.</span></span> <span data-ttu-id="241eb-112">Por ejemplo, si un usuario de un portátil inicia una conexión de red de acceso telefónico, un proxy adaptable podría reconocer este cambio, descubrir y ejecutar su nuevo script de configuración y ajustar su configuración de manera adecuada.</span><span class="sxs-lookup"><span data-stu-id="241eb-112">For example, if a laptop user starts a dialup network connection, an adaptive proxy would recognize this change, discover and run its new configuration script, and adjust its settings appropriately.</span></span>  
  
 <span data-ttu-id="241eb-113">Los servidores proxy adaptables se configuran por medio de un script de configuración (vea [Detección automática de proxy](automatic-proxy-detection.md)).</span><span class="sxs-lookup"><span data-stu-id="241eb-113">Adaptive proxies are configured by a configuration script (see [Automatic Proxy Detection](automatic-proxy-detection.md)).</span></span> <span data-ttu-id="241eb-114">El script genera un conjunto de protocolos de aplicación y un proxy para cada protocolo.</span><span class="sxs-lookup"><span data-stu-id="241eb-114">The script generates a set of application protocols and a proxy for each protocol.</span></span>  
  
 <span data-ttu-id="241eb-115">Los cambios en el entorno de red pueden requerir que el sistema use un nuevo conjunto de servidores proxy.</span><span class="sxs-lookup"><span data-stu-id="241eb-115">Changes in the network environment may require that the system use a new set of proxies.</span></span> <span data-ttu-id="241eb-116">Si una conexión de red deja de funcionar o se inicializa una nueva conexión de red, el sistema debe descubrir el origen adecuado del script de configuración en el nuevo entorno y ejecutar el script nuevo.</span><span class="sxs-lookup"><span data-stu-id="241eb-116">If a network connection goes down or a new network connection is initialized, the system must discover the appropriate source of the configuration script in the new environment and run the new script.</span></span>  
  
 <span data-ttu-id="241eb-117">Puede usar el atributo `usesystemdefault` del elemento [`<proxy>`](../configure-apps/file-schema/network/proxy-element-network-settings.md) en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="241eb-117">You can use the `usesystemdefault` attribute of the [`<proxy>`](../configure-apps/file-schema/network/proxy-element-network-settings.md) element in your configuration file.</span></span> <span data-ttu-id="241eb-118">El atributo `usesystemdefault` controla si la configuración de proxy estática (dirección de proxy, lista de omisión y omitir para las direcciones locales) debe leerse de la configuración de proxy de Internet Explorer para el usuario.</span><span class="sxs-lookup"><span data-stu-id="241eb-118">The `usesystemdefault` attribute controls whether the static proxy settings (proxy address, bypass list, and bypass on local) should be read from the Internet Explorer proxy settings for the user.</span></span> <span data-ttu-id="241eb-119">Si este valor se establece en `true`, se usará la configuración de proxy estática de Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="241eb-119">If this value is set to `true`, the static proxy settings from Internet Explorer will be used.</span></span> <span data-ttu-id="241eb-120">Si este valor es `false` o no se establece, la configuración de proxy estática se puede especificar en la configuración y reemplazará la configuración de proxy de Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="241eb-120">If this value is `false` or not set, the static proxy settings can be specified in the configuration and will override the Internet Explorer proxy settings.</span></span> <span data-ttu-id="241eb-121">Este valor debe establecerse en `false` o no establecerse para que se habiliten los servidores proxy adaptables.</span><span class="sxs-lookup"><span data-stu-id="241eb-121">This value must also be set to `false` or not set for adaptive proxies to be enabled.</span></span>  
  
 <span data-ttu-id="241eb-122">En el ejemplo siguiente se muestra una configuración típica de proxy adaptable.</span><span class="sxs-lookup"><span data-stu-id="241eb-122">The following example shows a typical adaptive proxy configuration.</span></span>  
  
```xml  
<system.net>  
    <defaultProxy>  
      <proxy usesystemdefault="false" />
    </defaultProxy>  
</system.net>  
```  
  
## <a name="static-proxies"></a><span data-ttu-id="241eb-123">Servidores proxy estáticos</span><span class="sxs-lookup"><span data-stu-id="241eb-123">Static Proxies</span></span>  
 <span data-ttu-id="241eb-124">Los servidores proxy estáticos se suelen configurar explícitamente por medio de una aplicación o cuando una aplicación o el sistema invoca un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="241eb-124">Static proxies are usually configured explicitly by an application, or when a configuration file is invoked by an application or the system.</span></span> <span data-ttu-id="241eb-125">Los servidores proxy estáticos son útiles en las redes en las que la topología cambia con poca frecuencia, como un equipo de escritorio conectado a una red corporativa.</span><span class="sxs-lookup"><span data-stu-id="241eb-125">Static proxies are useful in networks in which the topology changes infrequently, such as a desktop computer connected to a corporate network.</span></span>  
  
 <span data-ttu-id="241eb-126">Varias opciones controlan el funcionamiento de un proxy estático.</span><span class="sxs-lookup"><span data-stu-id="241eb-126">Several options control how a static proxy operates.</span></span> <span data-ttu-id="241eb-127">Puede especificar los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="241eb-127">You can specify the following:</span></span>  
  
- <span data-ttu-id="241eb-128">La dirección del proxy.</span><span class="sxs-lookup"><span data-stu-id="241eb-128">The address of the proxy.</span></span>  
  
- <span data-ttu-id="241eb-129">Si debe omitirse el proxy para direcciones locales.</span><span class="sxs-lookup"><span data-stu-id="241eb-129">Whether the proxy should be bypassed for local addresses.</span></span>  
  
- <span data-ttu-id="241eb-130">Si debe omitirse el proxy para un conjunto de direcciones.</span><span class="sxs-lookup"><span data-stu-id="241eb-130">Whether the proxy should be bypassed for a set of addresses.</span></span>  
  
 <span data-ttu-id="241eb-131">En la siguiente tabla se muestran las opciones de configuración de un proxy estático.</span><span class="sxs-lookup"><span data-stu-id="241eb-131">The following table shows the configuration options for a static proxy.</span></span>  
  
|<span data-ttu-id="241eb-132">Parámetro, atributo o propiedad del archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="241eb-132">Attribute, property, or configuration file setting</span></span>|<span data-ttu-id="241eb-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="241eb-133">Description</span></span>|  
|--------------------------------------------------------|-----------------|  
|<span data-ttu-id="241eb-134">`proxyaddress` o <xref:System.Net.WebProxy.Address></span><span class="sxs-lookup"><span data-stu-id="241eb-134">`proxyaddress` or <xref:System.Net.WebProxy.Address></span></span>|<span data-ttu-id="241eb-135">La dirección de proxy que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="241eb-135">The address of the proxy to use.</span></span>|  
|<span data-ttu-id="241eb-136">`bypassonlocal` o <xref:System.Net.WebProxy.BypassProxyOnLocal></span><span class="sxs-lookup"><span data-stu-id="241eb-136">`bypassonlocal` or <xref:System.Net.WebProxy.BypassProxyOnLocal></span></span>|<span data-ttu-id="241eb-137">Controla si se omite el proxy para direcciones locales.</span><span class="sxs-lookup"><span data-stu-id="241eb-137">Controls whether the proxy is bypassed for local addresses.</span></span>|  
|<span data-ttu-id="241eb-138">`bypasslist` o <xref:System.Net.WebProxy.BypassArrayList></span><span class="sxs-lookup"><span data-stu-id="241eb-138">`bypasslist` or <xref:System.Net.WebProxy.BypassArrayList></span></span>|<span data-ttu-id="241eb-139">Describe, con expresiones regulares, un conjunto de direcciones que omiten el proxy.</span><span class="sxs-lookup"><span data-stu-id="241eb-139">Describes, with regular expressions, a set of addresses that bypass the proxy.</span></span>|  
|`usesystemdefault`|<span data-ttu-id="241eb-140">Controla si la configuración de proxy estática (dirección de proxy, lista de omisión y omitir para las direcciones locales) debe leerse de la configuración de proxy de Internet Explorer para el usuario.</span><span class="sxs-lookup"><span data-stu-id="241eb-140">Controls whether the static proxy settings (proxy address, bypass list, and bypass on local) should be read from the Internet Explorer proxy settings for the user.</span></span> <span data-ttu-id="241eb-141">Si este valor se establece en `true`, se usará la configuración de proxy estática de Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="241eb-141">If this value is set to `true`, then the static proxy settings from Internet Explorer will be used.</span></span> <span data-ttu-id="241eb-142">En .NET Framework 2.0, cuando este valor se establece en `true`, la configuración de proxy de Internet Explorer no se reemplaza por otros parámetros de proxy del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="241eb-142">On .NET Framework 2.0 when this value is set to `true`, the Internet Explorer proxy settings are not overridden by other proxy settings in the configuration file.</span></span> <span data-ttu-id="241eb-143">En .NET Framework 1.1, la configuración de proxy de Internet Explorer puede reemplazarse por otra configuración de proxy en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="241eb-143">On .NET Framework 1.1, the Internet Explorer proxy settings can be overridden by other proxy settings in the configuration file.</span></span><br /><br /> <span data-ttu-id="241eb-144">Si este valor es `false` o no se establece, entonces la configuración de proxy estática se puede especificar en la configuración y reemplazará la configuración de proxy de Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="241eb-144">If this value is `false` or not set, then the static proxy settings can be specified in the configuration and will override the Internet Explorer proxy settings.</span></span> <span data-ttu-id="241eb-145">Este valor debe establecerse en `false` o no establecerse para que se habiliten los servidores proxy adaptables.</span><span class="sxs-lookup"><span data-stu-id="241eb-145">This value must also be set to `false` or not set for adaptive proxies to be enabled.</span></span>|  
  
 <span data-ttu-id="241eb-146">En el ejemplo siguiente se muestra una configuración típica de proxy estático.</span><span class="sxs-lookup"><span data-stu-id="241eb-146">The following example shows a typical static proxy configuration.</span></span>  
  
```xml  
<system.net>  
    <defaultProxy>  
        <proxy  proxyaddress="http://proxy.contoso.com:3128"  
                bypassonlocal="True"  
        />  
        <bypasslist>  
            <add address="[a-z]+.blueyonderairlines.com$" />  
        </bypasslist>  
    </defaultProxy>  
</system.net>  
```  
  
## <a name="see-also"></a><span data-ttu-id="241eb-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="241eb-147">See also</span></span>

- <xref:System.Net.WebProxy>
- <xref:System.Net.GlobalProxySelection>
- [<span data-ttu-id="241eb-148">Detección automática de proxy</span><span class="sxs-lookup"><span data-stu-id="241eb-148">Automatic Proxy Detection</span></span>](automatic-proxy-detection.md)
