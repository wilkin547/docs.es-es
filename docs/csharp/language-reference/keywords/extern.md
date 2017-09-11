---
title: extern (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- extern_CSharpKeyword
- extern
dev_langs:
- CSharp
helpviewer_keywords:
- DllImport attribute
- extern keyword [C#]
ms.assetid: 9c3f02c4-51b8-4d80-9cb2-f2b6e1ae15c7
caps.latest.revision: 26
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: e499ade5ec8a9339b0d425c59809cf7c177466fb
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="extern-c-reference"></a><span data-ttu-id="a2e5c-102">extern (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="a2e5c-102">extern (C# Reference)</span></span>
<span data-ttu-id="a2e5c-103">El modificador `extern` se usa para declarar un método que se implementa externamente.</span><span class="sxs-lookup"><span data-stu-id="a2e5c-103">The `extern` modifier is used to declare a method that is implemented externally.</span></span> <span data-ttu-id="a2e5c-104">Un uso común del modificador `extern` es con el atributo `DllImport` al usar servicios de interoperabilidad para llamar a código no administrado.</span><span class="sxs-lookup"><span data-stu-id="a2e5c-104">A common use of the `extern` modifier is with the `DllImport` attribute when you are using Interop services to call into unmanaged code.</span></span> <span data-ttu-id="a2e5c-105">En este caso, el método se debe declarar también como `static`, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a2e5c-105">In this case, the method must also be declared as `static`, as shown in the following example:</span></span>  
  
```  
[DllImport("avifil32.dll")]  
private static extern void AVIFileInit();  
```  
  
 <span data-ttu-id="a2e5c-106">La palabra clave `extern` también puede definir un alias del ensamblado externo, lo que permite hacer referencia a diferentes versiones del mismo componente desde un único ensamblado.</span><span class="sxs-lookup"><span data-stu-id="a2e5c-106">The `extern` keyword can also define an external assembly alias, which makes it possible to reference different versions of the same component from within a single assembly.</span></span> <span data-ttu-id="a2e5c-107">Para obtener más información, vea [alias externo](../../../csharp/language-reference/keywords/extern-alias.md).</span><span class="sxs-lookup"><span data-stu-id="a2e5c-107">For more information, see [extern alias](../../../csharp/language-reference/keywords/extern-alias.md).</span></span>  
  
 <span data-ttu-id="a2e5c-108">Es un error usar los modificadores [abstract](../../../csharp/language-reference/keywords/abstract.md) y `extern` juntos para modificar el mismo miembro.</span><span class="sxs-lookup"><span data-stu-id="a2e5c-108">It is an error to use the [abstract](../../../csharp/language-reference/keywords/abstract.md) and `extern` modifiers together to modify the same member.</span></span> <span data-ttu-id="a2e5c-109">El uso del modificador `extern` significa que el método se implementa fuera del código de C#, mientras que el uso del modificador `abstract` significa que la implementación del método no se proporciona en la clase.</span><span class="sxs-lookup"><span data-stu-id="a2e5c-109">Using the `extern` modifier means that the method is implemented outside the C# code, whereas using the `abstract` modifier means that the method implementation is not provided in the class.</span></span>  
  
 <span data-ttu-id="a2e5c-110">La palabra clave extern tiene usos más limitados en C# que en C++.</span><span class="sxs-lookup"><span data-stu-id="a2e5c-110">The extern keyword has more limited uses in C# than in C++.</span></span> <span data-ttu-id="a2e5c-111">Para comparar la palabra clave de C# con la de C++, consulte el tema sobre el uso de extern para especificar vinculación en la referencia del lenguaje C++.</span><span class="sxs-lookup"><span data-stu-id="a2e5c-111">To compare the C# keyword with the C++ keyword, see Using extern to Specify Linkage in the C++ Language Reference.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2e5c-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a2e5c-112">Example</span></span>  
 <span data-ttu-id="a2e5c-113">**Ejemplo 1.**</span><span class="sxs-lookup"><span data-stu-id="a2e5c-113">**Example 1.**</span></span> <span data-ttu-id="a2e5c-114">En este ejemplo, el programa recibe una cadena del usuario y la muestra en un cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="a2e5c-114">In this example, the program receives a string from the user and displays it inside a message box.</span></span> <span data-ttu-id="a2e5c-115">El programa usa el método `MessageBox` importado de la biblioteca User32.dll.</span><span class="sxs-lookup"><span data-stu-id="a2e5c-115">The program uses the `MessageBox` method imported from the User32.dll library.</span></span>  
  
 <span data-ttu-id="a2e5c-116">[!code-cs[csrefKeywordsModifiers#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/extern_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="a2e5c-116">[!code-cs[csrefKeywordsModifiers#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/extern_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2e5c-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a2e5c-117">Example</span></span>  
 <span data-ttu-id="a2e5c-118">**Ejemplo 2.**</span><span class="sxs-lookup"><span data-stu-id="a2e5c-118">**Example 2.**</span></span> <span data-ttu-id="a2e5c-119">En este ejemplo se muestra un programa de C# que llama a una biblioteca de C (una DLL nativa).</span><span class="sxs-lookup"><span data-stu-id="a2e5c-119">This example illustrates a C# program that calls into a C library (a native DLL).</span></span>  
  
 1. <span data-ttu-id="a2e5c-120">Cree el archivo de C siguiente y denomínelo `cmdll.c`:</span><span class="sxs-lookup"><span data-stu-id="a2e5c-120">Create the following C file and name it `cmdll.c`:</span></span>  
  
```  
// cmdll.c  
// Compile with: /LD  
int __declspec(dllexport) SampleMethod(int i)  
{  
   return i*10;  
}  
```  
  
## <a name="example"></a><span data-ttu-id="a2e5c-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a2e5c-121">Example</span></span>  
 2. <span data-ttu-id="a2e5c-122">Abra una ventana del símbolo del sistema de las herramientas nativas de Visual Studio x64 (o x32) del directorio de instalación de Visual Studio y compile el archivo `cmdll.c` escribiendo **cl /LD cmdll.c** en el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="a2e5c-122">Open a Visual Studio x64 (or x32) Native Tools Command Prompt window from the Visual Studio installation directory and compile the `cmdll.c` file by typing **cl /LD cmdll.c** at the command prompt.</span></span>  
  
 3. <span data-ttu-id="a2e5c-123">En el mismo directorio, cree el siguiente archivo de C# y denomínelo `cm.cs`:</span><span class="sxs-lookup"><span data-stu-id="a2e5c-123">In the same directory, create the following C# file and name it `cm.cs`:</span></span>  
  
```  
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
  
## <a name="example"></a><span data-ttu-id="a2e5c-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a2e5c-124">Example</span></span>  
 3. <span data-ttu-id="a2e5c-125">Abra una ventana del símbolo del sistema de las herramientas nativas de Visual Studio x64 (o x32) del directorio de instalación de Visual Studio y compile el archivo `cm.cs` escribiendo:</span><span class="sxs-lookup"><span data-stu-id="a2e5c-125">Open a Visual Studio x64 (or x32) Native Tools Command Prompt window from the Visual Studio installation directory and compile the `cm.cs` file by typing:</span></span>  
  
> <span data-ttu-id="a2e5c-126">**csc cm.cs** (para el símbolo del sistema x64)</span><span class="sxs-lookup"><span data-stu-id="a2e5c-126">**csc cm.cs** (for the x64 command prompt)</span></span>   
>  <span data-ttu-id="a2e5c-127">-O bien-</span><span class="sxs-lookup"><span data-stu-id="a2e5c-127">—or—</span></span>  
> <span data-ttu-id="a2e5c-128">**csc /platform:x86 cm.cs** (para el símbolo del sistema x32)</span><span class="sxs-lookup"><span data-stu-id="a2e5c-128">**csc /platform:x86 cm.cs** (for the x32 command prompt)</span></span>  
  
 <span data-ttu-id="a2e5c-129">De esta forma, se creará el archivo ejecutable `cm.exe`.</span><span class="sxs-lookup"><span data-stu-id="a2e5c-129">This will create the executable file `cm.exe`.</span></span>  
  
 4. <span data-ttu-id="a2e5c-130">Ejecute `cm.exe`.</span><span class="sxs-lookup"><span data-stu-id="a2e5c-130">Run `cm.exe`.</span></span> <span data-ttu-id="a2e5c-131">El método `SampleMethod` pasa el valor 5 al archivo DLL, que devuelve el valor multiplicado por 10.</span><span class="sxs-lookup"><span data-stu-id="a2e5c-131">The `SampleMethod` method passes the value 5 to the DLL file, which returns the value multiplied by 10.</span></span>  <span data-ttu-id="a2e5c-132">El programa produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="a2e5c-132">The program produces the following output:</span></span>  
  
```  
SampleMethod() returns 50.  
```  
  
## <a name="c-language-specification"></a><span data-ttu-id="a2e5c-133">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="a2e5c-133">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a2e5c-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="a2e5c-134">See Also</span></span>  
 <span data-ttu-id="a2e5c-135"><xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="a2e5c-135"><xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName></span></span>   
 <span data-ttu-id="a2e5c-136">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="a2e5c-136">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="a2e5c-137">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="a2e5c-137">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="a2e5c-138">[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="a2e5c-138">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 [<span data-ttu-id="a2e5c-139">Modificadores</span><span class="sxs-lookup"><span data-stu-id="a2e5c-139">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)

