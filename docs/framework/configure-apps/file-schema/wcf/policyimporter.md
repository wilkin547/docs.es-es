---
title: <policyImporter>
ms.date: 03/30/2017
ms.assetid: b0d03456-546f-44bb-ab12-1b2ce7f98fca
ms.openlocfilehash: 81f38d2a163163ca7255ca546bbddbbb58fa3a1b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61783193"
---
# <a name="policyimporter"></a>\<policyImporter>
Especifica un importador de directivas que controla la importación de aserciones de directivas personalizadas de los enlaces.  
  
 \<system.ServiceModel>  
\<client>  
\<metadata>  
\<policyImporters>  
\<policyImporter>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<metadata>
  <policyImporters>
    <policyImporter type="String" />
  </policyImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`type`|El tipo de este elemento.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguna  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<policyImporters>](../../../../../docs/framework/configure-apps/file-schema/wcf/policyimporters.md)|Especifica todos los importadores de directivas que controlan la importación de aserciones de directivas personalizadas de los enlaces.|  
  
## <a name="remarks"></a>Comentarios  
 Un importador de directiva se usa para buscar en las aserciones de directivas personalizadas sobre características de enlace, así como para adjuntar un elemento de enlace personalizado que implementa las características que la aserción requiere.  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>
- <xref:System.ServiceModel.Configuration.PolicyImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Description.MetadataImporter>
- [Configuración del cliente de WCF](../../../../../docs/framework/wcf/feature-details/client-configuration.md)
- [Clientes](../../../../../docs/framework/wcf/feature-details/clients.md)
