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
# <a name="how-to-create-and-use-assemblies-using-the-command-line-c"></a><span data-ttu-id="8f4f8-102">Procedimiento para crear y usar ensamblados mediante la línea de comandos (C#)</span><span class="sxs-lookup"><span data-stu-id="8f4f8-102">How to: Create and Use Assemblies Using the Command Line (C#)</span></span>
<span data-ttu-id="8f4f8-103">Un ensamblado, o una biblioteca de vínculos dinámicos (DLL), se vincula al programa en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="8f4f8-103">An assembly, or a dynamic linking library (DLL), is linked to your program at run time.</span></span> <span data-ttu-id="8f4f8-104">Para ilustrar la creación y uso de una DLL, considere el siguiente escenario:</span><span class="sxs-lookup"><span data-stu-id="8f4f8-104">To demonstrate building and using a DLL, consider the following scenario:</span></span>  
  
- <span data-ttu-id="8f4f8-105">`MathLibrary.DLL`: el archivo de biblioteca que contiene los métodos que se van a llamar en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="8f4f8-105">`MathLibrary.DLL`: The library file that contains the methods to be called at run time.</span></span> <span data-ttu-id="8f4f8-106">En este ejemplo, la DLL contiene dos métodos, `Add` y `Multiply`.</span><span class="sxs-lookup"><span data-stu-id="8f4f8-106">In this example, the DLL contains two methods, `Add` and `Multiply`.</span></span>  
  
- <span data-ttu-id="8f4f8-107">`Add`: el archivo de origen que contiene el método `Add`.</span><span class="sxs-lookup"><span data-stu-id="8f4f8-107">`Add`: The source file that contains the method `Add`.</span></span> <span data-ttu-id="8f4f8-108">Devuelve la suma de sus parámetros.</span><span class="sxs-lookup"><span data-stu-id="8f4f8-108">It returns the sum of its parameters.</span></span> <span data-ttu-id="8f4f8-109">La clase `AddClass` que contiene el método `Add` es un miembro del espacio de nombres `UtilityMethods`.</span><span class="sxs-lookup"><span data-stu-id="8f4f8-109">The class `AddClass` that contains the method `Add` is a member of the namespace `UtilityMethods`.</span></span>  
  
- <span data-ttu-id="8f4f8-110">`Mult`: el código fuente que contiene el método `Multiply`.</span><span class="sxs-lookup"><span data-stu-id="8f4f8-110">`Mult`: The source code that contains the method `Multiply`.</span></span> <span data-ttu-id="8f4f8-111">Devuelve el producto de sus parámetros.</span><span class="sxs-lookup"><span data-stu-id="8f4f8-111">It returns the product of its parameters.</span></span> <span data-ttu-id="8f4f8-112">La clase `MultiplyClass` que contiene el método `Multiply` también es un miembro del espacio de nombres `UtilityMethods`.</span><span class="sxs-lookup"><span data-stu-id="8f4f8-112">The class `MultiplyClass` that contains the method `Multiply` is also a member of the namespace `UtilityMethods`.</span></span>  
  
- <span data-ttu-id="8f4f8-113">`TestCode`: el archivo que contiene el método `Main`.</span><span class="sxs-lookup"><span data-stu-id="8f4f8-113">`TestCode`: The file that contains the `Main` method.</span></span> <span data-ttu-id="8f4f8-114">Usa los métodos en el archivo DLL para calcular la suma y el producto de los argumentos de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="8f4f8-114">It uses the methods in the DLL file to calculate the sum and the product of the run-time arguments.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8f4f8-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8f4f8-115">Example</span></span>  
  
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
  
 <span data-ttu-id="8f4f8-116">Este archivo contiene el algoritmo que usa los métodos de la DLL, `Add` y `Multiply`.</span><span class="sxs-lookup"><span data-stu-id="8f4f8-116">This file contains the algorithm that uses the DLL methods, `Add` and `Multiply`.</span></span> <span data-ttu-id="8f4f8-117">Empieza analizando los argumentos especificados en la línea de comandos, `num1` y `num2`.</span><span class="sxs-lookup"><span data-stu-id="8f4f8-117">It starts with parsing the arguments entered from the command line, `num1` and `num2`.</span></span> <span data-ttu-id="8f4f8-118">Después, calcula la suma mediante el método `Add` de la clase `AddClass`, y el producto mediante el método `Multiply` de la clase `MultiplyClass`.</span><span class="sxs-lookup"><span data-stu-id="8f4f8-118">Then it calculates the sum by using the `Add` method on the `AddClass` class, and the product by using the `Multiply` method on the `MultiplyClass` class.</span></span>  
  
 <span data-ttu-id="8f4f8-119">Observe que la directiva `using` al principio del archivo permite usar los nombres de clase no completos para hacer referencia a los métodos de la DLL en tiempo de compilación, como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="8f4f8-119">Notice that the `using` directive at the beginning of the file enables you to use the unqualified class names to reference the DLL methods at compile time, as follows:</span></span>  
  
```csharp  
MultiplyClass.Multiply(num1, num2);  
```  
  
 <span data-ttu-id="8f4f8-120">En caso contrario, deberá usar los nombres completos, como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="8f4f8-120">Otherwise, you have to use the fully qualified names, as follows:</span></span>  
  
```csharp  
UtilityMethods.MultiplyClass.Multiply(num1, num2);  
```  
  
## <a name="execution"></a><span data-ttu-id="8f4f8-121">Execution</span><span class="sxs-lookup"><span data-stu-id="8f4f8-121">Execution</span></span>  
 <span data-ttu-id="8f4f8-122">Para ejecutar el programa, escriba el nombre del archivo EXE, seguido de dos números, de esta forma:</span><span class="sxs-lookup"><span data-stu-id="8f4f8-122">To run the program, enter the name of the EXE file, followed by two numbers, as follows:</span></span>  
  
 `TestCode 1234 5678`  
  
## <a name="see-also"></a><span data-ttu-id="8f4f8-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="8f4f8-123">See also</span></span>

- [<span data-ttu-id="8f4f8-124">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="8f4f8-124">C# Programming Guide</span></span>](../../index.md)
- [<span data-ttu-id="8f4f8-125">Ensamblados de .NET</span><span class="sxs-lookup"><span data-stu-id="8f4f8-125">Assemblies in .NET</span></span>](../../../../standard/assembly/index.md)
- [<span data-ttu-id="8f4f8-126">Creación de una clase para contener funciones de archivos DLL</span><span class="sxs-lookup"><span data-stu-id="8f4f8-126">Creating a Class to Hold DLL Functions</span></span>](../../../../framework/interop/creating-a-class-to-hold-dll-functions.md)
