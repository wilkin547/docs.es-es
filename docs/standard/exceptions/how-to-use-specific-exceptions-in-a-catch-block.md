---
title: "C&#243;mo: Utilizar excepciones espec&#237;ficas en un bloque Catch | Microsoft Docs"
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
  - "bloques catch"
  - "excepciones, bloques Try/Catch"
  - "bloques Try/Catch"
ms.assetid: 12af9ff3-8587-4f31-90cf-6c2244e0fdae
caps.latest.revision: 9
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 7
---
# C&#243;mo: Utilizar excepciones espec&#237;ficas en un bloque Catch
Cuando se produce una excepción, asciende por la pila y se da a cada uno de los bloques Catch la oportunidad de controlarla.  El orden de las instrucciones Catch es importante.  Ponga los bloques Catch dirigidos a excepciones específicas antes de un bloque Catch de excepción general, pues de lo contrario el compilador puede emitir un error.  El bloque Catch adecuado se determina haciendo coincidir el tipo de excepción con el nombre de la excepción especificada en el bloque Catch.  Si no hay un bloque Catch específico, un bloque Catch general, si lo hay, detecta la excepción.  
  
 En el siguiente ejemplo de código se utiliza un bloque try\/catch para detectar una excepción <xref:System.InvalidCastException>.  En el ejemplo se crea una clase denominada `Employee` con una única propiedad, el nivel de empleado \(`Emlevel`\).  Un método`, PromoteEmployee`, toma un objeto e incrementa el nivel del empleado.  Se produce una **InvalidCastException** cuando se pasa una instancia de <xref:System.DateTime> al método `PromoteEmployee`.  
  
## Ejemplo  
 [!code-cpp[CatchException#2](../../../samples/snippets/cpp/VS_Snippets_CLR/CatchException/CPP/catchexception1.cpp#2)]
 [!code-csharp[CatchException#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CatchException/CS/catchexception1.cs#2)]
 [!code-vb[CatchException#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CatchException/VB/catchexception1.vb#2)]  
  
 Common Language Runtime detecta las excepciones que no detecta un bloque Catch.  Según cómo esté configurado el motor tiempo de ejecución, aparece un cuadro de diálogo de depuración o el programa se deja de ejecutar y aparece un cuadro de diálogo con información de la excepción.  Para obtener información sobre la depuración, vea [Depurar y generar perfiles de aplicaciones](../../../docs/framework/debug-trace-profile/index.md).  
  
## Vea también  
 [Cómo: Utilizar el bloque Try\/Catch para detectar excepciones](../../../docs/standard/exceptions/how-to-use-the-try-catch-block-to-catch-exceptions.md)   
 [Cómo: Iniciar excepciones explícitamente](../../../docs/standard/exceptions/how-to-explicitly-throw-exceptions.md)   
 [Cómo: Crear excepciones definidas por el usuario](../../../docs/standard/exceptions/how-to-create-user-defined-exceptions.md)   
 [Cómo: Utilizar bloques Finally](../../../docs/standard/exceptions/how-to-use-finally-blocks.md)   
 [Clase Exception y propiedades](../../../docs/standard/exceptions/exception-class-and-properties.md)   
 [Fundamentos del control de excepciones](../../../docs/standard/exceptions/exception-handling-fundamentals.md)