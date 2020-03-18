---
title: 'Palabra clave namespace: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- namespace_CSharpKeyword
- namespace
helpviewer_keywords:
- namespace keyword [C#]
- scope [C#]
ms.assetid: 0a788423-9110-42e0-97d9-bda41ca4870f
ms.openlocfilehash: b35f0a2a5cc0b2895b491d4ee24f89955f4b8fed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "77625805"
---
# <a name="namespace-c-reference"></a><span data-ttu-id="cf8d0-102">espacio de nombres (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="cf8d0-102">namespace (C# Reference)</span></span>

<span data-ttu-id="cf8d0-103">La palabra clave `namespace` se usa para declarar un ámbito que contiene un conjunto de objetos relacionados.</span><span class="sxs-lookup"><span data-stu-id="cf8d0-103">The `namespace` keyword is used to declare a scope that contains a set of related objects.</span></span> <span data-ttu-id="cf8d0-104">Puede usar un espacio de nombres para organizar los elementos de código y crear tipos únicos globales.</span><span class="sxs-lookup"><span data-stu-id="cf8d0-104">You can use a namespace to organize code elements and to create globally unique types.</span></span>

[!code-csharp[csrefKeywordsNamespace#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#1)]

## <a name="remarks"></a><span data-ttu-id="cf8d0-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cf8d0-105">Remarks</span></span>

<span data-ttu-id="cf8d0-106">En un espacio de nombres, se pueden declarar cero o más de los siguientes tipos:</span><span class="sxs-lookup"><span data-stu-id="cf8d0-106">Within a namespace, you can declare zero or more of the following types:</span></span>

- <span data-ttu-id="cf8d0-107">otro espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="cf8d0-107">another namespace</span></span>

- [<span data-ttu-id="cf8d0-108">class</span><span class="sxs-lookup"><span data-stu-id="cf8d0-108">class</span></span>](class.md)

- [<span data-ttu-id="cf8d0-109">interface</span><span class="sxs-lookup"><span data-stu-id="cf8d0-109">interface</span></span>](interface.md)

- [<span data-ttu-id="cf8d0-110">struct</span><span class="sxs-lookup"><span data-stu-id="cf8d0-110">struct</span></span>](../builtin-types/struct.md)

- [<span data-ttu-id="cf8d0-111">enum</span><span class="sxs-lookup"><span data-stu-id="cf8d0-111">enum</span></span>](../builtin-types/enum.md)

- [<span data-ttu-id="cf8d0-112">delegate</span><span class="sxs-lookup"><span data-stu-id="cf8d0-112">delegate</span></span>](../builtin-types/reference-types.md#the-delegate-type)

<span data-ttu-id="cf8d0-113">Tanto si se declara explícitamente un espacio de nombres en un archivo de código fuente de C# como si no, el compilador agrega un espacio de nombres predeterminado.</span><span class="sxs-lookup"><span data-stu-id="cf8d0-113">Whether or not you explicitly declare a namespace in a C# source file, the compiler adds a default namespace.</span></span> <span data-ttu-id="cf8d0-114">Este espacio de nombres sin nombre, que a veces se denomina espacio de nombres global, está presente en todos los archivos.</span><span class="sxs-lookup"><span data-stu-id="cf8d0-114">This unnamed namespace, sometimes referred to as the global namespace, is present in every file.</span></span> <span data-ttu-id="cf8d0-115">Todos los identificadores del espacio de nombres global están disponibles para su uso en un espacio de nombres con nombre.</span><span class="sxs-lookup"><span data-stu-id="cf8d0-115">Any identifier in the global namespace is available for use in a named namespace.</span></span>

<span data-ttu-id="cf8d0-116">Los espacios de nombres tienen implícitamente acceso público y esto no se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="cf8d0-116">Namespaces implicitly have public access and this is not modifiable.</span></span> <span data-ttu-id="cf8d0-117">Para ver una descripción de los modificadores de acceso que se pueden asignar a los elementos de un espacio de nombres, vea [Modificadores de acceso](access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="cf8d0-117">For a discussion of the access modifiers you can assign to elements in a namespace, see [Access Modifiers](access-modifiers.md).</span></span>

<span data-ttu-id="cf8d0-118">Es posible definir un espacio de nombres en dos o más declaraciones.</span><span class="sxs-lookup"><span data-stu-id="cf8d0-118">It is possible to define a namespace in two or more declarations.</span></span> <span data-ttu-id="cf8d0-119">Por ejemplo, en el ejemplo siguiente se definen dos clases como parte del espacio de nombres `MyCompany`:</span><span class="sxs-lookup"><span data-stu-id="cf8d0-119">For example, the following example defines two classes as part of the `MyCompany` namespace:</span></span>

[!code-csharp[csrefKeywordsNamespace#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#2)]

## <a name="example"></a><span data-ttu-id="cf8d0-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cf8d0-120">Example</span></span>

<span data-ttu-id="cf8d0-121">En el ejemplo siguiente se muestra cómo llamar a un método estático en un espacio de nombres anidado.</span><span class="sxs-lookup"><span data-stu-id="cf8d0-121">The following example shows how to call a static method in a nested namespace.</span></span>

[!code-csharp[csrefKeywordsNamespace#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#3)]

## <a name="c-language-specification"></a><span data-ttu-id="cf8d0-122">especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="cf8d0-122">C# language specification</span></span>

<span data-ttu-id="cf8d0-123">Para más información, vea la sección [Espacio de nombres](~/_csharplang/spec/namespaces.md) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="cf8d0-123">For more information, see the [Namespaces](~/_csharplang/spec/namespaces.md) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="cf8d0-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="cf8d0-124">See also</span></span>

- [<span data-ttu-id="cf8d0-125">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="cf8d0-125">C# reference</span></span>](../index.md)
- [<span data-ttu-id="cf8d0-126">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="cf8d0-126">C# keywords</span></span>](index.md)
- [<span data-ttu-id="cf8d0-127">using</span><span class="sxs-lookup"><span data-stu-id="cf8d0-127">using</span></span>](using-directive.md)
- [<span data-ttu-id="cf8d0-128">using static</span><span class="sxs-lookup"><span data-stu-id="cf8d0-128">using static</span></span>](using-static.md)
- [<span data-ttu-id="cf8d0-129">Calificadores de alias de espacio de nombres`::`</span><span class="sxs-lookup"><span data-stu-id="cf8d0-129">Namespace alias qualifier `::`</span></span>](../operators/namespace-alias-qualifier.md)
- [<span data-ttu-id="cf8d0-130">Espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="cf8d0-130">Namespaces</span></span>](../../programming-guide/namespaces/index.md)
