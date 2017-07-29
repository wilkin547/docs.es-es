---
title: "Cómo: Crear y usar ensamblados desde la línea de comandos (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 408ddce3-89e3-4e12-8353-34a49beeb72b
caps.latest.revision: 4
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 630a799331e03860fbee34eab6bea3bb594ef0f0
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-create-and-use-assemblies-using-the-command-line-c"></a>Cómo: Crear y usar ensamblados desde la línea de comandos (C#)
Un ensamblado, o una biblioteca de vínculos dinámicos (DLL), se vincula al programa en tiempo de ejecución. Para ilustrar la creación y uso de una DLL, considere el siguiente escenario:  
  
-   `MathLibrary.DLL`: el archivo de biblioteca que contiene los métodos que se van a llamar en tiempo de ejecución. En este ejemplo, la DLL contiene dos métodos, `Add` y `Multiply`.  
  
-   `Add`: el archivo de origen que contiene el método `Add`. Devuelve la suma de sus parámetros. La clase `AddClass` que contiene el método `Add` es un miembro del espacio de nombres `UtilityMethods`.  
  
-   `Mult`: el código fuente que contiene el método `Multiply`. Devuelve el producto de sus parámetros. La clase `MultiplyClass` que contiene el método `Multiply` también es un miembro del espacio de nombres `UtilityMethods`.  
  
-   `TestCode`: el archivo que contiene el método `Main`. Usa los métodos en el archivo DLL para calcular la suma y el producto de los argumentos de tiempo de ejecución.  
  
## <a name="example"></a>Ejemplo  
  
```csharp  
// File: Add.cs   
namespace UtilityMethods  
{  
    public class AddClass   
    {  
        public static long Add(long i, long j)   
        {   
            return (i + j);  
        }  
    }  
}  
```  
  
```csharp  
// File: Mult.cs  
namespace UtilityMethods   
{  
    public class MultiplyClass  
    {  
        public static long Multiply(long x, long y)   
        {  
            return (x * y);   
        }  
    }  
}  
```  
  
```csharp  
// File: TestCode.cs  
  
using UtilityMethods;  
  
class TestCode  
{  
    static void Main(string[] args)   
    {  
        System.Console.WriteLine("Calling methods from MathLibrary.DLL:");  
  
        if (args.Length != 2)  
        {  
            System.Console.WriteLine("Usage: TestCode <num1> <num2>");  
            return;  
        }  
  
        long num1 = long.Parse(args[0]);  
        long num2 = long.Parse(args[1]);  
  
        long sum = AddClass.Add(num1, num2);  
        long product = MultiplyClass.Multiply(num1, num2);  
  
        System.Console.WriteLine("{0} + {1} = {2}", num1, num2, sum);  
        System.Console.WriteLine("{0} * {1} = {2}", num1, num2, product);  
    }  
}  
/* Output (assuming 1234 and 5678 are entered as command-line arguments):  
    Calling methods from MathLibrary.DLL:  
    1234 + 5678 = 6912  
    1234 * 5678 = 7006652          
*/  
```  
  
 Este archivo contiene el algoritmo que usa los métodos de la DLL, `Add` y `Multiply`. Empieza analizando los argumentos especificados en la línea de comandos, `num1` y `num2`. Después, calcula la suma mediante el método `Add` de la clase `AddClass`, y el producto mediante el método `Multiply` de la clase `MultiplyClass`.  
  
 Observe que la directiva `using` al principio del archivo permite usar los nombres de clase no completos para hacer referencia a los métodos de la DLL en tiempo de compilación, como se muestra a continuación:  
  
```csharp  
MultiplyClass.Multiply(num1, num2);  
```  
  
 En caso contrario, deberá usar los nombres completos, como se muestra a continuación:  
  
```csharp  
UtilityMethods.MultiplyClass.Multiply(num1, num2);  
```  
  
## <a name="execution"></a>Execution  
 Para ejecutar el programa, escriba el nombre del archivo EXE, seguido de dos números, de esta forma:  
  
 `TestCode 1234 5678`  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para generar el archivo `MathLibrary.DLL`, compile los dos archivos `Add` y `Mult` mediante la línea de comandos siguiente.  
  
```csharp  
csc /target:library /out:MathLibrary.DLL Add.cs Mult.cs  
```  
  
 La opción del compilador [/target:library](../../../../csharp/language-reference/compiler-options/target-library-compiler-option.md) indica al compilador que genere un archivo DLL en lugar de un archivo EXE. Se usa la opción del compilador [/out](../../../../csharp/language-reference/compiler-options/out-compiler-option.md) seguida de un nombre de archivo para especificar el nombre del archivo DLL. De lo contrario, el compilador usa el primer archivo (`Add.cs`) como el nombre de la DLL.  
  
 Para compilar el archivo ejecutable, `TestCode.exe`, use la siguiente línea de comandos:  
  
```csharp  
csc /out:TestCode.exe /reference:MathLibrary.DLL TestCode.cs  
```  
  
 La opción del compilador **/out** indica al compilador que genere un archivo EXE y especifica el nombre del archivo de salida (`TestCode.exe`). Esta opción del compilador es opcional. La opción del compilador [/reference](../../../../csharp/language-reference/compiler-options/reference-compiler-option.md) especifica el archivo o archivos DLL que usa este programa. Para obtener más información, vea [/reference](../../../../csharp/language-reference/compiler-options/reference-compiler-option.md).  
  
 Para más información sobre la compilación desde la línea de comandos, vea [Compilación de línea de comandos con csc.exe](../../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../../csharp/programming-guide/index.md)   
 [Ensamblados y caché global de ensamblados (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md)   
 [Creación de una clase para contener funciones de archivos DLL](../../../../framework/interop/creating-a-class-to-hold-dll-functions.md)

