---
title: Control de acceso
description: Obtenga información sobre cómo controlar el acceso a elementos de programación, como tipos, métodos y funciones, en F# el lenguaje de programación.
ms.date: 05/16/2016
ms.openlocfilehash: fe204a883a440794fdd033c54d6d8d4fb68e0ce2
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2019
ms.locfileid: "73425111"
---
# <a name="access-control"></a><span data-ttu-id="ec392-103">Control de acceso</span><span class="sxs-lookup"><span data-stu-id="ec392-103">Access Control</span></span>

<span data-ttu-id="ec392-104">El *control de acceso* hace referencia a la declaración de los clientes que pueden usar determinados elementos de programa, como tipos, métodos y funciones.</span><span class="sxs-lookup"><span data-stu-id="ec392-104">*Access control* refers to declaring which clients can use certain program elements, such as types, methods, and functions.</span></span>

## <a name="basics-of-access-control"></a><span data-ttu-id="ec392-105">Aspectos básicos de Access Control</span><span class="sxs-lookup"><span data-stu-id="ec392-105">Basics of Access Control</span></span>

<span data-ttu-id="ec392-106">En F#, los especificadores de control de acceso `public`, `internal`y `private` pueden aplicarse a módulos, tipos, métodos, definiciones de valores, funciones, propiedades y campos explícitos.</span><span class="sxs-lookup"><span data-stu-id="ec392-106">In F#, the access control specifiers `public`, `internal`, and `private` can be applied to modules, types, methods, value definitions, functions, properties, and explicit fields.</span></span>

- <span data-ttu-id="ec392-107">`public` indica que todos los llamadores pueden tener acceso a la entidad.</span><span class="sxs-lookup"><span data-stu-id="ec392-107">`public` indicates that the entity can be accessed by all callers.</span></span>

- <span data-ttu-id="ec392-108">`internal` indica que solo se puede tener acceso a la entidad desde el mismo ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ec392-108">`internal` indicates that the entity can be accessed only from the same assembly.</span></span>

- <span data-ttu-id="ec392-109">`private` indica que solo se puede tener acceso a la entidad desde el tipo o módulo envolvente.</span><span class="sxs-lookup"><span data-stu-id="ec392-109">`private` indicates that the entity can be accessed only from the enclosing type or module.</span></span>

> [!NOTE]
> <span data-ttu-id="ec392-110">El especificador de acceso `protected` no se utiliza F#en, aunque es aceptable si se usan tipos creados en lenguajes que admiten el acceso a `protected`.</span><span class="sxs-lookup"><span data-stu-id="ec392-110">The access specifier `protected` is not used in F#, although it is acceptable if you are using types authored in languages that do support `protected` access.</span></span> <span data-ttu-id="ec392-111">Por consiguiente, si invalida un método protegido, el método permanece accesible solo dentro de la clase y sus descendientes.</span><span class="sxs-lookup"><span data-stu-id="ec392-111">Therefore, if you override a protected method, your method remains accessible only within the class and its descendents.</span></span>

<span data-ttu-id="ec392-112">En general, el especificador se coloca delante del nombre de la entidad, excepto cuando se usa un especificador `mutable` o `inline`, que aparece después del especificador de control de acceso.</span><span class="sxs-lookup"><span data-stu-id="ec392-112">In general, the specifier is put in front of the name of the entity, except when a `mutable` or `inline` specifier is used, which appear after the access control specifier.</span></span>

<span data-ttu-id="ec392-113">Si no se usa ningún especificador de acceso, el valor predeterminado es `public`, excepto para los enlaces de `let` en un tipo, que siempre se `private` al tipo.</span><span class="sxs-lookup"><span data-stu-id="ec392-113">If no access specifier is used, the default is `public`, except for `let` bindings in a type, which are always `private` to the type.</span></span>

<span data-ttu-id="ec392-114">Las firmas de F# proporcionan otro mecanismo para controlar el acceso F# a los elementos del programa.</span><span class="sxs-lookup"><span data-stu-id="ec392-114">Signatures in F# provide another mechanism for controlling access to F# program elements.</span></span> <span data-ttu-id="ec392-115">No se necesitan firmas para el control de acceso.</span><span class="sxs-lookup"><span data-stu-id="ec392-115">Signatures are not required for access control.</span></span> <span data-ttu-id="ec392-116">Para más información, vea [Signatures](signature-files.md) (Firmas).</span><span class="sxs-lookup"><span data-stu-id="ec392-116">For more information, see [Signatures](signature-files.md).</span></span>

