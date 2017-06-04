---
title: "C&#243;mo: Utilizar bloques Finally | Microsoft Docs"
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
  - "ArgumentOutOfRangeException (clase)"
  - "excepciones, bloques finally"
  - "excepciones, bloques Try/Catch"
  - "bloques finally"
  - "bloques Try/Catch"
ms.assetid: 4b9c0137-04af-4468-91d1-b9014df8ddd2
caps.latest.revision: 9
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 7
---
# C&#243;mo: Utilizar bloques Finally
Cuando se produce una excepción, se detiene la ejecución y da el control al controlador de excepciones más cercano.  A menudo, esto significa que no se ejecutan líneas de código que se espera que se llamen siempre.  Siempre se debe ejecutar cierta limpieza de recursos, como el cierre de un archivo, incluso si se produce una excepción.  Para lograr esto, se puede usar un bloque Finally.  Los bloques Finally se ejecutan siempre, independientemente de si se produce una excepción o no.  
  
 En el siguiente ejemplo de código se utiliza un bloque try\/catch para detectar una excepción <xref:System.ArgumentOutOfRangeException>.  El método `Main` crea dos matrices e intenta copiar una en la otra.  La acción genera una **ArgumentOutOfRangeException** y el error se escribe en la consola.  El bloque Finally se ejecuta, sea cual sea el resultado de la acción de copia.  
  
## Ejemplo  
 [!code-cpp[CodeTryCatchFinallyExample#3](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeTryCatchFinallyExample/CPP/source2.cpp#3)]
 [!code-csharp[CodeTryCatchFinallyExample#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeTryCatchFinallyExample/CS/source2.cs#3)]
 [!code-vb[CodeTryCatchFinallyExample#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeTryCatchFinallyExample/VB/source2.vb#3)]  
  
## Vea también  
 [Cómo: Utilizar el bloque Try\/Catch para detectar excepciones](../../../docs/standard/exceptions/how-to-use-the-try-catch-block-to-catch-exceptions.md)   
 [Cómo: Iniciar excepciones explícitamente](../../../docs/standard/exceptions/how-to-explicitly-throw-exceptions.md)   
 [Cómo: Crear excepciones definidas por el usuario](../../../docs/standard/exceptions/how-to-create-user-defined-exceptions.md)   
 [Fundamentos del control de excepciones](../../../docs/standard/exceptions/exception-handling-fundamentals.md)