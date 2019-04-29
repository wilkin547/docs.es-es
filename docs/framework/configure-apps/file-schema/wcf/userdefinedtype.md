---
title: <userDefinedType>
ms.date: 03/30/2017
ms.assetid: 0f70ec06-8249-4f0c-9f49-b4df59985fb8
ms.openlocfilehash: 46beb88cedf051ed1683161b6ed9b37273ed01f1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769842"
---
# <a name="userdefinedtype"></a>\<userDefinedType>
Representa un tipo definido por el usuario (UDT) que se va a incluir en el contrato del servicio.  
  
 \<system.ServiceModel>  
\<comContracts>  
\<comContract>  
\<userDefinedTypes>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<comContracts>
  <comContract>
    <userDefinedTypes>
      <userDefinedType name="String"
                       typeLibID="String"
                       typeLibVersion="String"
                       typeDefID="String">
      </userDefinedType>
    </userDefinedTypes>
  </comContract>
</comContracts>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`name`|Un atributo opcional que contiene una cadena que proporciona el nombre de tipo legible. El tiempo de ejecución no lo usa, pero ayuda a que un lector distinga los tipos.|  
|`TypeDefID`|Una cadena GUID que identifica el tipo UDT concreto dentro de la biblioteca de tipos registrados.|  
|`TypeLibID`|Una cadena GUID que identifica la biblioteca de tipos registrados que define el tipo.|  
|`TypeLibVersion`|Una cadena que identifica la versión de biblioteca de tipos que define el tipo.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`userDefinedTypes`|Una colección de elementos de `userDefinedType`.|  
  
## <a name="remarks"></a>Comentarios  
 El tiempo de ejecución de integración de COM+ crea los servicios mediante la inspección de la biblioteca de tipos. Cuando un componente de COM+ contiene métodos que pasan una VARIANTE, el sistema no puede determinar los tipos reales que se van a pasar antes del tiempo de ejecución. Por consiguiente, al intentar pasar un tipo definido por el usuario dentro de una VARIANTE , se produce un error porque no es un tipo conocido para la serialización.  
  
 Para prevenir este problema, puede agregar los UDT al archivo de configuración para que puedan estar incluidos como tipos conocidos en el contrato del servicio adecuado. Para ello, tiene que identificar de manera unívoca el UDT y los contratos, es decir, las interfaces COM originales que lo utilizan.  
  
 El ejemplo siguiente se muestra cómo agregar dos UDT concretos a la <`userDefinedTypes`> sección del archivo de configuración para este propósito.  
  
```xml  
<comContracts>
  <comContract contract="{5163B1E7-F0CF-4B6A-9A02-4AB654F34284}"
               namespace="http://tempuri.org/5163B1E7-F0CF-4B6A-9A02-4AB654F34284"
               name="_Broker"
               requireSession="true">
    <userDefinedTypes>
      <userDefinedType name="CustomerType"
                       typeLibID="{91DC728C-4F1A-45de-A9B6-B538E209CEA6}"
                       typeLibVersion="1.0"
                       typeDefID="{D129765C-F211-434e-825A-9A63198C41F2}">
      </userDefinedType>
      <userDefinedType name="AddressType"
                       typeLibID="{91DC728C-4F1A-45de-A9B6-B538E209CEA6}"
                       typeLibVersion="1.0"
                       typeDefID="{4616AE0D-687A-43B7-BC63-141AE3DFD099}">
      </userDefinedType>
    </userDefinedTypes>
    <exposedMethods>
      <exposedMethod name="BuyStock" />
      <exposedMethod name="SellStock" />
      <exposedMethod name="ExecuteTransaction" />
    </exposedMethods>
  </comContract>
</comContracts>
```  
  
 Cuando se inicializa el servicio, el tiempo de ejecución de integración busca los tipos especificados y los agrega a la colección de tipos conocidos para los contratos especificados.  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Configuration.ComContractElement.UserDefinedTypes%2A>
- <xref:System.ServiceModel.Configuration.ComUdtElementCollection>
- <xref:System.ServiceModel.Configuration.ComUdtElement>
- [\<comContracts>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)
- [Integración en aplicaciones COM+](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
- [Cómo: Configurar el servicio COM +](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
