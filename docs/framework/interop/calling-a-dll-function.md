---
title: "Calling a DLL Function | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "unmanaged functions, calling"
  - "unmanaged functions"
  - "COM interop, platform invoke"
  - "platform invoke, calling unmanaged functions"
  - "interoperation with unmanaged code, platform invoke"
  - "DLL functions"
ms.assetid: 113646de-7ea0-4f0e-8df0-c46dab3e8733
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Calling a DLL Function
Aunque las llamadas a funciones no administradas de archivos DLL son prácticamente idénticas a las llamadas a cualquier otro código administrado, hay diferencias que pueden hacer que las funciones de archivos DLL parezcan complicadas en un principio.  En esta sección se proporcionan temas que describen algunos de las cuestiones menos frecuentes relacionados con las llamadas.  
  
 Las estructuras que se devuelven desde llamadas de invocación de plataforma deben ser tipos de datos que tienen la misma representación en código administrado y no administrado.  Esos tipos se denominan *tipos que pueden transferirse en bloque de bits* porque no necesitan conversión \(vea [Blittable and Non\-Blittable Types](../../../docs/framework/interop/blittable-and-non-blittable-types.md)\).  Para llamar a una función que tiene una estructura que no puede transferirse en bloque de bits como tipo de valor devuelto, se puede definir un tipo auxiliar que puede transferirse en bloque de bits del mismo tamaño que el tipo que no puede transferirse en bloque de bits y convertir los datos después de que la función vuelva.  
  
## En esta sección  
 [Pasar estructuras](../../../docs/framework/interop/passing-structures.md)  
 Identifica las cuestiones relacionados con el paso de estructuras de datos con una distribución predefinida.  
  
 [Funciones de devolución de llamada](../../../docs/framework/interop/callback-functions.md)  
 Proporciona la información básica sobre las funciones de devolución de llamada.  
  
 [Cómo: Implementar funciones de devolución de llamada](../../../docs/framework/interop/how-to-implement-callback-functions.md)  
 Describe la forma de implementar funciones de devolución de llamada en código administrado.  
  
## Secciones relacionadas  
 [Consuming Unmanaged DLL Functions](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)  
 Describe cómo llamar a funciones no administradas de archivos DLL mediante invocación de plataforma.  
  
 [Marshaling Data with Platform Invoke](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)  
 Se describe cómo declarar parámetros de método y pasar argumentos a funciones que exportan bibliotecas no administradas.