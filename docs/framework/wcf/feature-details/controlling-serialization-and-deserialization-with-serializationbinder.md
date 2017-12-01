---
title: "Controlar la serialización y la deserialización con SerializationBinder"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ba8dcecf-acc7-467c-939d-021bbac797d4
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: be5faf5e465eeacc190081c22d7bc59c3caf5825
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="controlling-serialization-and-deserialization-with-serializationbinder"></a>Controlar la serialización y la deserialización con SerializationBinder
Durante la serialización, un formateador transmite la información necesaria para crear una instancia de un objeto con el tipo y la versión correctos. Por lo general, esta información incluye el nombre de tipo completo y el nombre de ensamblado del objeto. De forma predeterminada, la deserialización usa esta información para crear una instancia de un objeto idéntico. Puede que algunos usuarios tengan que controlar qué clase desean serializar y deserializar, bien porque la clase original no exista en el equipo que realiza la deserialización, porque la clase original se haya movido entre los ensamblados, o bien porque sea necesaria una versión diferente de la clase en el servidor y en el cliente. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Uso del enlazador de serialización](../../../../docs/framework/wcf/samples/usage-of-serialization-binder.md).  
  
> [!WARNING]
>  Esta funcionalidad solo está disponible al usar <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> o <xref:System.Runtime.Serialization.NetDataContractSerializer>.  
  
## <a name="using-serializationbinder"></a>Usar SerializationBinder  
 <xref:System.Runtime.Serialization.SerializationBinder> es una clase abstracta usada para controlar los tipos reales empleados durante la serialización y la deserialización. Para controlar los tipos usados durante la serialización y la deserialización, derive una clase de <xref:System.Runtime.Serialization.SerializationBinder> e invalide los métodos <xref:System.Runtime.Serialization.SerializationBinder.BindToName(System.Type,System.String@,System.String@)> y <xref:System.Runtime.Serialization.SerializationBinder.BindToType(System.String,System.String)>. El método <xref:System.Runtime.Serialization.SerializationBinder.BindToName(System.Type,System.String@,System.String@)> toma una clase <xref:System.Type> y devuelve un nombre de tipo y ensamblado. El método <xref:System.Runtime.Serialization.SerializationBinder.BindToType(System.String,System.String)> toma un nombre de tipo y ensamblado y devuelve una clase <xref:System.Type>.  
  
## <a name="see-also"></a>Vea también  
 [Serialización y deserialización](../../../../docs/framework/wcf/feature-details/serialization-and-deserialization.md)  
 [Uso del enlazador de serialización](../../../../docs/framework/wcf/samples/usage-of-serialization-binder.md)
