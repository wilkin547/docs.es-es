---
title: "Configuraci&#243;n de aplicaciones de Internet | Microsoft Docs"
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
  - "descargar de recursos de Internet, proxy predeterminado"
  - "envío de datos, proxy predeterminado"
  - "recepción de datos, proxy predeterminado"
  - "descarga de recursos de Internet, configuración de aplicaciones de Internet"
  - "módulos específicos del protocolo"
  - "módulos de autenticación personalizados"
  - "recepción de datos, configuración de aplicaciones de Internet"
  - "opciones de configuración [.NET Framework], aplicaciones de Internet"
  - "solicitud de datos de Internet, configuración de aplicaciones de Internet"
  - "solicitud de datos de Internet, proxy predeterminado"
  - "respuesta a una solicitud de Internet, proxy predeterminado"
  - "Internet, configuración de aplicaciones de Internet"
  - "respuesta a una solicitud de Internet, configuración de aplicaciones de Internet"
  - "proxy predeterminado"
  - "recursos de red, proxy predeterminado"
  - "envío de datos, configuración de aplicaciones de Internet"
  - "recursos de red, configuración de aplicaciones de Internet"
  - "Internet, proxy predeterminado"
ms.assetid: bb707c72-eed2-4a82-8800-c9e68df2fd4f
caps.latest.revision: 15
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 15
---
# Configuraci&#243;n de aplicaciones de Internet
El elemento de configuración de [\<system.Net\> \(elemento\) \(configuración de red\)](../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md) contiene información de configuración de red para las aplicaciones.  Mediante el elemento de [\<system.Net\> \(elemento\) \(configuración de red\)](../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md) , puede establecer los servidores proxy, establezca parámetros de administración de la conexión, y módulos de autenticación personalizada de inclusión y la solicitud en la aplicación.  
  
 El elemento de [\<defaultProxy\> \(Elemento, Configuración de red\)](../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md) define el servidor proxy devuelto por la clase de `GlobalProxySelection` .  Cualquier <xref:System.Net.HttpWebRequest> que no tiene su propia propiedad de <xref:System.Net.HttpWebRequest.Proxy%2A> establecida en un valor concreto utiliza el proxy predeterminado.  Además de establecer la dirección del proxy, puede crear una lista de direcciones del servidor que no utilizan el proxy, y puede indicar que el proxy no se debe utilizar para las direcciones locales.  
  
 Es importante recordar que los valores de Microsoft Internet Explorer se combinan con las opciones de configuración, con la última prioridad que toma.  
  
 El ejemplo siguiente establece la dirección predeterminada del servidor proxy a http:\/\/proxyserver, indica que el proxy no se debe utilizar para las direcciones locales, y especifica que todas las solicitudes a los servidores situados en el dominio de contoso.com deben omitir el servidor proxy.  
  
```  
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
  
 Utilice el elemento de [\<connectionManagement\> \(Elemento, Configuración de red\)](../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md) para configurar el número de conexiones persistentes que se pueden crear en un servidor concreto o al resto de los servidores.  El ejemplo siguiente se configura la aplicación para utilizar dos conexiones persistentes el servidor www.contoso.com, cuatro conexiones persistentes el servidor con la dirección IP 192.168.1.2, y una conexión persistente al resto de los servidores.  
  
```  
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
  
 Los módulos de autenticación personalizada se configuran con el elemento de [\<authenticationModules\> \(Elemento, Configuración de red\)](../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md) .  Los módulos de autenticación personalizada deben implementar la interfaz de <xref:System.Net.IAuthenticationModule> .  
  
 El ejemplo siguiente configura un módulo de autenticación personalizada.  
  
```  
<configuration>  
    <system.net>  
        <authenticationModules>  
            <add type="MyAuthModule, MyAuthModule.dll" />  
        </authenticationModules>  
    </system.net>  
</configuration>  
```  
  
 Puede utilizar el elemento de [\<webRequestModules\> \(Elemento, Configuración de red\)](../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md) para configurar la aplicación para utilizar los módulos protocolo\- específicos personalizados para solicitar información de recursos de internet.  Los módulos especificados deben implementar la interfaz de <xref:System.Net.IWebRequestCreate> .  Puede invalidar el HTTP predeterminado, HTTPS, y módulos de la solicitud del archivo especificando el módulo personalizado en el archivo de configuración, como en el ejemplo siguiente.  
  
```  
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
  
## Vea también  
 [Programación para redes en .NET Framework](../../../docs/framework/network-programming/index.md)   
 [Esquema de la configuración de red](../../../docs/framework/configure-apps/file-schema/network/index.md)   
 [\<system.Net\> \(elemento\) \(configuración de red\)](../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)