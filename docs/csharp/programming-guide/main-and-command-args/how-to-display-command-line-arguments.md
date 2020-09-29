---
title: 'Visualización de argumentos de la línea de comandos: Guía de programación de C#'
description: Aprenda a mostrar argumentos de la línea de comandos. Vea un ejemplo de código y examine los recursos adicionales disponibles.
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments [C#], displaying
ms.assetid: b8479f2d-9e05-4d38-82da-2e61246e5437
ms.openlocfilehash: 717e27c23724e63c03a38b028ef99dc6530b4745
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91195485"
---
# <a name="how-to-display-command-line-arguments-c-programming-guide"></a><span data-ttu-id="cbc14-104">Visualización de argumentos de la línea de comandos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="cbc14-104">How to display command-line arguments (C# Programming Guide)</span></span>

<span data-ttu-id="cbc14-105">El acceso a los argumentos proporcionados para un archivo ejecutable en la línea de comandos se puede realizar a través de un parámetro opcional para `Main`.</span><span class="sxs-lookup"><span data-stu-id="cbc14-105">Arguments provided to an executable on the command line are accessible through an optional parameter to `Main`.</span></span> <span data-ttu-id="cbc14-106">Los argumentos se proporcionan en forma de una matriz de cadenas.</span><span class="sxs-lookup"><span data-stu-id="cbc14-106">The arguments are provided in the form of an array of strings.</span></span> <span data-ttu-id="cbc14-107">Cada elemento de la matriz contiene un argumento.</span><span class="sxs-lookup"><span data-stu-id="cbc14-107">Each element of the array contains one argument.</span></span> <span data-ttu-id="cbc14-108">Se quita el espacio en blanco entre los argumentos.</span><span class="sxs-lookup"><span data-stu-id="cbc14-108">White-space between arguments is removed.</span></span> <span data-ttu-id="cbc14-109">Por ejemplo, considere estas invocaciones de línea de comandos de un ejecutable ficticio:</span><span class="sxs-lookup"><span data-stu-id="cbc14-109">For example, consider these command-line invocations of a fictitious executable:</span></span>  
  
|<span data-ttu-id="cbc14-110">Entrada en la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="cbc14-110">Input on command line</span></span>|<span data-ttu-id="cbc14-111">Matriz de cadenas que se pasa a Main</span><span class="sxs-lookup"><span data-stu-id="cbc14-111">Array of strings passed to Main</span></span>|  
|----------------------------|-------------------------------------|  
|<span data-ttu-id="cbc14-112">**executable.exe a b c**</span><span class="sxs-lookup"><span data-stu-id="cbc14-112">**executable.exe a b c**</span></span>|<span data-ttu-id="cbc14-113">"a"</span><span class="sxs-lookup"><span data-stu-id="cbc14-113">"a"</span></span><br /><br /> <span data-ttu-id="cbc14-114">"b"</span><span class="sxs-lookup"><span data-stu-id="cbc14-114">"b"</span></span><br /><br /> <span data-ttu-id="cbc14-115">"c"</span><span class="sxs-lookup"><span data-stu-id="cbc14-115">"c"</span></span>|  
|<span data-ttu-id="cbc14-116">**executable.exe one two**</span><span class="sxs-lookup"><span data-stu-id="cbc14-116">**executable.exe one two**</span></span>|<span data-ttu-id="cbc14-117">"one"</span><span class="sxs-lookup"><span data-stu-id="cbc14-117">"one"</span></span><br /><br /> <span data-ttu-id="cbc14-118">"two"</span><span class="sxs-lookup"><span data-stu-id="cbc14-118">"two"</span></span>|  
|<span data-ttu-id="cbc14-119">**executable.exe "one two" three**</span><span class="sxs-lookup"><span data-stu-id="cbc14-119">**executable.exe "one two" three**</span></span>|<span data-ttu-id="cbc14-120">"one two"</span><span class="sxs-lookup"><span data-stu-id="cbc14-120">"one two"</span></span><br /><br /> <span data-ttu-id="cbc14-121">"three"</span><span class="sxs-lookup"><span data-stu-id="cbc14-121">"three"</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="cbc14-122">Si se ejecuta una aplicación en Visual Studio, se pueden especificar argumentos de línea de comandos en la [Página Depuración, Diseñador de proyectos](/visualstudio/ide/reference/debug-page-project-designer).</span><span class="sxs-lookup"><span data-stu-id="cbc14-122">When you are running an application in Visual Studio, you can specify command-line arguments in the [Debug Page, Project Designer](/visualstudio/ide/reference/debug-page-project-designer).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cbc14-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cbc14-123">Example</span></span>  

 <span data-ttu-id="cbc14-124">En este ejemplo se muestran los argumentos de la línea de comandos pasados a una aplicación de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="cbc14-124">This example displays the command-line arguments passed to a command-line application.</span></span> <span data-ttu-id="cbc14-125">La salida que se muestra corresponde a la primera entrada de la tabla anterior.</span><span class="sxs-lookup"><span data-stu-id="cbc14-125">The output shown is for the first entry in the table above.</span></span>  
  
 [!code-csharp[csProgGuideMain#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class1.cs#9)]  
  
## <a name="see-also"></a><span data-ttu-id="cbc14-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cbc14-126">See also</span></span>

- [<span data-ttu-id="cbc14-127">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="cbc14-127">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="cbc14-128">Compilar la línea de comandos con csc.exe</span><span class="sxs-lookup"><span data-stu-id="cbc14-128">Command-line Building With csc.exe</span></span>](../../language-reference/compiler-options/command-line-building-with-csc-exe.md)
- [<span data-ttu-id="cbc14-129">Main() y argumentos de línea de comandos</span><span class="sxs-lookup"><span data-stu-id="cbc14-129">Main() and Command-Line Arguments</span></span>](./index.md)
- [<span data-ttu-id="cbc14-130">Valores devueltos de Main()</span><span class="sxs-lookup"><span data-stu-id="cbc14-130">Main() Return Values</span></span>](./main-return-values.md)
