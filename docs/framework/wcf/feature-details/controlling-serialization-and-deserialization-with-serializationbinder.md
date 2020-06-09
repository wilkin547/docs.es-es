---
title: Controlar la serialización y la deserialización con SerializationBinder
ms.date: 03/30/2017
ms.assetid: ba8dcecf-acc7-467c-939d-021bbac797d4
ms.openlocfilehash: 1101a3caf2a033b4dbbc5f45737f187c58adbef2
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595575"
---
# <a name="controlling-serialization-and-deserialization-with-serializationbinder"></a>Controlar la serialización y la deserialización con SerializationBinder
Durante la serialización, un formateador transmite la información necesaria para crear una instancia de un objeto con el tipo y la versión correctos. Por lo general, esta información incluye el nombre de tipo completo y el nombre de ensamblado del objeto. De forma predeterminada, la deserialización usa esta información para crear una instancia de un objeto idéntico. Puede que algunos usuarios tengan que controlar qué clase desean serializar y deserializar, bien porque la clase original no exista en el equipo que realiza la deserialización, porque la clase original se haya movido entre los ensamblados, o bien porque sea necesaria una versión diferente de la clase en el servidor y en el cliente. Para obtener más información, vea [uso del enlazador de serialización](../samples/usage-of-serialization-binder.md).  
  
> [!WARNING]
> Esta funcionalidad solo está disponible al usar <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> o <xref:System.Runtime.Serialization.NetDataContractSerializer>.  
  
## <a name="using-serializationbinder"></a>Usar SerializationBinder  
 <xref:System.Runtime.Serialization.SerializationBinder> es una clase abstracta usada para controlar los tipos reales empleados durante la serialización y la deserialización. Para controlar los tipos usados durante la serialización y la deserialización, derive una clase de <xref:System.Runtime.Serialization.SerializationBinder> e invalide los métodos <xref:System.Runtime.Serialization.SerializationBinder.BindToName(System.Type,System.String@,System.String@)> y <xref:System.Runtime.Serialization.SerializationBinder.BindToType(System.String,System.String)>. El método <xref:System.Runtime.Serialization.SerializationBinder.BindToName(System.Type,System.String@,System.String@)> toma una clase <xref:System.Type> y devuelve un nombre de tipo y ensamblado. El método <xref:System.Runtime.Serialization.SerializationBinder.BindToType(System.String,System.String)> toma un nombre de tipo y ensamblado y devuelve una clase <xref:System.Type>.  
  
## <a name="see-also"></a>Vea también

- [Serialización y deserialización](serialization-and-deserialization.md)
- [Uso del enlazador de serialización](../samples/usage-of-serialization-binder.md)
