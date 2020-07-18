---
title: Controlar la serialización y la deserialización con SerializationBinder
ms.date: 07/14/2020
ms.assetid: ba8dcecf-acc7-467c-939d-021bbac797d4
ms.openlocfilehash: 5a7d0bf2aabfcdf789a77cf0fcfeb26357575806
ms.sourcegitcommit: 2543a78be6e246aa010a01decf58889de53d1636
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/17/2020
ms.locfileid: "86444487"
---
# <a name="controlling-serialization-and-deserialization-with-serializationbinder"></a>Controlar la serialización y la deserialización con SerializationBinder

> [!WARNING]
> <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>no es seguro y ***no*** se puede proteger. Para obtener más información, vea la [Guía de seguridad BinaryFormatter](../../../standard/serialization/binaryformatter-security-guide.md).

Durante la serialización, un formateador transmite la información necesaria para crear una instancia de un objeto con el tipo y la versión correctos. Por lo general, esta información incluye el nombre de tipo completo y el nombre de ensamblado del objeto. De forma predeterminada, la deserialización usa esta información para crear una instancia de un objeto idéntico. Puede que algunos usuarios tengan que controlar qué clase desean serializar y deserializar, bien porque la clase original no exista en el equipo que realiza la deserialización, porque la clase original se haya movido entre los ensamblados, o bien porque sea necesaria una versión diferente de la clase en el servidor y en el cliente. Para obtener más información, vea [uso del enlazador de serialización](../samples/usage-of-serialization-binder.md).  
  
> [!WARNING]
> Esta funcionalidad solo está disponible al usar <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> o <xref:System.Runtime.Serialization.NetDataContractSerializer>.  
  
## <a name="using-serializationbinder"></a>Usar SerializationBinder  
 <xref:System.Runtime.Serialization.SerializationBinder> es una clase abstracta usada para controlar los tipos reales empleados durante la serialización y la deserialización. Para controlar los tipos usados durante la serialización y la deserialización, derive una clase de <xref:System.Runtime.Serialization.SerializationBinder> e invalide los métodos <xref:System.Runtime.Serialization.SerializationBinder.BindToName(System.Type,System.String@,System.String@)> y <xref:System.Runtime.Serialization.SerializationBinder.BindToType(System.String,System.String)>. El método <xref:System.Runtime.Serialization.SerializationBinder.BindToName(System.Type,System.String@,System.String@)> toma una clase <xref:System.Type> y devuelve un nombre de tipo y ensamblado. El método <xref:System.Runtime.Serialization.SerializationBinder.BindToType(System.String,System.String)> toma un nombre de tipo y ensamblado y devuelve una clase <xref:System.Type>.  
  
## <a name="see-also"></a>Consulte también

- [Serialización y deserialización](serialization-and-deserialization.md)
- [Uso del enlazador de serialización](../samples/usage-of-serialization-binder.md)
