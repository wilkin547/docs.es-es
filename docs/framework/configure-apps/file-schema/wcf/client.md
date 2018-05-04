---
title: '&lt;Cliente&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel/client
- http://schemas.microsoft.com/.NetConfiguration/v2.0#client
ms.assetid: bf0f7031-76c8-4e7e-a6c6-9ad9119134be
ms.openlocfilehash: b8a006d3dee4149569b3f5b573d9d765504b0d65
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltclientgt"></a>&lt;Cliente&gt;
El elemento `client` define una lista de extremos a los que un cliente puede conectarse.  
  
 \<system.ServiceModel>  
\<cliente >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<system.serviceModel>  
    <client>  
        <endpoint>  
        </endpoint>  
                <metadata>  
        </metadata>  
    </client>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
 Ninguna  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<punto de conexión >](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md)|Contiene una colección de elementos de punto de conexión, que especifica los puntos de conexión a los que este cliente puede conectarse.|  
|[\<metadatos >](../../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md)|Contiene los valores para procesar los metadatos.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<system.serviceModel>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|El elemento raíz de todos los elementos de configuración de la Windows Communication Foundation (WCF).|  
  
## <a name="remarks"></a>Comentarios  
 La sección `client` define una lista de extremos a los que un cliente puede conectarse. Cada extremo enumerado en la sección de cliente define su propio enlace, comportamiento y contrato. La combinación de los atributos `name` y `contract` identifica singularmente. El código de cliente especifica el `name` para conectar el servicio que el cliente implementa a un extremo. Si se omite el atributo de `name`, el extremo actúa como el extremo predeterminado para el contrato que implementa.  
  
 Además, esta sección también especifica los valores para procesar los metadatos.  
  
## <a name="example"></a>Ejemplo  
  
```xml  
<client>  
    <endpoint address="/HelloWorld/"  
              bindingConfiguration="usingDefaults"  
              name="MyBinding"  
              binding="customBinding"  
              contract="HelloWorld">  
    <addressProperties actingAs="http://www.microsoft.com/TestActor"  
             identityData="BasicReadWrite" identityType="Spn" isAddressPrivate="false">  
    </endpoint>  
</client>  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Configuration.ClientSection>  
 <xref:System.ServiceModel.Configuration.MetadataElement>  
 [Configuración del cliente de WCF](../../../../../docs/framework/wcf/feature-details/client-configuration.md)  
 [Clientes](../../../../../docs/framework/wcf/feature-details/clients.md)
