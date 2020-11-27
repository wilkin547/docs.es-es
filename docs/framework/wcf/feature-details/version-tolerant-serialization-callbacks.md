---
title: Devoluciones de llamadas en la serialización tolerante a versiones
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- OnDeserializedAttribute [WCF]
- OnDeserializingAttribute [WCF]
- OnSerializingAttribute [WCF]
- serialization [WCF], setting default values
- OnSerializedAttribute [WCF]
ms.assetid: aa4a3a6f-05ec-4efd-bdbf-2181e13e6468
ms.openlocfilehash: ad162f24042f30eabee7a1fad2025072b26d9af5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96289378"
---
# <a name="version-tolerant-serialization-callbacks"></a>Devoluciones de llamadas en la serialización tolerante a versiones

El modelo de programación del contrato de datos admite totalmente los métodos de devolución de llamada de serialización tolerante a versiones que las clases <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> y <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> admiten.  
  
## <a name="version-tolerant-attributes"></a>Atributos tolerantes a versiones  

 Hay cuatro atributos de devolución de llamada. Cada atributo se puede aplicar a un método que el motor de serialización/deserialización denomina en varios momentos. La siguiente tabla explica cuándo utilizar cada atributo.  
  
|Atributo|Cuando se llama al método correspondiente|  
|---------------|---------------------------------------------|  
|<xref:System.Runtime.Serialization.OnSerializingAttribute>|Llamado antes de serializar el tipo.|  
|<xref:System.Runtime.Serialization.OnSerializedAttribute>|Llamado después de serializar el tipo.|  
|<xref:System.Runtime.Serialization.OnDeserializingAttribute>|Llamado antes de deserializar el tipo.|  
|<xref:System.Runtime.Serialization.OnDeserializedAttribute>|Llamado después de deserializar el tipo.|  
  
 Los métodos deben aceptar un parámetro <xref:System.Runtime.Serialization.StreamingContext>.  
  
 Estos métodos están pensados principalmente para utilizarlos con controlador de versiones o inicialización. No se llama a ningún constructor durante la deserialización. Por lo tanto, puede que no se puedan inicializar correctamente los miembros de datos (en valores predeterminados intencionales), si los datos de estos miembros faltan en la secuencia de entrada, por ejemplo, si los datos proceden de una versión anterior de un tipo al cual le faltan algunos miembros de datos.  Para corregirlo, utilice el método de devolución de llamada marcado con <xref:System.Runtime.Serialization.OnDeserializingAttribute>, tal y como se muestra en el siguiente ejemplo.  
  
 Puede marcar sólo un método por tipo con cada uno de los atributos de devolución de llamada anteriores.  
  
### <a name="example"></a>Ejemplo  

 [!code-csharp[C_DataContract#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontract/cs/source.cs#9)]
 [!code-vb[C_DataContract#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontract/vb/source.vb#9)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Runtime.Serialization.OnSerializingAttribute>
- <xref:System.Runtime.Serialization.OnSerializedAttribute>
- <xref:System.Runtime.Serialization.OnDeserializingAttribute>
- <xref:System.Runtime.Serialization.OnDeserializedAttribute>
- <xref:System.Runtime.Serialization.StreamingContext>
- [Serialización tolerante a versiones](../../../standard/serialization/version-tolerant-serialization.md)
