---
title: "&lt;par&#225;metro&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0fb41e2d-64f7-44ab-993e-05892eac6d82
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# &lt;par&#225;metro&gt;
Especifica el parámetro genérico cuando el tipo declarado es un tipo genérico.  
  
## Sintaxis  
  
```  
  
<parameter index="integer"  
                      type=String" />  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|índice|Cuando el tipo declarado es un tipo genérico, especifica el parámetro genérico que devolverá el tipo conocido.|  
|tipo|Una cadena que describe el tipo conocido usado para la serialización y deserialización.|  
  
## Atributo index  
  
|Valor|Descripción|  
|-----------|-----------------|  
|"0"|El primer parámetro en el tipo genérico.  Por ejemplo, un <xref:System.Collections.Generic.List%601> tiene solo un parámetro.  Si se usa como tipo declarado, el índice estaría establecido en "0".|  
|"1"|El segundo parámetro en un tipo genérico.  Por ejemplo, un <xref:System.Collections.Generic.Dictionary%602> tiene dos parámetros.  Si el segundo parámetro devuelve el tipo conocido, establezca el atributo de índice en "1".|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<knownType\>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowntype.md)|Especifica un tipo conocido que un campo o propiedad de un tipo declarado puede devolver.|  
  
## Comentarios  
 Los tipos conocidos de [!INCLUDE[crabout](../../../../../includes/crabout-md.md)], consulte [Tipos conocidos de contratos de datos](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) y <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
 Para obtener un ejemplo del uso de este elemento, consulte [\<dataContractSerializer\>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md).  
  
 Este elemento de configuración no puede tener al mismo tiempo ambos atributos.  Si se establecen ambos atributos, se produce un <xref:System.Configuration.ConfigurationErrorsException>.  
  
## Vea también  
 <xref:System.Runtime.Serialization.DataContractSerializer>   
 [Tipos conocidos de contratos de datos](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)   
 [\<dataContractSerializer\>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)   
 [\<agregar\>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)