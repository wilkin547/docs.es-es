---
title: <endpointDiscovery>
ms.date: 03/30/2017
ms.assetid: 70812717-888a-4748-9640-0df6715ff029
ms.openlocfilehash: 5cb64c54067ba695f67d86c0026db77ebbe7d5ee
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919048"
---
# <a name="endpointdiscovery"></a>\<endpointDiscovery>
Especifica las distintas configuraciones de detección para un punto de conexión, como su detectabilidad, ámbitos y cualquier extensión personalizada a sus metadatos.  
  
\<system.ServiceModel>  
\<comportamientos >  
\<endpointBehaviors>  
\<comportamiento >  
\<endpointDiscovery>  
  
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
  
|Atributo|DESCRIPCIÓN|  
|---------------|-----------------|  
|enabled|Valor booleano que especifica si la detectabilidad está habilitada en este extremo. El valor predeterminado es `false`.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<scopes>](scopes.md)|Colección de URI de ámbito para el extremo. Se puede asociar más de un URI de ámbito a un único punto de conexión.|  
|Extensiones > [de \<endpointDiscovery >] [ \<](extensions.md)|Colección de elementos XML que le permite especificar metadatos personalizados que se van a publicar para un extremo.|  
|\<tipos >|Una colección de interfaces para buscar.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<comportamiento >](behavior-of-endpointbehaviors.md)|Especifica un elemento de comportamiento.|  
|||  
  
## <a name="remarks"></a>Comentarios  
 Cuando se agrega a la configuración de comportamiento del punto de conexión y con el atributo `enabled` establecido en `true`, este elemento de configuración habilita su detectabilidad. Además, puede utilizar los [ \<ámbitos >](scopes.md)elemento secundario para especificar los URI de ámbito personalizado que se pueden usar para filtrar los extremos de servicio durante la consulta, así como las [ \<extensiones >](extensions.md) elemento secundario para especificar el personalizado. metadatos que se deben publicar junto con los metadatos detectables estándar (EPR, ContractTypeName, BindingName, Scope y ListenURI).  
  
 Este elemento de configuración depende [ \<del elemento > serviceDiscovery](servicediscovery.md) que proporciona el control de nivel de servicio de detectabilidad. Esto significa que la configuración de este elemento se omite si [ \<serviceDiscovery >](servicediscovery.md) no está presente en la configuración.  
  
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
