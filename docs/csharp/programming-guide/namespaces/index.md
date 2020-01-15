---
title: 'Espacios de nombres: Guía de programación de C#'
ms.date: 08/21/2018
helpviewer_keywords:
- C# language, namespaces
- namespaces [C#]
ms.assetid: b1c4ab46-3fad-4ffa-9deb-dd50a2d8c65a
ms.openlocfilehash: 21452e259596c9ab10b3d653ec1d8fb90fad131d
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937611"
---
# <a name="namespaces-c-programming-guide"></a><span data-ttu-id="895f5-102">Espacios de nombres (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="895f5-102">Namespaces (C# Programming Guide)</span></span>

<span data-ttu-id="895f5-103">Los espacios de nombres se usan mucho en programación de C# de dos maneras.</span><span class="sxs-lookup"><span data-stu-id="895f5-103">Namespaces are heavily used in C# programming in two ways.</span></span> <span data-ttu-id="895f5-104">En primer lugar, .NET usa espacios de nombres para organizar sus clases de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="895f5-104">First, .NET uses namespaces to organize its many classes, as follows:</span></span>  

[!code-csharp[csProgGuide#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#22)]

<span data-ttu-id="895f5-105"><xref:System> es un espacio de nombres y <xref:System.Console> es una clase de ese espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="895f5-105"><xref:System> is a namespace and <xref:System.Console> is a class in that namespace.</span></span> <span data-ttu-id="895f5-106">La palabra clave `using` se puede usar para que no se necesite el nombre completo, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="895f5-106">The `using` keyword can be used so that the complete name is not required, as in the following example:</span></span>

[!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]

[!code-csharp[csProgGuide#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#25)]

<span data-ttu-id="895f5-107">Para más información, vea [using (Directiva)](../../language-reference/keywords/using-directive.md).</span><span class="sxs-lookup"><span data-stu-id="895f5-107">For more information, see the [using Directive](../../language-reference/keywords/using-directive.md).</span></span>

<span data-ttu-id="895f5-108">En segundo lugar, declarar sus propios espacios de nombres puede ayudarle a controlar el ámbito de nombres de clase y método en proyectos de programación grandes.</span><span class="sxs-lookup"><span data-stu-id="895f5-108">Second, declaring your own namespaces can help you control the scope of class and method names in larger programming projects.</span></span> <span data-ttu-id="895f5-109">Use la palabra clave [namespace](../../language-reference/keywords/namespace.md) para declarar un espacio de nombres, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="895f5-109">Use the [namespace](../../language-reference/keywords/namespace.md) keyword to declare a namespace, as in the following example:</span></span>

[!code-csharp[csProgGuideNamespaces#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#6)]

<span data-ttu-id="895f5-110">El nombre del espacio de nombres debe ser un [nombre de identificador](../inside-a-program/identifier-names.md) de C# válido.</span><span class="sxs-lookup"><span data-stu-id="895f5-110">The name of the namespace must be a valid C# [identifier name](../inside-a-program/identifier-names.md).</span></span>

## <a name="namespaces-overview"></a><span data-ttu-id="895f5-111">Información general sobre los espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="895f5-111">Namespaces overview</span></span>

<span data-ttu-id="895f5-112">Los espacios de nombres tienen las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="895f5-112">Namespaces have the following properties:</span></span>

- <span data-ttu-id="895f5-113">Organizan proyectos de código de gran tamaño.</span><span class="sxs-lookup"><span data-stu-id="895f5-113">They organize large code projects.</span></span>
- <span data-ttu-id="895f5-114">Se delimitan mediante el operador `.`.</span><span class="sxs-lookup"><span data-stu-id="895f5-114">They are delimited by using the `.` operator.</span></span>
- <span data-ttu-id="895f5-115">La directiva `using` obvia la necesidad de especificar el nombre del espacio de nombres para cada clase.</span><span class="sxs-lookup"><span data-stu-id="895f5-115">The `using` directive obviates the requirement to specify the name of the namespace for every class.</span></span>
- <span data-ttu-id="895f5-116">El espacio de nombres `global` es el espacio de nombres "raíz": `global::System` siempre hará referencia al espacio de nombres <xref:System> de .NET.</span><span class="sxs-lookup"><span data-stu-id="895f5-116">The `global` namespace is the "root" namespace: `global::System` will always refer to the .NET <xref:System> namespace.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="895f5-117">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="895f5-117">C# language specification</span></span>

<span data-ttu-id="895f5-118">Para más información, vea la sección [Espacio de nombres](~/_csharplang/spec/namespaces.md) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="895f5-118">For more information, see the [Namespaces](~/_csharplang/spec/namespaces.md) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="895f5-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="895f5-119">See also</span></span>

- [<span data-ttu-id="895f5-120">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="895f5-120">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="895f5-121">Utilizar espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="895f5-121">Using Namespaces</span></span>](using-namespaces.md)
- [<span data-ttu-id="895f5-122">Procedimiento para usar el espacio de nombres My</span><span class="sxs-lookup"><span data-stu-id="895f5-122">How to use the My namespace</span></span>](how-to-use-the-my-namespace.md)
- [<span data-ttu-id="895f5-123">Nombres de identificador</span><span class="sxs-lookup"><span data-stu-id="895f5-123">Identifier names</span></span>](../inside-a-program/identifier-names.md)
- [<span data-ttu-id="895f5-124">using (directiva)</span><span class="sxs-lookup"><span data-stu-id="895f5-124">using Directive</span></span>](../../language-reference/keywords/using-directive.md)
- [<span data-ttu-id="895f5-125">:: !</span><span class="sxs-lookup"><span data-stu-id="895f5-125">:: Operator</span></span>](../../language-reference/operators/namespace-alias-qualifier.md)
