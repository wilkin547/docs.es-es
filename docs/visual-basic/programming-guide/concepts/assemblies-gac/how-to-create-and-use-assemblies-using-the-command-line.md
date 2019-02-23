---
title: Procedimiento Crear y usar ensamblados desde la línea de comandos (Visual Basic)
ms.date: 03/14/2018
ms.assetid: 229ff9fb-1bd1-403b-946b-526104864c60
ms.openlocfilehash: cbfccfc80c683dfd49739e680587ca40e6ca24f3
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "56746395"
---
# <a name="how-to-create-and-use-assemblies-using-the-command-line-visual-basic"></a><span data-ttu-id="9955e-102">Procedimiento Crear y usar ensamblados desde la línea de comandos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9955e-102">How to: Create and Use Assemblies Using the Command Line (Visual Basic)</span></span>
<span data-ttu-id="9955e-103">Un ensamblado, o una biblioteca de vínculos dinámicos (DLL), se vincula al programa en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9955e-103">An assembly, or a dynamic linking library (DLL), is linked to your program at run time.</span></span> <span data-ttu-id="9955e-104">Para ilustrar la creación y uso de una DLL, considere el siguiente escenario:</span><span class="sxs-lookup"><span data-stu-id="9955e-104">To demonstrate building and using a DLL, consider the following scenario:</span></span>  
  
-   <span data-ttu-id="9955e-105">`MathLibrary.DLL`: el archivo de biblioteca que contiene los métodos que se van a llamar en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9955e-105">`MathLibrary.DLL`: The library file that contains the methods to be called at run time.</span></span> <span data-ttu-id="9955e-106">En este ejemplo, la DLL contiene dos métodos, `Add` y `Multiply`.</span><span class="sxs-lookup"><span data-stu-id="9955e-106">In this example, the DLL contains two methods, `Add` and `Multiply`.</span></span>  
  
-   <span data-ttu-id="9955e-107">`Add`: el archivo de origen que contiene el método `Add`.</span><span class="sxs-lookup"><span data-stu-id="9955e-107">`Add`: The source file that contains the method `Add`.</span></span> <span data-ttu-id="9955e-108">Devuelve la suma de sus parámetros.</span><span class="sxs-lookup"><span data-stu-id="9955e-108">It returns the sum of its parameters.</span></span> <span data-ttu-id="9955e-109">La clase `AddClass` que contiene el método `Add` es un miembro del espacio de nombres `UtilityMethods`.</span><span class="sxs-lookup"><span data-stu-id="9955e-109">The class `AddClass` that contains the method `Add` is a member of the namespace `UtilityMethods`.</span></span>  
  
-   <span data-ttu-id="9955e-110">`Mult`: el código fuente que contiene el método `Multiply`.</span><span class="sxs-lookup"><span data-stu-id="9955e-110">`Mult`: The source code that contains the method `Multiply`.</span></span> <span data-ttu-id="9955e-111">Devuelve el producto de sus parámetros.</span><span class="sxs-lookup"><span data-stu-id="9955e-111">It returns the product of its parameters.</span></span> <span data-ttu-id="9955e-112">La clase `MultiplyClass` que contiene el método `Multiply` también es un miembro del espacio de nombres `UtilityMethods`.</span><span class="sxs-lookup"><span data-stu-id="9955e-112">The class `MultiplyClass` that contains the method `Multiply` is also a member of the namespace `UtilityMethods`.</span></span>  
  
-   <span data-ttu-id="9955e-113">`TestCode`: el archivo que contiene el método `Main`.</span><span class="sxs-lookup"><span data-stu-id="9955e-113">`TestCode`: The file that contains the `Main` method.</span></span> <span data-ttu-id="9955e-114">Usa los métodos en el archivo DLL para calcular la suma y el producto de los argumentos de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9955e-114">It uses the methods in the DLL file to calculate the sum and the product of the run-time arguments.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9955e-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9955e-115">Example</span></span>  
  
```vb  
' File: Add.vb   
Namespace UtilityMethods  
    Public Class AddClass  
        Public Shared Function Add(ByVal i As Long, ByVal j As Long) As Long  
            Return i + j  
        End Function  
    End Class  
End Namespace  
```  
  
```vb  
' File: Mult.vb  
Namespace UtilityMethods  
    Public Class MultiplyClass  
        Public Shared Function Multiply(ByVal x As Long, ByVal y As Long) As Long  
            Return x * y  
        End Function  
    End Class  
End Namespace  
```  
  
```vb  
' File: TestCode.vb  
  
Imports UtilityMethods  
  
Module Test  
  
    Sub Main(ByVal args As String())  
  
        System.Console.WriteLine("Calling methods from MathLibrary.DLL:")  
  
        If args.Length <> 2 Then  
            System.Console.WriteLine("Usage: TestCode <num1> <num2>")  
            Return  
        End If  
  
        Dim num1 As Long = Long.Parse(args(0))  
        Dim num2 As Long = Long.Parse(args(1))  
  
        Dim sum As Long = AddClass.Add(num1, num2)  
        Dim product As Long = MultiplyClass.Multiply(num1, num2)  
  
        System.Console.WriteLine("{0} + {1} = {2}", num1, num2, sum)  
        System.Console.WriteLine("{0} * {1} = {2}", num1, num2, product)  
  
    End Sub  
  
End Module  
  
' Output (assuming 1234 and 5678 are entered as command-line arguments):  
' Calling methods from MathLibrary.DLL:  
' 1234 + 5678 = 6912  
' 1234 * 5678 = 7006652  
```  
  
 <span data-ttu-id="9955e-116">Este archivo contiene el algoritmo que usa los métodos de la DLL, `Add` y `Multiply`.</span><span class="sxs-lookup"><span data-stu-id="9955e-116">This file contains the algorithm that uses the DLL methods, `Add` and `Multiply`.</span></span> <span data-ttu-id="9955e-117">Empieza analizando los argumentos especificados en la línea de comandos, `num1` y `num2`.</span><span class="sxs-lookup"><span data-stu-id="9955e-117">It starts with parsing the arguments entered from the command line, `num1` and `num2`.</span></span> <span data-ttu-id="9955e-118">Después, calcula la suma mediante el método `Add` de la clase `AddClass`, y el producto mediante el método `Multiply` de la clase `MultiplyClass`.</span><span class="sxs-lookup"><span data-stu-id="9955e-118">Then it calculates the sum by using the `Add` method on the `AddClass` class, and the product by using the `Multiply` method on the `MultiplyClass` class.</span></span>  
  
 <span data-ttu-id="9955e-119">Tenga en cuenta que el `Imports` instrucción al principio del archivo le permite usar los nombres de clase no completos para hacer referencia a los métodos de la DLL en tiempo de compilación, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="9955e-119">Notice that the  `Imports` statement at the beginning of the file enables you to use the unqualified class names to reference the DLL methods at compile time, as follows:</span></span>  
  
