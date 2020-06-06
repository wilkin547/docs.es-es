---
title: <comContract>
ms.date: 03/30/2017
ms.assetid: 3f8e1c0c-cfdf-4c79-ac65-c64e9323a51c
ms.openlocfilehash: b499294af71ba230dcf985d4af1d013b1ca260cf
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850027"
---
# \<comContract>
Especifica un contrato de servicio de integración de COM+.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContracts>**](comcontracts.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<comContract>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<comContracts>
  <comContract contract="String"
               namespace="String"
               name="String"
               requireSession="Boolean">
    <exposedMethods>
      <exposedMethod name="String" />
    </exposedMethods>
    <userDefinedTypes>
      <userDefinedType name="String"
                       typeLibID="String"
                       typeLibVersion="String"
                       typeDefID="String">
      </userDefinedType>
    </userDefinedTypes>
    <persistableTypes>
      <persistableType id="String"
                       name="String">
      </persistableType>
    </persistableTypes>
  </comContract>
</comContracts>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|contrato|Una cadena que contiene el tipo de contrato.|  
|name|Una cadena que contiene el nombre del contrato.|  
|espacio de nombres|Una cadena que contiene el espacio de nombres del contrato.|  
|requiresSession|Un valor booleano que especifica si el contrato sólo se puede utilizar en enlaces con canal. Cuando se inicializa el servicio, el tiempo de ejecución de integración garantiza que este valor es coherente con el tipo de enlace que se va a usar. Se genera una excepción si uno o más de los enlaces para el contrato están en conflicto. Si esta propiedad es `false`, y un canal unidireccional está en uso y hay parámetros [fuera], también se genera una excepción.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|persistableTypes|Todos los tipos con persistencia.|  
|userDefinedTypes|Una colección de tipos definidos por el usuario (UDT) que se va a incluir en el contrato del servicio.|  
|exposedMethods|Una colección de métodos COM+ que se exponen cuando la interfaz en un componente de COM+ se expone como un servicio Web.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|comContracts|Contiene una colección de elementos `comContract`.|  
  
## <a name="remarks"></a>Comentarios  
 Los contratos de servicio de integración de COM+ están restringidos actualmente al `http://tempuri.org` espacio de nombres y el nombre del contrato se deriva de la interfaz com compatible. Puede, sin embargo, especificar las alternativas utilizando la sección `comContracts`, así como el elemento `comContract` en el archivo de configuración. Por ejemplo, puede utilizar la configuración siguiente para especificar el espacio de nombres, el nombre del contrato y los tipos definidos por el usuario que se van incluir, así como otros valores para un contrato de servicios.  
  
```xml  
<comContracts>
  <comContract contract="{5163B1E7-F0CF-4B6A-9A02-4AB654F34284}"
               namespace="http://tempuri.org/5163B1E7-F0CF-4B6A-9A02-4AB654F34284"
               name="_Broker"
               requireSession="true">
    <exposedMethods>
      <exposedMethod name="BuyStock" />
      <exposedMethod name="SellStock" />
      <exposedMethod name="ExecuteTransaction" />
    </exposedMethods>
  </comContract>
</comContracts>
```  
  
 Cuando se inicializa el servicio, los espacios de nombres y nombres del contrato especificados se aplican a las descripciones de servicio generadas.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.ServiceModel.Configuration.ComContractElementCollection>
- <xref:System.ServiceModel.Configuration.ComContractElement>
- [\<comContracts>](comcontracts.md)
- [Integración con aplicaciones COM+](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [Procedimiento para configurar los parámetros de los servicios COM+](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
