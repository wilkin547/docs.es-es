---
title: Espacios de nombres (Guía de programación de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- C# language, namespaces
- namespaces [C#]
ms.assetid: b1c4ab46-3fad-4ffa-9deb-dd50a2d8c65a
caps.latest.revision: 27
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 3eb645f5beb61d3cec97a70a54e660c65be52091
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="namespaces-c-programming-guide"></a><span data-ttu-id="6ac47-102">Espacios de nombres (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="6ac47-102">Namespaces (C# Programming Guide)</span></span>
<span data-ttu-id="6ac47-103">Los espacios de nombres se usan mucho en programación de C# de dos maneras.</span><span class="sxs-lookup"><span data-stu-id="6ac47-103">Namespaces are heavily used in C# programming in two ways.</span></span> <span data-ttu-id="6ac47-104">En primer lugar, .NET Framework usa espacios de nombres para organizar sus clases, de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="6ac47-104">First, the .NET Framework uses namespaces to organize its many classes, as follows:</span></span>  
  
 [!code-csharp[csProgGuide#22](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_1.cs)]  
  
 <span data-ttu-id="6ac47-105">`System` es un espacio de nombres y `Console` es una clase de ese espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="6ac47-105">`System` is a namespace and `Console` is a class in that namespace.</span></span> <span data-ttu-id="6ac47-106">La palabra clave `using` se puede usar para que no se necesite el nombre completo, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6ac47-106">The `using` keyword can be used so that the complete name is not required, as in the following example:</span></span>  
  
 [!code-csharp[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_2.cs)]  
  
 [!code-csharp[csProgGuide#25](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_3.cs)]  
  
 <span data-ttu-id="6ac47-107">Para obtener más información, consulte [using (Directiva)](../../../csharp/language-reference/keywords/using-directive.md).</span><span class="sxs-lookup"><span data-stu-id="6ac47-107">For more information, see [using Directive](../../../csharp/language-reference/keywords/using-directive.md).</span></span>  
  
 <span data-ttu-id="6ac47-108">En segundo lugar, declarar sus propios espacios de nombres puede ayudarle a controlar el ámbito de nombres de clase y método en proyectos de programación grandes.</span><span class="sxs-lookup"><span data-stu-id="6ac47-108">Second, declaring your own namespaces can help you control the scope of class and method names in larger programming projects.</span></span> <span data-ttu-id="6ac47-109">Use la palabra clave [namespace](../../../csharp/language-reference/keywords/namespace.md) para declarar un espacio de nombres, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6ac47-109">Use the [namespace](../../../csharp/language-reference/keywords/namespace.md) keyword to declare a namespace, as in the following example:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#6](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/index_4.cs)]  
  
## <a name="namespaces-overview"></a><span data-ttu-id="6ac47-110">Información general sobre los espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="6ac47-110">Namespaces Overview</span></span>  
 <span data-ttu-id="6ac47-111">Los espacios de nombres tienen las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="6ac47-111">Namespaces have the following properties:</span></span>  
  
-   <span data-ttu-id="6ac47-112">Organizan proyectos de código de gran tamaño.</span><span class="sxs-lookup"><span data-stu-id="6ac47-112">They organize large code projects.</span></span>  
  
-   <span data-ttu-id="6ac47-113">Se delimitan mediante el operador `.`.</span><span class="sxs-lookup"><span data-stu-id="6ac47-113">They are delimited by using the `.` operator.</span></span>  
  
-   <span data-ttu-id="6ac47-114">`using directive` obvia la necesidad de especificar el nombre del espacio de nombres para cada clase.</span><span class="sxs-lookup"><span data-stu-id="6ac47-114">The `using directive` obviates the requirement to specify the name of the namespace for every class.</span></span>  
  
-   <span data-ttu-id="6ac47-115">El espacio de nombres `global` es el espacio de nombres "raíz": `global::System` siempre hará referencia al espacio de nombres `System` de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6ac47-115">The `global` namespace is the "root" namespace: `global::System` will always refer to the .NET Framework namespace `System`.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="6ac47-116">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="6ac47-116">Related Sections</span></span>  
 <span data-ttu-id="6ac47-117">Vea los siguientes temas para obtener más información sobre los espacios de nombres:</span><span class="sxs-lookup"><span data-stu-id="6ac47-117">See the following topics for more information about namespaces:</span></span>  
  
-   [<span data-ttu-id="6ac47-118">Utilizar espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="6ac47-118">Using Namespaces</span></span>](../../../csharp/programming-guide/namespaces/using-namespaces.md)  
  
-   [<span data-ttu-id="6ac47-119">Cómo: Utilizar el alias del espacio de nombres global</span><span class="sxs-lookup"><span data-stu-id="6ac47-119">How to: Use the Global Namespace Alias</span></span>](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)  
  
-   [<span data-ttu-id="6ac47-120">Cómo: Utilizar el espacio de nombres My</span><span class="sxs-lookup"><span data-stu-id="6ac47-120">How to: Use the My Namespace</span></span>](../../../csharp/programming-guide/namespaces/how-to-use-the-my-namespace.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="6ac47-121">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="6ac47-121">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6ac47-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="6ac47-122">See Also</span></span>  
 [<span data-ttu-id="6ac47-123">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="6ac47-123">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="6ac47-124">Palabras clave del espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="6ac47-124">Namespace Keywords</span></span>](../../../csharp/language-reference/keywords/namespace-keywords.md)  
 [<span data-ttu-id="6ac47-125">using (directiva)</span><span class="sxs-lookup"><span data-stu-id="6ac47-125">using Directive</span></span>](../../../csharp/language-reference/keywords/using-directive.md)  
 [<span data-ttu-id="6ac47-126">Operador ::</span><span class="sxs-lookup"><span data-stu-id="6ac47-126">:: Operator</span></span>](../../../csharp/language-reference/operators/namespace-alias-qualifer.md)  
 [<span data-ttu-id="6ac47-127">. !</span><span class="sxs-lookup"><span data-stu-id="6ac47-127">. Operator</span></span>](../../../csharp/language-reference/operators/member-access-operator.md)
