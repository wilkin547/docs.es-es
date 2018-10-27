---
title: '&lt;red&gt; elemento (configuración de red)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#network
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/network
helpviewer_keywords:
- <network> element
- network element
ms.assetid: 2c2c6ad4-ed11-48ab-b28e-2bc0ba9b42c7
ms.openlocfilehash: 242ee42ded339b349cb9e4eb93750b9f5db29b51
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/26/2018
ms.locfileid: "50135238"
---
# <a name="ltnetworkgt-element-network-settings"></a>&lt;red&gt; elemento (configuración de red)
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
|`clientDomain`|Especifica el nombre de dominio de cliente para usar en la solicitud de protocolo SMTP inicial para conectarse al servidor de correo SMTP. El valor predeterminado es el nombre de host local del equipo local envía la solicitud.|  
|`defaultCredentials`|Especifica si se deben usar las credenciales de usuario predeterminadas para tener acceso al servidor de correo SMTP para las transacciones SMTP. El valor predeterminado es `false`.|  
|`enableSsl`|Especifica si se usa SSL para tener acceso a un servidor de correo SMTP. El valor predeterminado es `false`.|  
|`host`|Especifica el nombre de host del servidor de correo SMTP que se utilizará para las transacciones SMTP. Este atributo tiene ningún valor predeterminado.|  
|`password`|Especifica la contraseña que se utilizará para la autenticación en el servidor de correo SMTP. Este atributo tiene ningún valor predeterminado.|  
|`port`|Especifica el número de puerto para conectarse al servidor de correo SMTP. El valor predeterminado es 25.|  
|`targetName`|Especifica el nombre de proveedor de servicio (SPN) que se usará para la autenticación al usar la protección ampliada para las transacciones SMTP. Este atributo tiene ningún valor predeterminado.|  
|`userName`|Especifica el nombre de usuario que se usará para la autenticación en el servidor de correo SMTP. Este atributo tiene ningún valor predeterminado.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<SMTP > elemento (configuración de red)](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|Configura las opciones de envío de correo de Protocolo Simple de transferencia de correo (SMTP).|  
  
## <a name="remarks"></a>Comentarios  
 Algunos servidores SMTP requieren autenticarse en el servidor antes de su uso. Si desea autenticarse utilizando las credenciales de red predeterminadas en el host, establezca el `defaultCredentials` atributo `true`. El <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType> propiedad puede usarse para obtener el valor actual de la `defaultCredentials` atributo desde archivos de configuración aplicables.  
  
 También puede usar la autenticación básica (nombre de usuario y contraseña) para autenticarse en el servidor SMTP. Para usar esta opción, debe especificar un nombre de usuario válido y una contraseña para el servidor SMTP especificado.  
  
> [!NOTE]
>  La autenticación básica envía el `userName` y `password` valores sin cifrar al servidor. Cualquiera que controle el tráfico de red puede ver sus credenciales y utilizarlas para conectarse al servidor. Debe considerar el uso de un mecanismo de autenticación más seguro, por ejemplo, Kerberos o NT LAN Manager (NTLM). Si `defaultCredentials` es `true`, Kerberos o NTLM se utilizará si el servidor admite estos protocolos.  
  
 Las opciones de credenciales de red predeterminada y la autenticación básicas se excluyen mutuamente; Si establece `defaultCredentials` a `true` y especifique un nombre de usuario y una contraseña, se utiliza la credencial de red predeterminada y se omiten los datos de la autenticación básica.  
  
 Para la autenticación básica si especifica un `userName`, también debe especificar un `password` a la autenticación para el servidor de correo.  
  
 El <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType> propiedad puede usarse para obtener el valor actual de la `userName` atributo desde archivos de configuración aplicables. El <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType> propiedad puede usarse para obtener el valor actual de la `password` atributo desde archivos de configuración aplicables. Un `password` atributo no normalmente se especificaría en archivos de configuración por motivos de seguridad.  
  
 El `clientDomain` atributo cambia el nombre de dominio del cliente utilizado en la solicitud de protocolo SMTP inicial para un servidor SMTP. El `clientDomain` atributo puede establecerse en el nombre de dominio completo del equipo local, en lugar de con el nombre de host local que se usa de forma predeterminada. Esto proporciona mayor compatibilidad con los estándares de protocolo SMTP. El valor predeterminado es el nombre de host local del equipo local envía la solicitud. El <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType> propiedad puede usarse para obtener el valor actual de la `clientDomain` atributo desde archivos de configuración aplicables.  
  
 El `targetName` atributo se utiliza para la autenticación cuando se usa la protección extendida. El valor predeterminado es el formato "SMTPSVC /\<host >" donde \<host > es el nombre de host del servidor de correo SMTP. El <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType> propiedad puede usarse para obtener el valor actual de la `targetName` atributo desde archivos de configuración aplicables.  
  
 El `enableSsl` atributo especifica si se usa SSL para tener acceso a un servidor de correo SMTP. La <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType> clase sólo admite la extensión de servicio SMTP para SMTP seguro a través de la seguridad de la capa de transporte como se define en RFC 3207. En este modo, la sesión SMTP comienza en un canal no cifrado, a continuación, se emite un comando STARTTLS por el cliente al servidor para cambiar a una comunicación segura mediante SSL. Vea RFC 3207 publicada por Internet Engineering Task Force (IETF) para obtener más información.  
  
 Un método de conexión alternativo es donde se establece por adelantado una sesión SSL antes de cualquier protocolo que se envían comandos. Este método de conexión a veces se denomina SMTPS y usa el puerto 465 de forma predeterminada. Este método de conexión alternativo mediante SSL no se admite actualmente.  
  
 El <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType> propiedad puede usarse para obtener el valor actual de la `enableSsl` atributo desde archivos de configuración aplicables.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente especifica los parámetros SMTP adecuados para enviar correo electrónico utilizando las credenciales de red predeterminadas.  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="Network">  
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
