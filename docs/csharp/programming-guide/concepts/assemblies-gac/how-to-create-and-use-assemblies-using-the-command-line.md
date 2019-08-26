---
title: Procedimiento para crear y usar ensamblados mediante la línea de comandos (C#)
ms.date: 07/20/2015
ms.assetid: 408ddce3-89e3-4e12-8353-34a49beeb72b
ms.openlocfilehash: 0a8db22a05d834d15f6e6b7f049f59f86bc1fe1d
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2019
ms.locfileid: "69595969"
---
# <a name="how-to-create-and-use-assemblies-using-the-command-line-c"></a>Procedimiento para crear y usar ensamblados mediante la línea de comandos (C#)
Un ensamblado, o una biblioteca de vínculos dinámicos (DLL), se vincula al programa en tiempo de ejecución. Para ilustrar la creación y uso de una DLL, considere el siguiente escenario:  
  
- `MathLibrary.DLL`: el archivo de biblioteca que contiene los métodos que se van a llamar en tiempo de ejecución. En este ejemplo, la DLL contiene dos métodos, `Add` y `Multiply`.  
  
- `Add`: el archivo de origen que contiene el método `Add`. Devuelve la suma de sus parámetros. La clase `AddClass` que contiene el método `Add` es un miembro del espacio de nombres `UtilityMethods`.  
  
- `Mult`: el código fuente que contiene el método `Multiply`. Devuelve el producto de sus parámetros. La clase `MultiplyClass` que contiene el método `Multiply` también es un miembro del espacio de nombres `UtilityMethods`.  
  
- `TestCode`: el archivo que contiene el método `Main`. Usa los métodos en el archivo DLL para calcular la suma y el producto de los argumentos de tiempo de ejecución.  
  
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
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../../index.md)
- [Ensamblados de .NET](../../../../standard/assembly/index.md)
- [Creación de una clase para contener funciones de archivos DLL](../../../../framework/interop/creating-a-class-to-hold-dll-functions.md)
