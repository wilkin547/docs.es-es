---
title: "Estructura general de un programa de C# (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, program structure
ms.assetid: 5ae964a5-0ef0-40fe-88fb-6d1793371d0d
caps.latest.revision: 21
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
ms.openlocfilehash: d55ac6a6d35e5f47ab26da681afe9fb5555331ec
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="general-structure-of-a-c-program-c-programming-guide"></a><span data-ttu-id="9c03f-102">Estructura general de un programa de C# (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="9c03f-102">General Structure of a C# Program (C# Programming Guide)</span></span>
<span data-ttu-id="9c03f-103">Los programas de C# pueden constar de uno o más archivos.</span><span class="sxs-lookup"><span data-stu-id="9c03f-103">C# programs can consist of one or more files.</span></span> <span data-ttu-id="9c03f-104">Cada archivo puede contener cero o más espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="9c03f-104">Each file can contain zero or more namespaces.</span></span> <span data-ttu-id="9c03f-105">Un espacio de nombres puede contener tipos como clases, structs, interfaces, enumeraciones y delegados, además de otros espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="9c03f-105">A namespace can contain types such as classes, structs, interfaces, enumerations, and delegates, in addition to other namespaces.</span></span> <span data-ttu-id="9c03f-106">El siguiente es el esqueleto de un programa de C# que contiene todos estos elementos.</span><span class="sxs-lookup"><span data-stu-id="9c03f-106">The following is the skeleton of a C# program that contains all of these elements.</span></span>  
  
 <span data-ttu-id="9c03f-107">[!code-cs[csProgGuide#34](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/general-structure-of-a-csharp-program_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="9c03f-107">[!code-cs[csProgGuide#34](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/general-structure-of-a-csharp-program_1.cs)]</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="9c03f-108">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="9c03f-108">Related Sections</span></span>  
 <span data-ttu-id="9c03f-109">Para obtener más información:</span><span class="sxs-lookup"><span data-stu-id="9c03f-109">For more information:</span></span>  
  
-   [<span data-ttu-id="9c03f-110">Clases</span><span class="sxs-lookup"><span data-stu-id="9c03f-110">Classes</span></span>](../../../csharp/programming-guide/classes-and-structs/classes.md)  
  
-   [<span data-ttu-id="9c03f-111">Estructuras</span><span class="sxs-lookup"><span data-stu-id="9c03f-111">Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/structs.md)  
  
-   [<span data-ttu-id="9c03f-112">Espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="9c03f-112">Namespaces</span></span>](../../../csharp/programming-guide/namespaces/index.md)  
  
-   [<span data-ttu-id="9c03f-113">Interfaces</span><span class="sxs-lookup"><span data-stu-id="9c03f-113">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)  
  
-   [<span data-ttu-id="9c03f-114">Delegados</span><span class="sxs-lookup"><span data-stu-id="9c03f-114">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="9c03f-115">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="9c03f-115">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9c03f-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="9c03f-116">See Also</span></span>  
 <span data-ttu-id="9c03f-117">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="9c03f-117">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="9c03f-118">[Dentro de un programa de C#](../../../csharp/programming-guide/inside-a-program/index.md) </span><span class="sxs-lookup"><span data-stu-id="9c03f-118">[Inside a C# Program](../../../csharp/programming-guide/inside-a-program/index.md) </span></span>  
 <span data-ttu-id="9c03f-119">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="9c03f-119">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="9c03f-120">[\<paveover>C# Sample Applications](http://msdn.microsoft.com/en-us/9a9d7aaa-51d3-4224-b564-95409b0f3e15) (<paveover> Aplicaciones de ejemplo de C#)</span><span class="sxs-lookup"><span data-stu-id="9c03f-120">[\<paveover>C# Sample Applications](http://msdn.microsoft.com/en-us/9a9d7aaa-51d3-4224-b564-95409b0f3e15)</span></span>

