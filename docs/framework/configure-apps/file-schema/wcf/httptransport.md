---
title: <httpTransport>
ms.date: 03/30/2017
ms.assetid: 8b30c065-b32a-4fa3-8eb4-5537a9c6b897
ms.openlocfilehash: 14d774ba7711c9ce60fb1db5a2b050c310550ec1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203896"
---
# \<httpTransport>

Especifica un transporte HTTP para transmitir los mensajes SOAP para un enlace personalizado.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<httpTransport>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<httpTransport allowCookies="Boolean"
               authenticationScheme="Digest/Negotiate/Ntlm/Basic/Anonymous"
               bypassProxyOnLocal="Boolean"
               hostnameComparisonMode="StrongWildcard/Exact/WeakWildcard"
               keepAliveEnabled="Boolean"
               maxBufferSize="Integer"
               proxyAddress="Uri"
               proxyAuthenticationScheme="None/Digest/Negotiate/Ntlm/Basic/Anonymous"
               realm="String"
               transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse"
               unsafeConnectionNtlmAuthentication="Boolean"
               useDefaultWebProxy="Boolean" />
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  

 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|allowCookies|Un valor booleano que especifica si el cliente acepta las cookies y las propaga en solicitudes futuras. De manera predeterminada, es `false`.<br /><br /> Puede usar este atributo al interactuar con los servicios Web ASMX que utilizan cookies. De esta manera, puede estar seguro de que las cookies devueltas del servidor se copian automáticamente en todas las solicitudes de cliente futuras para ese servicio.|  
|authenticationScheme|Especifica el protocolo utilizado para autenticar solicitudes de cliente que son procesadas por un agente de escucha HTTP. Los valores válidos incluyen los siguientes:<br /><br /> -Digest: especifica la autenticación implícita.<br />-Negotiate: negocia con el cliente para determinar el esquema de autenticación. Si cliente y el servidor son compatibles con Kerberos, se utiliza; de lo contrario, se utiliza NTLM.<br />-NTLM: especifica la autenticación NTLM.<br />-Basic: especifica la autenticación básica.<br />-Anonymous: especifica la autenticación anónima.<br /><br /> El valor predeterminado es Anonymous. Este atributo es del tipo <xref:System.Net.AuthenticationSchemes>. Se puede establecer este atributo sólo una vez.|  
|bypassProxyOnLocal|Valor de tipo booleano que indica si se omitirá el servidor proxy para las direcciones locales. De manera predeterminada, es `false`.<br /><br /> Una dirección local es la que está en la LAN local o intranet.<br /><br /> Windows Communication Foundation (WCF) siempre omite el proxy si la dirección de servicio comienza con `http://localhost` .<br /><br /> Debería utilizar el nombre del host en lugar del localhost si desea que los clientes pasen por un proxy al comunicarse con los servicios en el mismo equipo.|  
|hostnameComparisonMode|Especifica el modo de comparación de nombres de host HTTP usado para analizar los URI. Los valores válidos son<br /><br /> -StrongWildcard: ("+") coincide con todos los nombres de host posibles en el contexto del esquema especificado, el puerto y el URI relativo.<br />-Exact: sin caracteres comodín<br />-WeakWildcard: (" \* ") coincide con todos los nombres de host posibles en el contexto del esquema especificado, el puerto y los URI relativos que no se han encontrado explícitamente o a través del mecanismo de comodín seguro.<br /><br /> Este atributo es del tipo <xref:System.ServiceModel.HostNameComparisonMode>. El valor predeterminado es <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>.|  
|keepAliveEnabled|Un valor booleano que especifica si se debe establecer una conexión continua con el recurso de Internet.|  
|maxBufferSize|Un entero positivo que especifica el tamaño máximo del búfer. El valor predeterminado es 524288.|  
|proxyAddress|Un URI que especifica la dirección del proxy HTTP. Si `useSystemWebProxy` es `true`, este valor debe ser `null`. El valor predeterminado es `null`.|  
|proxyAuthenticationScheme|Especifica el protocolo utilizado para autenticar solicitudes de cliente que son procesadas por un proxy HTTP. Los valores válidos incluyen los siguientes:<br /><br /> -None: no se realiza ninguna autenticación.<br />-Digest: especifica la autenticación implícita.<br />-Negotiate: negocia con el cliente para determinar el esquema de autenticación. Si cliente y el servidor son compatibles con Kerberos, se utiliza; de lo contrario, se utiliza NTLM.<br />-NTLM: especifica la autenticación NTLM.<br />-Basic: especifica la autenticación básica.<br />-Anonymous: especifica la autenticación anónima.<br /><br /> El valor predeterminado es Anonymous. Este atributo es del tipo <xref:System.Net.AuthenticationSchemes>. Tenga en cuenta que <xref:System.Net.AuthenticationSchemes.IntegratedWindowsAuthentication?displayProperty=nameWithType> no se admite.|  
|realm|Una cadena que especifica el dominio kerberos que se utilizará en el proxy/servidor. El valor predeterminado es una cadena vacía.<br /><br /> Los servidores usan los dominios para particionar recursos protegidos. Cada partición puede tener su propio esquema de autenticación y/o base de datos de autorización. Los dominios sólo se utilizan para la autenticación básica e implícita. Cuando un cliente se autentica correctamente, la autenticación es válida para todos los recursos de un dominio kerberos determinado. Para obtener una descripción detallada de los territorios, consulte RFC 2617 en el [sitio web de IETF](https://www.ietf.org).|  
|transferMode|Especifica si los mensajes se almacenan en búfer, se transmiten o si son una solicitud o una respuesta. Los valores válidos incluyen los siguientes:<br /><br /> -Buffered: los mensajes de solicitud y respuesta se almacenan en búfer.<br />-Streamed: los mensajes de solicitud y respuesta se transmiten por secuencias.<br />-StreamedRequest: se transmite el mensaje de solicitud y se almacena en búfer el mensaje de respuesta.<br />-StreamedResponse: el mensaje de solicitud se almacena en búfer y se transmite el mensaje de respuesta.<br /><br /> El valor predeterminado es Buffered. Este atributo es del tipo <xref:System.ServiceModel.TransferMode>.|  
|unsafeConnectionNtlmAuthentication|Un valor booleano que especifica si la conexión compartida no segura está habilitada en el servidor. De manera predeterminada, es `false`. Si está habilitado, la autenticación NTLM se realiza una vez en cada conexión TCP.|  
|useDefaultWebProxy|Un valor que especifica si se utiliza la configuración del proxy del equipo en lugar de la configuración específica del usuario. El valor predeterminado es `true`.|  
  
### <a name="child-elements"></a>Elementos secundarios  

 None  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|Define todas las funcionalidades de enlace del enlace personalizado.|  
  
## <a name="remarks"></a>Observaciones  

 El elemento `httpTransport` es el punto inicial para crear un enlace personalizado que implementa el protocolo de transporte HTTP. HTTP es el transporte primario utilizado para fines de interoperabilidad. El Windows Communication Foundation (WCF) admite este transporte para garantizar la interoperabilidad con otras pilas de servicios web que no son de WCF.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.ServiceModel.Configuration.HttpTransportElement>
- <xref:System.ServiceModel.Channels.HttpTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Transportes](../../../wcf/feature-details/transports.md)
- [Elección del transporte](../../../wcf/feature-details/choosing-a-transport.md)
- [Enlaces](../../../wcf/bindings.md)
- [Extensión de enlaces](../../../wcf/extending/extending-bindings.md)
- [Enlaces personalizados](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
