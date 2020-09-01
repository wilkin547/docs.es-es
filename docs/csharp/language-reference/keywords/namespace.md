---
description: 'Palabra clave namespace: Referencia de C#'
title: 'Palabra clave namespace: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- namespace_CSharpKeyword
- namespace
helpviewer_keywords:
- namespace keyword [C#]
- scope [C#]
ms.assetid: 0a788423-9110-42e0-97d9-bda41ca4870f
ms.openlocfilehash: a6cfd1c3d37cbdef1f0dd72ddca85ce91f2e183b
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89139585"
---
# <a name="namespace-c-reference"></a><span data-ttu-id="30797-103">espacio de nombres (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="30797-103">namespace (C# Reference)</span></span>

<span data-ttu-id="30797-104">La palabra clave `namespace` se usa para declarar un ámbito que contiene un conjunto de objetos relacionados.</span><span class="sxs-lookup"><span data-stu-id="30797-104">The `namespace` keyword is used to declare a scope that contains a set of related objects.</span></span> <span data-ttu-id="30797-105">Puede usar un espacio de nombres para organizar los elementos de código y crear tipos únicos globales.</span><span class="sxs-lookup"><span data-stu-id="30797-105">You can use a namespace to organize code elements and to create globally unique types.</span></span>

[!code-csharp[csrefKeywordsNamespace#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#1)]

## <a name="remarks"></a><span data-ttu-id="30797-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="30797-106">Remarks</span></span>

<span data-ttu-id="30797-107">En un espacio de nombres, se pueden declarar cero o más de los siguientes tipos:</span><span class="sxs-lookup"><span data-stu-id="30797-107">Within a namespace, you can declare zero or more of the following types:</span></span>

- <span data-ttu-id="30797-108">otro espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="30797-108">another namespace</span></span>

- [<span data-ttu-id="30797-109">class</span><span class="sxs-lookup"><span data-stu-id="30797-109">class</span></span>](class.md)

- [<span data-ttu-id="30797-110">interface</span><span class="sxs-lookup"><span data-stu-id="30797-110">interface</span></span>](interface.md)

- [<span data-ttu-id="30797-111">struct</span><span class="sxs-lookup"><span data-stu-id="30797-111">struct</span></span>](../builtin-types/struct.md)

- [<span data-ttu-id="30797-112">enum</span><span class="sxs-lookup"><span data-stu-id="30797-112">enum</span></span>](../builtin-types/enum.md)

- [<span data-ttu-id="30797-113">delegate</span><span class="sxs-lookup"><span data-stu-id="30797-113">delegate</span></span>](../builtin-types/reference-types.md#the-delegate-type)

<span data-ttu-id="30797-114">Tanto si se declara explícitamente un espacio de nombres en un archivo de código fuente de C# como si no, el compilador agrega un espacio de nombres predeterminado.</span><span class="sxs-lookup"><span data-stu-id="30797-114">Whether or not you explicitly declare a namespace in a C# source file, the compiler adds a default namespace.</span></span> <span data-ttu-id="30797-115">Este espacio de nombres sin nombre, que a veces se denomina espacio de nombres global, está presente en todos los archivos.</span><span class="sxs-lookup"><span data-stu-id="30797-115">This unnamed namespace, sometimes referred to as the global namespace, is present in every file.</span></span> <span data-ttu-id="30797-116">Todos los identificadores del espacio de nombres global están disponibles para su uso en un espacio de nombres con nombre.</span><span class="sxs-lookup"><span data-stu-id="30797-116">Any identifier in the global namespace is available for use in a named namespace.</span></span>

<span data-ttu-id="30797-117">Los espacios de nombres tienen implícitamente acceso público y esto no se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="30797-117">Namespaces implicitly have public access and this is not modifiable.</span></span> <span data-ttu-id="30797-118">Para ver una descripción de los modificadores de acceso que se pueden asignar a los elementos de un espacio de nombres, vea [Modificadores de acceso](access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="30797-118">For a discussion of the access modifiers you can assign to elements in a namespace, see [Access Modifiers](access-modifiers.md).</span></span>

<span data-ttu-id="30797-119">Es posible definir un espacio de nombres en dos o más declaraciones.</span><span class="sxs-lookup"><span data-stu-id="30797-119">It is possible to define a namespace in two or more declarations.</span></span> <span data-ttu-id="30797-120">Por ejemplo, en el ejemplo siguiente se definen dos clases como parte del espacio de nombres `MyCompany`:</span><span class="sxs-lookup"><span data-stu-id="30797-120">For example, the following example defines two classes as part of the `MyCompany` namespace:</span></span>

[!code-csharp[csrefKeywordsNamespace#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#2)]

## <a name="example"></a><span data-ttu-id="30797-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="30797-121">Example</span></span>

<span data-ttu-id="30797-122">En el ejemplo siguiente se muestra cómo llamar a un método estático en un espacio de nombres anidado.</span><span class="sxs-lookup"><span data-stu-id="30797-122">The following example shows how to call a static method in a nested namespace.</span></span>

[!code-csharp[csrefKeywordsNamespace#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#3)]

## <a name="c-language-specification"></a><span data-ttu-id="30797-123">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="30797-123">C# language specification</span></span>

<span data-ttu-id="30797-124">Para más información, vea la sección [Espacio de nombres](~/_csharplang/spec/namespaces.md) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="30797-124">For more information, see the [Namespaces](~/_csharplang/spec/namespaces.md) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="30797-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="30797-125">See also</span></span>

- [<span data-ttu-id="30797-126">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="30797-126">C# reference</span></span>](../index.md)
- [<span data-ttu-id="30797-127">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="30797-127">C# keywords</span></span>](index.md)
- [<span data-ttu-id="30797-128">using</span><span class="sxs-lookup"><span data-stu-id="30797-128">using</span></span>](using-directive.md)
- [<span data-ttu-id="30797-129">using static</span><span class="sxs-lookup"><span data-stu-id="30797-129">using static</span></span>](using-static.md)
- [<span data-ttu-id="30797-130">Calificadores de alias de espacio de nombres`::`</span><span class="sxs-lookup"><span data-stu-id="30797-130">Namespace alias qualifier `::`</span></span>](../operators/namespace-alias-qualifier.md)
- [<span data-ttu-id="30797-131">Espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="30797-131">Namespaces</span></span>](../../programming-guide/namespaces/index.md)
