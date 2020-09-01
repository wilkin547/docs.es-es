---
description: 'Modificador sealed: Referencia de C#'
title: 'Modificador sealed: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- sealed
- sealed_CSharpKeyword
helpviewer_keywords:
- sealed keyword [C#]
ms.assetid: 8e4ed5d3-10be-47db-9488-0da2008e6f3f
ms.openlocfilehash: 5b945503c6f6546f571a2422ae77760da0363b08
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89136972"
---
# <a name="sealed-c-reference"></a><span data-ttu-id="686d4-103">sealed (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="686d4-103">sealed (C# Reference)</span></span>

<span data-ttu-id="686d4-104">Cuando se aplica a una clase, el modificador `sealed` impide que otras clases hereden de ella.</span><span class="sxs-lookup"><span data-stu-id="686d4-104">When applied to a class, the `sealed` modifier prevents other classes from inheriting from it.</span></span> <span data-ttu-id="686d4-105">En el ejemplo siguiente, la clase `B` hereda de la clase `A`, pero ninguna clase puede heredar de la clase `B`.</span><span class="sxs-lookup"><span data-stu-id="686d4-105">In the following example, class `B` inherits from class `A`, but no class can inherit from class `B`.</span></span>

```csharp
class A {}
sealed class B : A {}
```

<span data-ttu-id="686d4-106">También puede usar el modificador `sealed` en un método o propiedad que invalida un método o propiedad virtual en una clase base.</span><span class="sxs-lookup"><span data-stu-id="686d4-106">You can also use the `sealed` modifier on a method or property that overrides a virtual method or property in a base class.</span></span> <span data-ttu-id="686d4-107">De este modo, puede permitir que las clases deriven de su clase e impedir que invaliden determinados métodos o propiedades virtuales.</span><span class="sxs-lookup"><span data-stu-id="686d4-107">This enables you to allow classes to derive from your class and prevent them from overriding specific virtual methods or properties.</span></span>

## <a name="example"></a><span data-ttu-id="686d4-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="686d4-108">Example</span></span>

<span data-ttu-id="686d4-109">En el ejemplo siguiente, `Z` hereda de `Y` pero `Z` no puede invalidar la función virtual `F` que se declara en `X` y se sella en `Y`.</span><span class="sxs-lookup"><span data-stu-id="686d4-109">In the following example, `Z` inherits from `Y` but `Z` cannot override the virtual function `F` that is declared in `X` and sealed in `Y`.</span></span>

[!code-csharp[csrefKeywordsModifiers#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#16)]

<span data-ttu-id="686d4-110">Al definir nuevos métodos o propiedades en una clase, puede impedir que las clases derivadas los invaliden. Para ello, no los declare como [virtuales](virtual.md).</span><span class="sxs-lookup"><span data-stu-id="686d4-110">When you define new methods or properties in a class, you can prevent deriving classes from overriding them by not declaring them as [virtual](virtual.md).</span></span>

<span data-ttu-id="686d4-111">Es un error usar el modificador [abstract](abstract.md) con una clase sellada, porque una clase abstracta debe heredarla una clase que proporcione una implementación de los métodos o propiedades abstractos.</span><span class="sxs-lookup"><span data-stu-id="686d4-111">It is an error to use the [abstract](abstract.md) modifier with a sealed class, because an abstract class must be inherited by a class that provides an implementation of the abstract methods or properties.</span></span>

<span data-ttu-id="686d4-112">Cuando se aplica a un método o propiedad, el modificador `sealed` siempre se debe usar con [override](override.md).</span><span class="sxs-lookup"><span data-stu-id="686d4-112">When applied to a method or property, the `sealed` modifier must always be used with [override](override.md).</span></span>

<span data-ttu-id="686d4-113">Dado que los structs están sellados implícitamente, no puede heredarse.</span><span class="sxs-lookup"><span data-stu-id="686d4-113">Because structs are implicitly sealed, they cannot be inherited.</span></span>

<span data-ttu-id="686d4-114">Para obtener más información, vea [Herencia](../../programming-guide/classes-and-structs/inheritance.md).</span><span class="sxs-lookup"><span data-stu-id="686d4-114">For more information, see [Inheritance](../../programming-guide/classes-and-structs/inheritance.md).</span></span>

<span data-ttu-id="686d4-115">Para obtener más ejemplos, vea [Clases y miembros de clase abstractos y sellados](../../programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="686d4-115">For more examples, see [Abstract and Sealed Classes and Class Members](../../programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).</span></span>

## <a name="example"></a><span data-ttu-id="686d4-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="686d4-116">Example</span></span>

[!code-csharp[csrefKeywordsModifiers#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#17)]

<span data-ttu-id="686d4-117">En el ejemplo anterior, podría intentar heredar de la clase sellada mediante la instrucción siguiente:</span><span class="sxs-lookup"><span data-stu-id="686d4-117">In the previous example, you might try to inherit from the sealed class by using the following statement:</span></span>

`class MyDerivedC: SealedClass {}   // Error`

<span data-ttu-id="686d4-118">El resultado es un mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="686d4-118">The result is an error message:</span></span>

`'MyDerivedC': cannot derive from sealed type 'SealedClass'`

## <a name="remarks"></a><span data-ttu-id="686d4-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="686d4-119">Remarks</span></span>

<span data-ttu-id="686d4-120">Para determinar si se debe sellar una clase, un método o una propiedad, por lo general debe tener en cuenta los dos puntos siguientes:</span><span class="sxs-lookup"><span data-stu-id="686d4-120">To determine whether to seal a class, method, or property, you should generally consider the following two points:</span></span>

- <span data-ttu-id="686d4-121">Las posibles ventajas que podrían obtener las clases derivadas con la capacidad de personalizar la clase.</span><span class="sxs-lookup"><span data-stu-id="686d4-121">The potential benefits that deriving classes might gain through the ability to customize your class.</span></span>

- <span data-ttu-id="686d4-122">La posibilidad de que las clases derivadas modifiquen las clases de tal manera que no funcionen correctamente o del modo esperado.</span><span class="sxs-lookup"><span data-stu-id="686d4-122">The potential that deriving classes could modify your classes in such a way that they would no longer work correctly or as expected.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="686d4-123">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="686d4-123">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="686d4-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="686d4-124">See also</span></span>

- [<span data-ttu-id="686d4-125">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="686d4-125">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="686d4-126">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="686d4-126">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="686d4-127">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="686d4-127">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="686d4-128">Clases estáticas y sus miembros</span><span class="sxs-lookup"><span data-stu-id="686d4-128">Static Classes and Static Class Members</span></span>](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md)
- [<span data-ttu-id="686d4-129">Clases y miembros de clase abstractos y sellados</span><span class="sxs-lookup"><span data-stu-id="686d4-129">Abstract and Sealed Classes and Class Members</span></span>](../../programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)
- [<span data-ttu-id="686d4-130">Modificadores de acceso</span><span class="sxs-lookup"><span data-stu-id="686d4-130">Access Modifiers</span></span>](../../programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="686d4-131">Modificadores</span><span class="sxs-lookup"><span data-stu-id="686d4-131">Modifiers</span></span>](index.md)
- [<span data-ttu-id="686d4-132">override</span><span class="sxs-lookup"><span data-stu-id="686d4-132">override</span></span>](override.md)
- [<span data-ttu-id="686d4-133">virtual</span><span class="sxs-lookup"><span data-stu-id="686d4-133">virtual</span></span>](virtual.md)
