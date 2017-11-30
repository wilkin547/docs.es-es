---
title: "Cómo: Crear y usar ensamblados desde la línea de comandos (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 408ddce3-89e3-4e12-8353-34a49beeb72b
caps.latest.revision: "4"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d59988ec4899b4115d8d0fd7172e0c8ff8802378
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-and-use-assemblies-using-the-command-line-c"></a><span data-ttu-id="4de6d-102">Cómo: Crear y usar ensamblados desde la línea de comandos (C#)</span><span class="sxs-lookup"><span data-stu-id="4de6d-102">How to: Create and Use Assemblies Using the Command Line (C#)</span></span>
<span data-ttu-id="4de6d-103">Un ensamblado, o una biblioteca de vínculos dinámicos (DLL), se vincula al programa en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4de6d-103">An assembly, or a dynamic linking library (DLL), is linked to your program at run time.</span></span> <span data-ttu-id="4de6d-104">Para ilustrar la creación y uso de una DLL, considere el siguiente escenario:</span><span class="sxs-lookup"><span data-stu-id="4de6d-104">To demonstrate building and using a DLL, consider the following scenario:</span></span>  
  
-   <span data-ttu-id="4de6d-105">`MathLibrary.DLL`: el archivo de biblioteca que contiene los métodos que se van a llamar en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4de6d-105">`MathLibrary.DLL`: The library file that contains the methods to be called at run time.</span></span> <span data-ttu-id="4de6d-106">En este ejemplo, la DLL contiene dos métodos, `Add` y `Multiply`.</span><span class="sxs-lookup"><span data-stu-id="4de6d-106">In this example, the DLL contains two methods, `Add` and `Multiply`.</span></span>  
  
-   <span data-ttu-id="4de6d-107">`Add`: el archivo de origen que contiene el método `Add`.</span><span class="sxs-lookup"><span data-stu-id="4de6d-107">`Add`: The source file that contains the method `Add`.</span></span> <span data-ttu-id="4de6d-108">Devuelve la suma de sus parámetros.</span><span class="sxs-lookup"><span data-stu-id="4de6d-108">It returns the sum of its parameters.</span></span> <span data-ttu-id="4de6d-109">La clase `AddClass` que contiene el método `Add` es un miembro del espacio de nombres `UtilityMethods`.</span><span class="sxs-lookup"><span data-stu-id="4de6d-109">The class `AddClass` that contains the method `Add` is a member of the namespace `UtilityMethods`.</span></span>  
  
-   <span data-ttu-id="4de6d-110">`Mult`: el código fuente que contiene el método `Multiply`.</span><span class="sxs-lookup"><span data-stu-id="4de6d-110">`Mult`: The source code that contains the method `Multiply`.</span></span> <span data-ttu-id="4de6d-111">Devuelve el producto de sus parámetros.</span><span class="sxs-lookup"><span data-stu-id="4de6d-111">It returns the product of its parameters.</span></span> <span data-ttu-id="4de6d-112">La clase `MultiplyClass` que contiene el método `Multiply` también es un miembro del espacio de nombres `UtilityMethods`.</span><span class="sxs-lookup"><span data-stu-id="4de6d-112">The class `MultiplyClass` that contains the method `Multiply` is also a member of the namespace `UtilityMethods`.</span></span>  
  
-   <span data-ttu-id="4de6d-113">`TestCode`: el archivo que contiene el método `Main`.</span><span class="sxs-lookup"><span data-stu-id="4de6d-113">`TestCode`: The file that contains the `Main` method.</span></span> <span data-ttu-id="4de6d-114">Usa los métodos en el archivo DLL para calcular la suma y el producto de los argumentos de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4de6d-114">It uses the methods in the DLL file to calculate the sum and the product of the run-time arguments.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4de6d-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4de6d-115">Example</span></span>  
  
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
  
 <span data-ttu-id="4de6d-116">Este archivo contiene el algoritmo que usa los métodos de la DLL, `Add` y `Multiply`.</span><span class="sxs-lookup"><span data-stu-id="4de6d-116">This file contains the algorithm that uses the DLL methods, `Add` and `Multiply`.</span></span> <span data-ttu-id="4de6d-117">Empieza analizando los argumentos especificados en la línea de comandos, `num1` y `num2`.</span><span class="sxs-lookup"><span data-stu-id="4de6d-117">It starts with parsing the arguments entered from the command line, `num1` and `num2`.</span></span> <span data-ttu-id="4de6d-118">Después, calcula la suma mediante el método `Add` de la clase `AddClass`, y el producto mediante el método `Multiply` de la clase `MultiplyClass`.</span><span class="sxs-lookup"><span data-stu-id="4de6d-118">Then it calculates the sum by using the `Add` method on the `AddClass` class, and the product by using the `Multiply` method on the `MultiplyClass` class.</span></span>  
  
 <span data-ttu-id="4de6d-119">Observe que la directiva `using` al principio del archivo permite usar los nombres de clase no completos para hacer referencia a los métodos de la DLL en tiempo de compilación, como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="4de6d-119">Notice that the `using` directive at the beginning of the file enables you to use the unqualified class names to reference the DLL methods at compile time, as follows:</span></span>  
  
