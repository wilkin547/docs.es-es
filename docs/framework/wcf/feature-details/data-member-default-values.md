---
title: "Valores predeterminados de los miembros de datos | Microsoft Docs"
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
  - "miembros de datos [WCF]"
  - "miembros de datos [WCF], valores predeterminados"
ms.assetid: 53a3b505-4b27-444b-b079-0eb84a97cfd8
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# Valores predeterminados de los miembros de datos
En [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], los tipos tienen un concepto de *valores predeterminados*.Por ejemplo, para cualquier tipo de referencia el valor predeterminado es `null`, y para un tipo entero es cero.En ocasiones es deseable omitir un miembro de datos de los datos serializados cuando está establecido en su valor predeterminado.Dado que el miembro tiene un valor predeterminado, no es necesario serializar un valor real; esto es una ventaja en cuanto al rendimiento.  
  
 Para omitir un miembro de los datos serializados, establezca la propiedad <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> del atributo <xref:System.Runtime.Serialization.DataMemberAttribute> en `false` \(el valor predeterminado es `true`\).  
  
> [!NOTE]
>  Debe establecer la propiedad <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> en `false` si hubiese una necesidad concreta de hacerlo, como para reducir el tamaño de los datos u ofrecer interoperabilidad.  
  
## Ejemplo  
 El siguiente código tiene varios miembros con el <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> establecido en `false`.  
  
 [!code-csharp[DataMemberAttribute#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/datamemberattribute/cs/overview.cs#4)]
 [!code-vb[DataMemberAttribute#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/datamemberattribute/vb/overview.vb#4)]  
  
 Si se serializa una instancia de esta clase, el resultado es el siguiente: se serializan `employeeName` y `employeeID`.El valor null de `employeeName` y el valor cero para `employeeID` forma parte explícitamente de los datos serializados.Sin embargo, no se serializan los miembros `position`, `salary`y `bonus`.Finalmente, se serializa como de costumbre `targetSalary`, aunque la propiedad <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> esté establecida en `false`, porque 57800 no coincide con el valor predeterminado de .NET para un entero, que es cero.  
  
### Representación de XML  
 Si el ejemplo anterior se serializa en XML, la representación es similar a la siguiente.  
  
```  
<Employee>  
   <employeeName xsi:nil="true" />  
   <employeeID>0</employeeID>  
<targetSalary>57800</targetSalary>  
</Employee>  
```  
  
 El atributo `xsi:nil` es un atributo especial en el espacio de nombres de instancia del Esquema XML de World Wide Web Consortium \(W3C\), que proporciona una manera interoperable de representar explícitamente un valor nulo.Observe que no hay ninguna información en el XML sobre los miembros de datos de bonificaciones, posición ni sueldo.El extremo receptor puede interpretarlos como `null`, cero y `null`, respectivamente.No hay ninguna garantía de que un deserializador de otro fabricante pueda realizar la interpretación correcta, que es la razón por la que este modelo no se recomienda.La clase <xref:System.Runtime.Serialization.DataContractSerializer> siempre selecciona la interpretación correcta de los valores que faltan.  
  
### Interacción con IsRequired  
 Como se discutió en [Versiones de contratos de datos](../../../../docs/framework/wcf/feature-details/data-contract-versioning.md), el atributo <xref:System.Runtime.Serialization.DataMemberAttribute> tiene una propiedad <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> \(el valor predeterminado es `false`\).La propiedad indica si un miembro de datos determinado debe estar presente o no en los datos serializados cuando se deserialicen.Si `IsRequired` se establece en `true` \(lo que indica que un valor debe estar presente\) y <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> se establece en `false` \(lo que indica que el valor no debe estar presente si se establece en su valor predeterminado\), no se pueden serializar los valores predeterminados para este miembro de datos porque los resultados serían contradictorios.Si este tipo de miembro de datos está establecido en su valor predeterminado \(normalmente `null` o cero\) y se intenta una serialización, se produce una <xref:System.Runtime.Serialization.SerializationException>.  
  
### Representación del esquema  
 Los detalles de la representación de esquema del lenguaje de definición de esquemas XML \(XSD\) de miembros de datos cuando la propiedad `EmitDefaultValue` está establecida en `false` se discuten en [Referencia de esquema de contrato de datos](../../../../docs/framework/wcf/feature-details/data-contract-schema-reference.md).Sin embargo, la siguiente es una información general resumida:  
  
-   Cuando el <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> está establecido en `false`, se representa en el esquema como una anotación específica para [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].No hay ninguna manera interoperable de representar esta información.En particular, el atributo "default" \(predeterminado\) en el esquema no se utiliza para este propósito, el atributo `minOccurs` solo se ve afectado por el valor <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A>, y el atributo `nillable` solo se ve afectado por el tipo del miembro de datos.  
  
-   El valor predeterminado real a utilizar no se encuentra en el esquema.Depende del extremo receptor el interpretar correctamente un elemento que falta.  
  
 En la importación del esquema, la propiedad <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> está establecida automáticamente en `false` siempre que se detecte la anotación específica de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] mencionada con anterioridad.También está establecido en `false` para los tipos de referencia que tengan la propiedad `nillable` establecida en `false` para admitir escenarios de interoperabilidad concretos que normalmente tienen lugar al utilizar los servicios web de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].  
  
## Vea también  
 <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A>   
 <xref:System.Runtime.Serialization.DataMemberAttribute>