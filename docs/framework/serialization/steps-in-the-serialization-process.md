---
title: "Pasos en el proceso de la serializaci&#243;n | Microsoft Docs"
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
  - "serialización binaria, pasos"
  - "serialización, pasos"
ms.assetid: 4bcbc883-2a91-418f-b968-6c86a25e9737
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Pasos en el proceso de la serializaci&#243;n
Cuando se llama al método [Serialize](frlrfSystemRuntimeSerializationFormatterClassSerializeTopic) en un [formateador](frlrfSystemRuntimeSerializationFormatterClassTopic), la serialización de objetos procede según la secuencia siguiente de reglas:  
  
-   Una comprobación se realiza para determinar si el formateador tiene un selector de suplente.Si el formateador lo tiene, compruebe si el selector de suplente administra objetos del tipo determinado.Si el seleccionador administra el tipo de objeto, se llama a**ISerializable.GetObjectData** en el selector de suplente.  
  
-   Si no hay ningún selector de suplente o si no administra el tipo de objeto, se realiza una comprobación para determinar si el objeto se marca con el atributo [Serializable](frlrfSystemSerializableAttributeClassTopic).Si el objeto no está marcado, se inicia [SerializationException](frlrfSystemRuntimeSerializationSerializationExceptionClassTopic).  
  
-   Si el objeto está marcado apropiadamente, compruebe si el objeto implementa la interfaz [ISerializable](frlrfSystemRuntimeSerializationISerializableClassTopic).En caso afirmativo se llama a, [GetObjectData](frlrfSystemRuntimeSerializationISerializableClassGetObjectDataTopic) en el objeto.  
  
-   Si el objeto no implementa **ISerializable**, se utiliza la directiva de la serialización predeterminada, serializando todos los campos no marcados como [NonSerialized](frlrfSystemNonSerializedAttributeClassTopic).  
  
## Vea también  
 [Serialización binaria](../../../docs/framework/serialization/binary-serialization.md)   
 [Remote Objects](http://msdn.microsoft.com/es-es/515686e6-0a8d-42f7-8188-73abede57c58)   
 [Serialización de SOAP y XML](../../../docs/framework/serialization/xml-and-soap-serialization.md)