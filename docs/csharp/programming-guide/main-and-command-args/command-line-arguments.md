---
title: Argumentos de la línea de comandos (Guía de programación de C#)
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments [C#]
ms.assetid: 0e597e0d-ea7a-41ba-a38a-0198122f3c26
ms.openlocfilehash: a55e40a4a4880c39c74186c55b0886e06dc33bcb
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44083954"
---
# <a name="command-line-arguments-c-programming-guide"></a>Argumentos de la línea de comandos (Guía de programación de C#)
Puede enviar argumentos al método `Main` definiéndolo de una de las siguientes maneras:  
  
 [!code-csharp[csProgGuideMain#2](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/command-line-arguments_1.cs)]  
  
 [!code-csharp[csProgGuideMain#3](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/command-line-arguments_2.cs)]  
  
> [!NOTE]
>  Para habilitar los argumentos de la línea de comandos en el método `Main` de una aplicación de Windows Forms, modifique manualmente la firma de `Main` en program.cs. El código generado por el Diseñador de Windows Forms crea un `Main` sin ningún parámetro de entrada. También puede usar <xref:System.Environment.CommandLine%2A?displayProperty=nameWithType> o <xref:System.Environment.GetCommandLineArgs%2A?displayProperty=nameWithType> para tener acceso a los argumentos de la línea de comandos desde cualquier punto en una consola o aplicación Windows.  
  
 El parámetro del método `Main` es una matriz <xref:System.String> que representa los argumentos de la línea de comandos. Normalmente, para determinar si hay argumentos, se prueba la propiedad `Length`; por ejemplo:  
  
 [!code-csharp[csProgGuideMain#4](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/command-line-arguments_3.cs)]  
  
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
  
 Para obtener más información, consulte <xref:System.Int64.Parse%2A> y <xref:System.Convert>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo usar argumentos de la línea de comandos en una aplicación de consola. La aplicación toma un argumento en tiempo de ejecución, lo convierte en un entero y calcula el factorial del número. Si no se proporciona ningún argumento, la aplicación emite un mensaje en el que se explica el uso correcto del programa.  
  
 Para compilar y ejecutar la aplicación desde un símbolo del sistema, siga estos pasos:  
  
1.  Pegue el siguiente código en cualquier editor de texto y guarde el archivo como archivo de texto con el nombre `Factorial.cs`.  
  
     [!code-csharp[csProgGuideMain#16](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/command-line-arguments_4.cs)]  
  
2.  En la pantalla **Inicio** o en el menú **Inicio**, abra una ventana del **símbolo del sistema para desarrolladores** de Visual Studio y navegue hasta la carpeta que contiene el archivo que acaba de crear.  
  
3.  Escriba el siguiente comando para compilar la aplicación.  
  
     `csc Factorial.cs`  
  
     Si la aplicación no tiene ningún error de compilación, se creará un archivo ejecutable denominado `Factorial.exe`.  
  
4.  Escriba el siguiente comando para calcular el factorial de 3:  
  
     `Factorial 3`  
  
5.  El comando genera este resultado: `The factorial of 3 is 6.`  
  
> [!NOTE]
>  Al ejecutar una aplicación en Visual Studio, puede especificar argumentos de la línea de comandos en la [Página Depuración, Diseñador de proyectos](/visualstudio/ide/reference/debug-page-project-designer).  
  
 Para ver más ejemplos sobre cómo usar los argumentos de la línea de comandos, vea [How to: Create and Use Assemblies Using the Command Line](../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-and-use-assemblies-using-the-command-line.md) (Cómo: Crear y usar ensamblados mediante la línea de comandos).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Environment?displayProperty=nameWithType>  
- [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
- [Main() y argumentos de la línea de comandos](../../../csharp/programming-guide/main-and-command-args/index.md)  
- [Cómo: Mostrar argumentos de la línea de comandos](../../../csharp/programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)  
- [Cómo: Obtener acceso a argumentos de la línea de comandos utilizando foreach](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)  
- [Valores devueltos de Main()](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)  
- [Clases](../../../csharp/programming-guide/classes-and-structs/classes.md)
