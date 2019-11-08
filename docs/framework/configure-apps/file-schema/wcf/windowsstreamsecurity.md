---
title: <windowsStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 926bea29-90c7-4a26-9cf0-fb4aa44f6f70
ms.openlocfilehash: dab8505a9ddb348a6f7fe16ae9acb3a0119a8b06
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73735888"
---
# <a name="windowsstreamsecurity"></a>\<windowsStreamSecurity >
Especifique configuración de seguridad de secuencia de Windows del enlace personalizado.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;\<[**enlaces**](bindings.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**customBinding**](custombinding.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**enlace** >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<windowsStreamSecurity >**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign" />
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|protectionLevel|Define la seguridad del nivel de mensaje. Al firmar los mensajes se reduce el riesgo de que un tercero manipule el mensaje mientras se transfiere. El cifrado proporciona privacidad de nivel de datos durante el transporte. Los valores válidos son los siguientes:<br /><br /> -None: sin protección.<br />-Sign: los mensajes se firman.<br />-EncryptAndSign: los mensajes se firman y cifran.<br /><br /> El valor predeterminado es EncryptAndSign.<br /><br /> Este atributo es del tipo <xref:System.Net.Security.ProtectionLevel>.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<> de enlace](bindings.md)|Define todas las funcionalidades de enlace del enlace personalizado.|  
  
## <a name="remarks"></a>Comentarios  
 Transportes que utilizan un protocolo orientado a secuencias como TCP y canalizaciones con nombre que admiten las actualizaciones de transporte basadas en secuencias. Concretamente, WCF proporciona actualizaciones de seguridad. La configuración de esta seguridad de transporte está encapsulada por este elemento de configuración, así como por [\<sección sslstreamsecurity >](sslstreamsecurity.md), que se puede configurar y agregar a un enlace personalizado.  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>
- <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>
- [Enlaces](../../../wcf/bindings.md)
- [Extensión de enlaces](../../../wcf/extending/extending-bindings.md)
- [Enlaces personalizados](../../../wcf/extending/custom-bindings.md)
- [\<customBinding >](custombinding.md)
