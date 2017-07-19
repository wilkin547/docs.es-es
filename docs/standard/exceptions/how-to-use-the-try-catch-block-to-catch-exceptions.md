---
title: "C&#243;mo: Utilizar el bloque Try/Catch para detectar excepciones | Microsoft Docs"
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
  - "excepciones, bloques try/catch"
  - "bloques Try"
  - "bloques Try/Catch"
  - "bloques catch"
ms.assetid: a3ce6dfd-1f64-471b-8ad8-8cfaf406275d
caps.latest.revision: 9
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# C&#243;mo: Utilizar el bloque Try/Catch para detectar excepciones
Coloque las secciones del código que pueden producir excepciones en un bloque Try y el código que controla excepciones en un bloque Catch.  El bloque Catch es una serie de instrucciones que comienzan con la palabra clave **catch** seguida por un tipo de excepción y la acción que se debe tomar.  
  
> [!NOTE]
>  Prácticamente cualquier línea de código puede originar una excepción, especialmente las excepciones que produce el propio Common Language Runtime, como <xref:System.OutOfMemoryException> y <xref:System.StackOverflowException>.  La mayoría de las aplicaciones no tienen que encargarse de estas excepciones, pero se debe ser consciente de esta posibilidad al escribir bibliotecas que van a utilizar otros usuarios.  Para obtener sugerencias de cuándo establecer el código en un bloque Try, vea [Procedimientos recomendados para controlar excepciones](../../../docs/standard/exceptions/best-practices-for-exceptions.md).  
  
 En el ejemplo de código siguiente se usa un bloque try\/catch para detectar una posible excepción.  El método `Main` contiene un bloque Try con una instrucción **StreamReader** que abre un archivo de datos denominado `data.txt` y escribe una cadena del archivo.  Después del bloque Try hay un bloque Catch que detecta cualquier excepción que resulte del bloque Try.  
  
## Ejemplo  
 [!code-cpp[CatchException#3](../../../samples/snippets/cpp/VS_Snippets_CLR/CatchException/CPP/catchexception2.cpp#3)]
 [!code-csharp[CatchException#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CatchException/CS/catchexception2.cs#3)]
 [!code-vb[CatchException#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CatchException/VB/catchexception2.vb#3)]  
  
 Este ejemplo ilustra una instrucción Catch básica que detectará cualquier excepción.  Por lo general, se recomienda, cuando se esté programando, detectar un tipo de excepción específico en lugar de utilizar la instrucción Catch básica.  Para obtener información sobre la detección de excepciones específicas, vea [Utilizar excepciones específicas en un bloque Catch](../../../docs/standard/exceptions/how-to-use-specific-exceptions-in-a-catch-block.md).  
  
## Vea también  
 [Cómo: Utilizar excepciones específicas en un bloque Catch](../../../docs/standard/exceptions/how-to-use-specific-exceptions-in-a-catch-block.md)   
 [Cómo: Iniciar excepciones explícitamente](../../../docs/standard/exceptions/how-to-explicitly-throw-exceptions.md)   
 [Cómo: Crear excepciones definidas por el usuario](../../../docs/standard/exceptions/how-to-create-user-defined-exceptions.md)   
 [Cómo: Utilizar bloques Finally](../../../docs/standard/exceptions/how-to-use-finally-blocks.md)   
 [Fundamentos del control de excepciones](../../../docs/standard/exceptions/exception-handling-fundamentals.md)