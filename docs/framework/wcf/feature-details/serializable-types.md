---
description: 'Más información sobre: tipos serializables'
title: Tipos serializables
ms.date: 03/30/2017
ms.assetid: f1c8539a-6a79-4413-b294-896f0957b2cd
ms.openlocfilehash: 0316946a2d373f6fec4df388e5ed50bd4dc2b1c2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99793576"
---
# <a name="serializable-types"></a>Tipos serializables

De forma predeterminada, <xref:System.Runtime.Serialization.DataContractSerializer> serializa todos los tipos públicamente visibles. Se serializan todas las propiedades de lectura y escritura públicas y campos del tipo.  
  
 Puede cambiar el comportamiento predeterminado aplicando los atributos <xref:System.Runtime.Serialization.DataContractAttribute> y <xref:System.Runtime.Serialization.DataMemberAttribute> a los tipos y miembros. Esta característica puede ser útil en situaciones en las que hay tipos que no están bajo su control y no se pueden modificar para agregar atributos. <xref:System.Runtime.Serialization.DataContractSerializer> reconoce tales tipos "sin marcar".  
  
## <a name="serialization-defaults"></a>Valores predeterminados de la serialización  

 Puede aplicar los atributos <xref:System.Runtime.Serialization.DataContractAttribute> y <xref:System.Runtime.Serialization.DataMemberAttribute> para controlar explícitamente o personalizar la serialización de tipos y miembros. Además, puede aplicar estos atributos a campos privados. Sin embargo, incluso los tipos que no se marcan con estos atributos se serializan y deserializan. Se aplican las reglas y excepciones siguientes:  
  
- <xref:System.Runtime.Serialization.DataContractSerializer> deduce un contrato de datos a partir de los tipos sin atributos usando las propiedades predeterminadas de los tipos creados recientemente.  
  
- Se serializan todos los campos públicos y las propiedades con métodos `get` y `set` públicos, a menos que se aplique el atributo <xref:System.Runtime.Serialization.IgnoreDataMemberAttribute> a ese miembro.  
  
- La semántica de la serialización es similar a la de <xref:System.Xml.Serialization.XmlSerializer>.  
  
- En los tipos no marcados, solo se serializan los tipos públicos con constructores que no tienen parámetros. La excepción a esta regla es <xref:System.Runtime.Serialization.ExtensionDataObject> utilizado con la interfaz <xref:System.Runtime.Serialization.IExtensibleDataObject>.  
  
- No se serializan los campos de solo lectura, las propiedades sin un método `get` o `set` y las propiedades con métodos `set` o `get` internos o privados. Tales propiedades se omiten y no se produce ninguna excepción, salvo en el caso de las colecciones "get-only".  
  
- Se omiten los atributos <xref:System.Xml.Serialization.XmlSerializer> (como `XmlElement`, `XmlAttribute`, `XmlIgnore`, `XmlInclude`, etc.).  
  
- Si no se aplica el atributo <xref:System.Runtime.Serialization.DataContractAttribute> a un tipo determinado, el serializador omite cualquier miembro de ese tipo al que se aplique el atributo <xref:System.Runtime.Serialization.DataMemberAttribute>.  
  
- La propiedad <xref:System.Runtime.Serialization.DataContractSerializer.KnownTypes%2A> se admite en los tipos no marcados con el atributo <xref:System.Runtime.Serialization.DataContractAttribute>. Esto incluye la compatibilidad con el atributo <xref:System.Runtime.Serialization.KnownTypeAttribute> en los tipos no marcados.  
  
- Para descartar la serialización de miembros públicos, propiedades o campos, aplique el atributo <xref:System.Runtime.Serialization.IgnoreDataMemberAttribute> a ese miembro.  
  
## <a name="inheritance"></a>Herencia  

 Los tipos no marcados (tipos sin el atributo <xref:System.Runtime.Serialization.DataContractAttribute>) pueden heredar de los tipos que tienen este atributo; sin embargo, no es posible el caso inverso: los tipos con el atributo no pueden heredar de los tipos no marcados. Esta regla se aplica principalmente para garantizar la compatibilidad con el código escrito en versiones anteriores de .NET Framework.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Runtime.Serialization.IgnoreDataMemberAttribute>
- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.DataMemberAttribute>
- <xref:System.Xml.Serialization.XmlSerializer>
- [Tipos admitidos por el serializador de contratos de datos](types-supported-by-the-data-contract-serializer.md)
