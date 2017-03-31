---
title: "Argumentos de la línea de comandos (Guía de programación de C#) | Microsoft Docs"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- command-line arguments [C#]
ms.assetid: 0e597e0d-ea7a-41ba-a38a-0198122f3c26
caps.latest.revision: 27
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
ms.openlocfilehash: 4034f1575321c94f003a12a83df617d4a0d50702
ms.lasthandoff: 03/13/2017

---
# <a name="command-line-arguments-c-programming-guide"></a>Argumentos de la línea de comandos (Guía de programación de C#)
Puede enviar argumentos al método `Main` definiéndolo de una de las siguientes maneras:  
  
 [!code-cs[csProgGuideMain#2](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/command-line-arguments_1.cs)]  
  
 [!code-cs[csProgGuideMain#3](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/command-line-arguments_2.cs)]  
  
> [!NOTE]
>  Para habilitar los argumentos de la línea de comandos en el método `Main` de una aplicación de Windows Forms, modifique manualmente la firma de `Main` en program.cs. El código generado por el Diseñador de Windows Forms crea un `Main` sin ningún parámetro de entrada. También puede usar <xref:System.Environment.CommandLine%2A?displayProperty=fullName> o <xref:System.Environment.GetCommandLineArgs%2A?displayProperty=fullName> para obtener acceso a los argumentos de la línea de comandos desde cualquier punto de una consola o aplicación de Windows.  
  
 El parámetro del método `Main` es una matriz <xref:System.String> que representa los argumentos de la línea de comandos. Normalmente, para determinar si hay argumentos, se prueba la propiedad `Length`; por ejemplo:  
  
 [!code-cs[csProgGuideMain#4](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/command-line-arguments_3.cs)]  
  
 También puede convertir los argumentos de cadena en tipos numéricos mediante la clase <xref:System.Convert> o el método `Parse`. Por ejemplo, la siguiente instrucción convierte la `string` en un número `long` mediante el método <xref:System.Int64.Parse%2A>:  
  
```  
long num = Int64.Parse(args[0]);  
```  
  
 También se puede usar el tipo de C# `long`, que tiene como alias `Int64`:  
  
```  
long num = long.Parse(args[0]);  
```  
  
 También puede usar el método `ToInt64` de la clase `Convert` para hacer lo mismo:  
  
```  
long num = Convert.ToInt64(s);  
```  
  
 Para obtener más información, vea <xref:System.Int64.Parse%2A> y <xref:System.Convert>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo usar argumentos de la línea de comandos en una aplicación de consola. La aplicación toma un argumento en tiempo de ejecución, lo convierte en un entero y calcula el factorial del número. Si no se proporciona ningún argumento, la aplicación emite un mensaje en el que se explica el uso correcto del programa.  
  
 Para compilar y ejecutar la aplicación desde un símbolo del sistema, siga estos pasos:  
  
1.  Pegue el siguiente código en cualquier editor de texto y guarde el archivo como archivo de texto con el nombre `Factorial.cs`.  
  
     [!code-cs[csProgGuideMain#16](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/command-line-arguments_4.cs)]  
  
2.  En la pantalla **Inicio** o en el menú **Inicio**, abra una ventana del **símbolo del sistema para desarrolladores** de Visual Studio y navegue hasta la carpeta que contiene el archivo que acaba de crear.  
  
3.  Escriba el siguiente comando para compilar la aplicación.  
  
     `csc Factorial.cs`  
  
     Si la aplicación no tiene ningún error de compilación, se creará un archivo ejecutable denominado `Factorial.exe`.  
  
4.  Escriba el siguiente comando para calcular el factorial de 3:  
  
     `Factorial 3`  
  
5.  El comando genera este resultado: `The factorial of 3 is 6.`  
  
> [!NOTE]
>  Al ejecutar una aplicación en Visual Studio, puede especificar argumentos de la línea de comandos en la [Página Depuración, Diseñador de proyectos](https://docs.microsoft.com/visualstudio/ide/reference/debug-page-project-designer).  
  
 Para ver más ejemplos sobre cómo usar los argumentos de la línea de comandos, vea [How to: Create and Use Assemblies Using the Command Line](http://msdn.microsoft.com/library/70f65026-3687-4e9c-ab79-c18b97dd8be4) (Cómo: Crear y usar ensamblados mediante la línea de comandos).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Environment?displayProperty=fullName>   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Main() y argumentos de línea de comandos](../../../csharp/programming-guide/main-and-command-args/index.md)   
 [Cómo: Mostrar argumentos de la línea de comandos](../../../csharp/programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)   
 [Cómo: Obtener acceso a argumentos de la línea de comandos utilizando Foreach](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)   
 [Valores devueltos de Main()](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)   
 [Clases](../../../csharp/programming-guide/classes-and-structs/classes.md)
