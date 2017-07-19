---
title: "Controlar la serializaci&#243;n y la deserializaci&#243;n con SerializationBinder | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ba8dcecf-acc7-467c-939d-021bbac797d4
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Controlar la serializaci&#243;n y la deserializaci&#243;n con SerializationBinder
Durante la serialización, un formateador transmite la información necesaria para crear una instancia de un objeto con el tipo y la versión correctos.  Por lo general, esta información incluye el nombre de tipo completo y el nombre de ensamblado del objeto.  De forma predeterminada, la deserialización usa esta información para crear una instancia de un objeto idéntico.  Puede que algunos usuarios tengan que controlar qué clase desean serializar y deserializar, bien porque la clase original no exista en el equipo que realiza la deserialización, porque la clase original se haya movido entre los ensamblados, o bien porque sea necesaria una versión diferente de la clase en el servidor y en el cliente.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Uso del enlazador de serialización](../../../../docs/framework/wcf/samples/usage-of-serialization-binder.md).  
  
> [!WARNING]
>  Esta funcionalidad solo está disponible al usar <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> o <xref:System.Runtime.Serialization.NetDataContractSerializer>.  
  
## Usar SerializationBinder  
 <xref:System.Runtime.Serialization.SerializationBinder> es una clase abstracta usada para controlar los tipos reales empleados durante la serialización y la deserialización.  Para controlar los tipos usados durante la serialización y la deserialización, derive una clase de <xref:System.Runtime.Serialization.SerializationBinder> e invalide los métodos <xref:System.Runtime.Serialization.SerializationBinder.BindToName%2A> System.String, System.String)?qualifyHint=False&autoUpgrade=True y <xref:System.Runtime.Serialization.SerializationBinder.BindToType%2A> System.String)?qualifyHint=False&autoUpgrade=True.  El método <xref:System.Runtime.Serialization.SerializationBinder.BindToName%2A> System.String, System.String)?qualifyHint=False&autoUpgrade=True toma una clase <xref:System.Type> y devuelve un nombre de tipo y ensamblado.  El método <xref:System.Runtime.Serialization.SerializationBinder.BindToType%2A> System.String)?qualifyHint=False&autoUpgrade=True toma un nombre de tipo y ensamblado y devuelve una clase <xref:System.Type>.  
  
## Vea también  
 [Serialización y deserialización](../../../../docs/framework/wcf/feature-details/serialization-and-deserialization.md)   
 [Uso del enlazador de serialización](../../../../docs/framework/wcf/samples/usage-of-serialization-binder.md)