---
title: "Detecci&#243;n autom&#225;tica de proxy | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "detecciones automáticas de proxy"
  - "Detección automática de proxy web"
  - "Proxy web"
  - "detectar servidores proxy automáticamente"
  - "WebProxy (clase), detecciones automáticas de proxy"
  - "servidores proxy, detección automática"
  - "red"
  - "WPAD (detección automática de proxy web)"
ms.assetid: fcd9c3bd-93de-4c92-8ff3-837327ad18de
caps.latest.revision: 18
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 18
---
# Detecci&#243;n autom&#225;tica de proxy
La detección automática de proxy es un proceso que el sistema identifica y se utiliza un servidor proxy web para enviar solicitudes en nombre del cliente.  Esta característica también se conoce como Detección automática de proxy Web \(WPAD\).  Cuando se habilita la detección automática de proxy, el sistema intenta encontrar un script de configuración de proxy que es responsable de devolver el conjunto de servidores proxy que se pueden utilizar para la solicitud.  Si se encuentra el script de configuración de proxy, se descarga el script, compilado, y se ejecuta en el equipo local cuando la información de proxy, la secuencia de solicitud, o la respuesta se obtiene con una solicitud que use una instancia de <xref:System.Net.WebProxy> .  
  
 La detección automática de proxy realiza la clase de <xref:System.Net.WebProxy> y puede emplear valores de solicitud\- nivel, los archivos de configuración, y los valores especificados mediante el cuadro de diálogo de Internet Explorer **Red de área local \(LAN\)** .  
  
> [!NOTE]
>  Puede mostrar el cuadro de diálogo de Internet Explorer **Configuración de la red de área local \(LAN\)** seleccionando **Herramientas** de menú principal de Internet Explorer y seleccionando **Opciones de Internet**.  A continuación, seleccione la pestaña de **Conexiones** , y haga clic **Configuración de LAN**.  
  
 Cuando se habilita la detección automática de proxy, la clase de <xref:System.Net.WebProxy> intenta buscar el script de configuración de proxy como sigue:  
  
1.  La función WinINet `InternetQueryOption` se utiliza para buscar el script de configuración de proxy detectado recientemente por Internet Explorer.  
  
2.  Si el script no se encuentra, la clase de <xref:System.Net.WebProxy> utiliza Protocolo de configuración dinámica de host \(DHCP\) para buscar el script.  El servidor DHCP puede responder con la ubicación \(nombre de host\) de script o con la dirección URL completa para el script.  
  
3.  Si DHCP no identifica el host de WPAD, DNS se consulta para un host con WPAD como su nombre o alias.  
  
4.  Si el host no se identifica y la ubicación de un script de configuración de proxy es especificada por los valores de Internet Explorer LAN o un archivo de configuración, se utiliza esta ubicación.  
  
> [!NOTE]
>  Las aplicaciones que se ejecutan como NT Service o como parte de ASP.NET utilizan la configuración del servidor proxy de Internet Explorer \(si está disponible\) del usuario que llama.  Estos valores pueden no estar disponibles para todas las aplicaciones de servicios.  
  
 Servidores proxy se configuran por \- connectoid base.  Un connectoid es un elemento en el diálogo de red, y puede ser un dispositivo de red físico \(un módem o una tarjeta de Ethernet\) o una interfaz virtual \(como una conexión VPN que se ejecuta en un dispositivo de red\).  Cuando cambia un connectoid \(por ejemplo, una conexión inalámbrica cambia un punto de acceso, o está habilitada VPN\), el algoritmo de detección de proxy se ejecutan de nuevo.  
  
 De forma predeterminada, los valores de servidor proxy de Internet Explorer se utilizan para detectar el proxy.  Si la aplicación se ejecuta bajo una cuenta no interactiva \(sin una manera cómoda de configurar opciones de proxy de IE\), o si desea utilizar la configuración de proxy diferentes que los valores de IE, puede configurar el proxy creando un archivo de configuración con elementos de [\<defaultProxy\> \(Elemento, Configuración de red\)](../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md) y de [\<proxy\> \(Elemento, Configuración de red\)](../../../docs/framework/configure-apps/file-schema/network/proxy-element-network-settings.md) definidos.  
  
 Para las solicitudes que crea, puede deshabilitar la detección automática del proxy a solicitud de mediante <xref:System.Net.WebRequest.Proxy%2A> null con la solicitud, como se muestra en el siguiente ejemplo de código.  
  
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
  
 Solicitudes que no tienen el proxy predeterminado de proxy utilizará un su dominio de aplicación, que está disponible en la propiedad de <xref:System.Net.WebRequest.DefaultWebProxy%2A> .  
  
## Vea también  
 <xref:System.Net.WebProxy>   
 <xref:System.Net.WebRequest>   
 [\<system.Net\> \(elemento\) \(configuración de red\)](../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)