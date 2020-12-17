---
title: 'Tipos anidados: Guía de programación de C#'
description: Un tipo definido en una clase, estructura o interfaz se denomina tipo anidado en C#.
ms.date: 02/08/2020
helpviewer_keywords:
- nested types [C#]
ms.assetid: f2e1b315-e3d1-48ce-977f-7bae0960ba99
ms.openlocfilehash: 0741ae88103b16ce34fd5a38b789beaf428e734a
ms.sourcegitcommit: 0014aa4d5cb2da56a70e03fc68f663d64df5247a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2020
ms.locfileid: "96918585"
---
# <a name="nested-types-c-programming-guide"></a><span data-ttu-id="9b898-103">Tipos anidados (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="9b898-103">Nested Types (C# Programming Guide)</span></span>

<span data-ttu-id="9b898-104">Un tipo definido en una [clase](../../language-reference/keywords/class.md), [estructura](../../language-reference/builtin-types/struct.md), [delegado](../../language-reference/builtin-types/reference-types.md#the-delegate-type) o [interfaz](../../language-reference/keywords/interface.md) se denomina tipo anidado.</span><span class="sxs-lookup"><span data-stu-id="9b898-104">A type defined within a [class](../../language-reference/keywords/class.md), [struct](../../language-reference/builtin-types/struct.md), [delegate](../../language-reference/builtin-types/reference-types.md#the-delegate-type) or [interface](../../language-reference/keywords/interface.md) is called a nested type.</span></span> <span data-ttu-id="9b898-105">Por ejemplo</span><span class="sxs-lookup"><span data-stu-id="9b898-105">For example</span></span>

[!code-csharp[DeclareNestedClass](~/samples/snippets/csharp/objectoriented/nestedtypes.cs#DeclareNestedClass)]

<span data-ttu-id="9b898-106">Con independencia de si el tipo externo es una clase, una interfaz o una estructura, los tipos anidados se establecen de manera predeterminada en [private](../../language-reference/keywords/private.md); solo son accesibles desde su tipo contenedor.</span><span class="sxs-lookup"><span data-stu-id="9b898-106">Regardless of whether the outer type is a class, interface, or struct, nested types default to [private](../../language-reference/keywords/private.md); they are accessible only from their containing type.</span></span> <span data-ttu-id="9b898-107">En el ejemplo anterior, la clase `Nested` es inaccesible a los tipos externos.</span><span class="sxs-lookup"><span data-stu-id="9b898-107">In the previous example, the `Nested` class is inaccessible to external types.</span></span>

<span data-ttu-id="9b898-108">También puede especificar un [modificador de acceso](../../language-reference/keywords/access-modifiers.md) para definir la accesibilidad de un tipo anidado, de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="9b898-108">You can also specify an [access modifier](../../language-reference/keywords/access-modifiers.md) to define the accessibility of a nested type, as follows:</span></span>

- <span data-ttu-id="9b898-109">Los tipos anidados de una **clase** pueden ser [public](../../language-reference/keywords/public.md), [protected](../../language-reference/keywords/protected.md), [internal](../../language-reference/keywords/internal.md), [protected internal](../../language-reference/keywords/protected-internal.md), [private](../../language-reference/keywords/private.md) o [private protected](../../language-reference/keywords/private-protected.md).</span><span class="sxs-lookup"><span data-stu-id="9b898-109">Nested types of a **class** can be [public](../../language-reference/keywords/public.md), [protected](../../language-reference/keywords/protected.md), [internal](../../language-reference/keywords/internal.md), [protected internal](../../language-reference/keywords/protected-internal.md), [private](../../language-reference/keywords/private.md) or [private protected](../../language-reference/keywords/private-protected.md).</span></span>

   <span data-ttu-id="9b898-110">En cambio, al definir una clase anidada `protected`, `protected internal` o `private protected` dentro de una [clase sellada](../../language-reference/keywords/sealed.md), se genera una advertencia del compilador [CS0628](../../misc/cs0628.md), "Nuevo miembro protegido declarado en la clase sealed".</span><span class="sxs-lookup"><span data-stu-id="9b898-110">However, defining a `protected`, `protected internal` or `private protected` nested class inside a [sealed class](../../language-reference/keywords/sealed.md) generates compiler warning [CS0628](../../misc/cs0628.md), "new protected member declared in sealed class."</span></span>
  
- <span data-ttu-id="9b898-111">Los tipos anidados de un **struct** pueden ser [public](../../language-reference/keywords/public.md), [internal](../../language-reference/keywords/internal.md) o [private](../../language-reference/keywords/private.md).</span><span class="sxs-lookup"><span data-stu-id="9b898-111">Nested types of a **struct** can be [public](../../language-reference/keywords/public.md), [internal](../../language-reference/keywords/internal.md), or [private](../../language-reference/keywords/private.md).</span></span>

<span data-ttu-id="9b898-112">En el ejemplo siguiente se convierte la clase `Nested` en public:</span><span class="sxs-lookup"><span data-stu-id="9b898-112">The following example makes the `Nested` class public:</span></span>

[!code-csharp[PublicNestedClass](~/samples/snippets/csharp/objectoriented/nestedtypes.cs#PublicNestedClass)]

<span data-ttu-id="9b898-113">El tipo anidado o interno puede tener acceso al tipo contenedor o externo.</span><span class="sxs-lookup"><span data-stu-id="9b898-113">The nested, or inner, type can access the containing, or outer, type.</span></span> <span data-ttu-id="9b898-114">Para tener acceso al tipo contenedor, páselo como un argumento al constructor del tipo anidado.</span><span class="sxs-lookup"><span data-stu-id="9b898-114">To access the containing type, pass it as an argument to the constructor of the nested type.</span></span> <span data-ttu-id="9b898-115">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9b898-115">For example:</span></span>

[!code-csharp[DeclareNestedInstance](~/samples/snippets/csharp/objectoriented/nestedtypes.cs#DeclareNestedInstance)]

<span data-ttu-id="9b898-116">Un tipo anidado tiene acceso a todos los miembros que estén accesibles para el tipo contenedor.</span><span class="sxs-lookup"><span data-stu-id="9b898-116">A nested type has access to all of the members that are accessible to its containing type.</span></span> <span data-ttu-id="9b898-117">Puede tener acceso a los miembros privados y protegidos del tipo contenedor, incluidos los miembros protegidos heredados.</span><span class="sxs-lookup"><span data-stu-id="9b898-117">It can access private and protected members of the containing type, including any inherited protected members.</span></span>

<span data-ttu-id="9b898-118">En la declaración anterior, el nombre completo de la clase `Nested` es `Container.Nested`.</span><span class="sxs-lookup"><span data-stu-id="9b898-118">In the previous declaration, the full name of class `Nested` is `Container.Nested`.</span></span> <span data-ttu-id="9b898-119">Este es el nombre que se utiliza para crear una instancia nueva de la clase anidada, de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="9b898-119">This is the name used to create a new instance of the nested class, as follows:</span></span>

[!code-csharp[UseNestedInstance](~/samples/snippets/csharp/objectoriented/nestedtypes.cs#UseNestedInstance)]

## <a name="see-also"></a><span data-ttu-id="9b898-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="9b898-120">See also</span></span>

- [<span data-ttu-id="9b898-121">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="9b898-121">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="9b898-122">Clases y structs</span><span class="sxs-lookup"><span data-stu-id="9b898-122">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="9b898-123">Modificadores de acceso</span><span class="sxs-lookup"><span data-stu-id="9b898-123">Access Modifiers</span></span>](./access-modifiers.md)
- [<span data-ttu-id="9b898-124">Constructores</span><span class="sxs-lookup"><span data-stu-id="9b898-124">Constructors</span></span>](./constructors.md)