```vb  
MultiplyClass.Multiply(num1, num2)  
```  
  
 <span data-ttu-id="9955e-120">En caso contrario, deberá usar los nombres completos, como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="9955e-120">Otherwise, you have to use the fully qualified names, as follows:</span></span>  
  
```vb  
UtilityMethods.MultiplyClass.Multiply(num1, num2)  
```  
  
## <a name="execution"></a><span data-ttu-id="9955e-121">Execution</span><span class="sxs-lookup"><span data-stu-id="9955e-121">Execution</span></span>  
 <span data-ttu-id="9955e-122">Para ejecutar el programa, escriba el nombre del archivo EXE, seguido de dos números, de esta forma:</span><span class="sxs-lookup"><span data-stu-id="9955e-122">To run the program, enter the name of the EXE file, followed by two numbers, as follows:</span></span>  
  
 `TestCode 1234 5678`  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9955e-123">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="9955e-123">Compiling the Code</span></span>  
 <span data-ttu-id="9955e-124">Para generar el archivo `MathLibrary.DLL`, compile los dos archivos `Add` y `Mult` mediante la línea de comandos siguiente.</span><span class="sxs-lookup"><span data-stu-id="9955e-124">To build the file `MathLibrary.DLL`, compile the two files `Add` and `Mult` by using the following command line.</span></span>  
  
```console  
vbc -target:library -out:MathLibrary.DLL Add.vb Mult.vb  
```  
  
 <span data-ttu-id="9955e-125">El [-destino (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/target.md) opción del compilador indica al compilador que genere un archivo DLL en lugar de un archivo EXE.</span><span class="sxs-lookup"><span data-stu-id="9955e-125">The [-target (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/target.md) compiler option tells the compiler to output a DLL instead of an EXE file.</span></span> <span data-ttu-id="9955e-126">El [-out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md) opción del compilador seguido por un nombre de archivo se usa para especificar el nombre del archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="9955e-126">The [-out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md) compiler option followed by a file name is used to specify the DLL file name.</span></span> <span data-ttu-id="9955e-127">De lo contrario, el compilador usa el primer archivo (`Add.vb`) como el nombre de la DLL.</span><span class="sxs-lookup"><span data-stu-id="9955e-127">Otherwise, the compiler uses the first file (`Add.vb`) as the name of the DLL.</span></span>  
  
 <span data-ttu-id="9955e-128">Para compilar el archivo ejecutable, `TestCode.exe`, use la siguiente línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="9955e-128">To build the executable file, `TestCode.exe`, use the following command line:</span></span>  
  
```console  
vbc -out:TestCode.exe -reference:MathLibrary.DLL TestCode.vb  
```  
  
 <span data-ttu-id="9955e-129">El **-out** opción del compilador indica al compilador que genere un archivo EXE y especifica el nombre del archivo de salida (`TestCode.exe`).</span><span class="sxs-lookup"><span data-stu-id="9955e-129">The **-out** compiler option tells the compiler to output an EXE file and specifies the name of the output file (`TestCode.exe`).</span></span> <span data-ttu-id="9955e-130">Esta opción del compilador es opcional.</span><span class="sxs-lookup"><span data-stu-id="9955e-130">This compiler option is optional.</span></span> <span data-ttu-id="9955e-131">El [-referencia (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) opción del compilador especifica el archivo o archivos DLL que utiliza el programa.</span><span class="sxs-lookup"><span data-stu-id="9955e-131">The [-reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) compiler option specifies the DLL file or files that this program uses.</span></span>  
  
 <span data-ttu-id="9955e-132">Para obtener más información sobre la compilación desde la línea de comandos, vea y [compilar desde la línea de comandos](../../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span><span class="sxs-lookup"><span data-stu-id="9955e-132">For more information about building from the command line, see  and [Building from the Command Line](../../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9955e-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="9955e-133">See also</span></span>
- [<span data-ttu-id="9955e-134">Conceptos de programación</span><span class="sxs-lookup"><span data-stu-id="9955e-134">Programming Concepts</span></span>](../../../../visual-basic/programming-guide/concepts/index.md)
- [<span data-ttu-id="9955e-135">Ensamblados de .NET</span><span class="sxs-lookup"><span data-stu-id="9955e-135">Assemblies in .NET</span></span>](../../../../standard/assembly/index.md)
- [<span data-ttu-id="9955e-136">Creación de una clase para contener funciones de archivos DLL</span><span class="sxs-lookup"><span data-stu-id="9955e-136">Creating a Class to Hold DLL Functions</span></span>](../../../../framework/interop/creating-a-class-to-hold-dll-functions.md)
