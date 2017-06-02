---
title: "Secci&#243;n &lt;extensions&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 53a59fb6-dede-47ec-9384-b3c2e8f0c1fa
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# Secci&#243;n &lt;extensions&gt;
Esta sección de configuración contiene una colección de extensiones, que le permiten al usuario crear los enlaces definidos por el usuario, comportamientos y otros aspectos de las extensiones.  
  
 \<system.ServiceModel\>  
  
## Sintaxis  
  
```  
  
<system.serviceModel>  
    <extensions>  
      <bindingExtensions>  
      </bindingExtensions>  
      <behaviorExtensions>  
      </behaviorExtensions>  
      <bindingElementExtensions>  
      </bindingElementExtensions>  
      <endpointExtensions>  
      </endpointExtensions>  
    </extensions>  
</system.serviceModel>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
 Ninguno.  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<behaviorExtensions\>](../../../../../docs/framework/configure-apps/file-schema/wcf/behaviorextensions.md)|Esta sección contiene elementos secundarios que especifican extensiones de comportamiento, que permiten al usuario personalizar el servicio o los comportamientos del extremo.|  
|[\<bindingElementExtensions\>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindingelementextensions.md)|En esta sección se habilita el uso de un elemento de enlace personalizado de un equipo o archivo de configuración de la aplicación.|  
|[\<bindingExtensions\>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindingextensions.md)|Esta sección contiene elementos secundarios que especifican extensiones de enlace, que le permiten al usuario personalizar los enlaces.|  
|[\<endpointExtensions\>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointextensions.md)|Esta sección contiene elementos secundarios que registran los extremos estándar.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|system.ServiceModel|Elemento raíz de todos los elementos de configuración de WCF.|