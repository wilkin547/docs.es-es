---
title: "Serializaci&#243;n selectiva | Microsoft Docs"
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
  - "serialización binaria, serialización selectiva"
  - "serialización, serialización selectiva"
ms.assetid: 39c56635-95d2-4afd-aff1-b022e7649bb3
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Serializaci&#243;n selectiva
Una clase contiene a menudo campos que no se deberían serializar.Por ejemplo, suponga que una clase almacena un Identificador de subproceso en una variable miembro.Cuando se deserializa la clase, el subproceso almacenó el Id. para cuando se serializara, la clase ya no se podría estar ejecutando; serializar así este valor no tiene sentido.Puede evitar que las variables miembro se serialicen marcándolos con el atributo [NonSerialized](frlrfSystemNonSerializedAttributeClassTopic) como sigue.  
  
```csharp  
[Serializable]  
public class MyObject   
{  
  public int n1;  
  [NonSerialized] public int n2;  
  public String str;  
}  
```  
  
 Si es posible, haz que un objeto pueda contener datos seguros no serializables.Si se debe serializar el objeto, aplique el atributo **NonSerialized** a campos concretos que almacena los datos confidenciales.Si no excluye estos campos de la serialización, sea consciente de que los datos que almacenan se expondrán a cualquier código que tenga el permiso para serializar.Para obtener más información sobre cómo escribir el código de serialización seguro, vea [Seguridad y Serialización](../../../docs/framework/misc/security-and-serialization.md).  
  
## Vea también  
 [Serialización binaria](../../../docs/framework/serialization/binary-serialization.md)   
 [Remote Objects](http://msdn.microsoft.com/es-es/515686e6-0a8d-42f7-8188-73abede57c58)   
 [Serialización de SOAP y XML](../../../docs/framework/serialization/xml-and-soap-serialization.md)   
 [Security and Serialization](../../../docs/framework/misc/security-and-serialization.md)