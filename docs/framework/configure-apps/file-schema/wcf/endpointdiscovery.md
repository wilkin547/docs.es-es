---
description: 'Más información acerca de: <endpointDiscovery>'
title: <endpointDiscovery>
ms.date: 03/30/2017
ms.assetid: 70812717-888a-4748-9640-0df6715ff029
ms.openlocfilehash: 01913de37ae426484d5bb1ff6a815a64302024fb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99782135"
---
# \<endpointDiscovery>

Especifica las distintas configuraciones de detección para un punto de conexión, como su detectabilidad, ámbitos y cualquier extensión personalizada a sus metadatos.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endpointDiscovery>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="String">
      <endpointDiscovery enabled="Boolean">
        <scopes>
          <add scope="URI"/>
        </scopes>
        <extensions />
      </endpointDiscovery>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  

 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|enabled|Valor booleano que especifica si la detectabilidad está habilitada en este extremo. De manera predeterminada, es `false`.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<scopes>](scopes.md)|Colección de URI de ámbito para el extremo. Se puede asociar más de un URI de ámbito a un único punto de conexión.|  
|[\<extensions>](extensions.md) [de \<endpointDiscovery> ]|Colección de elementos XML que le permite especificar metadatos personalizados que se van a publicar para un extremo.|  
|\<types>|Una colección de interfaces para buscar.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|Especifica un elemento de comportamiento.|  
|||  
  
## <a name="remarks"></a>Observaciones  

 Cuando se agrega a la configuración de comportamiento del punto de conexión y con el atributo `enabled` establecido en `true`, este elemento de configuración habilita su detectabilidad. Además, puede usar el [\<scopes>](scopes.md) elemento secundario para especificar los URI de ámbito personalizado que se pueden usar para filtrar los extremos de servicio durante la consulta, así como el [\<extensions>](extensions.md) elemento secundario para especificar los metadatos personalizados que se deben publicar junto con los metadatos detectables estándar (EPR, ContractTypeName, BindingName, Scope y ListenURI).  
  
 Este elemento de configuración depende del [\<serviceDiscovery>](servicediscovery.md) elemento que proporciona el control de nivel de servicio de detectabilidad. Esto significa que la configuración de este elemento se omite si [\<serviceDiscovery>](servicediscovery.md) no está presente en la configuración.  
  
## <a name="example"></a>Ejemplo  

 El siguiente ejemplo de configuración especifica los ámbitos del filtrado y metadatos de la extensión que se van a publicar para un punto de conexión.  
  
```xml  
<services>
  <service name="CalculatorService"
           behaviorConfiguration="CalculatorServiceBehavior">
    <endpoint binding="basicHttpBinding"
              address="calculator"
              contract="ICalculatorService"
              behaviorConfiguration="calculatorEndpointBehavior" />
  </service>
</services>
<behaviors>
  <serviceBehaviors>
    <behavior name="CalculatorServiceBehavior">
      <serviceDiscovery />
    </behavior>
  </serviceBehaviors>
  <endpointBehaviors>
    <behavior name="calculatorEndpointBehavior">
      <endpointDiscovery enabled="true">
        <scopes>
          <add scope="http://contoso/test1" />
          <add scope="http://contoso/test2" />
        </scopes>
        <extensions>
          <e:Publisher xmlns:e="http://example.org">
            <e:Name>The Example Organization</e:Name>
            <e:Address>One Example Way, ExampleTown, EX 12345</e:Address>
            <e:Contact>support@example.org</e:Contact>
          </e:Publisher>
          <AnotherCustomMetadata>Custom Metadata</AnotherCustomMetadata>
        </extensions>
      </endpointDiscovery>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
