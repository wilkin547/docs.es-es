---
title: Utilización de contratos de datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataContractAttribute class
- WCF, data
- data contracts [WCF]
ms.assetid: a3ae7b21-c15c-4c05-abd8-f483bcbf31af
ms.openlocfilehash: 0d11b48d3021bf0d92d74ab67bc18c2bdd2bdd0e
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595003"
---
# <a name="using-data-contracts"></a>Utilización de contratos de datos
Un *contrato de datos* es un acuerdo formal entre un servicio y un cliente que abstractamente describe los datos que se van a intercambiar. Es decir, para comunicarse, el cliente y el servicio no tienen que compartir los mismos tipos, solo los mismos contratos de datos. Un contrato de datos define con precisión, para cada parámetro o tipo de valor devuelto, qué datos se serializan (se convierten en XML) para su intercambio.  
  
## <a name="data-contract-basics"></a>Fundamentos del contrato de datos  
 Windows Communication Foundation (WCF) usa un motor de serialización denominado serializador de contrato de datos de forma predeterminada para serializar y deserializar los datos (convertirlos a y desde XML). Todos .NET Framework tipos primitivos, como enteros y cadenas, así como ciertos tipos tratados como primitivos, como <xref:System.DateTime> y <xref:System.Xml.XmlElement> , se pueden serializar sin otra preparación y se consideran como si tuvieran contratos de datos predeterminados. Muchos tipos de .NET Framework también tienen contratos de datos existentes. Para obtener una lista completa de los tipos serializables, consulte [Types Supported by the Data Contract Serializer](types-supported-by-the-data-contract-serializer.md).  
  
 Los nuevos tipos complejos que se crean deben tener un contrato de datos definido para que sean serializables. De forma predeterminada, <xref:System.Runtime.Serialization.DataContractSerializer> deduce el contrato de datos y serializa todos los tipos públicamente visibles. Se serializan todas las propiedades de lectura y escritura públicas y campos del tipo. Puede descartar miembros de la serialización mediante el uso de <xref:System.Runtime.Serialization.IgnoreDataMemberAttribute>. También puede crear explícitamente un contrato de datos mediante el uso de los atributos <xref:System.Runtime.Serialization.DataContractAttribute> y <xref:System.Runtime.Serialization.DataMemberAttribute> . Esto se hace normalmente aplicando el atributo <xref:System.Runtime.Serialization.DataContractAttribute> al tipo. Este atributo se puede aplicar a clases, estructuras y enumeraciones. El atributo <xref:System.Runtime.Serialization.DataMemberAttribute> se debe aplicar a continuación a cada miembro del tipo de contrato de datos para indicar que es un *miembro de datos*, es decir, que se debería serializar. Para obtener más información, vea [tipos serializables](serializable-types.md).  
  
### <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra un contrato de servicio (una interfaz) al que se han aplicado los atributos <xref:System.ServiceModel.ServiceContractAttribute> y <xref:System.ServiceModel.OperationContractAttribute> explícitamente. El ejemplo muestra que los tipos primitivos no requieren un contrato de datos, mientras un tipo complejo sí lo hace.  
  
 [!code-csharp[C_DataContract#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontract/cs/source.cs#1)]
 [!code-vb[C_DataContract#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontract/vb/source.vb#1)]  
  
 El ejemplo siguiente muestra cómo se crea un contrato de datos para el tipo `MyTypes.PurchaseOrder` aplicando los atributos <xref:System.Runtime.Serialization.DataContractAttribute> y <xref:System.Runtime.Serialization.DataMemberAttribute> a la clase y sus miembros.  
  
 [!code-csharp[C_DataContract#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontract/cs/source.cs#2)]
 [!code-vb[C_DataContract#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontract/vb/source.vb#2)]  
  
### <a name="notes"></a>Notas  
 Las notas siguientes proporcionan los elementos a considerar al crear los contratos de datos:  
  
- El atributo <xref:System.Runtime.Serialization.IgnoreDataMemberAttribute> se observa solo cuando se usa con tipos no marcados. Se incluyen los tipos que no están marcados con uno de los atributos <xref:System.Runtime.Serialization.DataContractAttribute>, <xref:System.SerializableAttribute>, <xref:System.Runtime.Serialization.CollectionDataContractAttribute>o <xref:System.Runtime.Serialization.EnumMemberAttribute> , o que están marcados como serializables de alguna otra forma (como <xref:System.Xml.Serialization.IXmlSerializable>).  
  
- Puede aplicar el atributo <xref:System.Runtime.Serialization.DataMemberAttribute> a campos y propiedades.  
  
- Los niveles (interno, privado, protegido o público) de accesibilidad de miembros no afectan de forma alguna al contrato de datos.  
  
- Se omite el atributo <xref:System.Runtime.Serialization.DataMemberAttribute> si se aplica a los miembros estáticos.  
  
- Durante la serialización, se llama al código de obtención de propiedades para que los miembros de datos de propiedad obtengan el valor de las propiedades a serializar.  
  
- Durante la deserialización, primero se crea un objeto no inicializado, sin llamar a ningún constructor en el tipo. A continuación, se deserializan todos los miembros de datos.  
  
- Durante la serialización, se llama al código de conjunto de propiedades para que los miembros de datos de propiedad establezcan el valor de las propiedades que se están deserializando.  
  
- Para que un contrato de datos sea válido, debe ser posible serializar todos sus miembros de datos. Para obtener una lista completa de los tipos serializables, consulte [Types Supported by the Data Contract Serializer](types-supported-by-the-data-contract-serializer.md).  
  
     Los tipos genéricos se administran exactamente de la misma manera como los tipos no genéricos. No hay ningún requisito especial para los parámetros genéricos. Por ejemplo, veamos el siguiente tipo.  
  
 [!code-csharp[C_DataContract#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontract/cs/source.cs#3)]
 [!code-vb[C_DataContract#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontract/vb/source.vb#3)]  
  
 Este tipo es serializable tanto si el tipo que se usa para el parámetro de tipo genérico (`T`) es serializable como si no lo es. Dado que debe ser posible serializar todos los miembros de datos, el tipo siguiente solo es serializable solo si el parámetro de tipo genérico también es serializable, como se muestra en el código siguiente.  
  
 [!code-csharp[C_DataContract#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontract/cs/source.cs#4)]
 [!code-vb[C_DataContract#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontract/vb/source.vb#4)]  
  
 Para obtener un ejemplo de código completo de un servicio WCF que define un contrato de datos, consulte el ejemplo de [Basic Data Contract](../samples/basic-data-contract.md) .  
  
## <a name="see-also"></a>Vea también

- <xref:System.Runtime.Serialization.DataMemberAttribute>
- <xref:System.Runtime.Serialization.DataContractAttribute>
- [Tipos serializables](serializable-types.md)
- [Nombres de contratos de datos](data-contract-names.md)
- [Equivalencia del contrato de datos](data-contract-equivalence.md)
- [Orden de los miembros de datos](data-member-order.md)
- [Tipos conocidos de contratos de datos](data-contract-known-types.md)
- [Contratos de datos compatibles con el reenvío](forward-compatible-data-contracts.md)
- [Versiones de contratos de datos](data-contract-versioning.md)
- [Devoluciones de llamadas en la serialización tolerante a versiones](version-tolerant-serialization-callbacks.md)
- [Valores predeterminados de los miembros de datos](data-member-default-values.md)
- [Tipos admitidos por el serializador de contratos de datos](types-supported-by-the-data-contract-serializer.md)
- [Procedimiento para crear un contrato de datos básico para una clase o estructura](how-to-create-a-basic-data-contract-for-a-class-or-structure.md)
