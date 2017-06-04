---
title: "Utilizar controladores de excepciones filtradas por el usuario | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "excepciones, filtradas por el usuario"
  - "excepciones filtradas por el usuario"
ms.assetid: aa80d155-060d-41b4-a636-1ceb424afee8
caps.latest.revision: 10
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# Utilizar controladores de excepciones filtradas por el usuario
Actualmente, Visual Basic admite las excepciones filtradas por el usuario.  Los controladores de excepciones filtrados por el usuario detectan y controlan las excepciones basándose en requisitos que se definen para la excepción.  Estos controladores utilizan la instrucción **Catch** con la palabra clave **When**.  
  
 Esta técnica resulta útil cuando un objeto de excepción concreto corresponde a varios errores.  En este caso, normalmente, el objeto tiene una propiedad que contiene el código de error específico asociado al error.  La propiedad del código de error se puede usar en la expresión para seleccionar sólo el error concreto que se desea controlar en esa cláusula **Catch**.  
  
 El siguiente ejemplo de Visual Basic ilustra la instrucción **Catch\/When**.  
  
```  
Try  
      'Try statements.  
   Catch When Err = VBErr_ClassLoadException  
      'Catch statements.  
End Try  
```  
  
 La expresión de la cláusula definida por el usuario no tiene ningún tipo de restricción.  Si ocurre una excepción durante la ejecución de la expresión filtrada por el usuario, se descarta dicha excepción y la expresión de filtro se evalúa como False.  En este caso, el Common Language Runtime continúa buscando un controlador para la excepción actual.  
  
## Combinar las cláusulas de excepción específica y filtrada por el usuario  
 Una instrucción Catch puede contener las cláusulas de excepción específica y la filtrada por el usuario.  El motor en tiempo de ejecución prueba primero la excepción específica.  Si la excepción específica se realiza correctamente, el motor en tiempo de ejecución ejecuta el filtro de usuario.  El filtro genérico puede contener una referencia a la variable declarada en el filtro de la clase.  Tenga en cuenta que el orden de las dos cláusulas de filtro no se puede invertir.  
  
 En el siguiente ejemplo de Visual Basic se muestra la excepción específica `ClassLoadException` de la instrucción **Catch** además de la cláusula filtrada por el usuario que utiliza la palabra clave **When**.  
  
```  
Try  
      'Try statements.  
   Catch cle As ClassLoadException When cle.IsRecoverable()  
      'Catch statements.  
End Try  
```  
  
## Vea también  
 [Cómo: Utilizar el bloque Try\/Catch para detectar excepciones](../../../docs/standard/exceptions/how-to-use-the-try-catch-block-to-catch-exceptions.md)   
 [Cómo: Utilizar excepciones específicas en un bloque Catch](../../../docs/standard/exceptions/how-to-use-specific-exceptions-in-a-catch-block.md)   
 [Procedimientos recomendados para excepciones](../../../docs/standard/exceptions/best-practices-for-exceptions.md)   
 [Fundamentos del control de excepciones](../../../docs/standard/exceptions/exception-handling-fundamentals.md)