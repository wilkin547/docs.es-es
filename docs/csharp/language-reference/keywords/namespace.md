---
title: namespace (Palabra clave) (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- namespace_CSharpKeyword
- namespace
helpviewer_keywords:
- namespace keyword [C#]
- scope [C#]
ms.assetid: 0a788423-9110-42e0-97d9-bda41ca4870f
ms.openlocfilehash: 2cdc1e33d86dae675411b571e553b467e5c1f891
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43856431"
---
# <a name="namespace-c-reference"></a><span data-ttu-id="46b13-102">espacio de nombres (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="46b13-102">namespace (C# Reference)</span></span>

<span data-ttu-id="46b13-103">La palabra clave `namespace` se usa para declarar un ámbito que contiene un conjunto de objetos relacionados.</span><span class="sxs-lookup"><span data-stu-id="46b13-103">The `namespace` keyword is used to declare a scope that contains a set of related objects.</span></span> <span data-ttu-id="46b13-104">Puede usar un espacio de nombres para organizar los elementos de código y crear tipos únicos globales.</span><span class="sxs-lookup"><span data-stu-id="46b13-104">You can use a namespace to organize code elements and to create globally unique types.</span></span>

[!code-csharp[csrefKeywordsNamespace#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#1)]

## <a name="remarks"></a><span data-ttu-id="46b13-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="46b13-105">Remarks</span></span>

<span data-ttu-id="46b13-106">En un espacio de nombres, se pueden declarar cero o más de los siguientes tipos:</span><span class="sxs-lookup"><span data-stu-id="46b13-106">Within a namespace, you can declare zero or more of the following types:</span></span>

- <span data-ttu-id="46b13-107">otro espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="46b13-107">another namespace</span></span>

- [<span data-ttu-id="46b13-108">class</span><span class="sxs-lookup"><span data-stu-id="46b13-108">class</span></span>](class.md)

- [<span data-ttu-id="46b13-109">interface</span><span class="sxs-lookup"><span data-stu-id="46b13-109">interface</span></span>](interface.md)

- [<span data-ttu-id="46b13-110">struct</span><span class="sxs-lookup"><span data-stu-id="46b13-110">struct</span></span>](struct.md)

- [<span data-ttu-id="46b13-111">enum</span><span class="sxs-lookup"><span data-stu-id="46b13-111">enum</span></span>](enum.md)

- [<span data-ttu-id="46b13-112">delegate</span><span class="sxs-lookup"><span data-stu-id="46b13-112">delegate</span></span>](delegate.md)

<span data-ttu-id="46b13-113">Tanto si se declara explícitamente un espacio de nombres en un archivo de código fuente de C# como si no, el compilador agrega un espacio de nombres predeterminado.</span><span class="sxs-lookup"><span data-stu-id="46b13-113">Whether or not you explicitly declare a namespace in a C# source file, the compiler adds a default namespace.</span></span> <span data-ttu-id="46b13-114">Este espacio de nombres sin nombre, que a veces se denomina espacio de nombres global, está presente en todos los archivos.</span><span class="sxs-lookup"><span data-stu-id="46b13-114">This unnamed namespace, sometimes referred to as the global namespace, is present in every file.</span></span> <span data-ttu-id="46b13-115">Todos los identificadores del espacio de nombres global están disponibles para su uso en un espacio de nombres con nombre.</span><span class="sxs-lookup"><span data-stu-id="46b13-115">Any identifier in the global namespace is available for use in a named namespace.</span></span>

<span data-ttu-id="46b13-116">Los espacios de nombres tienen implícitamente acceso público y esto no se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="46b13-116">Namespaces implicitly have public access and this is not modifiable.</span></span> <span data-ttu-id="46b13-117">Para ver una descripción de los modificadores de acceso que se pueden asignar a los elementos de un espacio de nombres, vea [Modificadores de acceso](access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="46b13-117">For a discussion of the access modifiers you can assign to elements in a namespace, see [Access Modifiers](access-modifiers.md).</span></span>

<span data-ttu-id="46b13-118">Es posible definir un espacio de nombres en dos o más declaraciones.</span><span class="sxs-lookup"><span data-stu-id="46b13-118">It is possible to define a namespace in two or more declarations.</span></span> <span data-ttu-id="46b13-119">Por ejemplo, en el ejemplo siguiente se definen dos clases como parte del espacio de nombres `MyCompany`:</span><span class="sxs-lookup"><span data-stu-id="46b13-119">For example, the following example defines two classes as part of the `MyCompany` namespace:</span></span>

[!code-csharp[csrefKeywordsNamespace#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#2)]

## <a name="example"></a><span data-ttu-id="46b13-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="46b13-120">Example</span></span>

<span data-ttu-id="46b13-121">En el ejemplo siguiente se muestra cómo llamar a un método estático en un espacio de nombres anidado.</span><span class="sxs-lookup"><span data-stu-id="46b13-121">The following example shows how to call a static method in a nested namespace.</span></span>

[!code-csharp[csrefKeywordsNamespace#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#3)]

## <a name="related-resources"></a><span data-ttu-id="46b13-122">Recursos relacionados</span><span class="sxs-lookup"><span data-stu-id="46b13-122">Related resources</span></span>

<span data-ttu-id="46b13-123">Para obtener más información sobre el uso de los espacios de nombres, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="46b13-123">For more information about using namespaces, see the following topics:</span></span>

- [<span data-ttu-id="46b13-124">Espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="46b13-124">Namespaces</span></span>](../../programming-guide/namespaces/index.md)

- [<span data-ttu-id="46b13-125">Utilizar espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="46b13-125">Using Namespaces</span></span>](../../programming-guide/namespaces/using-namespaces.md)

- [<span data-ttu-id="46b13-126">Cómo: Utilizar el alias del espacio de nombres global</span><span class="sxs-lookup"><span data-stu-id="46b13-126">How to: Use the Global Namespace Alias</span></span>](../../programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)

## <a name="c-language-specification"></a><span data-ttu-id="46b13-127">especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="46b13-127">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="46b13-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="46b13-128">See also</span></span>

- [<span data-ttu-id="46b13-129">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="46b13-129">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="46b13-130">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="46b13-130">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="46b13-131">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="46b13-131">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="46b13-132">Palabras clave del espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="46b13-132">Namespace Keywords</span></span>](namespace-keywords.md)
- [<span data-ttu-id="46b13-133">using</span><span class="sxs-lookup"><span data-stu-id="46b13-133">using</span></span>](using.md)