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
ms.openlocfilehash: 28033e3e90c5010eee63f35791b0c3c77e64d1ec
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59129940"
---
# <a name="using-data-contracts"></a>Utilización de contratos de datos
Un *contrato de datos* es un acuerdo formal entre un servicio y un cliente que abstractamente describe los datos que se van a intercambiar. Es decir, para comunicarse, el cliente y el servicio no tienen que compartir los mismos tipos, solo los mismos contratos de datos. Un contrato de datos define con precisión, para cada parámetro o tipo de valor devuelto, qué datos se serializan (se convierten en XML) para su intercambio.  
  
## <a name="data-contract-basics"></a>Fundamentos del contrato de datos  
 Windows Communication Foundation (WCF) utiliza un motor de serialización llamado serializador de contratos de datos de forma predeterminada para serializar y deserializar datos (convertirlos a y desde XML). Todos los tipos primitivos [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] , como enteros y cadenas, así como ciertos tipos tratados como primitivos, como <xref:System.DateTime> y <xref:System.Xml.XmlElement>, se pueden serializar sin otra preparación y se considera que tienen contratos de datos predeterminados. Muchos tipos [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] también tienen contratos de datos existentes. Para obtener una lista completa de los tipos serializables, consulte [Types Supported by the Data Contract Serializer](../../../../docs/framework/wcf/feature-details/types-supported-by-the-data-contract-serializer.md).  
  
 Los nuevos tipos complejos que se crean deben tener un contrato de datos definido para que sean serializables. De forma predeterminada, <xref:System.Runtime.Serialization.DataContractSerializer> deduce el contrato de datos y serializa todos los tipos públicamente visibles. Se serializan todas las propiedades de lectura y escritura públicas y campos del tipo. Puede descartar miembros de la serialización mediante el uso de <xref:System.Runtime.Serialization.IgnoreDataMemberAttribute>. También puede crear explícitamente un contrato de datos mediante el uso de los atributos <xref:System.Runtime.Serialization.DataContractAttribute> y <xref:System.Runtime.Serialization.DataMemberAttribute> . Esto se hace normalmente aplicando el atributo <xref:System.Runtime.Serialization.DataContractAttribute> al tipo. Este atributo se puede aplicar a clases, estructuras y enumeraciones. El atributo <xref:System.Runtime.Serialization.DataMemberAttribute> se debe aplicar a continuación a cada miembro del tipo de contrato de datos para indicar que es un *miembro de datos*, es decir, que se debería serializar. Para obtener más información, consulte [tipos serializables](../../../../docs/framework/wcf/feature-details/serializable-types.md).  
  
