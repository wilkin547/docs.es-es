---
title: "Cómo: Mostrar argumentos de la línea de comandos (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- command-line arguments [C#], displaying
ms.assetid: b8479f2d-9e05-4d38-82da-2e61246e5437
caps.latest.revision: 19
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
ms.openlocfilehash: cf8a57cce252b3596f0a19c9df643427615467c6
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-display-command-line-arguments-c-programming-guide"></a><span data-ttu-id="f0076-102">Cómo: Mostrar argumentos de la línea de comandos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="f0076-102">How to: Display Command Line Arguments (C# Programming Guide)</span></span>
<span data-ttu-id="f0076-103">A los argumentos proporcionados a un archivo ejecutable en la línea de comandos se puede tener acceso a través de un parámetro opcional de `Main`.</span><span class="sxs-lookup"><span data-stu-id="f0076-103">Arguments provided to an executable on the command-line are accessible through an optional parameter to `Main`.</span></span> <span data-ttu-id="f0076-104">Los argumentos se proporcionan en forma de una matriz de cadenas.</span><span class="sxs-lookup"><span data-stu-id="f0076-104">The arguments are provided in the form of an array of strings.</span></span> <span data-ttu-id="f0076-105">Cada elemento de la matriz contiene un argumento.</span><span class="sxs-lookup"><span data-stu-id="f0076-105">Each element of the array contains one argument.</span></span> <span data-ttu-id="f0076-106">Se quita el espacio en blanco entre los argumentos.</span><span class="sxs-lookup"><span data-stu-id="f0076-106">White-space between arguments is removed.</span></span> <span data-ttu-id="f0076-107">Por ejemplo, considere estas invocaciones de línea de comandos de un ejecutable ficticio:</span><span class="sxs-lookup"><span data-stu-id="f0076-107">For example, consider these command-line invocations of a fictitious executable:</span></span>  
  
|<span data-ttu-id="f0076-108">Entrada en la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="f0076-108">Input on Command-line</span></span>|<span data-ttu-id="f0076-109">Matriz de cadenas que se pasa a Main</span><span class="sxs-lookup"><span data-stu-id="f0076-109">Array of strings passed to Main</span></span>|  
|----------------------------|-------------------------------------|  
|<span data-ttu-id="f0076-110">**executable.exe a b c**</span><span class="sxs-lookup"><span data-stu-id="f0076-110">**executable.exe a b c**</span></span>|<span data-ttu-id="f0076-111">"a"</span><span class="sxs-lookup"><span data-stu-id="f0076-111">"a"</span></span><br /><br /> <span data-ttu-id="f0076-112">"b"</span><span class="sxs-lookup"><span data-stu-id="f0076-112">"b"</span></span><br /><br /> <span data-ttu-id="f0076-113">"c"</span><span class="sxs-lookup"><span data-stu-id="f0076-113">"c"</span></span>|  
|<span data-ttu-id="f0076-114">**executable.exe one two**</span><span class="sxs-lookup"><span data-stu-id="f0076-114">**executable.exe one two**</span></span>|<span data-ttu-id="f0076-115">"one"</span><span class="sxs-lookup"><span data-stu-id="f0076-115">"one"</span></span><br /><br /> <span data-ttu-id="f0076-116">"two"</span><span class="sxs-lookup"><span data-stu-id="f0076-116">"two"</span></span>|  
|<span data-ttu-id="f0076-117">**executable.exe "one two" three**</span><span class="sxs-lookup"><span data-stu-id="f0076-117">**executable.exe "one two" three**</span></span>|<span data-ttu-id="f0076-118">"one two"</span><span class="sxs-lookup"><span data-stu-id="f0076-118">"one two"</span></span><br /><br /> <span data-ttu-id="f0076-119">"three"</span><span class="sxs-lookup"><span data-stu-id="f0076-119">"three"</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="f0076-120">Si se ejecuta una aplicación en Visual Studio, se pueden especificar argumentos de línea de comandos en la [Página Depuración, Diseñador de proyectos](/visualstudio/ide/reference/debug-page-project-designer).</span><span class="sxs-lookup"><span data-stu-id="f0076-120">When you are running an application in Visual Studio, you can specify command-line arguments in the [Debug Page, Project Designer](/visualstudio/ide/reference/debug-page-project-designer).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f0076-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f0076-121">Example</span></span>  
 <span data-ttu-id="f0076-122">En este ejemplo se muestran los argumentos de línea de comandos pasados a una aplicación de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="f0076-122">This example displays the command line arguments passed to a command-line application.</span></span> <span data-ttu-id="f0076-123">La salida que se muestra corresponde a la primera entrada de la tabla anterior.</span><span class="sxs-lookup"><span data-stu-id="f0076-123">The output shown is for the first entry in the table above.</span></span>  
  
 <span data-ttu-id="f0076-124">[!code-cs[csProgGuideMain#9](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-display-command-line-arguments_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="f0076-124">[!code-cs[csProgGuideMain#9](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-display-command-line-arguments_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0076-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="f0076-125">See Also</span></span>  
 <span data-ttu-id="f0076-126">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="f0076-126">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="f0076-127">[Compilar la línea de comandos con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) </span><span class="sxs-lookup"><span data-stu-id="f0076-127">[Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) </span></span>  
 <span data-ttu-id="f0076-128">[Main() y argumentos de línea de comandos](../../../csharp/programming-guide/main-and-command-args/index.md) </span><span class="sxs-lookup"><span data-stu-id="f0076-128">[Main() and Command-Line Arguments](../../../csharp/programming-guide/main-and-command-args/index.md) </span></span>  
 <span data-ttu-id="f0076-129">[Cómo: Obtener acceso a argumentos de la línea de comandos mediante foreach](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md) </span><span class="sxs-lookup"><span data-stu-id="f0076-129">[How to: Access Command-Line Arguments Using foreach](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md) </span></span>  
 [<span data-ttu-id="f0076-130">Valores devueltos de Main()</span><span class="sxs-lookup"><span data-stu-id="f0076-130">Main() Return Values</span></span>](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)

