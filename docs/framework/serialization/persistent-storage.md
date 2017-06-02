---
title: "Almacenamiento persistente | Microsoft Docs"
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
  - "serialización binaria, almacenamiento persistente"
  - "almacenamiento persistente"
  - "serialización, almacenamiento persistente"
ms.assetid: b112c0dd-93e2-4eef-908d-5963f80bab65
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Almacenamiento persistente
Es a menudo necesario almacenar el valor de los campos de un objeto en el disco y a continuación, más tarde, recuperar estos datos.Aunque esto es fácil de lograr sin confiar en la serialización, este enfoque es a menudo embarazoso y propenso a errores y se vuelve progresivamente más complejo al necesitar realizar el seguimiento de una jerarquía de objetos.Imagine escribir una aplicación empresarial grande, que contiene miles de objetos, y tener que escribir el código para guardar y restaurar los campos y propiedades a y desde el disco para cada objeto.La serialización proporciona un mecanismo conveniente para lograr este objetivo.  
  
 Common Language Runtime administra cómo los objetos están almacenados en memoria y proporcionan un mecanismo de la serialización automatizado utilizando [la reflexión](../../../docs/framework/reflection-and-codedom/reflection.md).Cuando se serializa un objeto, el nombre de la clase, el ensamblado y todos los miembros de datos de la instancia de clase se escribe en el almacenamiento.Los objetos almacenan a menudo referencias a otras instancias en variables miembro.Cuando se serializa la clase, las pistas de motor de serialización hacen referencia a los objetos, ya serializados, para asegurarse de que no se serializa el mismo objeto más de una vez.La arquitectura de la serialización proporcionada correctamente con [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] administra automáticamente gráficos de objetos y referencias circulares.El único requisito colocado en gráficos de objetos es que todos los objetos, hechos referencia por el objeto serializado, también se deben marcar como [Serializable](frlrfSystemSerializableAttributeClassTopic) \(para obtener más información, vea [Serialización de Basic](../../../docs/framework/serialization/basic-serialization.md)\).Si no se hace esto, se producirá una excepción cuando el serializador intente serializar el objeto sin marca.  
  
 Cuando se deserializa la clase serializada, se vuelve a crear la clase y se restauran los valores de todos los miembros de datos automáticamente.  
  
## Vea también  
 [Conceptos de la serialización](../../../docs/framework/serialization/serialization-concepts.md)   
 [Remote Objects](http://msdn.microsoft.com/es-es/515686e6-0a8d-42f7-8188-73abede57c58)   
 [Serialización de SOAP y XML](../../../docs/framework/serialization/xml-and-soap-serialization.md)