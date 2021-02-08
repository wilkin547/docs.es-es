---
description: 'Más información acerca de: Forward-Compatible contratos de datos'
title: Contratos de datos compatibles con el reenvío
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data contracts [WCF], forward compatibility
ms.assetid: 413c9044-26f8-4ecb-968c-18495ea52cd9
ms.openlocfilehash: 70256449d405290e9c32eebdc5b8e3a78b76ed56
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99793862"
---
# <a name="forward-compatible-data-contracts"></a>Contratos de datos compatibles con el reenvío

Una característica del sistema de contrato de datos Windows Communication Foundation (WCF) es que los contratos pueden evolucionar con el tiempo de maneras sin interrupción. Es decir, un cliente con una versión anterior de un contrato de datos puede comunicarse con un servicio con una versión más reciente del mismo contrato de datos, o un cliente con una versión más reciente de un contrato de datos puede comunicarse con una versión anterior del mismo contrato de datos. Para obtener más información, consulte [procedimientos recomendados: control de versiones de contratos de datos](../best-practices-data-contract-versioning.md).  
  
 Puede aplicar la mayoría de las características del control de versiones en la medida que se necesite cuando se crean las nuevas versiones de un contrato del dato existente. Sin embargo, una característica de control de versiones, *recorrido de ida y vuelta*, debe estar integrada en el tipo de la primera versión para que funcione correctamente.  
  
## <a name="round-tripping"></a>Round-Tripping (recorrido de ida y vuelta)  

 Round-tripping tiene lugar cuando los datos pasan de una nueva versión a una versión anterior y de vuelta a la nueva versión de un contrato de datos. El round-tripping garantiza que no se pierdan datos. Habilitar el round-tripping hace que el tipo sea compatible por adelantado con cualquier cambio futuro admitido por el modelo de control de versiones del contrato de datos.  
  
 Para habilitar el round-tripping para un tipo determinado, el tipo debe implementar la interfaz <xref:System.Runtime.Serialization.IExtensibleDataObject>. La interfaz contiene una propiedad, <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A> (que devuelve el tipo <xref:System.Runtime.Serialization.ExtensionDataObject> ). La propiedad almacena cualquier dato de las versiones futuras del contrato de datos que es desconocido para la versión actual.  
  
### <a name="example"></a>Ejemplo  

 El siguiente contrato de datos no compatible por adelantado con los cambios futuros.  
  
 [!code-csharp[C_DataContract#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontract/cs/source.cs#7)]
 [!code-vb[C_DataContract#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontract/vb/source.vb#7)]  
  
 Para hacer que el tipo sea compatible con los cambios futuros (como agregar un nuevo miembro de datos denominado "phoneNumber"), implemente la interfaz <xref:System.Runtime.Serialization.IExtensibleDataObject>.  
  
 [!code-csharp[C_DataContract#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontract/cs/source.cs#8)]
 [!code-vb[C_DataContract#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontract/vb/source.vb#8)]  
  
 Cuando la infraestructura de WCF encuentra datos que no forman parte del contrato de datos original, los datos se almacenan en la propiedad y se conservan. No se procesa para nada más, salvo para el almacenamiento temporal. Si el objeto se devuelve a donde se originó, se devuelven también los datos originales (desconocidos). Por consiguiente, los datos han realizado un viaje de ida y vuelta (round trip) hasta y desde el extremo de origen sin sufrir pérdidas. Tenga en cuenta, sin embargo, que si el punto de conexión de origen exigiera que se procesasen los datos, la expectativa no se cumple, y el punto de conexión debe detectar y adaptar el cambio de algún modo.  
  
 El tipo <xref:System.Runtime.Serialization.ExtensionDataObject> no contiene ningún método público ni propiedades. Por tanto, es imposible obtener acceso directo a los datos almacenados dentro de la propiedad <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A>.  
  
 La característica de round-tripping puede desactivarse, estableciendo `ignoreExtensionDataObject` en `true` en el constructor <xref:System.Runtime.Serialization.DataContractSerializer> o estableciendo la propiedad <xref:System.ServiceModel.ServiceBehaviorAttribute.IgnoreExtensionDataObject%2A> en `true` en el <xref:System.ServiceModel.ServiceBehaviorAttribute>. Cuando esta característica está deshabilitada, el deserializador no rellenará la propiedad <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A> y el serializador no emitirá el contenido de la propiedad.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Runtime.Serialization.IExtensibleDataObject>
- <xref:System.Runtime.Serialization.ExtensionDataObject>
- [Versiones de contratos de datos](data-contract-versioning.md)
- [Procedimientos recomendados: Versiones de contratos de datos](../best-practices-data-contract-versioning.md)
