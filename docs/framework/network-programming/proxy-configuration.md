---
title: Configuración de proxy
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
ms.openlocfilehash: 328f67c5afe22f336aa6337903b6569fb6ecc359
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64623057"
---
# <a name="proxy-configuration"></a><span data-ttu-id="3ce78-102">Configuración de proxy</span><span class="sxs-lookup"><span data-stu-id="3ce78-102">Proxy Configuration</span></span>
<span data-ttu-id="3ce78-103">Un servidor proxy controla las solicitudes de cliente de recursos.</span><span class="sxs-lookup"><span data-stu-id="3ce78-103">A proxy server handles client requests for resources.</span></span> <span data-ttu-id="3ce78-104">Un proxy puede devolver un recurso solicitado de su caché o reenviar la solicitud al servidor donde reside el recurso.</span><span class="sxs-lookup"><span data-stu-id="3ce78-104">A proxy can return a requested resource from its cache or forward the request to the server where the resource resides.</span></span> <span data-ttu-id="3ce78-105">Los servidores proxy pueden mejorar el rendimiento de la red al reducir el número de solicitudes enviadas a servidores remotos.</span><span class="sxs-lookup"><span data-stu-id="3ce78-105">Proxies can improve network performance by reducing the number of requests sent to remote servers.</span></span> <span data-ttu-id="3ce78-106">Los servidores proxy también pueden usarse para restringir el acceso a los recursos.</span><span class="sxs-lookup"><span data-stu-id="3ce78-106">Proxies can also be used to restrict access to resources.</span></span>  
  
## <a name="adaptive-proxies"></a><span data-ttu-id="3ce78-107">Servidores proxy adaptables</span><span class="sxs-lookup"><span data-stu-id="3ce78-107">Adaptive Proxies</span></span>  
 <span data-ttu-id="3ce78-108">En .NET Framework, los servidores proxy son de dos tipos: adaptable y estático.</span><span class="sxs-lookup"><span data-stu-id="3ce78-108">In the .NET Framework, proxies come in two varieties: adaptive and static.</span></span> <span data-ttu-id="3ce78-109">Los servidores proxy adaptables ajustan su configuración cuando cambia la configuración de red.</span><span class="sxs-lookup"><span data-stu-id="3ce78-109">Adaptive proxies adjust their settings when the network configuration changes.</span></span> <span data-ttu-id="3ce78-110">Por ejemplo, si un usuario de un portátil inicia una conexión de red de acceso telefónico, un proxy adaptable podría reconocer este cambio, descubrir y ejecutar su nuevo script de configuración y ajustar su configuración de manera adecuada.</span><span class="sxs-lookup"><span data-stu-id="3ce78-110">For example, if a laptop user starts a dialup network connection, an adaptive proxy would recognize this change, discover and run its new configuration script, and adjust its settings appropriately.</span></span>  
  
 <span data-ttu-id="3ce78-111">Los servidores proxy adaptables se configuran por medio de un script de configuración (vea [Detección automática de proxy](../../../docs/framework/network-programming/automatic-proxy-detection.md)).</span><span class="sxs-lookup"><span data-stu-id="3ce78-111">Adaptive proxies are configured by a configuration script (see [Automatic Proxy Detection](../../../docs/framework/network-programming/automatic-proxy-detection.md)).</span></span> <span data-ttu-id="3ce78-112">El script genera un conjunto de protocolos de aplicación y un proxy para cada protocolo.</span><span class="sxs-lookup"><span data-stu-id="3ce78-112">The script generates a set of application protocols and a proxy for each protocol.</span></span>  
  
 <span data-ttu-id="3ce78-113">Los cambios en el entorno de red pueden requerir que el sistema use un nuevo conjunto de servidores proxy.</span><span class="sxs-lookup"><span data-stu-id="3ce78-113">Changes in the network environment may require that the system use a new set of proxies.</span></span> <span data-ttu-id="3ce78-114">Si una conexión de red deja de funcionar o se inicializa una nueva conexión de red, el sistema debe descubrir el origen adecuado del script de configuración en el nuevo entorno y ejecutar el script nuevo.</span><span class="sxs-lookup"><span data-stu-id="3ce78-114">If a network connection goes down or a new network connection is initialized, the system must discover the appropriate source of the configuration script in the new environment and run the new script.</span></span>  
  
 <span data-ttu-id="3ce78-115">Puede usar el atributo `usesystemdefault` del elemento [`<proxy>`](../configure-apps/file-schema/network/proxy-element-network-settings.md) en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="3ce78-115">You can use the `usesystemdefault` attribute of the [`<proxy>`](../configure-apps/file-schema/network/proxy-element-network-settings.md) element in your configuration file.</span></span> <span data-ttu-id="3ce78-116">El atributo `usesystemdefault` controla si la configuración de proxy estática (dirección de proxy, lista de omisión y omitir para las direcciones locales) debe leerse de la configuración de proxy de Internet Explorer para el usuario.</span><span class="sxs-lookup"><span data-stu-id="3ce78-116">The `usesystemdefault` attribute controls whether the static proxy settings (proxy address, bypass list, and bypass on local) should be read from the Internet Explorer proxy settings for the user.</span></span> <span data-ttu-id="3ce78-117">Si este valor se establece en `true`, se usará la configuración de proxy estática de Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="3ce78-117">If this value is set to `true`, the static proxy settings from Internet Explorer will be used.</span></span> <span data-ttu-id="3ce78-118">Si este valor es `false` o no se establece, la configuración de proxy estática se puede especificar en la configuración y reemplazará la configuración de proxy de Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="3ce78-118">If this value is `false` or not set, the static proxy settings can be specified in the configuration and will override the Internet Explorer proxy settings.</span></span> <span data-ttu-id="3ce78-119">Este valor debe establecerse en `false` o no establecerse para que se habiliten los servidores proxy adaptables.</span><span class="sxs-lookup"><span data-stu-id="3ce78-119">This value must also be set to `false` or not set for adaptive proxies to be enabled.</span></span>  
  
 <span data-ttu-id="3ce78-120">En el ejemplo siguiente se muestra una configuración típica de proxy adaptable.</span><span class="sxs-lookup"><span data-stu-id="3ce78-120">The following example shows a typical adaptive proxy configuration.</span></span>  
  
