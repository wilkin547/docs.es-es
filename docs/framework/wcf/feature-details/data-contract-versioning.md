---
description: 'Más información sobre: control de versiones de contratos de datos'
title: Versiones de contratos de datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- versioning [WCF], data contracts
- versioning [WCF]
- data contracts [WCF], versioning
ms.assetid: 4a0700cb-5f5f-4137-8705-3a3ecf06461f
ms.openlocfilehash: 89b99ccad1671d33383cfce8d25b241d71788670
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99756609"
---
# <a name="data-contract-versioning"></a>Versiones de contratos de datos

A medida que las aplicaciones evolucionan, es posible que tenga que cambiar los contratos de datos que utilizan los servicios. En este tema se explica cómo controlar las versiones de los contratos de datos. En este tema se describen los mecanismos de control de versiones de los contratos de datos. Para obtener información general completa y una guía de versiones prescriptiva, vea [procedimientos recomendados: control de versiones de contratos de datos](../best-practices-data-contract-versioning.md).  
  
## <a name="breaking-vs-nonbreaking-changes"></a>Cambios con interrupción y sin interrupción  

 Los cambios en un contrato de datos pueden ser con o sin interrupción. Cuando un contrato de datos se cambia de una manera sin interrupción, una aplicación que use la versión anterior del contrato puede comunicarse con una aplicación utilizando la versión más reciente y una aplicación que utilice la versión más reciente del contrato puede comunicarse con una aplicación que utilice la versión anterior. Por otro lado, un cambio con interrupción evita la comunicación en una o ambas direcciones.  
  
 Los cambios realizados en un tipo que no afecten a la forma de la transmisión y recepción son cambios sin interrupción. Tales cambios no cambian el contrato de datos, solo el tipo subyacente. Por ejemplo, puede cambiar el nombre de un campo de una manera sin interrupción si establece a continuación la propiedad <xref:System.Runtime.Serialization.DataMemberAttribute.Name%2A> de <xref:System.Runtime.Serialization.DataMemberAttribute> en el nombre de la versión anterior. El código siguiente muestra la versión 1 de un contrato de datos.  
  
 [!code-csharp[C_DataContractVersioning#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractversioning/cs/source.cs#1)]
 [!code-vb[C_DataContractVersioning#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractversioning/vb/source.vb#1)]  
  
 El código siguiente muestra un cambio sin interrupción.  
  
 [!code-csharp[C_DataContractVersioning#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractversioning/cs/source.cs#2)]
 [!code-vb[C_DataContractVersioning#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractversioning/vb/source.vb#2)]  
  
 Algunos cambios modifican los datos transmitidos, pero puede que sean o no cambios con interrupción. Los siguientes cambios siempre son con interrupción:  
  
- Cambio del valor <xref:System.Runtime.Serialization.DataContractAttribute.Name%2A> o <xref:System.Runtime.Serialization.DataContractAttribute.Namespace%2A> de un contrato de datos.  
  
- Cambio del orden de miembros de datos utilizando la propiedad <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> de <xref:System.Runtime.Serialization.DataMemberAttribute>.  
  
- Cambio de nombre de un miembro de datos.  
  
- Cambio del contrato de datos de un miembro de datos. Por ejemplo, cambiar el tipo de miembro de datos de entero a cadena, o de un tipo con un contrato de datos denominado "Cliente" a un tipo con un contrato de datos denominado "Persona."  
  
 Los cambios siguientes también son posibles.  
  
## <a name="adding-and-removing-data-members"></a>Agregar y eliminar miembros de datos  

 En la mayoría de los casos, agregar o eliminar un miembro de datos no es un cambio con interrupción, a menos que requiera validez estricta de esquema (las nuevas instancias se validan frente al esquema anterior).  
  
 Cuando un tipo con un campo adicional se deserializa en un tipo con un campo que falta, se pasa por alto la información adicional. (También puede almacenarse para fines de ida y vuelta; para obtener más información, consulte [contratos de datos compatibles con el avance](forward-compatible-data-contracts.md)).  
  
 Cuando un tipo con un campo que falta se deserializa en un tipo con un campo adicional, el campo adicional se deja en su valor predeterminado, normalmente cero o `null`. (Se puede cambiar el valor predeterminado; para obtener más información, vea [devoluciones de llamada de serialización tolerante a versiones](version-tolerant-serialization-callbacks.md)).  
  
 Por ejemplo, puede utilizar la clase `CarV1` en un cliente y la clase `CarV2` en un servicio, o puede utilizar la clase `CarV1` en un servicio y la clase `CarV2` en un cliente.  
  
 [!code-csharp[C_DataContractVersioning#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractversioning/cs/source.cs#3)]
 [!code-vb[C_DataContractVersioning#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractversioning/vb/source.vb#3)]  
  
 El punto de conexión de versión 2 puede enviar datos correctamente al punto de conexión de versión 1. La serialización de la versión 2 del contrato de datos de `Car` produce un XML similar al siguiente.  
  
```xml  
<Car>  
    <Model>Porsche</Model>  
    <HorsePower>300</HorsePower>  
</Car>  
```  
  
 El motor de deserialización en V1 no encuentra un miembro de datos coincidente para el campo `HorsePower` y descarta esos datos.  
  
 Asimismo, el punto de conexión de versión 1 puede enviar datos al punto de conexión de versión 2. La serialización de la versión 1 del contrato de datos de `Car` produce un XML similar al siguiente.  
  
```xml  
<Car>  
    <Model>Porsche</Model>  
</Car>  
```  
  
 El deserializador de versión 2 no sabe qué valor asignar al campo `HorsePower`, porque no hay datos coincidentes en el XML de entrada. En su lugar, el campo se establece en el valor predeterminado de 0.  
  
## <a name="required-data-members"></a>Miembros de datos necesarios  

 Un miembro de datos se puede marcar como necesario estableciendo la propiedad <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> de <xref:System.Runtime.Serialization.DataMemberAttribute> en `true`. Si faltan datos necesarios al deserializar, se genera una excepción en lugar de establecer el miembro de datos en su valor predeterminado.  
  
 Agregar un miembro de datos necesario es un cambio con interrupción. Es decir, el tipo más nuevo todavía puede enviarse a los puntos de conexión con el tipo anterior, pero no al revés. Eliminar un miembro de datos marcado como necesario en cualquier versión anterior también es un cambio con interrupción.  
  
 Cambiar el valor de la propiedad <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> de `true` a `false` no es un cambio con interrupción, pero cambiarlo de `false` a `true` puede ser un cambio con interrupción si cualquier versión anterior del tipo no tiene el miembro de datos en cuestión.  
  
> [!NOTE]
> Aunque la propiedad <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> se establezca en `true`, el dato entrante puede ser nulo o cero, y se debe preparar un tipo para afrontar esta posibilidad. No utilice <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> como mecanismo de seguridad frente a datos entrante no válidos.  
  
## <a name="omitted-default-values"></a>Valores predeterminados ignorados  

 Es posible (aunque no se recomienda) establecer la `EmitDefaultValue` propiedad en el atributo DataMemberAttribute en `false` , tal y como se describe en [valores predeterminados de los miembros de datos](data-member-default-values.md). Si este valor es `false`, no se emitirá el miembro de datos si está establecido en su valor predeterminado (normalmente null o cero). Esto no es compatible con miembros de datos necesarios en versiones diferentes de dos maneras:  
  
- Un contrato de datos con un miembro de datos necesario en una versión no puede recibir datos predeterminados (null o cero) de una versión diferente en la que el miembro de datos tenga `EmitDefaultValue` establecido en `false`.  
  
- Un miembro de datos necesario que tiene `EmitDefaultValue` establecido en `false` no se puede utilizar para serializar su valor predeterminado (null o cero), pero puede recibir este tipo de valor en la deserialización. Esto crea un problema de ida y vuelta (los datos se pueden leer pero los mismos datos no se pueden escribir a continuación). Por consiguiente, si `IsRequired` es `true` y `EmitDefaultValue` es `false` en una versión, la misma combinación se debería aplicar al resto de versiones, de tal manera que ninguna versión del contrato de datos pudiese generar un valor que no resulte en un recorrido de ida y vuelta.  
  
## <a name="schema-considerations"></a>Consideraciones del esquema  

 Para obtener una explicación del esquema que se genera para los tipos de contrato de datos, vea [referencia de esquema de contrato de datos](data-contract-schema-reference.md).  
  
 El esquema que WCF genera para los tipos de contrato de datos no hace ninguna disposición para el control de versiones. Es decir, el esquema exportado desde una cierta versión de un tipo contiene solo esos miembros de datos presentes en esa versión. La implementación de la interfaz <xref:System.Runtime.Serialization.IExtensibleDataObject>, no cambia el esquema de un tipo.  
  
 Los miembros de datos se exportan de forma predeterminada al esquema como elementos opcionales. Es decir, el valor de `minOccurs` (atributo XML) se establece en 0. Los miembros de datos necesarios se exportan con `minOccurs` establecido en 1.  
  
 Muchos de los cambios considerados como cambios sin interrupción son, en realidad, cambios con interrupción si se requiere una adherencia estricta al esquema. En el ejemplo anterior, una instancia de `CarV1` simplemente con el elemento `Model` validaría frente al esquema `CarV2` (que tiene `Model` y `Horsepower`, pero ambos son opcionales). Sin embargo, lo inverso no es cierto: una instancia de `CarV2` produciría un error en la validación frente al esquema `CarV1`.  
  
 El recorrido de ida y vuelta implica algunas consideraciones adicionales. Para obtener más información, vea la sección "consideraciones del esquema" en [contratos de datos compatibles con versiones posteriores](forward-compatible-data-contracts.md).  
  
### <a name="other-permitted-changes"></a>Otros cambios permitidos  

 Implementar la interfaz <xref:System.Runtime.Serialization.IExtensibleDataObject> es un cambio sin interrupción. Sin embargo, la compatibilidad con el recorrido de ida y vuelta no existe para las versiones del tipo anterior a la versión en la que <xref:System.Runtime.Serialization.IExtensibleDataObject> se implementó. Para obtener más información, vea [Forward-Compatible Data Contracts](forward-compatible-data-contracts.md) (Contratos de datos compatibles con el reenvío).  
  
## <a name="enumerations"></a>Enumeraciones  

 Agregar o eliminar un miembro de enumeración es un cambio con interrupción. Cambiar el nombre de un miembro de enumeración es un cambio con interrupción, a menos que su nombre de contrato se mantenga igual que en la versión anterior mediante el atributo `EnumMemberAttribute`. Para obtener más información, vea [tipos de enumeración en contratos de datos](enumeration-types-in-data-contracts.md).  
  
## <a name="collections"></a>Colecciones  

 La mayoría de los cambios de colección son cambios sin interrupción, puesto que la mayoría de los tipos de colección son intercambiables entre sí en el modelo del contrato de datos. Sin embargo, personalizar una colección no personalizada o viceversa es un cambio con interrupción. Asimismo, cambiar la configuración de personalización de la colección es un cambio brusco; es decir, implica cambiar su espacio de nombres y nombre de contrato de datos, repitiendo el nombre del elemento, el nombre del elemento de la clave y el nombre del elemento del valor. Para obtener más información sobre la personalización de colecciones, vea [tipos de colección en contratos de datos](collection-types-in-data-contracts.md).  
Naturalmente, cambiar el contrato de datos del contenido de una colección (por ejemplo, cambiar de una lista de enteros a una lista de cadenas) es un cambio brusco.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Runtime.Serialization.DataMemberAttribute.Name%2A>
- <xref:System.Runtime.Serialization.DataMemberAttribute>
- <xref:System.Runtime.Serialization.DataContractAttribute.Name%2A>
- <xref:System.Runtime.Serialization.DataContractAttribute.Namespace%2A>
- <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A>
- <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A>
- <xref:System.Runtime.Serialization.SerializationException>
- <xref:System.Runtime.Serialization.IExtensibleDataObject>
- [Devoluciones de llamadas en la serialización tolerante a versiones](version-tolerant-serialization-callbacks.md)
- [Procedimientos recomendados: Versiones de contratos de datos](../best-practices-data-contract-versioning.md)
- [Utilización de contratos de datos](using-data-contracts.md)
- [Equivalencia del contrato de datos](data-contract-equivalence.md)
- [Contratos de datos compatibles con el reenvío](forward-compatible-data-contracts.md)
