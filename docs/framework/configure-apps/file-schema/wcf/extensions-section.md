---
title: <extensions>transversal
ms.date: 03/30/2017
ms.assetid: 53a59fb6-dede-47ec-9384-b3c2e8f0c1fa
ms.openlocfilehash: 35621acaf96a80ffa3ffe4a3c6605143c48995a5
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855358"
---
# <a name="extensions-section"></a>\<extensions>transversal
Esta sección de configuración contiene una colección de extensiones, que le permiten al usuario crear los enlaces definidos por el usuario, comportamientos y otros aspectos de las extensiones.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<extensions>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
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
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
 Ninguno.  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<behaviorExtensions>](behaviorextensions.md)|Esta sección contiene elementos secundarios que especifican extensiones de comportamiento, que permiten al usuario personalizar el servicio o los comportamientos del punto de conexión.|  
|[\<bindingElementExtensions>](bindingelementextensions.md)|En esta sección se habilita el uso de un elemento de enlace personalizado de un equipo o archivo de configuración de la aplicación.|  
|[\<bindingExtensions>](bindingextensions.md)|Esta sección contiene elementos secundarios que especifican extensiones de enlace, que le permiten al usuario personalizar los enlaces.|  
|[\<endpointExtensions>](endpointextensions.md)|Esta sección contiene elementos secundarios que registran los puntos de conexión estándar.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|system.ServiceModel|Elemento raíz de todos los elementos de configuración de WCF.|
