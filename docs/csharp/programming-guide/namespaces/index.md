---
title: 'Espacios de nombres: Guía de programación de C#'
description: Obtenga información sobre el uso de los espacios de nombres en la programación de C#. Vea información general sobre las propiedades de espacio de nombres y otros recursos.
ms.date: 08/21/2018
helpviewer_keywords:
- C# language, namespaces
- namespaces [C#]
ms.assetid: b1c4ab46-3fad-4ffa-9deb-dd50a2d8c65a
ms.openlocfilehash: 41a666fd5f368e6990e08a36700e18f648939213
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/10/2020
ms.locfileid: "94440346"
---
# <a name="namespaces-c-programming-guide"></a><span data-ttu-id="2df0f-104">Espacios de nombres (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="2df0f-104">Namespaces (C# Programming Guide)</span></span>

<span data-ttu-id="2df0f-105">Los espacios de nombres se usan mucho en programación de C# de dos maneras.</span><span class="sxs-lookup"><span data-stu-id="2df0f-105">Namespaces are heavily used in C# programming in two ways.</span></span> <span data-ttu-id="2df0f-106">En primer lugar, .NET usa espacios de nombres para organizar sus clases de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="2df0f-106">First, .NET uses namespaces to organize its many classes, as follows:</span></span>  

[!code-csharp[csProgGuide#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#22)]

<span data-ttu-id="2df0f-107"><xref:System> es un espacio de nombres y <xref:System.Console> es una clase de ese espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="2df0f-107"><xref:System> is a namespace and <xref:System.Console> is a class in that namespace.</span></span> <span data-ttu-id="2df0f-108">La palabra clave `using` se puede usar para que no se necesite el nombre completo, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2df0f-108">The `using` keyword can be used so that the complete name is not required, as in the following example:</span></span>

[!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]

[!code-csharp[csProgGuide#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#23)]

<span data-ttu-id="2df0f-109">Para más información, vea [using (Directiva)](../../language-reference/keywords/using-directive.md).</span><span class="sxs-lookup"><span data-stu-id="2df0f-109">For more information, see the [using Directive](../../language-reference/keywords/using-directive.md).</span></span>

<span data-ttu-id="2df0f-110">En segundo lugar, declarar sus propios espacios de nombres puede ayudarle a controlar el ámbito de nombres de clase y método en proyectos de programación grandes.</span><span class="sxs-lookup"><span data-stu-id="2df0f-110">Second, declaring your own namespaces can help you control the scope of class and method names in larger programming projects.</span></span> <span data-ttu-id="2df0f-111">Use la palabra clave [namespace](../../language-reference/keywords/namespace.md) para declarar un espacio de nombres, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2df0f-111">Use the [namespace](../../language-reference/keywords/namespace.md) keyword to declare a namespace, as in the following example:</span></span>

[!code-csharp[csProgGuideNamespaces#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#6)]

<span data-ttu-id="2df0f-112">El nombre del espacio de nombres debe ser un [nombre de identificador](../inside-a-program/identifier-names.md) de C# válido.</span><span class="sxs-lookup"><span data-stu-id="2df0f-112">The name of the namespace must be a valid C# [identifier name](../inside-a-program/identifier-names.md).</span></span>

## <a name="namespaces-overview"></a><span data-ttu-id="2df0f-113">Información general sobre los espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="2df0f-113">Namespaces overview</span></span>

<span data-ttu-id="2df0f-114">Los espacios de nombres tienen las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="2df0f-114">Namespaces have the following properties:</span></span>

- <span data-ttu-id="2df0f-115">Organizan proyectos de código de gran tamaño.</span><span class="sxs-lookup"><span data-stu-id="2df0f-115">They organize large code projects.</span></span>
- <span data-ttu-id="2df0f-116">Se delimitan mediante el operador `.`.</span><span class="sxs-lookup"><span data-stu-id="2df0f-116">They are delimited by using the `.` operator.</span></span>
- <span data-ttu-id="2df0f-117">La directiva `using` obvia la necesidad de especificar el nombre del espacio de nombres para cada clase.</span><span class="sxs-lookup"><span data-stu-id="2df0f-117">The `using` directive obviates the requirement to specify the name of the namespace for every class.</span></span>
- <span data-ttu-id="2df0f-118">El espacio de nombres `global` es el espacio de nombres "raíz": `global::System` siempre hará referencia al espacio de nombres <xref:System> de .NET.</span><span class="sxs-lookup"><span data-stu-id="2df0f-118">The `global` namespace is the "root" namespace: `global::System` will always refer to the .NET <xref:System> namespace.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="2df0f-119">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="2df0f-119">C# language specification</span></span>

<span data-ttu-id="2df0f-120">Para más información, vea la sección [Espacio de nombres](~/_csharplang/spec/namespaces.md) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="2df0f-120">For more information, see the [Namespaces](~/_csharplang/spec/namespaces.md) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2df0f-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="2df0f-121">See also</span></span>

- [<span data-ttu-id="2df0f-122">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="2df0f-122">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="2df0f-123">Utilizar espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="2df0f-123">Using Namespaces</span></span>](using-namespaces.md)
- [<span data-ttu-id="2df0f-124">Procedimiento para usar el espacio de nombres My</span><span class="sxs-lookup"><span data-stu-id="2df0f-124">How to use the My namespace</span></span>](how-to-use-the-my-namespace.md)
- [<span data-ttu-id="2df0f-125">Nombres de identificador</span><span class="sxs-lookup"><span data-stu-id="2df0f-125">Identifier names</span></span>](../inside-a-program/identifier-names.md)
- [<span data-ttu-id="2df0f-126">using (directiva)</span><span class="sxs-lookup"><span data-stu-id="2df0f-126">using Directive</span></span>](../../language-reference/keywords/using-directive.md)
- [<span data-ttu-id="2df0f-127">:: !</span><span class="sxs-lookup"><span data-stu-id="2df0f-127">:: Operator</span></span>](../../language-reference/operators/namespace-alias-qualifier.md)
