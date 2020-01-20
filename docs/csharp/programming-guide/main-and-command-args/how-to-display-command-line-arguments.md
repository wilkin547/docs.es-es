---
title: 'Procedimiento Mostrar argumentos de la línea de comandos: Guía de programación de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments [C#], displaying
ms.assetid: b8479f2d-9e05-4d38-82da-2e61246e5437
ms.openlocfilehash: 210dad71220572535a0325fac925b0453b0d4e03
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712031"
---
# <a name="how-to-display-command-line-arguments-c-programming-guide"></a><span data-ttu-id="b344e-102">Procedimiento Mostrar argumentos de la línea de comandos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="b344e-102">How to display command line arguments (C# Programming Guide)</span></span>
<span data-ttu-id="b344e-103">A los argumentos proporcionados a un archivo ejecutable en la línea de comandos se puede tener acceso a través de un parámetro opcional de `Main`.</span><span class="sxs-lookup"><span data-stu-id="b344e-103">Arguments provided to an executable on the command-line are accessible through an optional parameter to `Main`.</span></span> <span data-ttu-id="b344e-104">Los argumentos se proporcionan en forma de una matriz de cadenas.</span><span class="sxs-lookup"><span data-stu-id="b344e-104">The arguments are provided in the form of an array of strings.</span></span> <span data-ttu-id="b344e-105">Cada elemento de la matriz contiene un argumento.</span><span class="sxs-lookup"><span data-stu-id="b344e-105">Each element of the array contains one argument.</span></span> <span data-ttu-id="b344e-106">Se quita el espacio en blanco entre los argumentos.</span><span class="sxs-lookup"><span data-stu-id="b344e-106">White-space between arguments is removed.</span></span> <span data-ttu-id="b344e-107">Por ejemplo, considere estas invocaciones de línea de comandos de un ejecutable ficticio:</span><span class="sxs-lookup"><span data-stu-id="b344e-107">For example, consider these command-line invocations of a fictitious executable:</span></span>  
  
|<span data-ttu-id="b344e-108">Entrada en la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="b344e-108">Input on Command-line</span></span>|<span data-ttu-id="b344e-109">Matriz de cadenas que se pasa a Main</span><span class="sxs-lookup"><span data-stu-id="b344e-109">Array of strings passed to Main</span></span>|  
|----------------------------|-------------------------------------|  
|<span data-ttu-id="b344e-110">**executable.exe a b c**</span><span class="sxs-lookup"><span data-stu-id="b344e-110">**executable.exe a b c**</span></span>|<span data-ttu-id="b344e-111">"a"</span><span class="sxs-lookup"><span data-stu-id="b344e-111">"a"</span></span><br /><br /> <span data-ttu-id="b344e-112">"b"</span><span class="sxs-lookup"><span data-stu-id="b344e-112">"b"</span></span><br /><br /> <span data-ttu-id="b344e-113">"c"</span><span class="sxs-lookup"><span data-stu-id="b344e-113">"c"</span></span>|  
|<span data-ttu-id="b344e-114">**executable.exe one two**</span><span class="sxs-lookup"><span data-stu-id="b344e-114">**executable.exe one two**</span></span>|<span data-ttu-id="b344e-115">"one"</span><span class="sxs-lookup"><span data-stu-id="b344e-115">"one"</span></span><br /><br /> <span data-ttu-id="b344e-116">"two"</span><span class="sxs-lookup"><span data-stu-id="b344e-116">"two"</span></span>|  
|<span data-ttu-id="b344e-117">**executable.exe "one two" three**</span><span class="sxs-lookup"><span data-stu-id="b344e-117">**executable.exe "one two" three**</span></span>|<span data-ttu-id="b344e-118">"one two"</span><span class="sxs-lookup"><span data-stu-id="b344e-118">"one two"</span></span><br /><br /> <span data-ttu-id="b344e-119">"three"</span><span class="sxs-lookup"><span data-stu-id="b344e-119">"three"</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="b344e-120">Si se ejecuta una aplicación en Visual Studio, se pueden especificar argumentos de línea de comandos en la [Página Depuración, Diseñador de proyectos](/visualstudio/ide/reference/debug-page-project-designer).</span><span class="sxs-lookup"><span data-stu-id="b344e-120">When you are running an application in Visual Studio, you can specify command-line arguments in the [Debug Page, Project Designer](/visualstudio/ide/reference/debug-page-project-designer).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b344e-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b344e-121">Example</span></span>  
 <span data-ttu-id="b344e-122">En este ejemplo se muestran los argumentos de línea de comandos pasados a una aplicación de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="b344e-122">This example displays the command line arguments passed to a command-line application.</span></span> <span data-ttu-id="b344e-123">La salida que se muestra corresponde a la primera entrada de la tabla anterior.</span><span class="sxs-lookup"><span data-stu-id="b344e-123">The output shown is for the first entry in the table above.</span></span>  
  
 [!code-csharp[csProgGuideMain#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class1.cs#9)]  
  
## <a name="see-also"></a><span data-ttu-id="b344e-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="b344e-124">See also</span></span>

- [<span data-ttu-id="b344e-125">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="b344e-125">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="b344e-126">Compilar la línea de comandos con csc.exe</span><span class="sxs-lookup"><span data-stu-id="b344e-126">Command-line Building With csc.exe</span></span>](../../language-reference/compiler-options/command-line-building-with-csc-exe.md)
- [<span data-ttu-id="b344e-127">Main() y argumentos de la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="b344e-127">Main() and Command-Line Arguments</span></span>](./index.md)
- [<span data-ttu-id="b344e-128">Valores devueltos de Main()</span><span class="sxs-lookup"><span data-stu-id="b344e-128">Main() Return Values</span></span>](./main-return-values.md)
