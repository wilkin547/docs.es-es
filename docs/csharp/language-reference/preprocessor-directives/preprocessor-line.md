---
title: '#line (Referencia de C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#line'
helpviewer_keywords:
- '#line directive [C#]'
ms.assetid: 6439e525-5dd5-4acb-b8ea-efabb32ff95b
caps.latest.revision: 13
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 3d2f42915d214349eebff40949482d7f603c0c2c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="line-c-reference"></a><span data-ttu-id="5cb34-102">#line (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="5cb34-102">#line (C# Reference)</span></span>
<span data-ttu-id="5cb34-103">`#line` le permite modificar el número de línea del compilador y (opcionalmente) la salida del nombre de archivo de errores y advertencias.</span><span class="sxs-lookup"><span data-stu-id="5cb34-103">`#line` lets you modify the compiler's line number and (optionally) the file name output for errors and warnings.</span></span> <span data-ttu-id="5cb34-104">En este ejemplo, se muestra cómo notificar dos advertencias asociadas con números de línea.</span><span class="sxs-lookup"><span data-stu-id="5cb34-104">This example shows how to report two warnings associated with line numbers.</span></span> <span data-ttu-id="5cb34-105">La directiva `#line 200` fuerza el número de línea para que sea 200 (aunque el valor predeterminado es 7) y hasta la siguiente directiva #line, el nombre de archivo se notificará como "Especial".</span><span class="sxs-lookup"><span data-stu-id="5cb34-105">The `#line 200` directive forces the line number to be 200 (although the default is #7) and until the next #line directive, the filename will be reported as "Special".</span></span> <span data-ttu-id="5cb34-106">La directiva #line predeterminada devuelve la numeración de líneas a su numeración predeterminada, que cuenta las líneas a las que la directiva anterior ha cambiado el número.</span><span class="sxs-lookup"><span data-stu-id="5cb34-106">The #line default directive returns the line numbering to its default numbering, which counts the lines that were renumbered by the previous directive.</span></span>  
  
```csharp
class MainClass  
{  
    static void Main()  
    {  
#line 200 "Special"  
        int i;    // CS0168 on line 200  
        int j;    // CS0168 on line 201  
#line default  
        char c;   // CS0168 on line 9  
        float f;  // CS0168 on line 10  
#line hidden // numbering not affected  
        string s;   
        double d; // CS0168 on line 13  
    }  
}  
```  
  
