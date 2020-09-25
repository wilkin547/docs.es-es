---
title: Elemento <system.Net> (configuración de red)
description: El elemento de configuración de red <system.Net> contiene opciones que especifican cómo se conecta el .NET Framework a las opciones de red del .NET Framework.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.Net
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.Net
helpviewer_keywords:
- system.Net element
- <system.Net> element
ms.assetid: 52de4d6c-b24d-44aa-ba7d-6b5061f1357e
ms.openlocfilehash: 80d54df40c6798e146013b4f2d867386ae35169c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201725"
---
# <a name="systemnet-element-network-settings"></a>Elemento \<system.Net> (configuración de red)

Contiene valores que especifican cómo se conecta .NET Framework a la red.  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<system.net>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<system.net>
</system.net>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  

 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  

 Ninguno.  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|**Element**|**Descripción**|  
|-----------------|---------------------|  
|[authenticationModules](authenticationmodules-element-network-settings.md)|Especifica los módulos que se usan para autenticar las solicitudes de Internet.|  
|[connectionManagement](connectionmanagement-element-network-settings.md)|Especifica el número máximo de conexiones a un host de Internet.|  
|[defaultProxy](defaultproxy-element-network-settings.md)|Configura el servidor proxy de Protocolo de transferencia de hipertexto (HTTP).|  
|[mailSettings](mailsettings-element-network-settings.md)|Configura las opciones de envío de correo del Protocolo simple de transferencia de correo (SMTP).|  
|[requestCaching](requestcaching-element-network-settings.md)|Controla el mecanismo de almacenamiento en caché para las solicitudes de red.|  
|[settings](settings-element-network-settings.md)|Configura las opciones de red básicas para las clases de <xref:System.Net> y los espacios de nombres secundarios relacionados.|  
|[webRequestModules](webrequestmodules-element-network-settings.md)|Especifica los módulos que se van a usar para solicitar información de los hosts de Internet.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|**Element**|**Descripción**|  
|-----------------|---------------------|  
|[configuration](../configuration-element.md)|Contiene la configuración de todos los espacios de nombres.|  
  
## <a name="remarks"></a>Observaciones  

 El [\<system.net>](system-net-element-network-settings.md) elemento contiene la configuración para las clases en <xref:System.Net> y los espacios de nombres secundarios relacionados. La configuración configura los módulos de autenticación, la administración de conexiones, la configuración de correo, el servidor proxy y los módulos de solicitud de Internet para recibir información de los hosts de Internet.  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se muestra una configuración típica utilizada por <xref:System.Net> las clases.  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <add type="System.Net.DigestClient" />  
      <add type="System.Net.NegotiateClient" />  
      <add type="System.Net.KerberosClient" />  
      <add type="System.Net.NtlmClient" />  
      <add type="System.Net.BasicClient" />  
    </authenticationModules>  
    <connectionManagement>  
      <add address="*" maxconnection="2" />  
    </connectionManagement>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="true"  
        bypassonlocal="true"  
      />  
    </defaultProxy>  
    <webRequestModules>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator"  
      />  
      <add prefix="https"  
           type="System.Net.HttpRequestCreator"  
      />  
      <add prefix="file"  
           type="System.Net.FileWebRequestCreator"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Consulte también

- [Esquema de la configuración de red](index.md)
