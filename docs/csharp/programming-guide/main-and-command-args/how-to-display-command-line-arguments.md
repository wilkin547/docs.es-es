---
title: 'Procedimiento Mostrar argumentos de la línea de comandos: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments [C#], displaying
ms.assetid: b8479f2d-9e05-4d38-82da-2e61246e5437
ms.openlocfilehash: c88219d03d40c814338a1b09ccd37cfc03c2d577
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2019
ms.locfileid: "65881011"
---
# <a name="how-to-display-command-line-arguments-c-programming-guide"></a><span data-ttu-id="13df2-102">Procedimiento Mostrar argumentos de la línea de comandos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="13df2-102">How to: Display Command Line Arguments (C# Programming Guide)</span></span>
<span data-ttu-id="13df2-103">A los argumentos proporcionados a un archivo ejecutable en la línea de comandos se puede tener acceso a través de un parámetro opcional de `Main`.</span><span class="sxs-lookup"><span data-stu-id="13df2-103">Arguments provided to an executable on the command-line are accessible through an optional parameter to `Main`.</span></span> <span data-ttu-id="13df2-104">Los argumentos se proporcionan en forma de una matriz de cadenas.</span><span class="sxs-lookup"><span data-stu-id="13df2-104">The arguments are provided in the form of an array of strings.</span></span> <span data-ttu-id="13df2-105">Cada elemento de la matriz contiene un argumento.</span><span class="sxs-lookup"><span data-stu-id="13df2-105">Each element of the array contains one argument.</span></span> <span data-ttu-id="13df2-106">Se quita el espacio en blanco entre los argumentos.</span><span class="sxs-lookup"><span data-stu-id="13df2-106">White-space between arguments is removed.</span></span> <span data-ttu-id="13df2-107">Por ejemplo, considere estas invocaciones de línea de comandos de un ejecutable ficticio:</span><span class="sxs-lookup"><span data-stu-id="13df2-107">For example, consider these command-line invocations of a fictitious executable:</span></span>  
  
|<span data-ttu-id="13df2-108">Entrada en la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="13df2-108">Input on Command-line</span></span>|<span data-ttu-id="13df2-109">Matriz de cadenas que se pasa a Main</span><span class="sxs-lookup"><span data-stu-id="13df2-109">Array of strings passed to Main</span></span>|  
|----------------------------|-------------------------------------|  
|<span data-ttu-id="13df2-110">**executable.exe a b c**</span><span class="sxs-lookup"><span data-stu-id="13df2-110">**executable.exe a b c**</span></span>|<span data-ttu-id="13df2-111">"a"</span><span class="sxs-lookup"><span data-stu-id="13df2-111">"a"</span></span><br /><br /> <span data-ttu-id="13df2-112">"b"</span><span class="sxs-lookup"><span data-stu-id="13df2-112">"b"</span></span><br /><br /> <span data-ttu-id="13df2-113">"c"</span><span class="sxs-lookup"><span data-stu-id="13df2-113">"c"</span></span>|  
|<span data-ttu-id="13df2-114">**executable.exe one two**</span><span class="sxs-lookup"><span data-stu-id="13df2-114">**executable.exe one two**</span></span>|<span data-ttu-id="13df2-115">"one"</span><span class="sxs-lookup"><span data-stu-id="13df2-115">"one"</span></span><br /><br /> <span data-ttu-id="13df2-116">"two"</span><span class="sxs-lookup"><span data-stu-id="13df2-116">"two"</span></span>|  
|<span data-ttu-id="13df2-117">**executable.exe "one two" three**</span><span class="sxs-lookup"><span data-stu-id="13df2-117">**executable.exe "one two" three**</span></span>|<span data-ttu-id="13df2-118">"one two"</span><span class="sxs-lookup"><span data-stu-id="13df2-118">"one two"</span></span><br /><br /> <span data-ttu-id="13df2-119">"three"</span><span class="sxs-lookup"><span data-stu-id="13df2-119">"three"</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="13df2-120">Si se ejecuta una aplicación en Visual Studio, se pueden especificar argumentos de línea de comandos en la [Página Depuración, Diseñador de proyectos](/visualstudio/ide/reference/debug-page-project-designer).</span><span class="sxs-lookup"><span data-stu-id="13df2-120">When you are running an application in Visual Studio, you can specify command-line arguments in the [Debug Page, Project Designer](/visualstudio/ide/reference/debug-page-project-designer).</span></span>  
  
## <a name="example"></a><span data-ttu-id="13df2-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="13df2-121">Example</span></span>  
 <span data-ttu-id="13df2-122">En este ejemplo se muestran los argumentos de línea de comandos pasados a una aplicación de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="13df2-122">This example displays the command line arguments passed to a command-line application.</span></span> <span data-ttu-id="13df2-123">La salida que se muestra corresponde a la primera entrada de la tabla anterior.</span><span class="sxs-lookup"><span data-stu-id="13df2-123">The output shown is for the first entry in the table above.</span></span>  
  
 [!code-csharp[csProgGuideMain#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class1.cs#9)]  
  
## <a name="see-also"></a><span data-ttu-id="13df2-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="13df2-124">See also</span></span>

- [<span data-ttu-id="13df2-125">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="13df2-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="13df2-126">Compilar la línea de comandos con csc.exe</span><span class="sxs-lookup"><span data-stu-id="13df2-126">Command-line Building With csc.exe</span></span>](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)
- [<span data-ttu-id="13df2-127">Main() y argumentos de la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="13df2-127">Main() and Command-Line Arguments</span></span>](../../../csharp/programming-guide/main-and-command-args/index.md)
- [<span data-ttu-id="13df2-128">Valores devueltos de Main()</span><span class="sxs-lookup"><span data-stu-id="13df2-128">Main() Return Values</span></span>](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)
