---
title: "Control de excepciones (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "control de excepciones [C#], acerca del control de excepciones"
  - "excepciones [C#], controlar"
ms.assetid: b4e4ecf2-b907-4e58-891f-2563762258e9
caps.latest.revision: 24
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 24
---
# Control de excepciones (Gu&#237;a de programaci&#243;n de C#)
Los programadores de C\# usan bloques [try](../../../csharp/language-reference/keywords/try-catch.md) para separar el código al que puede afectar una excepción.  Los bloques [catch](../../../csharp/language-reference/keywords/try-catch.md) asociados se utilizan para controlar las excepciones resultantes.  Un bloque [finally](../../../csharp/language-reference/keywords/try-finally.md) contiene código que se ejecuta con independencia de que se produzca o no una excepción en el bloque `try`, como liberar recursos asignados en el bloque `try`.  Un bloque `try` requiere tener asociados uno o más bloques `catch` o un bloque `finally`, o bien ambas opciones.  
  
 En los ejemplos siguientes se muestra una instrucción `try-catch`, una instrucción `try-finally` y una instrucción `try-catch-finally`.  
  
 [!code-cs[csProgGuideExceptions#6](../../../csharp/programming-guide/exceptions/codesnippet/csharp/exception-handling_1.cs)]  
  
 [!code-cs[csProgGuideExceptions#7](../../../csharp/programming-guide/exceptions/codesnippet/csharp/exception-handling_2.cs)]  
  
 [!code-cs[csProgGuideExceptions#8](../../../csharp/programming-guide/exceptions/codesnippet/csharp/exception-handling_3.cs)]  
  
 Un bloque `try` sin un bloque `catch` o `finally` produce un error del compilador.  
  
## Bloques Catch  
 Un bloque `catch` puede especificar el tipo de excepción que se detectará.  La especificación de tipo se denomina *filtro de excepción*.  El tipo de excepción debe derivarse de <xref:System.Exception>.  En general, no especifique <xref:System.Exception> como filtro de excepción a menos que sepa cómo controlar todas las excepciones que puedan producirse en el bloque `try` o bien haya incluido una instrucción [throw](../../../csharp/language-reference/keywords/throw.md) al final del bloque `catch`.  
  
 Se pueden encadenar varios bloques `catch` con filtros de excepción diferentes.  Los bloques `catch` se evalúan de arriba abajo en el código, pero solo se ejecuta un bloque `catch` para cada excepción iniciada.  Se ejecutará el primer bloque `catch` que especifica el tipo exacto o una clase base de la excepción que se haya producido.  Si ningún bloque `catch` especifica un filtro coincidente de la excepción, un bloque `catch` que no tiene un filtro se selecciona, si hay alguno presente en la instrucción.  Es importante colocar los bloques `catch` con los tipos de excepción más concretos \(es decir, más derivados\) en primer lugar.  
  
 Debería detectar excepciones cuando se cumplen las condiciones siguientes:  
  
-   Comprende claramente por qué puede producirse la excepción y puede implementar una recuperación concreta, como pedir al usuario que escriba un nuevo nombre de archivo cuando se detecta un objeto <xref:System.IO.FileNotFoundException>.  
  
-   Pueda crear y producir una excepción nueva más específica.  
  
     [!code-cs[csProgGuideExceptions#9](../../../csharp/programming-guide/exceptions/codesnippet/csharp/exception-handling_4.cs)]  
  
-   Desea controlar parcialmente una excepción antes de pasarla para realizar un control adicional.  En el ejemplo siguiente, se usa un bloque `catch` para agregar una entrada a un registro de errores antes de volver a producir la excepción.  
  
     [!code-cs[csProgGuideExceptions#10](../../../csharp/programming-guide/exceptions/codesnippet/csharp/exception-handling_5.cs)]  
  
## Bloques Finally  
 Un bloque `finally` permite limpiar las acciones que se realizan en un bloque `try`.  Si está presente, el bloque `finally` se ejecuta en último lugar, después del bloque `try` y cualquier bloque `catch` coincidente.  Un bloque `finally` se ejecuta siempre, sin tener en cuenta si se produce una excepción o si se encuentra un bloque `catch` que coincida con el tipo de excepción.  
  
 El bloque `finally` se puede utilizar para liberar recursos como secuencias de archivos, conexiones de base de datos y controladores de gráficos sin esperar a que el recolector de elementos no utilizados del motor en tiempo de ejecución finalice los objetos.  Para obtener más información, consulte [using \(Instrucción\)](../../../csharp/language-reference/keywords/using-statement.md).  
  
 En el ejemplo siguiente, el bloque `finally` se usa para cerrar un archivo que se abre en el bloque `try`.  Observe que se comprueba el estado del identificador del archivo antes de cerrarlo.  Si el bloque `try` no puede abrir el archivo, el identificador de archivos seguirá teniendo el valor `null` y el bloque `finally` no intenta cerrarlo.  Como alternativa, si el archivo se abre correctamente en el bloque `try`, el bloque `finally` cierra el archivo abierto.  
  
 [!code-cs[csProgGuideExceptions#11](../../../csharp/programming-guide/exceptions/codesnippet/csharp/exception-handling_6.cs)]  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Excepciones y control de excepciones](../../../csharp/programming-guide/exceptions/exceptions-and-exception-handling.md)   
 [try\-catch](../../../csharp/language-reference/keywords/try-catch.md)   
 [try\-finally](../../../csharp/language-reference/keywords/try-finally.md)   
 [try\-catch\-finally](../../../csharp/language-reference/keywords/try-catch-finally.md)   
 [using \(Instrucción\)](../../../csharp/language-reference/keywords/using-statement.md)