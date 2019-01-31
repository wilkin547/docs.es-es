---
title: <transportConfigurationTypes>
ms.date: 03/30/2017
ms.assetid: 929c8b0a-5460-4f66-a098-2cb8d4e10b69
ms.openlocfilehash: 560da96c50e99461d25c1fd65def2dc10c284470
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55261677"
---
# <a name="transportconfigurationtypes"></a>\<transportConfigurationTypes>
Representa una colección de elementos de configuración que identifica el tipo de un transporte determinado. Esto se puede usar para agregar protocolos WAS personalizados.  
  
 \<system.ServiceModel>  
\<ServiceHostingEnvironment>  
\<transportConfigurationTypes>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|name|Nombre del transporte.|  
|transportConfigurationType|El tipo que implementa el transporte.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-transportconfigurationtype.md)|Agrega un elemento de configuración que identifica el tipo de un transporte determinado.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<serviceHostingEnvironment>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|Define el tipo del que el entorno host del servicio crea instancias para un transporte determinado.|  
  
## <a name="see-also"></a>Vea también
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElementCollection>
- [Hospedar aplicaciones de WPF](../../../../../docs/framework/wcf/feature-details/hosting.md)
