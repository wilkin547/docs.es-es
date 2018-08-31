---
title: Control de acceso (F#)
description: 'Obtenga información sobre cómo controlar el acceso a elementos de programación como tipos, métodos y funciones, en el lenguaje de programación F #.'
ms.date: 05/16/2016
ms.openlocfilehash: 6b13ac03d2a4a6c53b53d4c790760f5d51b334ee
ms.sourcegitcommit: a368166a51e5204c0224fbf5e46476e3ed122817
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2018
ms.locfileid: "43332244"
---
# <a name="access-control"></a><span data-ttu-id="b2889-103">Control de acceso</span><span class="sxs-lookup"><span data-stu-id="b2889-103">Access Control</span></span>

<span data-ttu-id="b2889-104">*Control de acceso* se refiere a declarar qué clientes pueden utilizar ciertos elementos del programa, como tipos, métodos y funciones.</span><span class="sxs-lookup"><span data-stu-id="b2889-104">*Access control* refers to declaring which clients can use certain program elements, such as types, methods, and functions.</span></span>

## <a name="basics-of-access-control"></a><span data-ttu-id="b2889-105">Conceptos básicos de Control de acceso</span><span class="sxs-lookup"><span data-stu-id="b2889-105">Basics of Access Control</span></span>
<span data-ttu-id="b2889-106">En F #, el acceso de control especificadores `public`, `internal`, y `private` puede aplicarse a los módulos, tipos, métodos, las definiciones de valor, funciones, propiedades y campos explícitos.</span><span class="sxs-lookup"><span data-stu-id="b2889-106">In F#, the access control specifiers `public`, `internal`, and `private` can be applied to modules, types, methods, value definitions, functions, properties, and explicit fields.</span></span>

- <span data-ttu-id="b2889-107">`public` indica que la entidad puede tener acceso a todos los llamadores.</span><span class="sxs-lookup"><span data-stu-id="b2889-107">`public` indicates that the entity can be accessed by all callers.</span></span>

- <span data-ttu-id="b2889-108">`internal` indica que la entidad se puede acceder solo desde el mismo ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b2889-108">`internal` indicates that the entity can be accessed only from the same assembly.</span></span>

- <span data-ttu-id="b2889-109">`private` indica que la entidad se puede acceder solo desde el tipo o módulo envolvente.</span><span class="sxs-lookup"><span data-stu-id="b2889-109">`private` indicates that the entity can be accessed only from the enclosing type or module.</span></span>

>[!NOTE] 
<span data-ttu-id="b2889-110">El especificador de acceso `protected` no se utiliza en F #, aunque es aceptable si se utilizan tipos creados en lenguajes que admiten `protected` acceso.</span><span class="sxs-lookup"><span data-stu-id="b2889-110">The access specifier `protected` is not used in F#, although it is acceptable if you are using types authored in languages that do support `protected` access.</span></span> <span data-ttu-id="b2889-111">Por lo tanto, si invalida un método protegido, el método sigue siendo accesible únicamente dentro de la clase y sus descendientes.</span><span class="sxs-lookup"><span data-stu-id="b2889-111">Therefore, if you override a protected method, your method remains accessible only within the class and its descendents.</span></span>

<span data-ttu-id="b2889-112">En general, el especificador se coloca delante del nombre de la entidad, excepto cuando una `mutable` o `inline` especificador se usa, que aparecen después del especificador de control de acceso.</span><span class="sxs-lookup"><span data-stu-id="b2889-112">In general, the specifier is put in front of the name of the entity, except when a `mutable` or `inline` specifier is used, which appear after the access control specifier.</span></span>

<span data-ttu-id="b2889-113">Si no se utiliza ningún especificador de acceso, el valor predeterminado es `public`, excepto para `let` enlaces en un tipo, que siempre son `private` al tipo.</span><span class="sxs-lookup"><span data-stu-id="b2889-113">If no access specifier is used, the default is `public`, except for `let` bindings in a type, which are always `private` to the type.</span></span>

<span data-ttu-id="b2889-114">Las firmas en F # proporcionan otro mecanismo para controlar el acceso a los elementos de programa F #.</span><span class="sxs-lookup"><span data-stu-id="b2889-114">Signatures in F# provide another mechanism for controlling access to F# program elements.</span></span> <span data-ttu-id="b2889-115">Las firmas no son necesarias para el control de acceso.</span><span class="sxs-lookup"><span data-stu-id="b2889-115">Signatures are not required for access control.</span></span> <span data-ttu-id="b2889-116">Para más información, vea [Signatures](signatures.md) (Firmas).</span><span class="sxs-lookup"><span data-stu-id="b2889-116">For more information, see [Signatures](signatures.md).</span></span>

## <a name="rules-for-access-control"></a><span data-ttu-id="b2889-117">Reglas de Control de acceso</span><span class="sxs-lookup"><span data-stu-id="b2889-117">Rules for Access Control</span></span>
<span data-ttu-id="b2889-118">Control de acceso está sujeto a las reglas siguientes:</span><span class="sxs-lookup"><span data-stu-id="b2889-118">Access control is subject to the following rules:</span></span>

- <span data-ttu-id="b2889-119">Las declaraciones de herencia (es decir, el uso de `inherit` para especificar una clase base para una clase), las declaraciones (es decir, especificar que una clase implementa una interfaz) de la interfaz y abstraer los miembros siempre tienen la misma accesibilidad que el tipo envolvente.</span><span class="sxs-lookup"><span data-stu-id="b2889-119">Inheritance declarations (that is, the use of `inherit` to specify a base class for a class), interface declarations (that is, specifying that a class implements an interface), and abstract members always have the same accessibility as the enclosing type.</span></span> <span data-ttu-id="b2889-120">Por lo tanto, no se puede usar un especificador de control de acceso en estas construcciones.</span><span class="sxs-lookup"><span data-stu-id="b2889-120">Therefore, an access control specifier cannot be used on these constructs.</span></span>

- <span data-ttu-id="b2889-121">Accesibilidad para los casos individuales de una unión discriminada viene determinada por la accesibilidad de la propia unión discriminada.</span><span class="sxs-lookup"><span data-stu-id="b2889-121">Accessibility for individual cases in a discriminated union is determined by the accessibility of the discriminated union itself.</span></span> <span data-ttu-id="b2889-122">Es decir, un caso de unión concreto no menos accesible que la propia unión.</span><span class="sxs-lookup"><span data-stu-id="b2889-122">That is, a particular union case is no less accessible than the union itself.</span></span>

- <span data-ttu-id="b2889-123">Accesibilidad para campos individuales de un tipo de registro no viene determinada por la accesibilidad del mismo registro.</span><span class="sxs-lookup"><span data-stu-id="b2889-123">Accessibility for individual fields of a record type cannot is determined by the accessibility of the record itself.</span></span> <span data-ttu-id="b2889-124">Es decir, una etiqueta de registro concreto no menos accesible que el mismo registro.</span><span class="sxs-lookup"><span data-stu-id="b2889-124">That is, a particular record label is no less accessible than the record itself.</span></span>

## <a name="example"></a><span data-ttu-id="b2889-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b2889-125">Example</span></span>
<span data-ttu-id="b2889-126">El código siguiente muestra el uso de especificadores de control de acceso.</span><span class="sxs-lookup"><span data-stu-id="b2889-126">The following code illustrates the use of access control specifiers.</span></span> <span data-ttu-id="b2889-127">Hay dos archivos en el proyecto, `Module1.fs` y `Module2.fs`.</span><span class="sxs-lookup"><span data-stu-id="b2889-127">There are two files in the project, `Module1.fs` and `Module2.fs`.</span></span> <span data-ttu-id="b2889-128">Cada archivo es implícitamente un módulo.</span><span class="sxs-lookup"><span data-stu-id="b2889-128">Each file is implicitly a module.</span></span> <span data-ttu-id="b2889-129">Por lo tanto, hay dos módulos, `Module1` y `Module2`.</span><span class="sxs-lookup"><span data-stu-id="b2889-129">Therefore, there are two modules, `Module1` and `Module2`.</span></span> <span data-ttu-id="b2889-130">Un tipo privado y un tipo interno se definen en `Module1`.</span><span class="sxs-lookup"><span data-stu-id="b2889-130">A private type and an internal type are defined in `Module1`.</span></span> <span data-ttu-id="b2889-131">El tipo privado no es accesible desde `Module2`, pero puede tipo interno.</span><span class="sxs-lookup"><span data-stu-id="b2889-131">The private type cannot be accessed from `Module2`, but the internal type can.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/access-control/snippet1.fs)]
    
<span data-ttu-id="b2889-132">El código siguiente comprueba la accesibilidad de los tipos creados en `Module1.fs`.</span><span class="sxs-lookup"><span data-stu-id="b2889-132">The following code tests the accessibility of the types created in `Module1.fs`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/access-control/snippet2.fs)]
    
## <a name="see-also"></a><span data-ttu-id="b2889-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="b2889-133">See Also</span></span>
[<span data-ttu-id="b2889-134">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="b2889-134">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="b2889-135">Firmas</span><span class="sxs-lookup"><span data-stu-id="b2889-135">Signatures</span></span>](signatures.md)
