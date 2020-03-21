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
ms.openlocfilehash: f7cfcc3b9d5a717c23175cd15aa48ae97c828e57
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154821"
---
# <a name="network-element-network-settings"></a>\<Elemento> de red (Configuración de red)
Configura las opciones de red para un servidor de Protocolo simple de transporte de correo (SMTP) externo.  

[**\<configuración>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>smtp**](smtp-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>de red**

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
|`clientDomain`|Especifica el nombre de dominio de cliente que se usará en la solicitud de protocolo SMTP inicial para conectarse al servidor de correo SMTP. El valor predeterminado es el nombre de host local del equipo local que envía la solicitud.|  
|`defaultCredentials`|Especifica si se deben usar las credenciales de usuario predeterminadas para acceder al servidor de correo SMTP para las transacciones SMTP. El valor predeterminado es `false`.|  
|`enableSsl`|Especifica si se utiliza SSL para acceder a un servidor de correo SMTP. El valor predeterminado es `false`.|  
|`host`|Especifica el nombre de host del servidor de correo SMTP que se usará para las transacciones SMTP. Este atributo no tiene ningún valor predeterminado.|  
|`password`|Especifica la contraseña que se usará para la autenticación en el servidor de correo SMTP. Este atributo no tiene ningún valor predeterminado.|  
|`port`|Especifica el número de puerto que se utilizará para conectarse al servidor de correo SMTP. El valor predeterminado es 25.|  
|`targetName`|Especifica el nombre del proveedor de servicios (SPN) que se usará para la autenticación cuando se usa protección ampliada para transacciones SMTP. Este atributo no tiene ningún valor predeterminado.|  
|`userName`|Especifica el nombre de usuario que se usará para la autenticación en el servidor de correo SMTP. Este atributo no tiene ningún valor predeterminado.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<Elemento> smtp (Configuración de red)](smtp-element-network-settings.md)|Configura las opciones de envío de correo del Protocolo simple de transporte de correo (SMTP).|  
  
## <a name="remarks"></a>Observaciones  
 Algunos servidores SMTP requieren que se autentique en el servidor antes de usarlo. Si desea autenticarse con las credenciales de red `defaultCredentials` predeterminadas `true`en el host, establezca el atributo en . La <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType> propiedad se puede utilizar para `defaultCredentials` obtener el valor actual del atributo de los archivos de configuración aplicables.  
  
 También puede utilizar la autenticación básica (un nombre de usuario y una contraseña) para autenticarse en el servidor SMTP. Para utilizar esta opción, debe especificar un nombre de usuario y una contraseña válidos para el servidor SMTP especificado.  
  
> [!NOTE]
> La autenticación `userName` básica `password` envía los valores y al servidor sin cifrar. Cualquier persona que supervise el tráfico de red puede ver sus credenciales y usarlas para conectarse al servidor. Debe considerar el uso de un mecanismo de autenticación más seguro, como Kerberos o NT LAN Manager (NTLM.) Si `defaultCredentials` `true`es , se utilizará Kerberos o NTLM si el servidor admite estos protocolos.  
  
 Las opciones básicas de autenticación y credenciales de red predeterminadas son mutuamente excluyentes; si establece `defaultCredentials` `true` y especifica un nombre de usuario y una contraseña, se utiliza la credencial de red predeterminada y se omiten los datos de autenticación básicos.  
  
 Para la autenticación básica `userName`si especifica un `password` , también debe especificar a para la autenticación usted mismo para el servidor de correo.  
  
 La <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType> propiedad se puede utilizar para `userName` obtener el valor actual del atributo de los archivos de configuración aplicables. La <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType> propiedad se puede utilizar para `password` obtener el valor actual del atributo de los archivos de configuración aplicables. Normalmente, `password` no se introduciría un atributo en los archivos de configuración por motivos de seguridad.  
  
 El `clientDomain` atributo cambia el nombre de dominio de cliente utilizado en la solicitud de protocolo SMTP inicial a un servidor SMTP. El `clientDomain` atributo se puede establecer en el nombre de dominio completo de la máquina local, en lugar del nombre de host local que se usa de forma predeterminada. Esto proporciona un mayor cumplimiento con los estándares de protocolo SMTP. El valor predeterminado es el nombre de host local del equipo local que envía la solicitud. La <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType> propiedad se puede utilizar para `clientDomain` obtener el valor actual del atributo de los archivos de configuración aplicables.  
  
 El `targetName` atributo se utiliza para la autenticación cuando se usa la protección extendida. El valor predeterminado es del formulario\<"SMTPSVC/ host>" donde \<el host> es el nombre de host del servidor de correo SMTP. La <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType> propiedad se puede utilizar para `targetName` obtener el valor actual del atributo de los archivos de configuración aplicables.  
  
 El `enableSsl` atributo especifica si SSL se utiliza para acceder a un servidor de correo SMTP. La <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType> clase solo admite la extensión de servicio SMTP para SMTP seguro sobre la seguridad de la capa de transporte tal como se define en RFC 3207. En este modo, la sesión SMTP comienza en un canal sin cifrar y, a continuación, el cliente emite un comando STARTTLS al servidor para cambiar a la comunicación segura mediante SSL. Consulte RFC 3207 publicado por internet Engineering Task Force (IETF) para obtener más información.  
  
 Un método de conexión alternativo es donde se establece una sesión SSL por adelantado antes de enviar los comandos de protocolo. Este método de conexión a veces se denomina SMTPS y, de forma predeterminada, utiliza el puerto 465. Actualmente no se admite este método de conexión alternativo mediante SSL.  
  
 La <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType> propiedad se puede utilizar para `enableSsl` obtener el valor actual del atributo de los archivos de configuración aplicables.  
  
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
  
## <a name="see-also"></a>Consulte también

- <xref:System.Net.Configuration.SmtpNetworkElement?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- [Esquema de configuración de red](index.md)