```xml  
<system.net>  
    <defaultProxy>  
      <proxy usesystemdefault="false" />
    </defaultProxy>  
</system.net>  
```  
  
## <a name="static-proxies"></a><span data-ttu-id="3ce78-121">Servidores proxy estáticos</span><span class="sxs-lookup"><span data-stu-id="3ce78-121">Static Proxies</span></span>  
 <span data-ttu-id="3ce78-122">Los servidores proxy estáticos se suelen configurar explícitamente por medio de una aplicación o cuando una aplicación o el sistema invoca un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="3ce78-122">Static proxies are usually configured explicitly by an application, or when a configuration file is invoked by an application or the system.</span></span> <span data-ttu-id="3ce78-123">Los servidores proxy estáticos son útiles en las redes en las que la topología cambia con poca frecuencia, como un equipo de escritorio conectado a una red corporativa.</span><span class="sxs-lookup"><span data-stu-id="3ce78-123">Static proxies are useful in networks in which the topology changes infrequently, such as a desktop computer connected to a corporate network.</span></span>  
  
 <span data-ttu-id="3ce78-124">Varias opciones controlan el funcionamiento de un proxy estático.</span><span class="sxs-lookup"><span data-stu-id="3ce78-124">Several options control how a static proxy operates.</span></span> <span data-ttu-id="3ce78-125">Puede especificar los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="3ce78-125">You can specify the following:</span></span>  
  
- <span data-ttu-id="3ce78-126">La dirección del proxy.</span><span class="sxs-lookup"><span data-stu-id="3ce78-126">The address of the proxy.</span></span>  
  
- <span data-ttu-id="3ce78-127">Si debe omitirse el proxy para direcciones locales.</span><span class="sxs-lookup"><span data-stu-id="3ce78-127">Whether the proxy should be bypassed for local addresses.</span></span>  
  
- <span data-ttu-id="3ce78-128">Si debe omitirse el proxy para un conjunto de direcciones.</span><span class="sxs-lookup"><span data-stu-id="3ce78-128">Whether the proxy should be bypassed for a set of addresses.</span></span>  
  
 <span data-ttu-id="3ce78-129">En la siguiente tabla se muestran las opciones de configuración de un proxy estático.</span><span class="sxs-lookup"><span data-stu-id="3ce78-129">The following table shows the configuration options for a static proxy.</span></span>  
  
