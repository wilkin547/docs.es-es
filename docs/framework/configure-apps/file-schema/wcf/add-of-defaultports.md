---
title: '&lt;add&gt; de &lt;defaultPorts&gt;'
ms.date: 03/30/2017
ms.assetid: f162ce42-963b-4779-96a7-d6d8b4ea0d2f
ms.openlocfilehash: 8b7a4730af6690616058a91cf23bb39734d81abc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54541721"
---
# <a name="ltaddgt-of-ltdefaultportsgt"></a>&lt;add&gt; de &lt;defaultPorts&gt;
punto de conexión de las comunicaciones predeterminado que escucha la aplicación cliente.  
  
 \<system.ServiceModel>  
\<comportamientos >  
\<serviceBehaviors>  
\<comportamiento >  
\<useRequestHeadersForMetadataAddress>  
\<defaultPorts>  
\<add>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add port="Integer"
         scheme="String" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|puerto|Entero que especifica el número del puerto de comunicaciones predeterminado.|  
|scheme|Cadena que especifica el grupo de configuración del protocolo asociado a un puerto de comunicaciones.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<defaultPorts>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultports.md)|Colección de puertos predeterminados que enumeran los puntos de conexión de comunicaciones predeterminados que escucha la aplicación cliente.|  
  
## <a name="see-also"></a>Vea también
- <xref:System.ServiceModel.Configuration.DefaultPortElement>
