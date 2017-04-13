---
title: "&lt;proxy&gt; (Elemento, Configuraci&#243;n de red) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/proxy"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#proxy"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<proxy> (elemento)"
  - "proxy (elemento)"
ms.assetid: 37a548d8-fade-4ac5-82ec-b49b6c6cb22a
caps.latest.revision: 20
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 20
---
# &lt;proxy&gt; (Elemento, Configuraci&#243;n de red)
Define un servidor proxy.  
  
## Sintaxis  
  
```  
  
      <proxy   
  autoDetect="true|false|unspecified"    
  bypassonlocal="true|false|unspecified"   
  proxyaddress="uriString"  
  scriptLocation="uriString"   
  usesystemdefault="true|false|unspecified "   
/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|**Atributo**|**Descripción**|  
|------------------|---------------------|  
|`autoDetect`|Especifica si el servidor proxy se detecta automáticamente.  El valor predeterminado es `unspecified`.|  
|`bypassonlocal`|Especifica si el servidor proxy se omite para los recursos locales.  Los recursos locales incluyen el servidor local \(http:\/\/localhost, http:\/\/loopback o http:\/\/127.0.0.1\) y un URI sin puntos \(http:\/\/webserver\).  El valor predeterminado es `unspecified`.|  
|`proxyaddress`|Especifica el URI del servidor proxy que se va a utilizar.|  
|`scriptLocation`|Especifica la ubicación del script de configuración.|  
|`usesystemdefault`|Especifica si se va a utilizar la configuración de proxy de Internet Explorer.  Si se establece en `true`, los atributos subsiguientes reemplazarán la configuración de proxy de Internet Explorer.  El valor predeterminado es `unspecified`.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|**Elemento**|**Descripción**|  
|------------------|---------------------|  
|[defaultProxy](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|Configura el servidor proxy de Protocolo de transferencia de hipertexto \(HTTP\).|  
  
## Valor de texto  
  
## Comentarios  
 El elemento `proxy` define un servidor proxy para una aplicación.  Si este elemento no se encuentra en el archivo de configuración, .NET Framework utilizará la configuración de proxy de Internet Explorer.  
  
 El valor del atributo `proxyaddress` debe ser un identificador uniforme de recursos \(URI\) correcto.  
  
 El atributo `scriptLocation` hace referencia a la detección automática de scripts de configuración de proxy.  La clase <xref:System.Net.WebProxy> intentará localizar un script de configuración \(normalmente denominado Wpad.dat\) cuando la opción **Usar script de configuración automático** esté seleccionada en Internet Explorer.  
  
 Utilice el atributo `usesystemdefault` para las aplicaciones de la versión de 1.1 de .NET Framework que migren a la versión 2.0.  
  
 Se produce una excepción si el atributo `proxyaddress` especifica un proxy predeterminado no válido.  La propiedad <xref:System.Exception.InnerException%2A> en la excepción debería tener más información sobre la causa principal del error.  
  
## Archivos de configuración  
 Este elemento puede utilizarse en el archivo de configuración de la aplicación o en el archivo de configuración del equipo \(Machine.config\).  
  
## Ejemplo  
 En el siguiente ejemplo de código se utilizan los valores predeterminados del servidor proxy de Internet Explorer, se especifica la dirección del servidor proxy y se omite el servidor proxy para el acceso local.  
  
```  
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
  
## Vea también  
 <xref:System.Net.WebProxy?displayProperty=fullName>   
 [Esquema de la configuración de red](../../../../../docs/framework/configure-apps/file-schema/network/index.md)