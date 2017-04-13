---
title: "&lt;&lt;declaredTypes&gt;&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "<declaredTypes> (elemento)"
  - "DataContractSerializer"
  - "dataContractSerializer (elemento)"
  - "declaredTypes (elemento)"
  - "KnownTypes"
ms.assetid: f35184e4-9d9e-4d37-8fb4-d5b58220eb3e
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# &lt;&lt;declaredTypes&gt;&gt;
Contiene los tipos conocidos que <xref:System.Runtime.Serialization.DataContractSerializer> usa al deserializar.  
  
 Para obtener más información sobre contratos de datos y tipos conocidos, consulte [Tipos conocidos de contratos de datos](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).  
  
## Sintaxis  
  
```  
  
<configuration>  
  <system.runtime.serialization>  
    <dataContractSerializer>  
      <declaredTypes>  
        <add type="String ">  
          <knownType type="String">  
                <parameter index="Integer"/>  
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
 Ninguno.  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<agregar\>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)|Agrega tipos que requieren tipos conocidos.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<dataContractSerializer\>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-of-system-runtime-serialization.md)|Contiene los datos de configuración para <xref:System.Runtime.Serialization.DataContractSerializer>.|  
  
## Comentarios  
 Los tipos conocidos de [!INCLUDE[crabout](../../../../../includes/crabout-md.md)], consulte [Tipos conocidos de contratos de datos](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) y <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
## Ejemplo  
 El siguiente código XML muestra tipos declarados y tipos conocidos agregados a un elemento `DataContractSerializer` .  El ejemplo muestra tres tipos que se va a agregar.  El primero es un tipo personalizado denominado "Orders" que usa un tipo conocido denominado "Item".  El segundo el tipo declarado es <xref:System.Collections.Generic.List%601> que usa `Item` como un tipo conocido.  Finalmente, el tercer tipo declarado es <xref:System.Collections.Generic.Dictionary%602>.  El tipo de clase <xref:System.Collections.Generic.Dictionary%602> es un tipo genérico, con dos parámetros de tipo.  El primero representa la clave y el segundo representa el valor.  El ejemplo siguiente agrega <xref:System.Collections.Generic.List%601> del segundo tipo \(el valor\) a la lista de tipos conocidos.  Debe usar el atributo `index` para especificar qué parámetro de tipo se va a usar en el tipo conocido.  En este caso, el atributo de índice indica el tipo de valor establecido en "1" \(la colección está basada en cero\).  
  
```  
<configuration>  
  <system.runtime.serialization>  
    <dataContractSerializer>  
      <declaredTypes>  
        <add type="Examples.Types.Orders, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">  
          <knownType type="Examples.Types.Item, SerializationTypes, Version=2.0.0.0, Culture=neutral, PublicKey=null" />  
        </add>  
        <add type="System.Collections.Generic.List`1, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">  
          <knownType type="Examples.Types.Item, SerializationTypes, Version=2.0.0.0, Culture=neutral, PublicKey=null" />  
        </add>  
        <add type="System.Collections.Generic.Dictionary`2, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">  
          <knownType type="System.Collections.Generic.List`1, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">  
            <parameter index="1"/>  
          </knownType>  
        </add>  
      </declaredTypes>  
    <dataContractSerializer>  
  </system.runtime.serialization>  
</configuration>  
```  
  
## Vea también  
 <xref:System.Runtime.Serialization.DataContractSerializer>   
 [\<dataContractSerializer\>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)   
 [Tipos conocidos de contratos de datos](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)   
 [\<agregar\>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)