---
title: Detección automática de proxy
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- automatic proxy detections
- Web Proxy Auto-Discovery
- Web proxy
- detecting proxies automatically
- WebProxy class, automatic proxy detections
- proxies, automatically detecting
- network
- WPAD (Web Proxy Auto-Discovery)
ms.assetid: fcd9c3bd-93de-4c92-8ff3-837327ad18de
ms.openlocfilehash: 4c5bc9e0efb39032d388d141e8bccf3e520ebd45
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "79180893"
---
# <a name="automatic-proxy-detection"></a><span data-ttu-id="8f767-102">Detección automática de proxy</span><span class="sxs-lookup"><span data-stu-id="8f767-102">Automatic Proxy Detection</span></span>
<span data-ttu-id="8f767-103">La detección automática de proxy es un proceso por el que el sistema identifica un servidor proxy web que se usa para enviar solicitudes en nombre del cliente.</span><span class="sxs-lookup"><span data-stu-id="8f767-103">Automatic proxy detection is a process by which a Web proxy server is identified by the system and used to send requests on behalf of the client.</span></span> <span data-ttu-id="8f767-104">Esta característica también se conoce como detección automática de proxy web (WPAD).</span><span class="sxs-lookup"><span data-stu-id="8f767-104">This feature is also known as Web Proxy Auto-Discovery (WPAD).</span></span> <span data-ttu-id="8f767-105">Cuando la detección automática de proxy está habilitada, el sistema intenta localizar un script de configuración de proxy responsable de devolver el conjunto de servidores proxy que se puede usar para la solicitud.</span><span class="sxs-lookup"><span data-stu-id="8f767-105">When automatic proxy detection is enabled, the system attempts to locate a proxy configuration script that is responsible for returning the set of proxies that can be used for the request.</span></span> <span data-ttu-id="8f767-106">Si se localiza el script de configuración de proxy, se descarga, se compila y se ejecuta en el equipo local cuando se obtiene información del proxy, el flujo de la solicitud o la respuesta de una solicitud que usa una instancia <xref:System.Net.WebProxy>.</span><span class="sxs-lookup"><span data-stu-id="8f767-106">If the proxy configuration script is found, the script is downloaded, compiled, and run on the local computer when proxy information, the request stream, or the response is obtained for a request that uses a <xref:System.Net.WebProxy> instance.</span></span>  
  
 <span data-ttu-id="8f767-107">La detección automática de proxy se realiza mediante la clase <xref:System.Net.WebProxy> y puede emplear la configuración de nivel de solicitud, la configuración de los archivos de configuración y la configuración especificada mediante el cuadro de diálogo **Red de área local (LAN)** de Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="8f767-107">Automatic proxy detection is performed by the <xref:System.Net.WebProxy> class and can employ request-level settings, settings in configuration files, and settings specified using the Internet Explorer **Local Area Network (LAN)** dialog box.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8f767-108">Puede mostrar el cuadro de diálogo **Configuración de la red de área local (LAN)** de Internet Explorer si selecciona **Herramientas** en el menú principal de Internet Explorer y luego **Opciones de Internet**.</span><span class="sxs-lookup"><span data-stu-id="8f767-108">You can display the Internet Explorer **Local Area Network (LAN) Settings** dialog box by selecting **Tools** from the Internet Explorer main menu and then selecting **Internet Options**.</span></span> <span data-ttu-id="8f767-109">Luego, seleccione la pestaña **Conexiones** y haga clic en **Configuración de LAN**.</span><span class="sxs-lookup"><span data-stu-id="8f767-109">Next, select the **Connections** tab, and click **LAN Settings**.</span></span>  
  
 <span data-ttu-id="8f767-110">Cuando la detección automática de proxy está habilitada, la clase <xref:System.Net.WebProxy> intenta localizar el script de configuración de proxy como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="8f767-110">When automatic proxy detection is enabled, the <xref:System.Net.WebProxy> class attempts to locate the proxy configuration script as follows:</span></span>  
  
1. <span data-ttu-id="8f767-111">La función `InternetQueryOption` de WinINet se usa para buscar el script de configuración de proxy detectado más recientemente por Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="8f767-111">The WinINet `InternetQueryOption` function is used to locate the proxy configuration script most recently detected by Internet Explorer.</span></span>  
  
2. <span data-ttu-id="8f767-112">Si no se encuentra el script, la clase <xref:System.Net.WebProxy> usa el Protocolo de configuración dinámica de host (DHCP) para buscarlo.</span><span class="sxs-lookup"><span data-stu-id="8f767-112">If the script is not located, the <xref:System.Net.WebProxy> class uses the Dynamic Host Configuration Protocol (DHCP) to locate the script.</span></span> <span data-ttu-id="8f767-113">El servidor DHCP puede responder con la ubicación (nombre de host) del script o con la dirección URL completa de este.</span><span class="sxs-lookup"><span data-stu-id="8f767-113">The DHCP server can respond either with the location (host name) of the script or with the full URL for the script.</span></span>  
  
3. <span data-ttu-id="8f767-114">Si el servidor DHCP no identifica el host WPAD, se pide a DNS un host con WPAD como su nombre o alias.</span><span class="sxs-lookup"><span data-stu-id="8f767-114">If DHCP does not identify the WPAD host, DNS is queried for a host with WPAD as its name or alias.</span></span>  
  
