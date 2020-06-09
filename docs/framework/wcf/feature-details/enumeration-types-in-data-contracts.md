---
title: Tipos de enumeración en contratos de datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data contracts [WCF], enumeration types
ms.assetid: b5d694da-68cb-4b74-a5fb-75108a68ec3b
ms.openlocfilehash: 86fa38b281d8944797fa858f8c67f0b60c733be8
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595549"
---
# <a name="enumeration-types-in-data-contracts"></a>Tipos de enumeración en contratos de datos
Las enumeraciones se pueden expresar en el modelo del contrato de datos. En este tema se exponen varios ejemplos que explican el modelo de programación.  
  
## <a name="enumeration-basics"></a>Fundamentos de enumeración  
 Una manera de utilizar tipos de enumeración en el modelo del contrato de datos es aplicar el atributo <xref:System.Runtime.Serialization.DataContractAttribute> al tipo. Debe aplicar a continuación el atributo <xref:System.Runtime.Serialization.EnumMemberAttribute> a cada miembro que debe estar incluido en el contrato de datos.  
  
 En el ejemplo siguiente se muestran dos clases. El primero utiliza la enumeración y el segundo define la enumeración.  
  
 [!code-csharp[c_DataContractEnumerations#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractenumerations/cs/source.cs#1)]
 [!code-vb[c_DataContractEnumerations#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractenumerations/vb/source.vb#1)]  
  
 Una instancia de la clase `Car` se puede enviar o recibir solo si el campo `condition` está establecido en uno de los valores `New`, `Used`o `Rental`. Si la propiedad `condition` es `Broken` o `Stolen`, se produce <xref:System.Runtime.Serialization.SerializationException>.  
  
 Puede utilizar las propiedades (<xref:System.Runtime.Serialization.DataContractAttribute> y <xref:System.Runtime.Serialization.DataContractAttribute.Name%2A>) <xref:System.Runtime.Serialization.DataContractAttribute.Namespace%2A> de forma habitual para los contratos de datos de enumeración.  
  
### <a name="enumeration-member-values"></a>Valores miembro de enumeración  
 Generalmente, el contrato de datos incluye nombres miembro de enumeración, no valores numéricos. Sin embargo, cuando se usa el modelo de contrato de datos, si el lado receptor es un cliente de WCF, el esquema exportado conserva los valores numéricos. Tenga en cuenta que este no es el caso cuando se usa la [clase XmlSerializer](using-the-xmlserializer-class.md).  
  
 En el ejemplo anterior, si `condition` está establecido en `Used` y se serializan los datos a XML, el XML resultante es `<condition>Used</condition>``<condition>1</condition>` y no . Por consiguiente, el contrato de datos siguiente es equivalente al contrato de datos de `CarConditionEnum`.  
  
 [!code-csharp[c_DataContractEnumerations#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractenumerations/cs/source.cs#2)]
 [!code-vb[c_DataContractEnumerations#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractenumerations/vb/source.vb#2)]  
  
 Por ejemplo, puede utilizar `CarConditionEnum` en el lado emisor y `CarConditionWithNumbers` en el lado receptor. Aunque el lado emisor usa el valor "1" para `Used` y el lado receptor usa el valor "20", la representación XML es `<condition>Used</condition>` para ambos lados.  
  
 Para que se incluya en el contrato de datos, debe aplicar el atributo <xref:System.Runtime.Serialization.EnumMemberAttribute>. En el .NET Framework, siempre puede aplicar el valor especial 0 (cero) a una enumeración, que también es el valor predeterminado para cualquier enumeración. Sin embargo, este valor especial cero no se puede serializar a menos que se marque con el atributo <xref:System.Runtime.Serialization.EnumMemberAttribute>.  
  
 Existen dos excepciones a esto:  
  
- Enumeraciones de marcas (se describe más adelante en este tema).  
  
- Miembros de datos de enumeración con la propiedad <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> establecida en `false` (en cuyo caso la enumeración con el valor cero se omite de los datos serializados).  
  
### <a name="customizing-enumeration-member-values"></a>Personalización de valores miembro de enumeración  
 Puede personalizar el valor miembro de enumeración que constituye una parte del contrato de datos utilizando la propiedad <xref:System.Runtime.Serialization.EnumMemberAttribute.Value%2A> del atributo <xref:System.Runtime.Serialization.EnumMemberAttribute>.  
  
 Por ejemplo, el siguiente contrato de datos es también equivalente al contrato de datos de `CarConditionEnum`.  
  
 [!code-csharp[c_DataContractEnumerations#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractenumerations/cs/source.cs#3)]
 [!code-vb[c_DataContractEnumerations#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractenumerations/vb/source.vb#3)]  
  
 Cuando se serializa, el valor de `PreviouslyOwned` tiene representación XML `<condition>Used</condition>`.  
  
## <a name="simple-enumerations"></a>Enumeraciones simples  
 También puede serializar los tipos de enumeración a los que no se ha aplicado el atributo <xref:System.Runtime.Serialization.DataContractAttribute>. Estos tipos de enumeración se tratan tal y como se ha descrito anteriormente, a excepción de que cada miembro (que no tiene el atributo <xref:System.NonSerializedAttribute> aplicado) se trata como si se hubiera aplicado el atributo <xref:System.Runtime.Serialization.EnumMemberAttribute>. Por ejemplo, la enumeración siguiente tiene de forma implícita un contrato de datos equivalente al del ejemplo de `CarConditionEnum` anterior.  
  
 [!code-csharp[c_DataContractEnumerations#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractenumerations/cs/source.cs#6)]
 [!code-vb[c_DataContractEnumerations#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractenumerations/vb/source.vb#6)]  
  
 Puede usar las enumeraciones simples cuando no necesite personalizar el espacio de nombres y el nombre del contrato de datos de la enumeración y los valores miembro de la enumeración.  
  
#### <a name="notes-on-simple-enumerations"></a>Notas en enumeraciones simples  
 Aplicar el atributo <xref:System.Runtime.Serialization.EnumMemberAttribute> a las enumeraciones simples no tiene ningún efecto.  
  
 No se produce ninguna diferencia si se aplica el atributo <xref:System.SerializableAttribute> o no a la enumeración.  
  
 El hecho que la clase <xref:System.Runtime.Serialization.DataContractSerializer> acepte el atributo <xref:System.NonSerializedAttribute> aplicado a los miembros de enumeración es diferente del comportamiento de <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> y <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>. Ambos de esos serializadores omiten el atributo <xref:System.NonSerializedAttribute>.  
  
## <a name="flag-enumerations"></a>Enumeraciones de marcas  
 Puede aplicar el atributo <xref:System.FlagsAttribute> a enumeraciones. En ese caso, una lista de cero o más valores de enumeración se puede enviar o recibir simultáneamente.  
  
 Para ello, aplique el atributo <xref:System.Runtime.Serialization.DataContractAttribute> a la enumeración de marca y, a continuación, marque todos los miembros que son potencias de dos con el atributo <xref:System.Runtime.Serialization.EnumMemberAttribute>. Tenga en cuenta que para utilizar una enumeración de marca, la progresión debe ser una secuencia ininterrumpida de potencias de 2 (por ejemplo, 1, 2, 4, 8, 16, 32, 64).  
  
 Los pasos siguientes se aplican al envío de un valor de enumeración de un marca:  
  
1. Intente buscar un miembro de enumeración (con el atributo <xref:System.Runtime.Serialization.EnumMemberAttribute> aplicado) que asigna al valor numérico. Si lo encuentra, envíe una lista que contenga solo ese miembro.  
  
2. Intente desglosar el valor numérico en una suma de tal forma que haya miembros de enumeración (cada uno con el atributo <xref:System.Runtime.Serialization.EnumMemberAttribute> aplicado) que estén asignados a cada parte de la suma. Envíe la lista de todos estos miembros. Tenga en cuenta que el *algoritmo expansivo* se usa para encontrar este tipo de suma y, por lo tanto, no hay ninguna garantía de que se encuentre una suma de este tipo, aunque esté presente. Para evitar este problema, asegúrese de que los valores numéricos de los miembros de enumeración son potencias de dos.  
  
3. Si los dos pasos anteriores fallan, y el valor numérico es distinto de cero, inicie <xref:System.Runtime.Serialization.SerializationException>. Si el valor numérico es cero, envíe la lista vacía.  
  
### <a name="example"></a>Ejemplo  
 El ejemplo de enumeración siguiente se puede utilizar en una operación de la marca.  
  
 [!code-csharp[c_DataContractEnumerations#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractenumerations/cs/source.cs#4)]
 [!code-vb[c_DataContractEnumerations#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractenumerations/vb/source.vb#4)]  
  
 Los valores de ejemplo siguientes se serializan tal y como se ha indicado.  
  
 [!code-csharp[c_DataContractEnumerations#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractenumerations/cs/source.cs#5)]
 [!code-vb[c_DataContractEnumerations#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractenumerations/vb/source.vb#5)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [Utilización de contratos de datos](using-data-contracts.md)
- [Especificación de transferencia de datos en contratos de servicio](specifying-data-transfer-in-service-contracts.md)
