---
title: Valores predeterminados de los miembros de datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data members [WCF], default values
- data members [WCF]
ms.assetid: 53a3b505-4b27-444b-b079-0eb84a97cfd8
ms.openlocfilehash: 2d323566aa211ced9ed76302756ed5dc82c5d2c3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61857121"
---
# <a name="data-member-default-values"></a>Valores predeterminados de los miembros de datos
En el [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], tipos tienen un concepto de *los valores predeterminados*. Por ejemplo, para cualquier tipo de referencia el valor predeterminado es `null`, y para un tipo entero es cero. En ocasiones es deseable omitir un miembro de datos de los datos serializados cuando está establecido en su valor predeterminado. Dado que el miembro tiene un valor predeterminado, no es necesario serializar un valor real; esto es una ventaja en cuanto al rendimiento.  
  
 Para omitir un miembro de los datos serializados, establezca la propiedad <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> del atributo <xref:System.Runtime.Serialization.DataMemberAttribute> en `false` (el valor predeterminado es `true`).  
  
> [!NOTE]
>  Debe establecer la propiedad <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> en `false` si hubiese una necesidad concreta de hacerlo, como para reducir el tamaño de los datos u ofrecer interoperabilidad.  
  
## <a name="example"></a>Ejemplo  
 El siguiente código tiene varios miembros con el <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> establecido en `false`.  
  
 [!code-csharp[DataMemberAttribute#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/datamemberattribute/cs/overview.cs#4)]
 [!code-vb[DataMemberAttribute#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/datamemberattribute/vb/overview.vb#4)]  
  
 Si se serializa una instancia de esta clase, el resultado es el siguiente: se serializan `employeeName` y `employeeID`. El valor null de `employeeName` y el valor cero para `employeeID` forma parte explícitamente de los datos serializados. Sin embargo, no se serializan los miembros `position`, `salary`y `bonus`. Finalmente, se serializa como de costumbre `targetSalary`, aunque la propiedad <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> esté establecida en `false`, porque 57800 no coincide con el valor predeterminado de .NET para un entero, que es cero.  
  
### <a name="xml-representation"></a>Representación de XML  
 Si el ejemplo anterior se serializa en XML, la representación es similar a la siguiente.  
  
```xml  
<Employee>  
   <employeeName xsi:nil="true" />  
   <employeeID>0</employeeID>  
<targetSalary>57800</targetSalary>  
</Employee>  
```  
  
 El atributo `xsi:nil` es un atributo especial en el espacio de nombres de instancia del Esquema XML de World Wide Web Consortium (W3C), que proporciona una manera interoperable de representar explícitamente un valor nulo. Observe que no hay ninguna información en el XML sobre los miembros de datos de bonificaciones, posición ni sueldo. El extremo receptor puede interpretarlos como `null`, cero y `null`, respectivamente. No hay ninguna garantía de que un deserializador de otro fabricante pueda realizar la interpretación correcta, que es la razón por la que este patrón no se recomienda. La clase <xref:System.Runtime.Serialization.DataContractSerializer> siempre selecciona la interpretación correcta de los valores que faltan.  
  
### <a name="interaction-with-isrequired"></a>Interacción con IsRequired  
 Como se describe en [versiones de contratos de datos](../../../../docs/framework/wcf/feature-details/data-contract-versioning.md), <xref:System.Runtime.Serialization.DataMemberAttribute> atributo tiene un <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> propiedad (el valor predeterminado es `false`). La propiedad indica si un miembro de datos determinado debe estar presente o no en los datos serializados cuando se deserialicen. Si `IsRequired` se establece en `true` (lo que indica que un valor debe estar presente) y <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> se establece en `false` (lo que indica que el valor no debe estar presente si se establece en su valor predeterminado), no se pueden serializar los valores predeterminados para este miembro de datos porque los resultados serían contradictorios. Si este tipo de miembro de datos está establecido en su valor predeterminado (normalmente `null` o cero) y se intenta una serialización, se produce una <xref:System.Runtime.Serialization.SerializationException>.  
  
### <a name="schema-representation"></a>Representación del esquema  
 Los detalles de la representación de esquema de lenguaje (XSD) de definición de esquema XML de miembros de datos cuando el `EmitDefaultValue` propiedad está establecida en `false` se tratan en [Data Contract Schema Reference](../../../../docs/framework/wcf/feature-details/data-contract-schema-reference.md). Sin embargo, la siguiente es una información general resumida:  
  
-   Cuando el <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> está establecido en `false`, se representa en el esquema como una anotación específica para Windows Communication Foundation (WCF). No hay ninguna manera interoperable de representar esta información. En particular, el atributo "default" (predeterminado) en el esquema no se utiliza para este propósito, el atributo `minOccurs` solo se ve afectado por el valor <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A>, y el atributo `nillable` solo se ve afectado por el tipo del miembro de datos.  
  
-   El valor predeterminado real a utilizar no se encuentra en el esquema. Depende del punto de conexión receptor el interpretar correctamente un elemento que falta.  
  
 Al importar el esquema, el <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> propiedad se establece automáticamente en `false` cada vez que la anotación específica de WCF que se ha mencionado anteriormente se ha detectado. También está establecido en `false` para los tipos de referencia que tengan la propiedad `nillable` establecida en `false` para admitir escenarios de interoperabilidad concretos que normalmente tienen lugar al utilizar los servicios web de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].  
  
## <a name="see-also"></a>Vea también

- <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A>
- <xref:System.Runtime.Serialization.DataMemberAttribute>