```csharp  
MultiplyClass.Multiply(num1, num2);  
```  
  
 <span data-ttu-id="4de6d-120">En caso contrario, deberá usar los nombres completos, como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="4de6d-120">Otherwise, you have to use the fully qualified names, as follows:</span></span>  
  
```csharp  
UtilityMethods.MultiplyClass.Multiply(num1, num2);  
```  
  
## <a name="execution"></a><span data-ttu-id="4de6d-121">Execution</span><span class="sxs-lookup"><span data-stu-id="4de6d-121">Execution</span></span>  
 <span data-ttu-id="4de6d-122">Para ejecutar el programa, escriba el nombre del archivo EXE, seguido de dos números, de esta forma:</span><span class="sxs-lookup"><span data-stu-id="4de6d-122">To run the program, enter the name of the EXE file, followed by two numbers, as follows:</span></span>  
  
 `TestCode 1234 5678`  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4de6d-123">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="4de6d-123">Compiling the Code</span></span>  
 <span data-ttu-id="4de6d-124">Para generar el archivo `MathLibrary.DLL`, compile los dos archivos `Add` y `Mult` mediante la línea de comandos siguiente.</span><span class="sxs-lookup"><span data-stu-id="4de6d-124">To build the file `MathLibrary.DLL`, compile the two files `Add` and `Mult` by using the following command line.</span></span>  
  
```csharp  
csc /target:library /out:MathLibrary.DLL Add.cs Mult.cs  
```  
  
 <span data-ttu-id="4de6d-125">La opción del compilador [/target:library](../../../../csharp/language-reference/compiler-options/target-library-compiler-option.md) indica al compilador que genere un archivo DLL en lugar de un archivo EXE.</span><span class="sxs-lookup"><span data-stu-id="4de6d-125">The [/target:library](../../../../csharp/language-reference/compiler-options/target-library-compiler-option.md) compiler option tells the compiler to output a DLL instead of an EXE file.</span></span> <span data-ttu-id="4de6d-126">Se usa la opción del compilador [/out](../../../../csharp/language-reference/compiler-options/out-compiler-option.md) seguida de un nombre de archivo para especificar el nombre del archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="4de6d-126">The [/out](../../../../csharp/language-reference/compiler-options/out-compiler-option.md) compiler option followed by a file name is used to specify the DLL file name.</span></span> <span data-ttu-id="4de6d-127">De lo contrario, el compilador usa el primer archivo (`Add.cs`) como el nombre de la DLL.</span><span class="sxs-lookup"><span data-stu-id="4de6d-127">Otherwise, the compiler uses the first file (`Add.cs`) as the name of the DLL.</span></span>  
  
 <span data-ttu-id="4de6d-128">Para compilar el archivo ejecutable, `TestCode.exe`, use la siguiente línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="4de6d-128">To build the executable file, `TestCode.exe`, use the following command line:</span></span>  
  
```csharp  
csc /out:TestCode.exe /reference:MathLibrary.DLL TestCode.cs  
```  
  
 <span data-ttu-id="4de6d-129">La opción del compilador **/out** indica al compilador que genere un archivo EXE y especifica el nombre del archivo de salida (`TestCode.exe`).</span><span class="sxs-lookup"><span data-stu-id="4de6d-129">The **/out** compiler option tells the compiler to output an EXE file and specifies the name of the output file (`TestCode.exe`).</span></span> <span data-ttu-id="4de6d-130">Esta opción del compilador es opcional.</span><span class="sxs-lookup"><span data-stu-id="4de6d-130">This compiler option is optional.</span></span> <span data-ttu-id="4de6d-131">La opción del compilador [/reference](../../../../csharp/language-reference/compiler-options/reference-compiler-option.md) especifica el archivo o archivos DLL que usa este programa.</span><span class="sxs-lookup"><span data-stu-id="4de6d-131">The [/reference](../../../../csharp/language-reference/compiler-options/reference-compiler-option.md) compiler option specifies the DLL file or files that this program uses.</span></span> <span data-ttu-id="4de6d-132">Para obtener más información, vea [/reference](../../../../csharp/language-reference/compiler-options/reference-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="4de6d-132">For more information, see [/reference](../../../../csharp/language-reference/compiler-options/reference-compiler-option.md).</span></span>  
  
 <span data-ttu-id="4de6d-133">Para más información sobre la compilación desde la línea de comandos, vea [Compilación de línea de comandos con csc.exe](../../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="4de6d-133">For more information about building from the command line, see [Command-line Building With csc.exe](../../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4de6d-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="4de6d-134">See Also</span></span>  
 [<span data-ttu-id="4de6d-135">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="4de6d-135">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)  
 <span data-ttu-id="4de6d-136">[Assemblies and the Global Assembly Cache (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md) (Ensamblados y caché global de ensamblados [C#])</span><span class="sxs-lookup"><span data-stu-id="4de6d-136">[Assemblies and the Global Assembly Cache (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md)</span></span>  
 [<span data-ttu-id="4de6d-137">Creación de una clase para contener funciones de archivos DLL</span><span class="sxs-lookup"><span data-stu-id="4de6d-137">Creating a Class to Hold DLL Functions</span></span>](../../../../framework/interop/creating-a-class-to-hold-dll-functions.md)
