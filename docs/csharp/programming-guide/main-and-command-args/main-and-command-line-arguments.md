---
redirect_url: /dotnet/articles/csharp/programming-guide/main-and-command-args/
caps.handback.revision: 30
---
# Main() y argumentos de l&#237;nea de comandos (Gu&#237;a de programaci&#243;n de C#)
El método `Main` es el punto de entrada de una aplicación de consola de C\# o una aplicación para Windows.  \(Las bibliotecas y los servicios no requieren un método `Main` como punto de entrada.\)  Cuando se inicia la aplicación, el método `Main` es el primer método que se invoca.  
  
 En un programa de C\#, sólo puede haber un punto de entrada.  Si tiene más de una clase con un método `Main`, debe compilar el programa con la opción del compilador **\/main** para especificar qué método `Main` se va a utilizar como punto de entrada.  Para obtener más información, vea [\/main \(Specify Location of Main Method\)](../../../csharp/language-reference/compiler-options/main-compiler-option.md).  
  
 [!code-cs[csProgGuideMain#17](../../../csharp/programming-guide/inside-a-program/codesnippet/csharp/main-and-command-line-ar_1.cs)]  
  
## Información general  
  
-   El método `Main` es el punto de entrada de un programa .exe, donde se inicia y finaliza el control del programa.  
  
-   `Main` se declara dentro de una clase o un struct.  `Main` debe ser [estático](../../../csharp/language-reference/keywords/static.md) y no debe ser [público](../../../csharp/language-reference/keywords/public.md).  \(En el ejemplo anterior, recibe el acceso predeterminado de [private](../../../csharp/language-reference/keywords/private.md).\) No es necesario que el struct o la clase envolvente sean de tipo estático.  
  
-   `Main` puede tener un tipo de valor devuelto `void` o `int`.  
  
-   El método `Main` se puede declarar con o sin un parámetro `string[]` que contenga los argumentos de la línea de comandos.  Si se utiliza [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)] para crear aplicaciones de formularios Windows Forms, puede agregar el parámetro manualmente o bien utilizar la clase <xref:System.Environment> para obtener los argumentos de la línea de comandos.  Los parámetros se leen como argumentos de la línea de comandos cero\- se indizan. A diferencia de c y C\+\+, el nombre del programa no se trata como el primer argumento de la línea de comandos.  
  
## En esta sección  
  
-   [Argumentos de la línea de comandos](../../../csharp/programming-guide/main-and-command-args/command-line-arguments.md)  
  
-   [Cómo: Mostrar argumentos de la línea de comandos](../../../csharp/programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)  
  
-   [Cómo: Obtener acceso a argumentos de la línea de comandos utilizando foreach](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)  
  
-   [Valores devueltos Main\(\)](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 [Command\-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Métodos](../../../csharp/programming-guide/classes-and-structs/methods.md)   
 [Dentro de un programa de C\#](../../../csharp/programming-guide/inside-a-program/index.md)   
 [\<paveover\>C\# Sample Applications](http://msdn.microsoft.com/es-es/9a9d7aaa-51d3-4224-b564-95409b0f3e15)