---
title: 'Palabra clave namespace: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- namespace_CSharpKeyword
- namespace
helpviewer_keywords:
- namespace keyword [C#]
- scope [C#]
ms.assetid: 0a788423-9110-42e0-97d9-bda41ca4870f
ms.openlocfilehash: b5c6b8081c188d5b184930222d54ad8f4b5d7a71
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53242768"
---
# <a name="namespace-c-reference"></a><span data-ttu-id="37d4e-102">espacio de nombres (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="37d4e-102">namespace (C# Reference)</span></span>

<span data-ttu-id="37d4e-103">La palabra clave `namespace` se usa para declarar un ámbito que contiene un conjunto de objetos relacionados.</span><span class="sxs-lookup"><span data-stu-id="37d4e-103">The `namespace` keyword is used to declare a scope that contains a set of related objects.</span></span> <span data-ttu-id="37d4e-104">Puede usar un espacio de nombres para organizar los elementos de código y crear tipos únicos globales.</span><span class="sxs-lookup"><span data-stu-id="37d4e-104">You can use a namespace to organize code elements and to create globally unique types.</span></span>

[!code-csharp[csrefKeywordsNamespace#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#1)]

## <a name="remarks"></a><span data-ttu-id="37d4e-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="37d4e-105">Remarks</span></span>

<span data-ttu-id="37d4e-106">En un espacio de nombres, se pueden declarar cero o más de los siguientes tipos:</span><span class="sxs-lookup"><span data-stu-id="37d4e-106">Within a namespace, you can declare zero or more of the following types:</span></span>

- <span data-ttu-id="37d4e-107">otro espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="37d4e-107">another namespace</span></span>

- [<span data-ttu-id="37d4e-108">class</span><span class="sxs-lookup"><span data-stu-id="37d4e-108">class</span></span>](class.md)

- [<span data-ttu-id="37d4e-109">interface</span><span class="sxs-lookup"><span data-stu-id="37d4e-109">interface</span></span>](interface.md)

- [<span data-ttu-id="37d4e-110">struct</span><span class="sxs-lookup"><span data-stu-id="37d4e-110">struct</span></span>](struct.md)

- [<span data-ttu-id="37d4e-111">enum</span><span class="sxs-lookup"><span data-stu-id="37d4e-111">enum</span></span>](enum.md)

- [<span data-ttu-id="37d4e-112">delegate</span><span class="sxs-lookup"><span data-stu-id="37d4e-112">delegate</span></span>](delegate.md)

<span data-ttu-id="37d4e-113">Tanto si se declara explícitamente un espacio de nombres en un archivo de código fuente de C# como si no, el compilador agrega un espacio de nombres predeterminado.</span><span class="sxs-lookup"><span data-stu-id="37d4e-113">Whether or not you explicitly declare a namespace in a C# source file, the compiler adds a default namespace.</span></span> <span data-ttu-id="37d4e-114">Este espacio de nombres sin nombre, que a veces se denomina espacio de nombres global, está presente en todos los archivos.</span><span class="sxs-lookup"><span data-stu-id="37d4e-114">This unnamed namespace, sometimes referred to as the global namespace, is present in every file.</span></span> <span data-ttu-id="37d4e-115">Todos los identificadores del espacio de nombres global están disponibles para su uso en un espacio de nombres con nombre.</span><span class="sxs-lookup"><span data-stu-id="37d4e-115">Any identifier in the global namespace is available for use in a named namespace.</span></span>

<span data-ttu-id="37d4e-116">Los espacios de nombres tienen implícitamente acceso público y esto no se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="37d4e-116">Namespaces implicitly have public access and this is not modifiable.</span></span> <span data-ttu-id="37d4e-117">Para ver una descripción de los modificadores de acceso que se pueden asignar a los elementos de un espacio de nombres, vea [Modificadores de acceso](access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="37d4e-117">For a discussion of the access modifiers you can assign to elements in a namespace, see [Access Modifiers](access-modifiers.md).</span></span>

<span data-ttu-id="37d4e-118">Es posible definir un espacio de nombres en dos o más declaraciones.</span><span class="sxs-lookup"><span data-stu-id="37d4e-118">It is possible to define a namespace in two or more declarations.</span></span> <span data-ttu-id="37d4e-119">Por ejemplo, en el ejemplo siguiente se definen dos clases como parte del espacio de nombres `MyCompany`:</span><span class="sxs-lookup"><span data-stu-id="37d4e-119">For example, the following example defines two classes as part of the `MyCompany` namespace:</span></span>

[!code-csharp[csrefKeywordsNamespace#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#2)]

## <a name="example"></a><span data-ttu-id="37d4e-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="37d4e-120">Example</span></span>

<span data-ttu-id="37d4e-121">En el ejemplo siguiente se muestra cómo llamar a un método estático en un espacio de nombres anidado.</span><span class="sxs-lookup"><span data-stu-id="37d4e-121">The following example shows how to call a static method in a nested namespace.</span></span>

[!code-csharp[csrefKeywordsNamespace#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#3)]

## <a name="related-resources"></a><span data-ttu-id="37d4e-122">Recursos relacionados</span><span class="sxs-lookup"><span data-stu-id="37d4e-122">Related resources</span></span>

<span data-ttu-id="37d4e-123">Para obtener más información sobre el uso de los espacios de nombres, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="37d4e-123">For more information about using namespaces, see the following topics:</span></span>

- [<span data-ttu-id="37d4e-124">Espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="37d4e-124">Namespaces</span></span>](../../programming-guide/namespaces/index.md)

- [<span data-ttu-id="37d4e-125">Utilizar espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="37d4e-125">Using Namespaces</span></span>](../../programming-guide/namespaces/using-namespaces.md)

- [<span data-ttu-id="37d4e-126">Cómo: Utilizar el alias del espacio de nombres global</span><span class="sxs-lookup"><span data-stu-id="37d4e-126">How to: Use the Global Namespace Alias</span></span>](../../programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)

## <a name="c-language-specification"></a><span data-ttu-id="37d4e-127">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="37d4e-127">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="37d4e-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="37d4e-128">See also</span></span>

- [<span data-ttu-id="37d4e-129">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="37d4e-129">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="37d4e-130">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="37d4e-130">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="37d4e-131">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="37d4e-131">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="37d4e-132">Palabras clave del espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="37d4e-132">Namespace Keywords</span></span>](namespace-keywords.md)
- [<span data-ttu-id="37d4e-133">using</span><span class="sxs-lookup"><span data-stu-id="37d4e-133">using</span></span>](using.md)