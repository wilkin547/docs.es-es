---
title: extern (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- extern_CSharpKeyword
- extern
helpviewer_keywords:
- DllImport attribute
- extern keyword [C#]
ms.assetid: 9c3f02c4-51b8-4d80-9cb2-f2b6e1ae15c7
ms.openlocfilehash: 996888a585f8355bdda14e09b6bb9544257ae824
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2018
ms.locfileid: "34172298"
---
# <a name="extern-c-reference"></a><span data-ttu-id="7f6b3-102">extern (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="7f6b3-102">extern (C# Reference)</span></span>
<span data-ttu-id="7f6b3-103">El modificador `extern` se usa para declarar un método que se implementa externamente.</span><span class="sxs-lookup"><span data-stu-id="7f6b3-103">The `extern` modifier is used to declare a method that is implemented externally.</span></span> <span data-ttu-id="7f6b3-104">Un uso común del modificador `extern` es con el atributo `DllImport` al usar servicios de interoperabilidad para llamar a código no administrado.</span><span class="sxs-lookup"><span data-stu-id="7f6b3-104">A common use of the `extern` modifier is with the `DllImport` attribute when you are using Interop services to call into unmanaged code.</span></span> <span data-ttu-id="7f6b3-105">En este caso, el método se debe declarar también como `static`, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7f6b3-105">In this case, the method must also be declared as `static`, as shown in the following example:</span></span>  
  
```csharp  
[DllImport("avifil32.dll")]  
private static extern void AVIFileInit();  
```  
  
 <span data-ttu-id="7f6b3-106">La palabra clave `extern` también puede definir un alias del ensamblado externo, lo que permite hacer referencia a diferentes versiones del mismo componente desde un único ensamblado.</span><span class="sxs-lookup"><span data-stu-id="7f6b3-106">The `extern` keyword can also define an external assembly alias, which makes it possible to reference different versions of the same component from within a single assembly.</span></span> <span data-ttu-id="7f6b3-107">Para obtener más información, vea [alias externo](../../../csharp/language-reference/keywords/extern-alias.md).</span><span class="sxs-lookup"><span data-stu-id="7f6b3-107">For more information, see [extern alias](../../../csharp/language-reference/keywords/extern-alias.md).</span></span>  
  
 <span data-ttu-id="7f6b3-108">Es un error usar los modificadores [abstract](../../../csharp/language-reference/keywords/abstract.md) y `extern` juntos para modificar el mismo miembro.</span><span class="sxs-lookup"><span data-stu-id="7f6b3-108">It is an error to use the [abstract](../../../csharp/language-reference/keywords/abstract.md) and `extern` modifiers together to modify the same member.</span></span> <span data-ttu-id="7f6b3-109">El uso del modificador `extern` significa que el método se implementa fuera del código de C#, mientras que el uso del modificador `abstract` significa que la implementación del método no se proporciona en la clase.</span><span class="sxs-lookup"><span data-stu-id="7f6b3-109">Using the `extern` modifier means that the method is implemented outside the C# code, whereas using the `abstract` modifier means that the method implementation is not provided in the class.</span></span>  
  
 <span data-ttu-id="7f6b3-110">La palabra clave extern tiene usos más limitados en C# que en C++.</span><span class="sxs-lookup"><span data-stu-id="7f6b3-110">The extern keyword has more limited uses in C# than in C++.</span></span> <span data-ttu-id="7f6b3-111">Para comparar la palabra clave de C# con la de C++, consulte el tema sobre el uso de extern para especificar vinculación en la referencia del lenguaje C++.</span><span class="sxs-lookup"><span data-stu-id="7f6b3-111">To compare the C# keyword with the C++ keyword, see Using extern to Specify Linkage in the C++ Language Reference.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7f6b3-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7f6b3-112">Example</span></span>  
 <span data-ttu-id="7f6b3-113">**Ejemplo 1.**</span><span class="sxs-lookup"><span data-stu-id="7f6b3-113">**Example 1.**</span></span> <span data-ttu-id="7f6b3-114">En este ejemplo, el programa recibe una cadena del usuario y la muestra en un cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="7f6b3-114">In this example, the program receives a string from the user and displays it inside a message box.</span></span> <span data-ttu-id="7f6b3-115">El programa usa el método `MessageBox` importado de la biblioteca User32.dll.</span><span class="sxs-lookup"><span data-stu-id="7f6b3-115">The program uses the `MessageBox` method imported from the User32.dll library.</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/extern_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="7f6b3-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7f6b3-116">Example</span></span>  
 <span data-ttu-id="7f6b3-117">**Ejemplo 2.**</span><span class="sxs-lookup"><span data-stu-id="7f6b3-117">**Example 2.**</span></span> <span data-ttu-id="7f6b3-118">En este ejemplo se muestra un programa de C# que llama a una biblioteca de C (una DLL nativa).</span><span class="sxs-lookup"><span data-stu-id="7f6b3-118">This example illustrates a C# program that calls into a C library (a native DLL).</span></span>  
  
 1. <span data-ttu-id="7f6b3-119">Cree el archivo de C siguiente y denomínelo `cmdll.c`:</span><span class="sxs-lookup"><span data-stu-id="7f6b3-119">Create the following C file and name it `cmdll.c`:</span></span>  
  
```  
// cmdll.c  
// Compile with: /LD  
int __declspec(dllexport) SampleMethod(int i)  
{  
   return i*10;  
}  
```  
  
## <a name="example"></a><span data-ttu-id="7f6b3-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7f6b3-120">Example</span></span>  
 2. <span data-ttu-id="7f6b3-121">Abra una ventana del símbolo del sistema de las herramientas nativas de Visual Studio x64 (o x32) del directorio de instalación de Visual Studio y compile el archivo `cmdll.c` escribiendo **cl /LD cmdll.c** en el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="7f6b3-121">Open a Visual Studio x64 (or x32) Native Tools Command Prompt window from the Visual Studio installation directory and compile the `cmdll.c` file by typing **cl /LD cmdll.c** at the command prompt.</span></span>  
  
 3. <span data-ttu-id="7f6b3-122">En el mismo directorio, cree el siguiente archivo de C# y denomínelo `cm.cs`:</span><span class="sxs-lookup"><span data-stu-id="7f6b3-122">In the same directory, create the following C# file and name it `cm.cs`:</span></span>  
  
```csharp  
// cm.cs  
using System;  
using System.Runtime.InteropServices;  
public class MainClass   
{  
   [DllImport("Cmdll.dll")]  
   public static extern int SampleMethod(int x);  
  
   static void Main()   
   {  
      Console.WriteLine("SampleMethod() returns {0}.", SampleMethod(5));  
   }  
}  
```  
  
## <a name="example"></a><span data-ttu-id="7f6b3-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7f6b3-123">Example</span></span>  
 3. <span data-ttu-id="7f6b3-124">Abra una ventana del símbolo del sistema de las herramientas nativas de Visual Studio x64 (o x32) del directorio de instalación de Visual Studio y compile el archivo `cm.cs` escribiendo:</span><span class="sxs-lookup"><span data-stu-id="7f6b3-124">Open a Visual Studio x64 (or x32) Native Tools Command Prompt window from the Visual Studio installation directory and compile the `cm.cs` file by typing:</span></span>  
  
> <span data-ttu-id="7f6b3-125">**csc cm.cs** (para el símbolo del sistema x64)</span><span class="sxs-lookup"><span data-stu-id="7f6b3-125">**csc cm.cs** (for the x64 command prompt)</span></span>   
>  <span data-ttu-id="7f6b3-126">-O bien-</span><span class="sxs-lookup"><span data-stu-id="7f6b3-126">—or—</span></span>  
> <span data-ttu-id="7f6b3-127">**csc /platform:x86 cm.cs** (para el símbolo del sistema x32)</span><span class="sxs-lookup"><span data-stu-id="7f6b3-127">**csc /platform:x86 cm.cs** (for the x32 command prompt)</span></span>  
  
 <span data-ttu-id="7f6b3-128">De esta forma, se creará el archivo ejecutable `cm.exe`.</span><span class="sxs-lookup"><span data-stu-id="7f6b3-128">This will create the executable file `cm.exe`.</span></span>  
  
 4. <span data-ttu-id="7f6b3-129">Ejecute `cm.exe`.</span><span class="sxs-lookup"><span data-stu-id="7f6b3-129">Run `cm.exe`.</span></span> <span data-ttu-id="7f6b3-130">El método `SampleMethod` pasa el valor 5 al archivo DLL, que devuelve el valor multiplicado por 10.</span><span class="sxs-lookup"><span data-stu-id="7f6b3-130">The `SampleMethod` method passes the value 5 to the DLL file, which returns the value multiplied by 10.</span></span>  <span data-ttu-id="7f6b3-131">El programa produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="7f6b3-131">The program produces the following output:</span></span>  
  
```  
SampleMethod() returns 50.  
```  
  
## <a name="c-language-specification"></a><span data-ttu-id="7f6b3-132">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="7f6b3-132">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7f6b3-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="7f6b3-133">See Also</span></span>  
 <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=nameWithType>  
 [<span data-ttu-id="7f6b3-134">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="7f6b3-134">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="7f6b3-135">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="7f6b3-135">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="7f6b3-136">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="7f6b3-136">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="7f6b3-137">Modificadores</span><span class="sxs-lookup"><span data-stu-id="7f6b3-137">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)