## <a name="remarks"></a><span data-ttu-id="5cb34-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5cb34-107">Remarks</span></span>  
 <span data-ttu-id="5cb34-108">La directiva `#line` podría usarse en un paso intermedio automatizado en el proceso de compilación.</span><span class="sxs-lookup"><span data-stu-id="5cb34-108">The `#line` directive might be used in an automated, intermediate step in the build process.</span></span> <span data-ttu-id="5cb34-109">Por ejemplo, si se han eliminado las líneas del archivo de código fuente original, pero aún quiere que el compilador genere unos resultados en función de la numeración de líneas original en el archivo, puede quitar las líneas y, después, simular la numeración de líneas original con `#line`.</span><span class="sxs-lookup"><span data-stu-id="5cb34-109">For example, if lines were removed from the original source code file, but you still wanted the compiler to generate output based on the original line numbering in the file, you could remove lines and then simulate the original line numbering with `#line`.</span></span>  
  
 <span data-ttu-id="5cb34-110">La directiva `#line hidden` oculta las líneas sucesivas del depurador, de forma que, cuando el desarrollador ejecuta paso a paso el código, cualquier línea entre `#line hidden` y la siguiente directiva `#line` (suponiendo que no sea otra directiva `#line hidden`) se depurará paso a paso por procedimientos.</span><span class="sxs-lookup"><span data-stu-id="5cb34-110">The `#line hidden` directive hides the successive lines from the debugger, such that when the developer steps through the code, any lines between a `#line hidden` and the next `#line` directive (assuming that it is not another `#line hidden` directive) will be stepped over.</span></span> <span data-ttu-id="5cb34-111">Esta opción también se puede usar para permitir que ASP.NET diferencie entre el código generado por el equipo y el definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="5cb34-111">This option can also be used to allow ASP.NET to differentiate between user-defined and machine-generated code.</span></span> <span data-ttu-id="5cb34-112">Aunque ASP.NET es el consumidor principal de esta característica, es probable que la usen más generadores de código fuente.</span><span class="sxs-lookup"><span data-stu-id="5cb34-112">Although ASP.NET is the primary consumer of this feature, it is likely that more source generators will make use of it.</span></span>  
  
 <span data-ttu-id="5cb34-113">Una directiva `#line hidden` no afecta a los nombres de archivo o números de línea en el informe de errores.</span><span class="sxs-lookup"><span data-stu-id="5cb34-113">A `#line hidden` directive does not affect file names or line numbers in error reporting.</span></span> <span data-ttu-id="5cb34-114">Es decir, si se produce un error en un bloque oculto, el compilador notificará el nombre de archivo y número de línea reales del error.</span><span class="sxs-lookup"><span data-stu-id="5cb34-114">That is, if an error is encountered in a hidden block, the compiler will report the current file name and line number of the error.</span></span>  
  
 <span data-ttu-id="5cb34-115">La directiva `#line filename` especifica el nombre de archivo que quiere que aparezca en la salida del compilador.</span><span class="sxs-lookup"><span data-stu-id="5cb34-115">The `#line filename` directive specifies the file name you want to appear in the compiler output.</span></span> <span data-ttu-id="5cb34-116">De forma predeterminada, se usa el nombre real del archivo de código fuente.</span><span class="sxs-lookup"><span data-stu-id="5cb34-116">By default, the actual name of the source code file is used.</span></span> <span data-ttu-id="5cb34-117">El nombre de archivo debe estar entre comillas dobles ("") y debe ir precedido de un número de línea.</span><span class="sxs-lookup"><span data-stu-id="5cb34-117">The file name must be in double quotation marks ("") and must be preceded by a line number.</span></span>  
  
 <span data-ttu-id="5cb34-118">Un archivo de código fuente puede tener cualquier número de directivas `#line`.</span><span class="sxs-lookup"><span data-stu-id="5cb34-118">A source code file can have any number of `#line` directives.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="5cb34-119">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="5cb34-119">Example 1</span></span>  
 <span data-ttu-id="5cb34-120">En el ejemplo siguiente, se muestra cómo el depurador omite las líneas ocultas en el código.</span><span class="sxs-lookup"><span data-stu-id="5cb34-120">The following example shows how the debugger ignores the hidden lines in the code.</span></span> <span data-ttu-id="5cb34-121">Al ejecutar el ejemplo, mostrará tres líneas de texto.</span><span class="sxs-lookup"><span data-stu-id="5cb34-121">When you run the example, it will display three lines of text.</span></span> <span data-ttu-id="5cb34-122">En cambio, al establecer un punto de interrupción, como se muestra en el ejemplo, y presionar F10 para recorrer el código, observará que el depurador omite la línea oculta.</span><span class="sxs-lookup"><span data-stu-id="5cb34-122">However, when you set a break point, as shown in the example, and hit F10 to step through the code, you will notice that the debugger ignores the hidden line.</span></span> <span data-ttu-id="5cb34-123">Tenga también en cuenta que, incluso si configura un punto de interrupción en la línea oculta, el depurador lo omitirá.</span><span class="sxs-lookup"><span data-stu-id="5cb34-123">Notice also that even if you set a break point at the hidden line, the debugger will still ignore it.</span></span>  
  
```csharp
// preprocessor_linehidden.cs  
using System;  
class MainClass   
{  
    static void Main()   
    {  
        Console.WriteLine("Normal line #1."); // Set break point here.  
#line hidden  
        Console.WriteLine("Hidden line.");  
#line default  
        Console.WriteLine("Normal line #2.");  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="5cb34-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="5cb34-124">See Also</span></span>  
 [<span data-ttu-id="5cb34-125">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="5cb34-125">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="5cb34-126">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="5cb34-126">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="5cb34-127">Directivas de preprocesador de C#</span><span class="sxs-lookup"><span data-stu-id="5cb34-127">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
