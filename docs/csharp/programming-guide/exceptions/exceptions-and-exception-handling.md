---
redirect_url: /dotnet/articles/csharp/programming-guide/exceptions/
caps.handback.revision: 33
---
# Excepciones y control de excepciones (Gu&#237;a de programaci&#243;n de C#)
Las características de control de excepciones del lenguaje C\# proporcionan una manera de afrontar cualquier situación inesperada o excepcional que se presente mientras se ejecuta un programa.  El control de excepciones utiliza las palabras clave `try`, `catch` y `finally` para intentar realizar acciones que podrían plantear problemas, controlar errores cuando considere que sea razonable y limpiar los recursos después.  Pueden generar excepciones Common Language Runtime \(CLR\), .NET Framework, las bibliotecas de otros fabricantes o el código de aplicación.  Las excepciones se crean mediante la palabra clave `throw`.  
  
 En muchos casos, puede que una excepción no la produzca un método que el código ha llamado directamente, sino otro método que aparece más adelante en la pila de llamadas.  Cuando esto sucede, CLR desenredará la pila a fin de buscar un método con un bloque `catch` para el tipo de excepción específico y ejecutará el primer bloque `catch` de este tipo que encuentre.  Si no encuentra ningún bloque `catch` adecuado en la pila de llamadas, finalizará el proceso y mostrará un mensaje al usuario.  
  
 En este ejemplo, el método hace una prueba para realizar una división por cero y detecta el error.  Sin el control de excepciones, este programa finalizaría con un error **DivideByZeroException no controlado**.  
  
 [!code-cs[csProgGuideExceptions#18](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exceptions-and-exception-handling_1.cs)]  
  
## Información general sobre excepciones  
 Las excepciones tienen las propiedades siguientes:  
  
-   Las excepciones son tipos que se derivan en última instancia de `System.Exception`.  
  
-   Utilice un bloque `try` alrededor de las instrucciones que puedan generar excepciones.  
  
-   Cuando se produce una excepción dentro del bloque `try`, el flujo de control salta al primer controlador de excepciones asociado que se encuentre en cualquier parte de la pila de llamadas.  En C\#, la palabra clave `catch` se utiliza para definir un controlador de excepciones.  
  
-   Si no hay un controlador de excepciones para una excepción determinada, el programa deja de ejecutarse y presenta un mensaje de error.  
  
-   No detecte una excepción a menos que pueda controlarla y dejar la aplicación con un estado conocido.  Si detecta una excepción `System.Exception`, vuelva a producirla mediante la palabra clave `throw` al final del bloque `catch`.  
  
-   Si un bloque `catch` define una variable de excepción, puede utilizar dicho bloque para obtener más información sobre el tipo de excepción que se ha producido.  
  
-   Un programa que utiliza la palabra clave `throw` puede generar explícitamente excepciones.  
  
-   Los objetos de excepción contienen información detallada sobre el error, tal como el estado de la pila de llamadas y una descripción de texto del error.  
  
-   El código de un bloque `finally` se ejecuta aunque se produzca una excepción.  Use un bloque `finally` para liberar recursos, por ejemplo, para cerrar las secuencias o archivos que se abrieron en el bloque `try`.  
  
-   Las excepciones administradas de .NET Framework se implementan sobre el mecanismo de control de excepciones estructurado de Win32.  Para obtener más información, vea [Control de excepciones estructurado](/visual-cpp/cpp/structured-exception-handling-c-cpp) y [A Crash Course on the Depths of Win32 Structured Exception Handling](http://go.microsoft.com/fwlink/?LinkId=119654).  
  
## Secciones relacionadas  
 Consulte los temas siguientes para obtener más información sobre las excepciones y el control de excepciones:  
  
-   [Utilizar excepciones](../../../csharp/programming-guide/exceptions/using-exceptions.md)  
  
-   [Control de excepciones](../../../csharp/programming-guide/exceptions/exception-handling.md)  
  
-   [Crear y producir excepciones](../../../csharp/programming-guide/exceptions/creating-and-throwing-exceptions.md)  
  
-   [Excepciones generadas por el compilador](../../../csharp/programming-guide/exceptions/compiler-generated-exceptions.md)  
  
-   [Cómo: Controlar una excepción mediante Try y Catch](../../../csharp/programming-guide/exceptions/how-to-handle-an-exception-using-try-catch.md)  
  
-   [Cómo: Ejecutar código de limpieza mediante finally](../../../csharp/programming-guide/exceptions/how-to-execute-cleanup-code-using-finally.md)  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 <xref:System.SystemException>   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [throw](../../../csharp/language-reference/keywords/throw.md)   
 [try\-catch](../../../csharp/language-reference/keywords/try-catch.md)   
 [try\-finally](../../../csharp/language-reference/keywords/try-finally.md)   
 [try\-catch\-finally](../../../csharp/language-reference/keywords/try-catch-finally.md)   
 [Excepciones](../Topic/Handling%20and%20Throwing%20Exceptions.md)   
 [Jerarquía de excepciones](../Topic/Exception%20Hierarchy.md)   
 [Escritura de código confiable de .NET](http://go.microsoft.com/fwlink/?LinkId=112400)   
 [Minidumps para Excepciones Específicas](http://go.microsoft.com/fwlink/?LinkId=112408)