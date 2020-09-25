---
title: <service>
ms.date: 03/30/2017
ms.assetid: 13123dd6-c4a9-4a04-a984-df184b851788
ms.openlocfilehash: dcc32f5aa055942408a3f01d37b5aa27ac0f51ee
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173775"
---
# \<service>

El elemento `service` contiene los valores para un servicio de Windows Communication Foundation (WCF). También contiene puntos de conexión que exponen el servicio.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<service>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<service behaviorConfiguration="String"
         name="String">
</service>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  

 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|behaviorConfiguration|Una cadena que contiene el nombre de comportamiento que se va a usar para instanciar el servicio. El nombre de comportamiento debe estar en el ámbito en el punto definido del servicio. El valor predeterminado es una cadena vacía.|  
|name|Atributo String necesario que especifica el tipo del servicio del que se van a crear instancias. Este valor debe equivaler a un tipo válido. El formato debería ser `Namespace.Class.`.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<endpoint>](endpoint-element.md)|Una colección de elementos `endpoint` que exponen este servicio.|  
|[\<host>](host.md)|Especifica el host de esta instancia del servicio. Este elemento es del tipo <xref:System.ServiceModel.Configuration.HostElement>.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<services>](services.md)|Elemento raíz de todos los elementos de configuración de WCF.|  
  
## <a name="remarks"></a>Observaciones  

 Los servicios se definen en la sección de `services` del archivo de configuración. Un ensamblado puede contener cualquier número de servicios. Cada servicio tiene su propia sección de configuración de `service`. Esta sección y su contenido definen el contrato de servicios, comportamiento y puntos de conexión del servicio determinado.  
  
 El elemento `behaviorConfiguration` también es opcional. Identifica el comportamiento que el servicio utiliza. El comportamiento especificado en este atributo debe vincular a un comportamiento en ámbito en el mismo archivo de configuración.  
  
 Cada servicio expone uno o más extremos, que tienen su propia dirección y enlace. Todos los enlaces usados dentro del archivo de configuración se deben definir en el ámbito del archivo. Los enlaces se vinculan a los puntos de conexión a través de la combinación de los atributos `name` y `bindingConfiguration`. El atributo `name` describe la sección en la que está definido el enlace. El atributo `bindingConfiguration` define qué configuración se usa dentro de la sección de enlaces. Una sección de enlace puede definir varias configuraciones.  
  
## <a name="example"></a>Ejemplo  

 Éste es un ejemplo de una configuración de servicio.  
  
```xml  
<service behaviorConfiguration="testChannelBehavior"
         name="HelloWorld">
  <endpoint address="/HelloWorld2/"
            name="test"
            bindingNamespace="http://www.cohowinery.com/"
            binding="basicHttpBinding"
            contract="IHelloWorld" />
</service>
```  
  
## <a name="see-also"></a>Consulte también

- <xref:System.ServiceModel.Configuration.ServiceElement>
- [Configuración de servicios](../../../wcf/configuring-services.md)