4. <span data-ttu-id="8f767-115">Si no se identifica el host y la configuración de LAN de Internet Explorer o un archivo de configuración especifican la ubicación de un script de configuración de proxy, se usa esta ubicación.</span><span class="sxs-lookup"><span data-stu-id="8f767-115">If the host is not identified and the location of a proxy configuration script is specified by the Internet Explorer LAN settings or a configuration file, this location is used.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8f767-116">Las aplicaciones que se ejecutan como un servicio NT o como parte de ASP.NET usan la configuración del servidor proxy de Internet Explorer (si está disponible) del usuario que invoca.</span><span class="sxs-lookup"><span data-stu-id="8f767-116">Applications running as an NT Service or as part of ASP.NET use the Internet Explorer proxy server settings (if available) of the invoking user.</span></span> <span data-ttu-id="8f767-117">Es posible que esta configuración no esté disponible para todas las aplicaciones de servicio.</span><span class="sxs-lookup"><span data-stu-id="8f767-117">These settings may not be available for all service applications.</span></span>  
  
 <span data-ttu-id="8f767-118">Los servidores proxy se configuran conectoide a conectoide.</span><span class="sxs-lookup"><span data-stu-id="8f767-118">Proxies are configured on a per-connectoid basis.</span></span> <span data-ttu-id="8f767-119">Un conectoide es un elemento del cuadro de diálogo de conexión de red que puede ser un dispositivo de red físico (un módem o una tarjeta Ethernet) o una interfaz virtual (por ejemplo, una conexión VPN que se ejecuta a través de un dispositivo de red).</span><span class="sxs-lookup"><span data-stu-id="8f767-119">A connectoid is an item in the network connection dialog, and can be a physical network device (a modem or Ethernet card) or a virtual interface (such as a VPN connection running over a network device).</span></span> <span data-ttu-id="8f767-120">Cuando cambia un conectoide (por ejemplo, una conexión inalámbrica cambia un punto de acceso o se habilita una VPN), el algoritmo de detección de proxy se vuelve a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="8f767-120">When a connectoid changes (for example, a wireless connection changes an access point, or a VPN is enabled), the proxy detection algorithm is run again.</span></span>  
  
 <span data-ttu-id="8f767-121">De forma predeterminada, se usa la configuración de proxy de Internet Explorer para detectar el proxy.</span><span class="sxs-lookup"><span data-stu-id="8f767-121">By default, the Internet Explorer proxy settings are used to detect the proxy.</span></span> <span data-ttu-id="8f767-122">Si la aplicación se ejecuta en una cuenta no interactiva (sin una manera cómoda de configurar el proxy de Internet Explorer), o si quiere usar una configuración de proxy diferente a la de Internet Explorer, puede configurar el proxy mediante la creación de un archivo de configuración con los elementos [Elemento \<defaultProxy> (configuración de red)](../configure-apps/file-schema/network/defaultproxy-element-network-settings.md) y [Elemento \<proxy> (configuración de red)](../configure-apps/file-schema/network/proxy-element-network-settings.md) definidos.</span><span class="sxs-lookup"><span data-stu-id="8f767-122">If your application is running under a non-interactive account (without a convenient way to configure IE proxy settings), or if you want to use proxy settings different than the IE settings, you can configure your proxy by creating a configuration file with the [\<defaultProxy> Element (Network Settings)](../configure-apps/file-schema/network/defaultproxy-element-network-settings.md) and [\<proxy> Element (Network Settings)](../configure-apps/file-schema/network/proxy-element-network-settings.md) elements defined.</span></span>  
  
 <span data-ttu-id="8f767-123">En las solicitudes que cree puede deshabilitar la detección automática de proxy en el nivel de solicitud mediante un valor <xref:System.Net.WebRequest.Proxy%2A> null con la solicitud, como se muestra en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="8f767-123">For requests that you create, you can disable automatic proxy detection at the request level by using a null <xref:System.Net.WebRequest.Proxy%2A> with your request, as shown in the following code example.</span></span>  
  
```csharp  
public static void DisableForMyRequest (Uri resource)  
{  
    WebRequest request = WebRequest.Create (resource);  
    request.Proxy = null;  
    WebResponse response = request.GetResponse ();  
}  
```  
  
```vb  
Public Shared Sub DisableForMyRequest(ByVal resource As Uri)  
    Dim request As WebRequest = WebRequest.Create(resource)  
    request.Proxy = Nothing  
    Dim response As WebResponse = request.GetResponse()  
    End Sub
```  
  
 <span data-ttu-id="8f767-124">Las solicitudes que no tienen proxy usan el proxy predeterminado del dominio de aplicación, que está disponible en la propiedad <xref:System.Net.WebRequest.DefaultWebProxy%2A>.</span><span class="sxs-lookup"><span data-stu-id="8f767-124">Requests that do not have a proxy use your application domain's default proxy, which is available in the <xref:System.Net.WebRequest.DefaultWebProxy%2A> property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f767-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="8f767-125">See also</span></span>

- <xref:System.Net.WebProxy>
- <xref:System.Net.WebRequest>
- [<span data-ttu-id="8f767-126">Elemento \<system.Net> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="8f767-126">\<system.Net> Element (Network Settings)</span></span>](../configure-apps/file-schema/network/system-net-element-network-settings.md)