### <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra un contrato de servicio (una interfaz) al que se han aplicado los atributos <xref:System.ServiceModel.ServiceContractAttribute> y <xref:System.ServiceModel.OperationContractAttribute> explícitamente. El ejemplo muestra que los tipos primitivos no requieren un contrato de datos, mientras un tipo complejo sí lo hace.  
  
 [!code-csharp[C_DataContract#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontract/cs/source.cs#1)]
 [!code-vb[C_DataContract#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontract/vb/source.vb#1)]  
  
 El ejemplo siguiente muestra cómo se crea un contrato de datos para el tipo `MyTypes.PurchaseOrder` aplicando los atributos <xref:System.Runtime.Serialization.DataContractAttribute> y <xref:System.Runtime.Serialization.DataMemberAttribute> a la clase y sus miembros.  
  
 [!code-csharp[C_DataContract#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontract/cs/source.cs#2)]
 [!code-vb[C_DataContract#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontract/vb/source.vb#2)]  
  
### <a name="notes"></a>Notas  
 Las notas siguientes proporcionan los elementos a considerar al crear los contratos de datos:  
  
-   El atributo <xref:System.Runtime.Serialization.IgnoreDataMemberAttribute> se observa solo cuando se usa con tipos no marcados. Se incluyen los tipos que no están marcados con uno de los atributos <xref:System.Runtime.Serialization.DataContractAttribute>, <xref:System.SerializableAttribute>, <xref:System.Runtime.Serialization.CollectionDataContractAttribute>o <xref:System.Runtime.Serialization.EnumMemberAttribute> , o que están marcados como serializables de alguna otra forma (como <xref:System.Xml.Serialization.IXmlSerializable>).  
  
-   Puede aplicar el atributo <xref:System.Runtime.Serialization.DataMemberAttribute> a campos y propiedades.  
  
-   Los niveles (interno, privado, protegido o público) de accesibilidad de miembros no afectan de forma alguna al contrato de datos.  
  
-   Se omite el atributo <xref:System.Runtime.Serialization.DataMemberAttribute> si se aplica a los miembros estáticos.  
  
-   Durante la serialización, se llama al código de obtención de propiedades para que los miembros de datos de propiedad obtengan el valor de las propiedades a serializar.  
  
-   Durante la deserialización, primero se crea un objeto no inicializado, sin llamar a ningún constructor en el tipo. A continuación, se deserializan todos los miembros de datos.  
  
-   Durante la serialización, se llama al código de conjunto de propiedades para que los miembros de datos de propiedad establezcan el valor de las propiedades que se están deserializando.  
  
-   Para que un contrato de datos sea válido, debe ser posible serializar todos sus miembros de datos. Para obtener una lista completa de los tipos serializables, consulte [Types Supported by the Data Contract Serializer](../../../../docs/framework/wcf/feature-details/types-supported-by-the-data-contract-serializer.md).  
  
     Los tipos genéricos se administran exactamente de la misma manera como los tipos no genéricos. No hay ningún requisito especial para los parámetros genéricos. Por ejemplo, veamos el siguiente tipo.  
  
 [!code-csharp[C_DataContract#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontract/cs/source.cs#3)]
 [!code-vb[C_DataContract#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontract/vb/source.vb#3)]  
  
 Este tipo es serializable tanto si el tipo que se usa para el parámetro de tipo genérico (`T`) es serializable como si no lo es. Dado que debe ser posible serializar todos los miembros de datos, el tipo siguiente solo es serializable solo si el parámetro de tipo genérico también es serializable, como se muestra en el código siguiente.  
  
 [!code-csharp[C_DataContract#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontract/cs/source.cs#4)]
 [!code-vb[C_DataContract#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontract/vb/source.vb#4)]  
  
 Para obtener un ejemplo de código completo de un servicio WCF que define un contrato de datos, consulte el ejemplo de [Basic Data Contract](../../../../docs/framework/wcf/samples/basic-data-contract.md) .  
  
## <a name="see-also"></a>Vea también

- <xref:System.Runtime.Serialization.DataMemberAttribute>
- <xref:System.Runtime.Serialization.DataContractAttribute>
- [Tipos serializables](../../../../docs/framework/wcf/feature-details/serializable-types.md)
- [Nombres de contratos de datos](../../../../docs/framework/wcf/feature-details/data-contract-names.md)
- [Equivalencia de contratos de datos](../../../../docs/framework/wcf/feature-details/data-contract-equivalence.md)
- [Orden de los miembros de datos](../../../../docs/framework/wcf/feature-details/data-member-order.md)
- [Tipos conocidos de contratos de datos](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
- [Contratos de datos compatibles con el reenvío](../../../../docs/framework/wcf/feature-details/forward-compatible-data-contracts.md)
- [Versiones de contratos de datos](../../../../docs/framework/wcf/feature-details/data-contract-versioning.md)
- [Devoluciones de llamadas en la serialización tolerante a versiones](../../../../docs/framework/wcf/feature-details/version-tolerant-serialization-callbacks.md)
- [Valores predeterminados de los miembros de datos](../../../../docs/framework/wcf/feature-details/data-member-default-values.md)
- [Tipos admitidos por el serializador de contratos de datos](../../../../docs/framework/wcf/feature-details/types-supported-by-the-data-contract-serializer.md)
- [Cómo: Crear un contrato de datos básicos para una clase o estructura](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-data-contract-for-a-class-or-structure.md)
