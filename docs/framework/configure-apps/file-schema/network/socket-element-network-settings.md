---
title: "&lt;socket&gt; (Elemento, Configuraci&#243;n de red) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/socket"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#socket"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<socket> (elemento)"
  - "socket (elemento)"
ms.assetid: 366c634c-7d16-478f-aedf-053eda94a1a0
caps.latest.revision: 21
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 21
---
# &lt;socket&gt; (Elemento, Configuraci&#243;n de red)
Especifica si las operaciones del socket utilizan puertos de terminación.  
  
## Sintaxis  
  
```  
  
      <socket  
  alwaysUseCompletionPortsForConnect="true|false"  
  alwaysUseCompletionPortsForAccept="true|false"  
  ipProtectionLevel ="EdgeRestricted|Restricted|Unrestricted|Unspecified"  
/socket>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|**Atributo**|**Descripción**|  
|------------------|---------------------|  
|`alwaysUseCompletionPortsForAccept`|Indica si el socket siempre debería utilizar los puertos de terminación para llamadas al método Accept.  El valor predeterminado es `false`.|  
|`alwaysUseCompletionPortsForConnect`|Indica si el socket siempre debería utilizar los puertos de terminación para llamadas al método Connect.  El valor predeterminado es `false`.|  
|`ipProtectionLevel`|Especifica el <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=fullName> predeterminado que se debe utilizar para un socket.  El valor predeterminado depende de la versión de Windows.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|**Elemento**|**Descripción**|  
|------------------|---------------------|  
|[settings](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|Configura las opciones de red básicas para el espacio de nombres <xref:System.Net>.|  
  
## Comentarios  
 Los atributos de `alwaysUseCompletionPortsForAccept` y de `alwaysUseCompletionPortsForConnect` se utilizan para especificar el comportamiento predeterminado con respecto al uso de los puertos de finalización por clases en <xref:System.Net.Sockets?displayProperty=fullName>.namespace.  Se recomiendan puertos de terminación para aplicaciones de servidor del alto rendimiento.  
  
 El valor predeterminado de los atributos `alwaysUseCompletionPortsForConnect` y `alwaysUseCompletionPortsForAccept` es **false**.  
  
 La propiedad <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForAccept%2A> se puede utilizar para obtener el valor actual del atributo `alwaysUseCompletionPortsForAccept` de los archivos de configuración aplicables.  La propiedad <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForConnect%2A> se puede utilizar para obtener el valor actual del atributo `alwaysUseCompletionPortsForConnect` de los archivos de configuración aplicables.  
  
 El atributo `ipProtectionLevel` especifica el <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=fullName> predeterminado que se debe utilizar para un socket.  La propiedad <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> permite la configuración de una restricción para un socket de IPv6 al ámbito especificado, como direcciones con el mismo prefijo local de vínculo o sitio.  Esta opción permite que las aplicaciones coloquen restricciones de acceso en los sockets de IPv6.  Estas restricciones permiten que una aplicación que se ejecuta en una LAN privada se fortalezca de forma sencilla frente a ataques externos.  Esta opción amplía o reduce el ámbito de un socket de escucha, lo que permite el acceso no restringido de usuarios públicos y privados cuando sea adecuado o restringe el acceso únicamente al mismo sitio, según necesidad.  
  
 El valor del atributo `ipProtectionLevel` solo afecta al tráfico de entrada inicial:  
  
-   Un servidor TCP que realiza escuchas de las conexiones entrantes en un socket.  
  
-   Una aplicación UDP que recibe un paquete en un socket.  
  
 Este valor de configuración no afecta a las conexiones TCP ya establecidas \(el tráfico no tiene restricciones en ambas direcciones\) y no afecta a ninguna aplicación que envíe paquetes UDP.  
  
 Los valores posibles para el valor de atributo `ipProtectionLevel` corresponden a los niveles de protección definidos especificados en la enumeración <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=fullName> como sigue:  
  
|||  
|-|-|  
|**Valor de atributo**|**Descripción**|  
|EdgeRestricted|El nivel de protección de IP tiene una restricción perimetral.  Este valor lo usan las aplicaciones diseñadas para funcionar a través de Internet.  Este valor no permite NAT \(Traducción de direcciones de red\) transversal mediante la implementación de Teredo en Windows.  Estas aplicaciones pueden eludir los firewalls de IPv4, lo que hace necesario protegerlas frente a los ataques por Internet dirigidos al puerto abierto.  En Windows Server 2003 y Windows XP, el valor predeterminado para el nivel de protección de IP en un socket es la restricción perimetral.|  
|Restringido|El nivel de protección de IP está restringido.  Este valor lo usan las aplicaciones de intranet que no implementan escenarios de Internet.  Estas aplicaciones no se suelen probar ni proteger frente a los ataques por Internet.  Este valor limitará el tráfico recibido a las direcciones locales de vínculo.|  
|Sin restricciones|El nivel de protección de IP no está restringido.  Este valor lo usan las aplicaciones diseñadas para funcionar a través de Internet, incluidas las aplicaciones que aprovechan las funciones de NAT transversal de IPv6 integradas en Windows \(por ejemplo, Teredo\).  Estas aplicaciones pueden eludir los firewalls de IPv4, lo que hace necesario protegerlas frente a los ataques por Internet dirigidos al puerto abierto.  En Windows Server 2008 R2 y Windows Vista, el valor predeterminado para el nivel de protección de IP en un socket es no restringido.|  
|Sin especificar|El nivel de protección de IP no está especificado.  En Windows 7 y Windows Server 2008 R2, este es el valor predeterminado para el nivel de protección de IP en un socket.|  
  
 El valor predeterminado del atributo `ipProtectionLevel` es **Unspecified**.  
  
 La propiedad <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> se puede utilizar para obtener el valor actual del atributo `ipProtectionLevel` de los archivos de configuración aplicables.  
  
## Archivos de configuración  
 Este elemento puede utilizarse en el archivo de configuración de la aplicación o en el archivo de configuración del equipo \(Machine.config\).  
  
## Ejemplo  
 El siguiente ejemplo de código muestra cómo especificar que se deberían utilizar puertos de finalización y que el <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=fullName> predeterminado no debería tener restricciones.  
  
```  
<configuration>  
  <system.net>  
    <settings>  
      <socket  
        alwaysUseCompletionPortsForAccept="true"  
        alwaysUseCompletionPortsForConnect="true"  
        ipProtectionLevel="Unrestricted"  
       />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## Vea también  
 <xref:System.Net?displayProperty=fullName>   
 <xref:System.Net.Configuration.SocketElement?displayProperty=fullName>   
 <xref:System.Net.Sockets?displayProperty=fullName>   
 <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=fullName>   
 <xref:System.Net.Sockets.SocketOptionName?displayProperty=fullName>   
 [Esquema de la configuración de red](../../../../../docs/framework/configure-apps/file-schema/network/index.md)