---
title: '&lt;red&gt; Element (Network Settings)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#network
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/network
helpviewer_keywords:
- <network> element
- network element
ms.assetid: 2c2c6ad4-ed11-48ab-b28e-2bc0ba9b42c7
caps.latest.revision: "13"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 679351fd2d6f0727d40bd57c9ef2016738462eb7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltnetworkgt-element-network-settings"></a>&lt;red&gt; Element (Network Settings)
Configura las opciones de red para un servidor de Protocolo Simple de transferencia de correo (SMTP) externo.  
  
 \<configuration>  
\<System.NET >  
\<mailSettings >  
\<SMTP >  
\<red >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
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
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`clientDomain`|Especifica el nombre de dominio de cliente para utilizar en la solicitud de protocolo SMTP inicial para conectarse al servidor de correo SMTP. El valor predeterminado es el nombre de host local del equipo local que envía la solicitud.|  
|`defaultCredentials`|Especifica si se deben usar las credenciales de usuario predeterminadas para tener acceso al servidor de correo SMTP para las transacciones SMTP. El valor predeterminado es `false`.|  
|`enableSsl`|Especifica si se usa SSL para tener acceso a un servidor de correo SMTP. El valor predeterminado es `false`.|  
|`host`|Especifica el nombre de host del servidor de correo SMTP que se utilizará para las transacciones SMTP. Este atributo tiene ningún valor predeterminado.|  
|`password`|Especifica la contraseña que se utilizará para la autenticación en el servidor de correo SMTP. Este atributo tiene ningún valor predeterminado.|  
|`port`|Especifica el número de puerto para conectarse al servidor de correo SMTP. El valor predeterminado es 25.|  
|`targetName`|Especifica el nombre de proveedor de servicio (SPN) que se usará para la autenticación cuando se usa la protección extendida para las transacciones SMTP. Este atributo tiene ningún valor predeterminado.|  
|`userName`|Especifica el nombre de usuario que se utilizará para la autenticación en el servidor de correo SMTP. Este atributo tiene ningún valor predeterminado.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<SMTP > elemento (configuración de red)](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|Configura opciones de envío de correo de Protocolo Simple de transferencia de correo (SMTP).|  
  
## <a name="remarks"></a>Comentarios  
 Algunos servidores SMTP requieren autenticarse en el servidor antes de su uso. Si desea autenticarse utilizando las credenciales de red predeterminadas en su host, establezca el `defaultCredentials` atribuir a `true`. El <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType> propiedad puede utilizarse para obtener el valor actual de la `defaultCredentials` atributos de archivos de configuración aplicables.  
  
 También puede utilizar la autenticación básica (nombre de usuario y contraseña) para autenticarse en el servidor SMTP. Para usar esta opción, debe especificar un nombre de usuario válido y una contraseña para el servidor SMTP especificado.  
  
> [!NOTE]
>  La autenticación básica envía el `userName` y `password` valores al servidor sin cifrar. Cualquiera que controle el tráfico de red puede ver sus credenciales y utilizarlas para conectarse al servidor. Debe considerar el uso de un mecanismo de autenticación más seguro, como Kerberos o NT LAN Manager (NTLM). Si `defaultCredentials` es `true`, Kerberos o NTLM se utilizará si el servidor admite estos protocolos.  
  
 Las opciones de credenciales de red predeterminada y la autenticación básicas son mutuamente excluyentes; Si establece `defaultCredentials` a `true` y especifique un nombre de usuario y una contraseña, se utiliza la credencial de red predeterminada y se pasa por alto los datos de la autenticación básica.  
  
 Para la autenticación básica si especifica un `userName`, también debe especificar un `password` a la autenticación para el servidor de correo.  
  
 El <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType> propiedad puede utilizarse para obtener el valor actual de la `userName` atributos de archivos de configuración aplicables. El <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType> propiedad puede utilizarse para obtener el valor actual de la `password` atributos de archivos de configuración aplicables. Un `password` atributo no normalmente se especificaría en archivos de configuración por razones de seguridad.  
  
 El `clientDomain` atributo cambia el nombre de dominio de cliente utilizado en la solicitud de protocolo SMTP inicial a un servidor SMTP. El `clientDomain` atributo puede establecerse en el nombre de dominio completo del equipo local, en lugar de con el nombre de host local que se utiliza de forma predeterminada. Esto proporciona mayor compatibilidad con los estándares de protocolo SMTP. El valor predeterminado es el nombre de host local del equipo local que envía la solicitud. El <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType> propiedad puede utilizarse para obtener el valor actual de la `clientDomain` atributos de archivos de configuración aplicables.  
  
 El `targetName` atributo se utiliza para la autenticación cuando se usa la protección extendida. El valor predeterminado es el formato "SMTPSVC /\<host >" donde \<host > es el nombre de host del servidor de correo SMTP. El <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType> propiedad puede utilizarse para obtener el valor actual de la `targetName` atributos de archivos de configuración aplicables.  
  
 El `enableSsl` atributo especifica si se usa SSL para tener acceso a un servidor de correo SMTP. La <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType> clase solo admite la extensión de servicio SMTP para SMTP seguro sobre seguridad de la capa de transporte como se define en RFC 3207. En este modo, la sesión de SMTP comienza en un canal no cifrado, a continuación, se emite un comando STARTTLS por el cliente al servidor para cambiar a una comunicación segura mediante SSL. Vea RFC 3207 publicada por Internet Engineering Task Force (IETF) para obtener más información.  
  
 Un método de conexión alternativo es donde se establece por adelantado una sesión SSL antes que cualquier protocolo que se envían comandos. Este método de conexión a veces se denomina SMTPS y de forma predeterminada usa el puerto 465. Este método de conexión alternativo usando SSL no se admite actualmente.  
  
 El <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType> propiedad puede utilizarse para obtener el valor actual de la `enableSsl` atributos de archivos de configuración aplicables.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se especifica los parámetros SMTP adecuados para enviar correo electrónico mediante las credenciales de red predeterminadas.  
  
```xml  
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
  
## <a name="see-also"></a>Vea también  
 <xref:System.Net.Configuration.SmtpNetworkElement?displayProperty=nameWithType>  
 <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>  
 <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>  
 [Esquema de la configuración de red](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
