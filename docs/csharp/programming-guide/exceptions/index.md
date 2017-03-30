---
title: "Excepciones y control de excepciones (Guía de programación de C#) | Microsoft Docs"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- exception handling [C#]
- exceptions [C#]
- C# language, exceptions
ms.assetid: 0001887f-4fa2-47e2-8034-2819477e2344
caps.latest.revision: 33
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 95563b84f633789fb35eed64c510a11c44b3492b
ms.lasthandoff: 03/13/2017

---
# <a name="exceptions-and-exception-handling-c-programming-guide"></a>Excepciones y control de excepciones (Guía de programación de C#)
Las características de control de excepciones del lenguaje C# le ayudan a afrontar cualquier situación inesperada o excepcional que se produce cuando se ejecuta un programa. El control de excepciones usa las palabras clave `try`, `catch` y `finally` para intentar realizar acciones que pueden no completarse correctamente, para controlar errores cuando decide que es razonable hacerlo y para limpiar recursos más adelante. Las excepciones las puede generar Common Language Runtime (CLR), .NET Framework, cualquier biblioteca de terceros o el código de aplicación. Las excepciones se crean mediante el uso de la palabra clave `throw`.  
  
 En muchos casos, una excepción la puede no producir un método al que el código ha llamado directamente, sino otro método más bajo en la pila de llamadas. Cuando esto sucede, CLR desenredar la pila, busca un método con un bloque `catch` para el tipo de excepción específico y ejecuta el primer bloque `catch` que encuentra. Si no encuentra ningún bloque `catch` adecuado en cualquier parte de la pila de llamadas, finalizará el proceso y mostrará un mensaje al usuario.  
  
 En este ejemplo, un método prueba a hacer la división entre cero y detecta el error. Sin el control de excepciones, este programa finalizaría con un error **DivideByZeroException no controlada**.  
  
 [!code-cs[csProgGuideExceptions#18](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exceptions-and-exception-handling_1.cs)]  
  
## <a name="exceptions-overview"></a>Información general sobre excepciones  
 Las excepciones tienen las siguientes propiedades:  
  
-   Las excepciones son tipos que derivan en última instancia de `System.Exception`.  
  
-   Use un bloque `try` alrededor de las instrucciones que pueden producir excepciones.  
  
-   Una vez que se produce una excepción en el bloque `try`, el flujo de control salta al primer controlador de excepciones asociado que está presente en cualquier parte de la pila de llamadas. En C#, la palabra clave `catch` se utiliza para definir un controlador de excepciones.  
  
-   Si no hay ningún controlador de excepciones para una excepción determinada, el programa deja de ejecutarse con un mensaje de error.  
  
-   No detecte una excepción a menos que pueda controlarla y dejar la aplicación en un estado conocido. Si se detecta `System.Exception`, reinícielo con la palabra clave `throw` al final del bloque `catch`.  
  
-   Si un bloque `catch` define una variable de excepción, puede utilizarla para obtener más información sobre el tipo de excepción que se ha producido.  
  
-   Las excepciones puede generarlas explícitamente un programa con la palabra clave `throw`.  
  
-   Los objetos de excepción contienen información detallada sobre el error, como el estado de la pila de llamadas y una descripción de texto del error.  
  
-   El código de un bloque `finally` se ejecuta incluso si se produce una excepción. Use un bloque `finally` para liberar recursos, por ejemplo, para cerrar las secuencias o los archivos que se abrieron en el bloque `try`.  
  
-   Las excepciones administradas de .NET Framework se implementan en el mecanismo de control de excepciones estructurado de Win32. Para más información, vea [Control de excepciones estructurado (C/C++)](https://docs.microsoft.com/cpp/cpp/structured-exception-handling-c-cpp) y [A Crash Course on the Depths of Win32 Structured Exception Handling](http://go.microsoft.com/fwlink/?LinkId=119654) (Curso intensivo sobre los aspectos específicos del control de excepciones estructurado de Win32).  
  
## <a name="related-sections"></a>Secciones relacionadas  
 Vea los temas siguientes para obtener más información sobre excepciones y control de excepciones:  
  
-   [Utilizar excepciones](../../../csharp/programming-guide/exceptions/using-exceptions.md)  
  
-   [Control de excepciones](../../../csharp/programming-guide/exceptions/exception-handling.md)  
  
-   [Crear y producir excepciones](../../../csharp/programming-guide/exceptions/creating-and-throwing-exceptions.md)  
  
-   [Excepciones generadas por el compilador](../../../csharp/programming-guide/exceptions/compiler-generated-exceptions.md)  
  
-   [Control de una excepción mediante Try y Catch (Guía de programación de C#)](../../../csharp/programming-guide/exceptions/how-to-handle-an-exception-using-try-catch.md)  
  
-   [Cómo: Ejecutar código de limpieza mediante finally](../../../csharp/programming-guide/exceptions/how-to-execute-cleanup-code-using-finally.md)  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.SystemException>   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)   
 [throw](../../../csharp/language-reference/keywords/throw.md)   
 [try-catch](../../../csharp/language-reference/keywords/try-catch.md)   
 [try-finally](../../../csharp/language-reference/keywords/try-finally.md)   
 [try-catch-finally](../../../csharp/language-reference/keywords/try-catch-finally.md)   
 [Excepciones](http://msdn.microsoft.com/library/f99a1d29-a2a8-47af-9707-9909f9010735)   
 [Jerarquía de excepciones](http://msdn.microsoft.com/library/f7d68675-be06-40fb-a555-05f0c5a6f66b)   
 [Escritura segura de código .NET](http://go.microsoft.com/fwlink/?LinkId=112400)   
 [Minivolcados para excepciones concretas](http://go.microsoft.com/fwlink/?LinkId=112408)
