---
title: "&lt;network&gt; (Elemento, Configuraci&#243;n de red) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#network"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/network"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<network> (elemento)"
  - "network (elemento)"
ms.assetid: 2c2c6ad4-ed11-48ab-b28e-2bc0ba9b42c7
caps.latest.revision: 13
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 13
---
# &lt;network&gt; (Elemento, Configuraci&#243;n de red)
Configura las opciones de red para un servidor de protocolo simple de transferencia de correo \(SMTP\) externo.  
  
## Sintaxis  
  
```  
  
      <network  
  clientDomain="string"   
  defaultCredentials="true|false"  
  enableSsl="true|false"  
  host="string"   
  password="string"  
  port="integer"   
  targetName="string"  
  userName="string"  
/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`clientDomain`|Especifica el nombre de dominio del cliente que se utiliza en la solicitud de protocolo SMTP inicial para conectarse al servidor de correo SMTP.  El valor predeterminado es el nombre de host local del equipo local que envía la solicitud.|  
|`defaultCredentials`|Especifica si las credenciales del usuario predeterminado se deberían utilizar para tener acceso al servidor de correo SMTP para las transacciones SMTP.  El valor predeterminado es `false`.|  
|`enableSsl`|Especifica si se usa SSL para obtener acceso a un servidor de correo SMTP.  El valor predeterminado es `false`.|  
|`host`|Especifica el nombre del host del servidor de correo SMTP que se utilizará para las transacciones SMTP.  Este atributo no tiene ningún valor predeterminado.|  
|`password`|Especifica la contraseña que debe utilizarse para la autenticación en el servidor de correo SMTP.  Este atributo no tiene ningún valor predeterminado.|  
|`port`|Especifica el número de puerto que debe utilizarse para conectarse al servidor de correo SMTP.  El valor predeterminado es 25.|  
|`targetName`|Especifica el nombre del proveedor de servicios \(SPN\) que se utiliza para la autenticación cuando se usa la protección extendida para transacciones SMTP.  Este atributo no tiene ningún valor predeterminado.|  
|`userName`|Especifica el nombre de usuario que debe utilizarse para la autenticación en el servidor de correo SMTP.  Este atributo no tiene ningún valor predeterminado.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<smtp\> \(Elemento, Configuración de red\)](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|Configura opciones para el envío de correo del Protocolo simple de transferencia de correo \(SMTP\).|  
  
## Comentarios  
 Algunos servidores SMTP requieren la autenticación del usuario en el servidor antes de su utilización.  Si desea autenticarse utilizando las credenciales de red predeterminadas de su host, establezca el atributo `defaultCredentials` en `true`.  La propiedad <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=fullName> se puede utilizar para obtener el valor actual del atributo `defaultCredentials` de los archivos de configuración aplicables.  
  
 También es posible utilizar la autenticación básica \(un nombre de usuario y una contraseña\) para autenticarse en el servidor SMTP.  Para utilizar esta opción, es necesario especificar una contraseña y un nombre de usuario válido para el servidor SMTP especificado.  
  
> [!NOTE]
>  La autenticación básica envía los valores `userName` y `password` al servidor no cifrado.  Cualquier usuario que supervise el tráfico de red podrá ver sus credenciales y utilizarlas para conectarse al servidor.  Se debería considerar la utilización de un mecanismo de autenticación más seguro, como Kerberos o NT LAN Manager \(NTLM\). Si `defaultCredentials` es `true`, se utilizarán Kerberos o NTLM si el servidor admite estos protocolos.  
  
 La autenticación básica y las opciones de credenciales de red predeterminadas son mutuamente exclusivas; si se establece `defaultCredentials` en `true` y se especifica un nombre de usuario y una contraseña, se utilizará la credencial de red predeterminada y se omitirán los datos de autenticación básicos.  
  
 En el caso de la autenticación básica, si especifica `userName`, también deberá especificar `password` para autenticarse a sí mismo ante el servidor de correo.  
  
 La propiedad <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=fullName> se puede utilizar para obtener el valor actual del atributo `userName` de los archivos de configuración aplicables.  La propiedad <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=fullName> se puede utilizar para obtener el valor actual del atributo `password` de los archivos de configuración aplicables.  Un atributo `password` no se escribiría normalmente por razones de seguridad en archivos de configuración.  
  
 El atributo `clientDomain` cambia el nombre de dominio del cliente utilizado en la solicitud de protocolo SMTP inicial para un servidor SMTP.  El atributo `clientDomain` se puede establecer en el nombre de dominio completo del equipo local, en lugar del nombre del host local que se utiliza de forma predeterminada.  Esto proporciona mayor cumplimiento de los estándares del protocolo SMTP.  El valor predeterminado es el nombre de host local del equipo local que envía la solicitud.  La propiedad <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=fullName> se puede utilizar para obtener el valor actual del atributo `clientDomain` de los archivos de configuración aplicables.  
  
 El atributo `targetName` se utiliza para la autenticación cuando se utiliza la protección extendida.  El valor predeterminado tiene el formato “SMTPSVC\/Host\<\>” donde \<es\> el nombre del host del host del servidor de correo SMTP.  La propiedad <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=fullName> se puede utilizar para obtener el valor actual del atributo `targetName` de los archivos de configuración aplicables.  
  
 El atributo `enableSsl`  especifica si se usa SSL para obtener acceso a un servidor de correo SMTP.  La clase <xref:System.Net.Mail.SmtpClient?displayProperty=fullName> sólo admite la extensión de servicio SMTP para SMTP seguro sobre Seguridad de la capa de transporte como se define en RFC 3207.  En este modo, la sesión de SMTP comienza en un canal no cifrado, a continuación, el cliente ejecuta un comando STARTTLS al servidor para intercambiar para proteger la comunicación mediante SSL.  Vea RFC 3207 publicada por Internet Engineering Task Force \(IETF\) para obtener más información.  
  
 Un método de conexión alternativo es donde una sesión de SSL se establece al frente antes de que se envíe cualquier comando de protocolo.  Este método de conexión a veces se denomina SMTP\/SSL y de forma predeterminada usa el puerto 465.  Actualmente no se admite este método de conexión alternativo usando SSL.  
  
 La propiedad <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=fullName> se puede utilizar para obtener el valor actual del atributo `enableSsl` de los archivos de configuración aplicables.  
  
## Ejemplo  
 En el ejemplo de código siguiente se especifican los parámetros SMTP adecuados para enviar correo electrónico mediante las credenciales de red predeterminadas.  
  
```  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="network">  
        <network  
          clientDomain="www.contoso.com"  
          defaultCredentials="true"  
          enableSsl="false"  
          host="mail.contoso.com"  
          port="25"  
        />  
      </smtp>  
    </mailSettings>  
  </system.net>  
</configuration>  
```  
  
## Vea también  
 <xref:System.Net.Configuration.SmtpNetworkElement?displayProperty=fullName>   
 <xref:System.Net.Configuration.SmtpSection?displayProperty=fullName>   
 <xref:System.Net.Mail.SmtpClient?displayProperty=fullName>   
 [Esquema de la configuración de red](../../../../../docs/framework/configure-apps/file-schema/network/index.md)