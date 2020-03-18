---
title: 'this keyword: Referencia de C#'
description: Palabra clave this (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- this
- this_CSharpKeyword
helpviewer_keywords:
- this keyword [C#]
ms.assetid: d4f827fe-4710-410b-89b8-867dad44b8a3
ms.openlocfilehash: 2a2c487ad93e6fc75ecf95c541e859b8b60bb5b5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75715103"
---
# <a name="this-c-reference"></a><span data-ttu-id="dae2e-103">this (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="dae2e-103">this (C# Reference)</span></span>

<span data-ttu-id="dae2e-104">La palabra clave `this` hace referencia a la instancia actual de la clase y también se usa como modificador del primer parámetro de un método de extensión.</span><span class="sxs-lookup"><span data-stu-id="dae2e-104">The `this` keyword refers to the current instance of the class and is also used as a modifier of the first parameter of an extension method.</span></span>

> [!NOTE]
> <span data-ttu-id="dae2e-105">En este artículo se describe el uso de `this` con instancias de clase.</span><span class="sxs-lookup"><span data-stu-id="dae2e-105">This article discusses the use of `this` with class instances.</span></span> <span data-ttu-id="dae2e-106">Para obtener más información sobre su uso en métodos de extensión, vea [Métodos de extensión](../../programming-guide/classes-and-structs/extension-methods.md).</span><span class="sxs-lookup"><span data-stu-id="dae2e-106">For more information about its use in extension methods, see [Extension Methods](../../programming-guide/classes-and-structs/extension-methods.md).</span></span>

<span data-ttu-id="dae2e-107">A continuación se indican usos habituales de `this`:</span><span class="sxs-lookup"><span data-stu-id="dae2e-107">The following are common uses of `this`:</span></span>

- <span data-ttu-id="dae2e-108">Para calificar a miembros ocultos por nombres similares, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="dae2e-108">To qualify members hidden by similar names, for example:</span></span>

  [!code-csharp[csrefKeywordsAccess#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsAccess/CS/csrefKeywordsAccess.cs#4)]  

- <span data-ttu-id="dae2e-109">Para pasar un objeto como parámetro a otros métodos, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="dae2e-109">To pass an object as a parameter to other methods, for example:</span></span>

  ```csharp
  CalcTax(this);
  ```

- <span data-ttu-id="dae2e-110">Para declarar indizadores, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="dae2e-110">To declare indexers, for example:</span></span>

  [!code-csharp[csrefKeywordsAccess#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsAccess/CS/csrefKeywordsAccess.cs#5)]

<span data-ttu-id="dae2e-111">Las funciones miembro estáticas no tienen un puntero `this`, debido a que existen en el nivel de clase y no como parte de un objeto.</span><span class="sxs-lookup"><span data-stu-id="dae2e-111">Static member functions, because they exist at the class level and not as part of an object, do not have a `this` pointer.</span></span> <span data-ttu-id="dae2e-112">Es un error hacer referencia a `this` en un método estático.</span><span class="sxs-lookup"><span data-stu-id="dae2e-112">It is an error to refer to `this` in a static method.</span></span>

## <a name="example"></a><span data-ttu-id="dae2e-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dae2e-113">Example</span></span>

<span data-ttu-id="dae2e-114">En este ejemplo, se usa `this` para calificar los miembros de la clase `Employee`, `name` y `alias`, que están ocultos por nombres similares.</span><span class="sxs-lookup"><span data-stu-id="dae2e-114">In this example, `this` is used to qualify the `Employee` class members, `name` and `alias`, which are hidden by similar names.</span></span> <span data-ttu-id="dae2e-115">También se usa para pasar un objeto al método `CalcTax`, que pertenece a otra clase.</span><span class="sxs-lookup"><span data-stu-id="dae2e-115">It is also used to pass an object to the method `CalcTax`, which belongs to another class.</span></span>

[!code-csharp[csrefKeywordsAccess#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsAccess/CS/csrefKeywordsAccess.cs#3)]

## <a name="c-language-specification"></a><span data-ttu-id="dae2e-116">especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="dae2e-116">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="dae2e-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="dae2e-117">See also</span></span>

- [<span data-ttu-id="dae2e-118">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="dae2e-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="dae2e-119">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="dae2e-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="dae2e-120">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="dae2e-120">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="dae2e-121">base</span><span class="sxs-lookup"><span data-stu-id="dae2e-121">base</span></span>](base.md)
- [<span data-ttu-id="dae2e-122">Métodos</span><span class="sxs-lookup"><span data-stu-id="dae2e-122">Methods</span></span>](../../programming-guide/classes-and-structs/methods.md)
