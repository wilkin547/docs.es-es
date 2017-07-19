---
title: "&lt;dataContractSerializer&gt; de &lt;system.runtime.serialization&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d9b3d625-be3f-4768-8e0d-1b7e6929f6a8
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# &lt;dataContractSerializer&gt; de &lt;system.runtime.serialization&gt;
Contiene los datos de configuración para <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
## Sintaxis  
  
```  
  
<configuration>  
  <system.runtime.serialization>  
    <dataContractSerializer ignoreExtensionDataObject="Boolean"  
            maxItemsInObjectGraph="Integer">  
      <declaredTypes>  
        <add type="String">  
          <knownType type="String">  
             <parameter index="Integer"  
                        type="String" />  
          </knownType>  
        </add>  
      </declaredTypes>  
    <dataContractSerializer>  
  </system.runtime.serialization>  
</configuration>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|ignoreExtensionDataObject|Un valor booleano que especifica si se omiten los datos proporcionados por el extremo cuando se serializa o deserializa.  Este atributo se puede configurar sólo en `<dataContractSerializer>` bajo el elemento `<behavior>`.|  
|maxItemsInObjectGraph|Un entero que especifica el número máximo de elementos para serializar o deserializar.  Este atributo es 65536.|  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<\<declaredTypes\>\>](../../../../../docs/framework/configure-apps/file-schema/wcf/declaredtypes.md)|Contiene los tipos conocidos que <xref:System.Runtime.Serialization.DataContractSerializer> usa al deserializar.<br /><br /> Para obtener más información sobre contratos de datos y tipos conocidos, consulte [Tipos conocidos de contratos de datos](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<system.runtime.serialization\>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)|Representa el elemento raíz para la sección de espacio de nombres <xref:System.Runtime.Serialization> y contiene elementos para establecer opciones de <xref:System.Runtime.Serialization.DataContractSerializer>.|  
  
## Comentarios  
 Para obtener más información sobre los tipos conocidos, consulte <xref:System.Runtime.Serialization.DataContractSerializer> y [Tipos conocidos de contratos de datos](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).  
  
## Vea también  
 <xref:System.Runtime.Serialization.DataContractSerializer>   
 <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>   
 [Tipos conocidos de contratos de datos](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)