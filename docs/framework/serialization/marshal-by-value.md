---
title: "Calcular las referencias por valor | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "serialización binaria, calcular las referencias por valor"
  - "objetos de cálculo de las referencias por valor"
  - "serialización, calcular las referencias por valor"
ms.assetid: ee91e8f0-92e0-4732-8015-d17dee154be1
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Calcular las referencias por valor
Los objetos solo son válidos en el dominio de aplicación donde se crean.Se producirá un error en cualquier intento para pasar el objeto como un parámetro o devolverlo como resultado a menos que el objeto derive de [MarshalByRefObject](frlrfSystemMarshalByRefObjectClassTopic) o se marque como [Serializable](frlrfSystemSerializableAttributeClassTopic).Si el objeto se marca como **Serializable**, se serializará el objeto automáticamente, se transportará de un dominio de aplicación al otro y, a continuación, se deserializará para generar una copia exacta del objeto en el segundo dominio de aplicación.Este proceso se conoce normalmente como valor por cálculo de referencias.  
  
 Cuando un objeto deriva de **MarshalByRefObject**, una referencia a objeto se pasa de un dominio de aplicación a otro, en lugar del propio objeto.También puede marcar un objeto que deriva de **MarshalByRefObject** como **Serializable**.Cuando este objeto se utiliza con comunicación remota, el formateador responsable para la serialización preconfigurada con un selector de suplente \([SurrogateSelector](frlrfSystemRuntimeSerializationSurrogateSelectorClassTopic)\) toma control del proceso de serialización y reemplaza todos los objetos derivados de [MarshalByRefObject](frlrfSystemMarshalByRefObjectClassTopic) con un proxy.Sin [SurrogateSelector](frlrfSystemRuntimeSerializationSurrogateSelectorClassTopic) en lugar, la arquitectura de la serialización sigue las reglas de la serialización estándar descritas en [Pasos en el Proceso de la Serialización](../../../docs/framework/serialization/steps-in-the-serialization-process.md).  
  
## Vea también  
 [Conceptos de la serialización](../../../docs/framework/serialization/serialization-concepts.md)   
 [Remote Objects](http://msdn.microsoft.com/es-es/515686e6-0a8d-42f7-8188-73abede57c58)   
 [Serialización de SOAP y XML](../../../docs/framework/serialization/xml-and-soap-serialization.md)