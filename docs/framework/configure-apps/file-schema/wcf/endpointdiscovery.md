---
title: "&lt;endpointDiscovery&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 70812717-888a-4748-9640-0df6715ff029
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# &lt;endpointDiscovery&gt;
Especifica las distintas configuraciones de detección para un extremo, como su detectabilidad, ámbitos y cualquier extensión personalizada a sus metadatos.  
  
## Sintaxis  
  
```  
  
<behaviors>  
  <endpointBehaviors>  
    <behavior name="String">  
      <endpointDiscovery enabled="Boolean">  
        <scopes>  
          <add scope="URI"/>  
        </scopes>  
        <extensions>  
        </extensions>  
      </endpointDiscovery>  
    </behavior>  
  </endpointBehaviors>  
</behaviors>  
  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|enabled|Valor booleano que especifica si la detectabilidad está habilitada en este extremo.  De manera predeterminada, es `false`.|  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<scopes\>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)|Colección de URI de ámbito para el extremo.  Se puede asociar más de un URI de ámbito a un único extremo.|  
|[\<extensiones\>](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) \[de \<endpointDiscovery\>\]|Colección de elementos XML que le permite especificar metadatos personalizados que se van a publicar para un extremo.|  
|\<types\>|Una colección de interfaces para buscar.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<comportamiento\>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Especifica un elemento de comportamiento.|  
|||  
  
## Comentarios  
 Cuando se agrega a la configuración de comportamiento del extremo y con el atributo `enabled` establecido en `true`, este elemento de configuración habilita su detectabilidad.  Además, puede utilizar el elemento secundario [\<scopes\>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md) para especificar varios URI de ámbito personalizado que se pueden utilizar para filtrar extremos de servicio durante una consulta, así como el elemento secundario [\<extensiones\>](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) para especificar metadatos personalizados que se deberían publicar junto con metadatos detectables estándar \(EPR, ContractTypeName, BindingName, Scope y ListenURI\).  
  
 Este elemento de configuración depende del elemento [\<serviceDiscovery\>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) que proporciona el control de nivel del servicio de detectabilidad.  Esto significa que se omite la configuración de este elemento si [\<serviceDiscovery\>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) no se encuentra en la configuración.  
  
## Ejemplo  
 El siguiente ejemplo de configuración especifica los ámbitos del filtrado y metadatos de la extensión que se van a publicar para un extremo.  
  
```  
  
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
          <add scope="http://contoso/test1"/>  
          <add scope="http://contoso/test2"/>  
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
  
## Vea también  
 <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>