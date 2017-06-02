---
title: "C&#243;mo: Iniciar excepciones expl&#237;citamente | Microsoft Docs"
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
  - "excepciones, iniciar"
  - "excepciones, bloques Try/Catch"
  - "FileNotFoundException (clase)"
  - "iniciar implícitamente excepciones"
  - "bloques Try/Catch"
ms.assetid: 72bdd157-caa9-4478-9ee3-cb4500b84528
caps.latest.revision: 10
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# C&#243;mo: Iniciar excepciones expl&#237;citamente
Una excepción se puede producir de manera explícita mediante la instrucción `throw`.  También se puede producir de nuevo una excepción detectada mediante la instrucción `throw`.  Cuando se escribe código, resulta muy recomendable agregar información a una excepción que se produce de nuevo para proporcionar más información durante el proceso de depuración.  
  
 En el ejemplo de código siguiente se usa un bloque try\/catch para detectar una posible excepción <xref:System.IO.FileNotFoundException>.  Después del bloque Try hay un bloque Catch que detecta <xref:System.IO.FileNotFoundException> y escribe un mensaje en la consola si no se encuentra el archivo de datos.  La siguiente instrucción es una instrucción Throw que produce una nueva excepción <xref:System.IO.FileNotFoundException> y agrega información de texto a la excepción.  
  
## Ejemplo  
 [!code-csharp[Exception.Throwing#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Exception.Throwing/CS/throw.cs#1)]
 [!code-vb[Exception.Throwing#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Exception.Throwing/VB/throw.vb#1)]  
  
## Vea también  
 [Cómo: Utilizar el bloque Try\/Catch para detectar excepciones](../../../docs/standard/exceptions/how-to-use-the-try-catch-block-to-catch-exceptions.md)   
 [Cómo: Utilizar excepciones específicas en un bloque Catch](../../../docs/standard/exceptions/how-to-use-specific-exceptions-in-a-catch-block.md)   
 [Cómo: Utilizar bloques Finally](../../../docs/standard/exceptions/how-to-use-finally-blocks.md)   
 [Fundamentos del control de excepciones](../../../docs/standard/exceptions/exception-handling-fundamentals.md)