|<span data-ttu-id="3ce78-130">Parámetro, atributo o propiedad del archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="3ce78-130">Attribute, property, or configuration file setting</span></span>|<span data-ttu-id="3ce78-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="3ce78-131">Description</span></span>|  
|--------------------------------------------------------|-----------------|  
|<span data-ttu-id="3ce78-132">`proxyaddress` o <xref:System.Net.WebProxy.Address></span><span class="sxs-lookup"><span data-stu-id="3ce78-132">`proxyaddress` or <xref:System.Net.WebProxy.Address></span></span>|<span data-ttu-id="3ce78-133">La dirección de proxy que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="3ce78-133">The address of the proxy to use.</span></span>|  
|<span data-ttu-id="3ce78-134">`bypassonlocal` o <xref:System.Net.WebProxy.BypassProxyOnLocal></span><span class="sxs-lookup"><span data-stu-id="3ce78-134">`bypassonlocal` or <xref:System.Net.WebProxy.BypassProxyOnLocal></span></span>|<span data-ttu-id="3ce78-135">Controla si se omite el proxy para direcciones locales.</span><span class="sxs-lookup"><span data-stu-id="3ce78-135">Controls whether the proxy is bypassed for local addresses.</span></span>|  
|<span data-ttu-id="3ce78-136">`bypasslist` o <xref:System.Net.WebProxy.BypassArrayList></span><span class="sxs-lookup"><span data-stu-id="3ce78-136">`bypasslist` or <xref:System.Net.WebProxy.BypassArrayList></span></span>|<span data-ttu-id="3ce78-137">Describe, con expresiones regulares, un conjunto de direcciones que omiten el proxy.</span><span class="sxs-lookup"><span data-stu-id="3ce78-137">Describes, with regular expressions, a set of addresses that bypass the proxy.</span></span>|  
|`usesystemdefault`|<span data-ttu-id="3ce78-138">Controla si la configuración de proxy estática (dirección de proxy, lista de omisión y omitir para las direcciones locales) debe leerse de la configuración de proxy de Internet Explorer para el usuario.</span><span class="sxs-lookup"><span data-stu-id="3ce78-138">Controls whether the static proxy settings (proxy address, bypass list, and bypass on local) should be read from the Internet Explorer proxy settings for the user.</span></span> <span data-ttu-id="3ce78-139">Si este valor se establece en `true`, se usará la configuración de proxy estática de Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="3ce78-139">If this value is set to `true`, then the static proxy settings from Internet Explorer will be used.</span></span> <span data-ttu-id="3ce78-140">En .NET Framework 2.0, cuando este valor se establece en `true`, la configuración de proxy de Internet Explorer no se reemplaza por otros parámetros de proxy del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="3ce78-140">On .NET Framework 2.0 when this value is set to `true`, the Internet Explorer proxy settings are not overridden by other proxy settings in the configuration file.</span></span> <span data-ttu-id="3ce78-141">En .NET Framework 1.1, la configuración de proxy de Internet Explorer puede reemplazarse por otra configuración de proxy en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="3ce78-141">On .NET Framework 1.1, the Internet Explorer proxy settings can be overridden by other proxy settings in the configuration file.</span></span><br /><br /> <span data-ttu-id="3ce78-142">Si este valor es `false` o no se establece, entonces la configuración de proxy estática se puede especificar en la configuración y reemplazará la configuración de proxy de Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="3ce78-142">If this value is `false` or not set, then the static proxy settings can be specified in the configuration and will override the Internet Explorer proxy settings.</span></span> <span data-ttu-id="3ce78-143">Este valor debe establecerse en `false` o no establecerse para que se habiliten los servidores proxy adaptables.</span><span class="sxs-lookup"><span data-stu-id="3ce78-143">This value must also be set to `false` or not set for adaptive proxies to be enabled.</span></span>|  
  
 <span data-ttu-id="3ce78-144">En el ejemplo siguiente se muestra una configuración típica de proxy estático.</span><span class="sxs-lookup"><span data-stu-id="3ce78-144">The following example shows a typical static proxy configuration.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3ce78-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="3ce78-145">See also</span></span>

- <xref:System.Net.WebProxy>
- <xref:System.Net.GlobalProxySelection>
- [<span data-ttu-id="3ce78-146">Detección automática de proxy</span><span class="sxs-lookup"><span data-stu-id="3ce78-146">Automatic Proxy Detection</span></span>](../../../docs/framework/network-programming/automatic-proxy-detection.md)
