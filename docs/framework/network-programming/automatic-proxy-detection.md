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
# <a name="automatic-proxy-detection"></a>Detección automática de proxy
La detección automática de proxy es un proceso por el que el sistema identifica un servidor proxy web que se usa para enviar solicitudes en nombre del cliente. Esta característica también se conoce como detección automática de proxy web (WPAD). Cuando la detección automática de proxy está habilitada, el sistema intenta localizar un script de configuración de proxy responsable de devolver el conjunto de servidores proxy que se puede usar para la solicitud. Si se localiza el script de configuración de proxy, se descarga, se compila y se ejecuta en el equipo local cuando se obtiene información del proxy, el flujo de la solicitud o la respuesta de una solicitud que usa una instancia <xref:System.Net.WebProxy>.  
  
 La detección automática de proxy se realiza mediante la clase <xref:System.Net.WebProxy> y puede emplear la configuración de nivel de solicitud, la configuración de los archivos de configuración y la configuración especificada mediante el cuadro de diálogo **Red de área local (LAN)** de Internet Explorer.  
  
> [!NOTE]
> Puede mostrar el cuadro de diálogo **Configuración de la red de área local (LAN)** de Internet Explorer si selecciona **Herramientas** en el menú principal de Internet Explorer y luego **Opciones de Internet**. Luego, seleccione la pestaña **Conexiones** y haga clic en **Configuración de LAN**.  
  
 Cuando la detección automática de proxy está habilitada, la clase <xref:System.Net.WebProxy> intenta localizar el script de configuración de proxy como se indica a continuación:  
  
1. La función `InternetQueryOption` de WinINet se usa para buscar el script de configuración de proxy detectado más recientemente por Internet Explorer.  
  
2. Si no se encuentra el script, la clase <xref:System.Net.WebProxy> usa el Protocolo de configuración dinámica de host (DHCP) para buscarlo. El servidor DHCP puede responder con la ubicación (nombre de host) del script o con la dirección URL completa de este.  
  
3. Si el servidor DHCP no identifica el host WPAD, se pide a DNS un host con WPAD como su nombre o alias.  
  
4. Si no se identifica el host y la configuración de LAN de Internet Explorer o un archivo de configuración especifican la ubicación de un script de configuración de proxy, se usa esta ubicación.  
  
> [!NOTE]
> Las aplicaciones que se ejecutan como un servicio NT o como parte de ASP.NET usan la configuración del servidor proxy de Internet Explorer (si está disponible) del usuario que invoca. Es posible que esta configuración no esté disponible para todas las aplicaciones de servicio.  
  
 Los servidores proxy se configuran conectoide a conectoide. Un conectoide es un elemento del cuadro de diálogo de conexión de red que puede ser un dispositivo de red físico (un módem o una tarjeta Ethernet) o una interfaz virtual (por ejemplo, una conexión VPN que se ejecuta a través de un dispositivo de red). Cuando cambia un conectoide (por ejemplo, una conexión inalámbrica cambia un punto de acceso o se habilita una VPN), el algoritmo de detección de proxy se vuelve a ejecutar.  
  
 De forma predeterminada, se usa la configuración de proxy de Internet Explorer para detectar el proxy. Si la aplicación se ejecuta en una cuenta no interactiva (sin una manera cómoda de configurar el proxy de Internet Explorer), o si quiere usar una configuración de proxy diferente a la de Internet Explorer, puede configurar el proxy mediante la creación de un archivo de configuración con los elementos [Elemento \<defaultProxy> (configuración de red)](../configure-apps/file-schema/network/defaultproxy-element-network-settings.md) y [Elemento \<proxy> (configuración de red)](../configure-apps/file-schema/network/proxy-element-network-settings.md) definidos.  
  
 En las solicitudes que cree puede deshabilitar la detección automática de proxy en el nivel de solicitud mediante un valor <xref:System.Net.WebRequest.Proxy%2A> null con la solicitud, como se muestra en el ejemplo de código siguiente.  
  
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
  
 Las solicitudes que no tienen proxy usan el proxy predeterminado del dominio de aplicación, que está disponible en la propiedad <xref:System.Net.WebRequest.DefaultWebProxy%2A>.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Net.WebProxy>
- <xref:System.Net.WebRequest>
- [Elemento \<system.Net> (configuración de red)](../configure-apps/file-schema/network/system-net-element-network-settings.md)
