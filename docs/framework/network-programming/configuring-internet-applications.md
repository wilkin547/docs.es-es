---
title: Configuración de aplicaciones de Internet
description: Obtenga información sobre el uso del elemento <system.Net> para configurar aplicaciones de Internet en .NET Framework. Este artículo contiene código de ejemplo.
ms.date: 03/30/2017
helpviewer_keywords:
- downloading Internet resources, default proxy
- sending data, default proxy
- receiving data, default proxy
- downloading Internet resources, configuring Internet applications
- protocol-specific modules
- custom authentication modules
- receiving data, configuring Internet applications
- configuration settings [.NET Framework], Internet applications
- requesting data from Internet, configuring Internet applications
- requesting data from Internet, default proxy
- response to Internet request, default proxy
- Internet, configuring Internet applications
- response to Internet request, configuring Internet applications
- default proxy
- network resources, default proxy
- sending data, configuring Internet applications
- network resources, configuring Internet applications
- Internet, default proxy
ms.assetid: bb707c72-eed2-4a82-8800-c9e68df2fd4f
ms.openlocfilehash: 796752ebf6e3cc5c3dac2a20213934f35d31b392
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96287467"
---
# <a name="configuring-internet-applications"></a>Configuración de aplicaciones de Internet

El [Elemento \<system.Net> (configuración de red)](../configure-apps/file-schema/network/system-net-element-network-settings.md) contiene información sobre la configuración de red de las aplicaciones. Con el [Elemento \<system.Net> (configuración de red)](../configure-apps/file-schema/network/system-net-element-network-settings.md), puede establecer servidores proxy, establecer parámetros de administración de conexiones e incluir módulos personalizados de autenticación y solicitud en la aplicación.  
  
 El [Elemento \<defaultProxy> (configuración de red)](../configure-apps/file-schema/network/defaultproxy-element-network-settings.md) define el servidor proxy devuelto por la clase `GlobalProxySelection`. Cualquier elemento <xref:System.Net.HttpWebRequest> que no tenga su propia propiedad <xref:System.Net.HttpWebRequest.Proxy%2A> establecida en un valor específico, usa el proxy predeterminado. Además de establecer la dirección de proxy, puede crear una lista de direcciones de servidor que no vayan a usar el proxy y puede indicar que no se debería usar el proxy para direcciones locales.  
  
 Es importante tener en cuenta que la configuración de Microsoft Internet Explorer se combina con los valores de configuración, que tienen preferencia.  
  
 En el siguiente ejemplo se establece la dirección del servidor proxy predeterminada en `http://proxyserver`, se indica que el proxy no debe usarse para las direcciones locales y se especifica que todas las solicitudes a servidores ubicados en el dominio contoso.com deben omitir el proxy.  
  
```xml  
<configuration>  
    <system.net>  
        <defaultProxy>  
            <proxy  
                usesystemdefault = "false"  
                proxyaddress = "http://proxyserver:80"  
                bypassonlocal = "true"  
            />  
            <bypasslist>  
                <add address="http://[a-z]+\.contoso\.com/" />  
            </bypasslist>  
        </defaultProxy>  
    </system.net>  
</configuration>  
```  
  
 Use el [Elemento \<connectionManagement> (configuración de red)](../configure-apps/file-schema/network/connectionmanagement-element-network-settings.md) para configurar el número de conexiones persistentes que pueden realizarse a un servidor concreto o a todos los demás servidores. En el ejemplo siguiente se configura la aplicación para que use dos conexiones persistentes al servidor `www.contoso.com`, cuatro conexiones persistentes al servidor con la dirección IP 192.168.1.2 y una conexión persistente a todos los demás servidores.  
  
```xml  
<configuration>  
    <system.net>  
        <connectionManagement>  
            <add address="http://www.contoso.com" maxconnection="2" />  
            <add address="192.168.1.2" maxconnection="4" />  
            <add address="*" maxconnection="1" />  
        </connectionManagement>  
    </system.net>  
</configuration>  
```  
  
 Los módulos de autenticación personalizados se configuran con el [Elemento \<authenticationModules> (configuración de red)](../configure-apps/file-schema/network/authenticationmodules-element-network-settings.md). Los módulos de autenticación personalizados deben implementar la interfaz <xref:System.Net.IAuthenticationModule>.  
  
 En el ejemplo siguiente se configura un módulo de autenticación personalizado.  
  
```xml  
<configuration>  
    <system.net>  
        <authenticationModules>  
            <add type="MyAuthModule, MyAuthModule.dll" />  
        </authenticationModules>  
    </system.net>  
</configuration>  
```  
  
 Puede usar el [Elemento \<webRequestModules> (configuración de red)](../configure-apps/file-schema/network/webrequestmodules-element-network-settings.md) para configurar la aplicación de modo que use módulos personalizados específicos del protocolo para solicitar información de recursos de Internet. Los módulos especificados deben implementar la interfaz <xref:System.Net.IWebRequestCreate>. Puede invalidar los módulos predeterminados HTTP, HTTPS y de solicitud de archivos si especifica el módulo personalizado en el archivo de configuración, como en el ejemplo siguiente.  
  
```xml  
<configuration>  
    <system.net>  
        <webRequestModules>  
            <add  
                prefix="HTTP"  
                type = "MyHttpRequest.dll, MyHttpRequestCreator"  
            />  
        </webRequestModules>  
    </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también

- [Programación para redes en .NET Framework](index.md)
- [Esquema de la configuración de red](../configure-apps/file-schema/network/index.md)
- [Elemento \<system.Net> (configuración de red)](../configure-apps/file-schema/network/system-net-element-network-settings.md)
