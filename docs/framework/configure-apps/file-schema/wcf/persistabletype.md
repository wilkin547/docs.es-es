---
title: '&lt;Type con persistencia&gt;'
ms.date: 03/30/2017
ms.assetid: e5425fe6-523a-4076-aab4-2c2515b1d830
ms.openlocfilehash: 23724957398ed1ade2c81a3932e9773d7cf4c642
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32747078"
---
# <a name="ltpersistabletypegt"></a>&lt;Type con persistencia&gt;
Especifica todos los tipos con persistencia.  
  
 \<system.ServiceModel>  
\<comContracts >  
\<comContract >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<comContracts>  
  <comContract>  
      <persistableTypes>  
         <persistableType id="string"  
            name="string">  
         </persistableType>  
      </persistableTypes>  
  </comContract>  
</comContracts>  
```  
  
## <a name="type"></a>Tipo  
 `Type`  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|id|Un atributo necesario que contiene una cadena que especifica un identificador único para un tipo con persistencia.|  
|name|Un atributo opcional que contiene una cadena que especifica el nombre del tipo con persistencia.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguna  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<persistableTypes >](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md)|Una colección de elementos de `persistableType`.|  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Configuration.ComPersistableTypeElementCollection>  
 <xref:System.ServiceModel.Configuration.ComPersistableTypeElement>  
 [\<comContracts >](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)  
 [Integración en aplicaciones COM+](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)  
 [Configuración de los parámetros de los servicios COM+](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
