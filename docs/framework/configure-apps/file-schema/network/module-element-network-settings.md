---
title: <module> (Elemento, Configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#module
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/module
helpviewer_keywords:
- module element
- <module> element
ms.assetid: 10318725-9666-4d65-ab61-b94c64e59f13
ms.openlocfilehash: 4658af3f55bddb5f5a748db5366c53f1d2733983
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55268204"
---
# <a name="module-element-network-settings"></a>\<módulo > elemento (configuración de red)
Agrega un nuevo módulo proxy a la aplicación.  
  
 \<configuration>  
\<system.net>  
\<defaultProxy>  
\<module>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<module   
  type="type_fullname, assembly_fullname"   
/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|**Attribute**|**Descripción**|  
|-------------------|---------------------|  
|`type`|El nombre de tipo completo (indicado por el <xref:System.Type.FullName%2A> propiedad) y el nombre del ensamblado (indicado por el <xref:System.Reflection.Assembly.FullName%2A> propiedad), separados por punto y coma, que implementa el proxy.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|**Element**|**Descripción**|  
|-----------------|---------------------|  
|[defaultProxy](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|Configura el servidor proxy de Protocolo de transferencia de hipertexto (HTTP).|  
  
## <a name="remarks"></a>Comentarios  
 El `module` elemento registra las clases de proxy que implementan la <xref:System.Net.IWebProxy> interfaz. Después de registrar la clase de proxy, `module` se puede usar para solicitar información a través del proxy compatible.  
  
 El valor de la `type` atributo debe ser el nombre de clase del módulo y el nombre de su biblioteca de vínculos dinámicos (DLL) correspondiente.  
  
## <a name="configuration-files"></a>Archivos de configuración  
 Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente registra una clase de proxy personalizada.  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <module  
        type="Test.CustomWebProxy, TestProxy, Version=2.0.3600.0, Culture=neutral, PublicKeyToken=b23a5c561934e385"  
      />  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también
- <xref:System.Net.IWebProxy?displayProperty=nameWithType>
- [Esquema de la configuración de red](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
