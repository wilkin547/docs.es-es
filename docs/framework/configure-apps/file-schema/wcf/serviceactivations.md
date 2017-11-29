---
title: '&lt;serviceActivations&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 97e665b6-1c51-410b-928a-9bb42c954ddb
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2a4f05b8164c0920893ea5b379017b1eb91f1b37
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltserviceactivationsgt"></a>&lt;serviceActivations&gt;
Un elemento de configuración que le permite agregar valores que definen la configuración de activación de servicio virtual que se asigna a sus tipos de servicio [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]. Esto hace posible activar servicios hospedados en WAS/IIS sin un archivo .svc.  
  
 \<sistema. ServiceModel >  
\<serviceHostingEnvironment >  
\<serviceActivations >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<serviceHostingEnvironment>   
   <serviceActivations>  
      <add factory="String"  
           service="String"/>  
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
|[\<serviceHostingEnvironment >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|Define el tipo del que el entorno host del servicio crea instancias para un transporte determinado.|  
  
## <a name="remarks"></a>Comentarios  
 En el siguiente ejemplo se muestra cómo configurar los valores de activación dentro del archivo web.config.  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <serviceHostingEnvironment>  
      <serviceActivations>  
        <add service="GreetingService"/>  
      </serviceActivations>  
    </serviceHostingEnvironment>  
  </system.serviceModel>  
</configuration>  
```  
  
 Con esta configuración, puede activar GreetingService sin usar un archivo .svc.  
  
 Observe que `<serviceHostingEnvironment>` es una configuración de nivel de aplicación. Tiene que colocar el archivo `web.config` que contiene la configuración en la raíz de la aplicación virtual. Además, `serviceHostingEnvironment` es una sección heredable de machinetoApplication. Si registra un solo servicio en la raíz del equipo, cada servicio de la aplicación heredará este servicio.  
  
 La activación basada en la configuración admite la activación a través de protocolos http y distintos de http. Requiere extensiones en relatativeAddress, es decir .svc, .xoml o .xamlx. Puede asignar sus propias extensiones al buildProviders conocido, que le permitirá activar el servicio a través de cualquier extensión. Si existe conflicto, la sección `<serviceActivations>` invalida los registros de .svc.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Configuration.ServiceActivationElementCollection>  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>
