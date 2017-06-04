---
title: "C&#243;mo: Crear excepciones definidas por el usuario | Microsoft Docs"
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
  - "excepciones, ejemplos"
  - "excepciones, definidas por el usuario"
  - "excepciones definidas por el usuario"
ms.assetid: 25819a5a-f915-4fc8-b924-a76915674e04
caps.latest.revision: 10
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# C&#243;mo: Crear excepciones definidas por el usuario
Si desea que los usuarios puedan distinguir, mediante programación, ciertas condiciones de error de otras, puede crear sus propias excepciones definidas por el usuario.  .NET Framework proporciona una jerarquía de clases de excepción que, en última instancia, derivan de la clase base <xref:System.Exception>.  Cada una de estas clases define una excepción específica, por lo que en muchos casos sólo hay que detectar la excepción.  También se pueden crear clases de excepción personalizadas derivándolas de la clase <xref:System.Exception>.  
  
 Cuando se creen excepciones personalizadas, es recomendable finalizar el nombre de la clase de la excepción definida por el usuario con la palabra "Excepción". También se recomienda implementar los tres constructores comunes recomendados, como se muestra en el ejemplo siguiente.  
  
> [!NOTE]
>  En los casos en los que se use la comunicación remota, se debe garantizar que los metadatos de cualquier excepción definida por el usuario están disponibles en el servidor \(destinatario de la llamada\) y en el cliente \(el objeto proxy o llamador\).  Por ejemplo, el código que llama a un método de otro dominio de aplicación debe poder encontrar el ensamblado que contiene una excepción producida por una llamada remota.  Para obtener más información, vea [Procedimientos recomendados para controlar excepciones](../../../docs/standard/exceptions/best-practices-for-exceptions.md).  
  
 En el ejemplo siguiente, se deriva una nueva clase de excepción, `EmployeeListNotFoundException`, de <xref:System.Exception>.  Se definen tres constructores en la clase, cada uno con parámetros diferentes.  
  
## Ejemplo  
 [!code-cpp[dg_exceptionDesign#14](../../../samples/snippets/cpp/VS_Snippets_CLR/dg_exceptionDesign/cpp/example2.cpp#14)]
 [!code-csharp[dg_exceptionDesign#14](../../../samples/snippets/csharp/VS_Snippets_CLR/dg_exceptionDesign/cs/example2.cs#14)]
 [!code-vb[dg_exceptionDesign#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/dg_exceptionDesign/vb/example2.vb#14)]  
  
## Vea también  
 [Cómo: Utilizar el bloque Try\/Catch para detectar excepciones](../../../docs/standard/exceptions/how-to-use-the-try-catch-block-to-catch-exceptions.md)   
 [Cómo: Utilizar excepciones específicas en un bloque Catch](../../../docs/standard/exceptions/how-to-use-specific-exceptions-in-a-catch-block.md)   
 [Procedimientos recomendados para excepciones](../../../docs/standard/exceptions/best-practices-for-exceptions.md)   
 [Fundamentos del control de excepciones](../../../docs/standard/exceptions/exception-handling-fundamentals.md)