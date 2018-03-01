---
title: "Cómo: Obtener acceso a argumentos de la línea de comandos utilizando Foreach (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- command-line arguments [C#]
ms.assetid: 89c3e335-3f5b-4e24-8c5a-b8036561fe8a
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 557e72342901fab8bbe66e9cc3405cb4b2d9c1e2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-access-command-line-arguments-using-foreach-c-programming-guide"></a><span data-ttu-id="f49e7-102">Cómo: Obtener acceso a argumentos de la línea de comandos utilizando Foreach (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="f49e7-102">How to: Access Command-Line Arguments Using foreach (C# Programming Guide)</span></span>
<span data-ttu-id="f49e7-103">Otro enfoque para recorrer en iteración la matriz es usar la instrucción [foreach](../../../csharp/language-reference/keywords/foreach-in.md) como se muestra en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="f49e7-103">Another approach to iterating over the array is to use the [foreach](../../../csharp/language-reference/keywords/foreach-in.md) statement as shown in this example.</span></span> <span data-ttu-id="f49e7-104">La instrucción `foreach` se puede utilizar para recorrer en iteración una matriz, una clase de colección de .NET Framework o cualquier clase o struct que implemente la interfaz <xref:System.Collections.IEnumerable>.</span><span class="sxs-lookup"><span data-stu-id="f49e7-104">The `foreach` statement can be used to iterate over an array, a .NET Framework collection class, or any class or struct that implements the <xref:System.Collections.IEnumerable> interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f49e7-105">Al ejecutar una aplicación en Visual Studio, puede especificar argumentos de la línea de comandos en la [Página Depuración, Diseñador de proyectos](/visualstudio/ide/reference/debug-page-project-designer).</span><span class="sxs-lookup"><span data-stu-id="f49e7-105">When running an application in Visual Studio, you can specify command-line arguments in the [Debug Page, Project Designer](/visualstudio/ide/reference/debug-page-project-designer).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f49e7-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f49e7-106">Example</span></span>  
 <span data-ttu-id="f49e7-107">En este ejemplo se muestra cómo imprimir los argumentos de la línea de comandos con `foreach`.</span><span class="sxs-lookup"><span data-stu-id="f49e7-107">This example demonstrates how to print out the command line arguments using `foreach`.</span></span>  
  
 [!code-csharp[csProgGuideMain#10](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-access-command-line-arguments-using-foreach_1.cs)]  
  
 [!code-csharp[csProgGuideMain#11](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-access-command-line-arguments-using-foreach_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="f49e7-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="f49e7-108">See Also</span></span>  
 <xref:System.Array>  
 <xref:System.Collections>  
 [<span data-ttu-id="f49e7-109">Compilar la línea de comandos con csc.exe</span><span class="sxs-lookup"><span data-stu-id="f49e7-109">Command-line Building With csc.exe</span></span>](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)  
 [<span data-ttu-id="f49e7-110">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="f49e7-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="f49e7-111">foreach, in</span><span class="sxs-lookup"><span data-stu-id="f49e7-111">foreach, in</span></span>](../../../csharp/language-reference/keywords/foreach-in.md)  
 [<span data-ttu-id="f49e7-112">Main() y argumentos de la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="f49e7-112">Main() and Command-Line Arguments</span></span>](../../../csharp/programming-guide/main-and-command-args/index.md)  
 [<span data-ttu-id="f49e7-113">Cómo: Mostrar argumentos de la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="f49e7-113">How to: Display Command Line Arguments</span></span>](../../../csharp/programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)  
 [<span data-ttu-id="f49e7-114">Valores devueltos de Main()</span><span class="sxs-lookup"><span data-stu-id="f49e7-114">Main() Return Values</span></span>](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)
