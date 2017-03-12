---
title: "Argumentos de la l&#237;nea de comandos (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "argumentos de la línea de comandos [C#]"
ms.assetid: 0e597e0d-ea7a-41ba-a38a-0198122f3c26
caps.latest.revision: 27
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 27
---
# Argumentos de la l&#237;nea de comandos (Gu&#237;a de programaci&#243;n de C#)
Puede enviar argumentos al método `Main` definiendo el método en una de las siguientes maneras:  
  
 [!code-cs[csProgGuideMain#2](../../../csharp/programming-guide/inside-a-program/codesnippet/csharp/command-line-arguments_1.cs)]  
  
 [!code-cs[csProgGuideMain#3](../../../csharp/programming-guide/inside-a-program/codesnippet/csharp/command-line-arguments_2.cs)]  
  
> [!NOTE]
>  Para habilitar argumentos de la línea de comandos en el método `Main` de una aplicación de formularios Windows Forms, debe modificar manualmente la firma de `Main` en program.cs.  El código generado por el diseñador de Windows Forms crea un elemento `Main` sin parámetros de entrada.  También puede utilizar <xref:System.Environment.CommandLine%2A?displayProperty=fullName> o <xref:System.Environment.GetCommandLineArgs%2A?displayProperty=fullName> a fin de obtener acceso a los argumentos de la línea de comandos desde cualquier punto en una aplicación de consola o para Windows.  
  
 El parámetro del método `Main` es una matriz de tipo <xref:System.String> que representa los argumentos de la línea de comandos.  Normalmente se comprueba si existen argumentos mediante la propiedad `Length`, por ejemplo:  
  
 [!code-cs[csProgGuideMain#4](../../../csharp/programming-guide/inside-a-program/codesnippet/csharp/command-line-arguments_3.cs)]  
  
 También se pueden convertir los argumentos de tipo string en tipos numéricos mediante la clase <xref:System.Convert> el método `Parse`.  Por ejemplo, la instrucción siguiente convierte `string` en un número `long` mediante el método <xref:System.Int64.Parse%2A>:  
  
```  
long num = Int64.Parse(args[0]);  
```  
  
 También se puede utilizar el tipo `long` de C\#, que equivale a `Int64`:  
  
```  
long num = long.Parse(args[0]);  
```  
  
 Igualmente, es posible usar el método `ToInt64` de la clase `Convert` para lograr el mismo objetivo:  
  
```  
long num = Convert.ToInt64(s);  
```  
  
 Para obtener más información, vea <xref:System.Int64.Parse%2A> y <xref:System.Convert>.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo utilizar argumentos de la línea de comandos en una aplicación de consola.  La aplicación toma un argumento en tiempo de ejecución, lo convierte en un número entero y calcula el valor factorial del número.  Si no se proporciona ningún argumento, la aplicación emite un mensaje en el que se describe la forma de utilizarlo correctamente.  
  
 Para compilar y ejecutar la aplicación desde un símbolo del sistema, siga estos pasos:  
  
1.  Pegue el código siguiente en cualquier editor de texto y, a continuación, guarde el archivo como archivo de texto con el nombre `Factorial.cs`.  
  
     [!code-cs[csProgGuideMain#16](../../../csharp/programming-guide/inside-a-program/codesnippet/csharp/command-line-arguments_4.cs)]  
  
2.  Desde la pantalla **Iniciar** o desde el menú **Iniciar**, abra una ventana **Símbolo del sistema para desarrolladores** de Visual Studio y después navegue hasta la carpeta que contiene el archivo que acaba de crear.  
  
3.  Especifique el comando siguiente para compilar la aplicación.  
  
     `csc Factorial.cs`  
  
     Si la aplicación no tiene ningún error de compilación, se crea un archivo ejecutable denominado `Factorial.exe`.  
  
4.  Escriba el comando siguiente para calcular el factorial de 3:  
  
     `Factorial 3`  
  
5.  El comando produce este resultado: `The factorial of 3 is 6.`  
  
> [!NOTE]
>  Si ejecuta una aplicación en Visual Studio, puede especificar argumentos de la línea de comandos en [Página Depuración, Diseñador de proyectos](/visual-studio/ide/reference/debug-page-project-designer).  
  
 Para obtener más ejemplos sobre cómo utilizar los argumentos de la línea de comandos, vea [Cómo: Crear y utilizar ensamblados mediante la línea de comandos](../Topic/How%20to:%20Create%20and%20Use%20Assemblies%20Using%20the%20Command%20Line%20\(C%23%20and%20Visual%20Basic\).md).  
  
## Vea también  
 <xref:System.Environment?displayProperty=fullName>   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Main\(\) y argumentos de la línea de comandos](../../../csharp/programming-guide/main-and-command-args/main-and-command-line-arguments.md)   
 [Cómo: Mostrar argumentos de la línea de comandos](../../../csharp/programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)   
 [Cómo: Obtener acceso a argumentos de la línea de comandos utilizando foreach](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)   
 [Valores devueltos Main\(\)](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)   
 [Clases](../../../csharp/programming-guide/classes-and-structs/classes.md)