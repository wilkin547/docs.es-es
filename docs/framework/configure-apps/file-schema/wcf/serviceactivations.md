---
title: <serviceActivations>
ms.date: 03/30/2017
ms.assetid: 97e665b6-1c51-410b-928a-9bb42c954ddb
ms.openlocfilehash: 7a091ecfbc0f4773ece620f93a9f21c219fcccb6
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55256709"
---
# <a name="serviceactivations"></a>\<serviceActivations>
Un elemento de configuración que le permite agregar valores que definen la configuración de activación de servicio virtual que se asignan a tipos de servicio Windows Communication Foundation (WCF). Esto hace posible activar servicios hospedados en WAS/IIS sin un archivo .svc.  
  
 \<system.ServiceModel>  
\<serviceHostingEnvironment>  
\<serviceActivations>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<serviceHostingEnvironment>
  <serviceActivations>
    <add factory="String"
         service="String" />
  </serviceActivations>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
 Ninguno.  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-serviceactivations.md)|Agrega un elemento de configuración que especifica la activación de una aplicación de servicio.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<serviceHostingEnvironment>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|Define el tipo del que el entorno host del servicio crea instancias para un transporte determinado.|  
  
## <a name="remarks"></a>Comentarios  
 En el siguiente ejemplo se muestra cómo configurar los valores de activación dentro del archivo web.config.  
  
```xml  
<configuration>
  <system.serviceModel>
    <serviceHostingEnvironment>
      <serviceActivations>
        <add service="GreetingService" />
      </serviceActivations>
    </serviceHostingEnvironment>
  </system.serviceModel>
</configuration>
```  
  
 Con esta configuración, puede activar GreetingService sin usar un archivo .svc.  
  
 Observe que `<serviceHostingEnvironment>` es una configuración de nivel de aplicación. Tiene que colocar el archivo `web.config` que contiene la configuración en la raíz de la aplicación virtual. Además, `serviceHostingEnvironment` es una sección heredable de machinetoApplication. Si registra un solo servicio en la raíz del equipo, cada servicio de la aplicación heredará este servicio.  
  
 La activación basada en la configuración admite la activación a través de protocolos http y distintos de http. Requiere extensiones en relatativeAddress, es decir .svc, .xoml o .xamlx. Puede asignar sus propias extensiones al buildProviders conocido, que le permitirá activar el servicio a través de cualquier extensión. Si existe conflicto, la sección `<serviceActivations>` invalida los registros de .svc.  
  
## <a name="see-also"></a>Vea también
- <xref:System.ServiceModel.Configuration.ServiceActivationElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
