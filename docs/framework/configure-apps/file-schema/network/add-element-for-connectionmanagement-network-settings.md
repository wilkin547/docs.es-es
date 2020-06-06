---
title: Elemento <add> para connectionManagement (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement/add
helpviewer_keywords:
- <add> element, connectionManagement
- <connectionManagement>, add element
- add element, connectionManagement
- connectionManagement, add element
ms.assetid: 856bf57d-1c63-46c7-a178-03d97b0a4149
ms.openlocfilehash: 093b68d31e03094bedefa96a2f2d53eb3d84edf0
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155016"
---
# <a name="add-element-for-connectionmanagement-network-settings"></a>Elemento \<add> para connectionManagement (configuración de red)
Agrega una dirección IP o nombre DNS a la lista de administración de conexión.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<connectionManagement>**](connectionmanagement-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a>Sintaxis  
  
```xml  
<add
  address="address expression"
  maxconnection="integer"
/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|**Attribute**|**Descripción**|  
|-------------------|---------------------|  
|`address`|Cadena que describe una dirección IP o nombre DNS.|  
|`maxconnection`|Número máximo de conexiones permitido en un servidor. Si no se proporciona, el valor predeterminado es 2.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|**Element**|**Descripción**|  
|-----------------|---------------------|  
|[connectionManagement](connectionmanagement-element-network-settings.md)|Especifica el número máximo de conexiones a un host de red.|  
  
## <a name="remarks"></a>Comentarios  
 El valor de la `address` atributo debe ser un asterisco para indicar todas las conexiones, o bien una cadena del formulario `<schema>://<idn_hostname>[:<port>]`.  
  
 Si el URI pasado a cualquier API de HTTP contiene Unicode, el nombre se convertirá internamente mediante <xref:System.Uri.DnsSafeHost%2A>, que puede devolver una cadena de punicode (comportamiento dependiente de la configuración actual de IDN).  
  
## <a name="configuration-files"></a>Archivos de configuración  
 Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se configura una aplicación para que use cuatro conexiones al servidor `www.contoso.com` y dos conexiones a todos los demás servidores.  
  
```xml  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <add address="http://www.contoso.com" maxconnection="4" />  
      <add address="*" maxconnection="2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [Esquema de la configuración de red](index.md)