## <a name="rules-for-access-control"></a><span data-ttu-id="ec392-117">Reglas para Access Control</span><span class="sxs-lookup"><span data-stu-id="ec392-117">Rules for Access Control</span></span>

<span data-ttu-id="ec392-118">El control de acceso está sujeto a las siguientes reglas:</span><span class="sxs-lookup"><span data-stu-id="ec392-118">Access control is subject to the following rules:</span></span>

- <span data-ttu-id="ec392-119">Las declaraciones de herencia (es decir, el uso de `inherit` para especificar una clase base para una clase), las declaraciones de interfaz (es decir, especificando que una clase implementa una interfaz) y los miembros abstractos siempre tienen la misma accesibilidad que el tipo envolvente.</span><span class="sxs-lookup"><span data-stu-id="ec392-119">Inheritance declarations (that is, the use of `inherit` to specify a base class for a class), interface declarations (that is, specifying that a class implements an interface), and abstract members always have the same accessibility as the enclosing type.</span></span> <span data-ttu-id="ec392-120">Por lo tanto, no se puede usar un especificador de control de acceso en estas construcciones.</span><span class="sxs-lookup"><span data-stu-id="ec392-120">Therefore, an access control specifier cannot be used on these constructs.</span></span>

- <span data-ttu-id="ec392-121">La accesibilidad de los casos individuales en una Unión discriminada viene determinada por la accesibilidad de la propia Unión discriminada.</span><span class="sxs-lookup"><span data-stu-id="ec392-121">Accessibility for individual cases in a discriminated union is determined by the accessibility of the discriminated union itself.</span></span> <span data-ttu-id="ec392-122">Es decir, un caso de Unión determinado no es menos accesible que la propia Unión.</span><span class="sxs-lookup"><span data-stu-id="ec392-122">That is, a particular union case is no less accessible than the union itself.</span></span>

- <span data-ttu-id="ec392-123">La accesibilidad del propio registro determina la accesibilidad de los campos individuales de un tipo de registro.</span><span class="sxs-lookup"><span data-stu-id="ec392-123">Accessibility for individual fields of a record type is determined by the accessibility of the record itself.</span></span> <span data-ttu-id="ec392-124">Es decir, una etiqueta de registro determinada no es menos accesible que el propio registro.</span><span class="sxs-lookup"><span data-stu-id="ec392-124">That is, a particular record label is no less accessible than the record itself.</span></span>

## <a name="example"></a><span data-ttu-id="ec392-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ec392-125">Example</span></span>

<span data-ttu-id="ec392-126">En el código siguiente se muestra el uso de especificadores de control de acceso.</span><span class="sxs-lookup"><span data-stu-id="ec392-126">The following code illustrates the use of access control specifiers.</span></span> <span data-ttu-id="ec392-127">Hay dos archivos en el proyecto, `Module1.fs` y `Module2.fs`.</span><span class="sxs-lookup"><span data-stu-id="ec392-127">There are two files in the project, `Module1.fs` and `Module2.fs`.</span></span> <span data-ttu-id="ec392-128">Cada archivo es implícitamente un módulo.</span><span class="sxs-lookup"><span data-stu-id="ec392-128">Each file is implicitly a module.</span></span> <span data-ttu-id="ec392-129">Por lo tanto, hay dos módulos, `Module1` y `Module2`.</span><span class="sxs-lookup"><span data-stu-id="ec392-129">Therefore, there are two modules, `Module1` and `Module2`.</span></span> <span data-ttu-id="ec392-130">En `Module1`se definen un tipo privado y un tipo interno.</span><span class="sxs-lookup"><span data-stu-id="ec392-130">A private type and an internal type are defined in `Module1`.</span></span> <span data-ttu-id="ec392-131">No se puede tener acceso al tipo privado desde `Module2`, pero el tipo interno puede.</span><span class="sxs-lookup"><span data-stu-id="ec392-131">The private type cannot be accessed from `Module2`, but the internal type can.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/access-control/snippet1.fs)]

<span data-ttu-id="ec392-132">En el código siguiente se prueba la accesibilidad de los tipos creados en `Module1.fs`.</span><span class="sxs-lookup"><span data-stu-id="ec392-132">The following code tests the accessibility of the types created in `Module1.fs`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/access-control/snippet2.fs)]

## <a name="see-also"></a><span data-ttu-id="ec392-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="ec392-133">See also</span></span>

- [<span data-ttu-id="ec392-134">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="ec392-134">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="ec392-135">Firmas</span><span class="sxs-lookup"><span data-stu-id="ec392-135">Signatures</span></span>](signature-files.md)
