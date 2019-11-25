---
title: Elemento <network> (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#network
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/network
helpviewer_keywords:
- <network> element
- network element
ms.assetid: 2c2c6ad4-ed11-48ab-b28e-2bc0ba9b42c7
ms.openlocfilehash: f7b73a725cd406df9ce41e2c4522850ce974022f
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089219"
---
# <a name="network-element-network-settings"></a>\<elemento de > de red (configuración de red)
Configura las opciones de red para un servidor de Protocolo simple de transferencia de correo (SMTP) externo.  

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<mailSettings >** ](mailsettings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**SMTP**](smtp-element-network-settings.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<> de **red**

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
|`clientDomain`|Especifica el nombre de dominio de cliente que se va a usar en la solicitud de protocolo SMTP inicial para conectarse al servidor de correo SMTP. El valor predeterminado es el nombre localhost del equipo local que envía la solicitud.|  
|`defaultCredentials`|Especifica si se deben usar las credenciales de usuario predeterminadas para obtener acceso al servidor de correo SMTP para las transacciones SMTP. El valor predeterminado es `false`.|  
|`enableSsl`|Especifica si se utiliza SSL para tener acceso a un servidor de correo SMTP. El valor predeterminado es `false`.|  
|`host`|Especifica el nombre de host del servidor de correo SMTP que se va a usar para las transacciones SMTP. Este atributo no tiene ningún valor predeterminado.|  
|`password`|Especifica la contraseña que se utilizará para la autenticación en el servidor de correo SMTP. Este atributo no tiene ningún valor predeterminado.|  
|`port`|Especifica el número de puerto que se va a utilizar para conectarse al servidor de correo SMTP. El valor predeterminado es 25.|  
|`targetName`|Especifica el nombre del proveedor de servicios (SPN) que se va a usar para la autenticación cuando se usa la protección extendida para transacciones SMTP. Este atributo no tiene ningún valor predeterminado.|  
|`userName`|Especifica el nombre de usuario que se utilizará para la autenticación en el servidor de correo SMTP. Este atributo no tiene ningún valor predeterminado.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<elemento > de SMTP (configuración de red)](smtp-element-network-settings.md)|Configura las opciones de envío de correo del Protocolo simple de transferencia de correo (SMTP).|  
  
## <a name="remarks"></a>Comentarios  
 Algunos servidores SMTP requieren que se autentique en el servidor antes de usarlo. Si desea autenticarse con las credenciales de red predeterminadas en el host, establezca el atributo `defaultCredentials` en `true`. La propiedad <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType> se puede utilizar para obtener el valor actual del atributo `defaultCredentials` de los archivos de configuración aplicables.  
  
 También puede usar la autenticación básica (un nombre de usuario y una contraseña) para autenticarse en el servidor SMTP. Para usar esta opción, debe especificar un nombre de usuario y una contraseña válidos para el servidor SMTP especificado.  
  
> [!NOTE]
> La autenticación básica envía los valores de `userName` y `password` al servidor sin cifrar. Cualquier persona que supervise el tráfico de red puede ver sus credenciales y usarlas para conectarse al servidor. Considere la posibilidad de usar un mecanismo de autenticación más seguro, como Kerberos o NT LAN Manager (NTLM). Si se `true``defaultCredentials`, se usarán Kerberos o NTLM si el servidor es compatible con estos protocolos.  
  
 Las opciones de autenticación básica y de credenciales de red predeterminadas son mutuamente excluyentes; Si establece `defaultCredentials` en `true` y especifica un nombre de usuario y una contraseña, se usa la credencial de red predeterminada y se omiten los datos de autenticación básicos.  
  
 En el caso de la autenticación básica, si especifica un `userName`, también debe especificar un `password` para autenticarse en el servidor de correo.  
  
 La propiedad <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType> se puede utilizar para obtener el valor actual del atributo `userName` de los archivos de configuración aplicables. La propiedad <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType> se puede utilizar para obtener el valor actual del atributo `password` de los archivos de configuración aplicables. Un atributo `password` no se escribiría normalmente en los archivos de configuración por motivos de seguridad.  
  
 El atributo `clientDomain` cambia el nombre de dominio del cliente utilizado en la solicitud de protocolo SMTP inicial a un servidor SMTP. El atributo `clientDomain` se puede establecer en el nombre de dominio completo del equipo local, en lugar del nombre de host local que se utiliza de forma predeterminada. Esto proporciona mayor compatibilidad con los estándares de protocolo SMTP. El valor predeterminado es el nombre localhost del equipo local que envía la solicitud. La propiedad <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType> se puede utilizar para obtener el valor actual del atributo `clientDomain` de los archivos de configuración aplicables.  
  
 El atributo `targetName` se utiliza para la autenticación cuando se usa la protección ampliada. El valor predeterminado tiene el formato "SMTPSVC/\<host >", donde \<host > es el nombre de host del servidor de correo SMTP. La propiedad <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType> se puede utilizar para obtener el valor actual del atributo `targetName` de los archivos de configuración aplicables.  
  
 El atributo `enableSsl` especifica si se utiliza SSL para tener acceso a un servidor de correo SMTP. La clase <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType> solo admite la extensión de servicio SMTP para SMTP seguro a través de la seguridad de la capa de transporte, tal y como se define en RFC 3207. En este modo, la sesión SMTP se inicia en un canal sin cifrar y, a continuación, el cliente emite un comando STARTTLS al servidor para cambiar a la comunicación segura mediante SSL. Para obtener más información, consulte RFC 3207 publicado por el equipo de ingeniería de Internet (IETF).  
  
 Un método de conexión alternativo es el lugar en el que se establece una sesión SSL antes de que se envíen los comandos del protocolo. Este método de conexión se denomina a veces SMTP y, de forma predeterminada, usa el puerto 465. Este método de conexión alternativo que usa SSL no se admite actualmente.  
  
 La propiedad <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType> se puede utilizar para obtener el valor actual del atributo `enableSsl` de los archivos de configuración aplicables.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se especifican los parámetros SMTP adecuados para enviar correo electrónico con las credenciales de red predeterminadas.  
  
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

- <xref:System.Net.Configuration.SmtpNetworkElement?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- [Esquema de la configuración de red](index.md)
