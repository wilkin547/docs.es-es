---
title: "&lt;add&gt; de &lt;declaredTypes&gt; (elemento) | Microsoft Docs"
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
  - "contratos de datos"
  - "DataContractAttribute"
  - "DataContractSerializer"
  - "dataContractSerializer (elemento)"
ms.assetid: c3d37ae4-8f1c-463f-b195-658c5a7e90a1
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# &lt;add&gt; de &lt;declaredTypes&gt; (elemento)
Agrega un tipo usado por <xref:System.Runtime.Serialization.DataContractSerializer> durante la deserialización.  Cada tipo declarado incluye los tipos conocidos que se devolverán como un campo o propiedad del tipo declarado.  
  
## Sintaxis  
  
```  
  
<add type="String">  
   <knownType type="String">  
       <parameter index="Integer"  
                  type="String" />  
   </knownType>  
</add>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|tipo|Atributo de cadena necesario.<br /><br /> Especifica el nombre del tipo \(incluido el espacio de nombres\), nombre de ensamblado, número de versión, referencia cultural y símbolo \(token\) de clave pública.|  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<knownType\>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowntype.md)|Especifica el tipo conocido del tipo declarado que se va a agregar.  Si el tipo declarado es un tipo genérico, también debe agregar un elemento de parámetro al elemento `<knownType>` para especificar qué parámetro genérico se usa para devolver el tipo conocido.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<\<declaredTypes\>\>](../../../../../docs/framework/configure-apps/file-schema/wcf/declaredtypes.md)|Contiene los tipos que requieren tipos conocidos durante la deserialización por <xref:System.Runtime.Serialization.DataContractSerializer>.|  
  
## Comentarios  
 Para obtener más información sobre los tipos conocidos, consulte [Tipos conocidos de contratos de datos](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) y <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
 Para obtener un ejemplo del uso de este elemento, consulte [\<dataContractSerializer\>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md).  
  
> [!NOTE]
>  Si agrega el tipo <xref:System.Object> como `<declaredType>` , a continuación, se inicia <xref:System.Configuration.ConfigurationErrorsException>.  Esto se debe a que el tipo <xref:System.Object> no se puede usar como un tipo declarado en configuración.  
  
## Ejemplo  
  
```  
<add type="MyCompany.Library.Shape,   
           MyAssembly, Version=2.0.0.0, Culture=neutral,  
           PublicKeyToken=XXXXXX, processorArchitecture=MSIL">  
           <knownType type="MyCompany.Library.Circle,   
                      MyAssembly, Version=2.0.0.0, Culture=neutral,  
                      PublicKeyToken=XXXXXX,  
                      processorArchitecture=MSIL"/>  
</add>  
```  
  
## Vea también  
 <xref:System.Runtime.Serialization.DataContractSerializer>   
 [Tipos conocidos de contratos de datos](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)   
 [\<dataContractSerializer\>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)   
 [\<add\> of \<declaredTypes\>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)