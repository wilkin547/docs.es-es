---
title: Control de acceso (F#)
description: "Obtener información sobre cómo controlar el acceso a elementos de programación como tipos, métodos y funciones, en el lenguaje de programación de F #."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 955b06fe-d1cd-431d-8db6-93e83b697453
ms.openlocfilehash: a02e20a585a0456577901f2762a0eeb0e3ecd2f0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="access-control"></a><span data-ttu-id="2c0eb-104">Control de acceso</span><span class="sxs-lookup"><span data-stu-id="2c0eb-104">Access Control</span></span>

<span data-ttu-id="2c0eb-105">*Control de acceso* se refiere a declarar qué clientes pueden utilizar ciertos elementos del programa, como tipos, métodos y funciones.</span><span class="sxs-lookup"><span data-stu-id="2c0eb-105">*Access control* refers to declaring which clients can use certain program elements, such as types, methods, and functions.</span></span>


## <a name="basics-of-access-control"></a><span data-ttu-id="2c0eb-106">Conceptos básicos de Control de acceso</span><span class="sxs-lookup"><span data-stu-id="2c0eb-106">Basics of Access Control</span></span>
<span data-ttu-id="2c0eb-107">En F #, el acceso de control especificadores `public`, `internal`, y `private` pueden aplicarse a los módulos, tipos, métodos, definiciones de valor, funciones, propiedades y campos explícitos.</span><span class="sxs-lookup"><span data-stu-id="2c0eb-107">In F#, the access control specifiers `public`, `internal`, and `private` can be applied to modules, types, methods, value definitions, functions, properties, and explicit fields.</span></span>


- <span data-ttu-id="2c0eb-108">`public`indica que la entidad puede tener acceso a todos los llamadores.</span><span class="sxs-lookup"><span data-stu-id="2c0eb-108">`public` indicates that the entity can be accessed by all callers.</span></span>

- <span data-ttu-id="2c0eb-109">`internal`indica que se puede tener acceso a la entidad únicamente desde el mismo ensamblado.</span><span class="sxs-lookup"><span data-stu-id="2c0eb-109">`internal` indicates that the entity can be accessed only from the same assembly.</span></span>

- <span data-ttu-id="2c0eb-110">`private`indica que la entidad puede tener acceso sólo desde el tipo o módulo envolvente.</span><span class="sxs-lookup"><span data-stu-id="2c0eb-110">`private` indicates that the entity can be accessed only from the enclosing type or module.</span></span>


>[!NOTE] 
<span data-ttu-id="2c0eb-111">El especificador de acceso `protected` no se utiliza en F #, aunque es aceptable si se utilizan tipos creados en lenguajes que admitan `protected` acceso.</span><span class="sxs-lookup"><span data-stu-id="2c0eb-111">The access specifier `protected` is not used in F#, although it is acceptable if you are using types authored in languages that do support `protected` access.</span></span> <span data-ttu-id="2c0eb-112">Por lo tanto, si invalida un método protegido, el método permanecerá accesible únicamente dentro de la clase y sus descendientes.</span><span class="sxs-lookup"><span data-stu-id="2c0eb-112">Therefore, if you override a protected method, your method remains accessible only within the class and its descendents.</span></span>

<span data-ttu-id="2c0eb-113">En general, el especificador se coloca delante del nombre de la entidad, excepto cuando una `mutable` o `inline` especificador se usa, que aparecen después del especificador de control de acceso.</span><span class="sxs-lookup"><span data-stu-id="2c0eb-113">In general, the specifier is put in front of the name of the entity, except when a `mutable` or `inline` specifier is used, which appear after the access control specifier.</span></span>

<span data-ttu-id="2c0eb-114">Si no se utiliza ningún especificador de acceso, el valor predeterminado es `public`, excepto para `let` enlaces en un tipo, que siempre son `private` al tipo.</span><span class="sxs-lookup"><span data-stu-id="2c0eb-114">If no access specifier is used, the default is `public`, except for `let` bindings in a type, which are always `private` to the type.</span></span>

<span data-ttu-id="2c0eb-115">Las firmas en F # proporcionan otro mecanismo para controlar el acceso a elementos de programa de F #.</span><span class="sxs-lookup"><span data-stu-id="2c0eb-115">Signatures in F# provide another mechanism for controlling access to F# program elements.</span></span> <span data-ttu-id="2c0eb-116">Las firmas no son necesarias para el control de acceso.</span><span class="sxs-lookup"><span data-stu-id="2c0eb-116">Signatures are not required for access control.</span></span> <span data-ttu-id="2c0eb-117">Para más información, vea [Signatures](signatures.md) (Firmas).</span><span class="sxs-lookup"><span data-stu-id="2c0eb-117">For more information, see [Signatures](signatures.md).</span></span>


## <a name="rules-for-access-control"></a><span data-ttu-id="2c0eb-118">Reglas para el Control de acceso</span><span class="sxs-lookup"><span data-stu-id="2c0eb-118">Rules for Access Control</span></span>
<span data-ttu-id="2c0eb-119">Control de acceso está sujeto a las reglas siguientes:</span><span class="sxs-lookup"><span data-stu-id="2c0eb-119">Access control is subject to the following rules:</span></span>


- <span data-ttu-id="2c0eb-120">Las declaraciones de herencia (es decir, el uso de `inherit` para especificar una clase base para una clase), interfaz declaraciones (es decir, especificar que una clase implementa una interfaz) y resumir los miembros siempre tienen la misma accesibilidad que el tipo envolvente.</span><span class="sxs-lookup"><span data-stu-id="2c0eb-120">Inheritance declarations (that is, the use of `inherit` to specify a base class for a class), interface declarations (that is, specifying that a class implements an interface), and abstract members always have the same accessibility as the enclosing type.</span></span> <span data-ttu-id="2c0eb-121">Por lo tanto, no se puede usar un especificador de control de acceso en estas construcciones.</span><span class="sxs-lookup"><span data-stu-id="2c0eb-121">Therefore, an access control specifier cannot be used on these constructs.</span></span>

- <span data-ttu-id="2c0eb-122">Los casos individuales de una unión discriminada no pueden tener sus propios modificadores de control de acceso independientes del tipo de unión.</span><span class="sxs-lookup"><span data-stu-id="2c0eb-122">Individual cases in a discriminated union cannot have their own access control modifiers separate from the union type.</span></span>

- <span data-ttu-id="2c0eb-123">Los campos individuales de un tipo de registro no pueden tener sus propios modificadores de control de acceso independientes del tipo de registro.</span><span class="sxs-lookup"><span data-stu-id="2c0eb-123">Individual fields of a record type cannot have their own access control modifiers separate from the record type.</span></span>


## <a name="example"></a><span data-ttu-id="2c0eb-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2c0eb-124">Example</span></span>
<span data-ttu-id="2c0eb-125">El código siguiente muestra el uso de especificadores de control de acceso.</span><span class="sxs-lookup"><span data-stu-id="2c0eb-125">The following code illustrates the use of access control specifiers.</span></span> <span data-ttu-id="2c0eb-126">Hay dos archivos en el proyecto, `Module1.fs` y `Module2.fs`.</span><span class="sxs-lookup"><span data-stu-id="2c0eb-126">There are two files in the project, `Module1.fs` and `Module2.fs`.</span></span> <span data-ttu-id="2c0eb-127">Cada archivo de forma implícita es un módulo.</span><span class="sxs-lookup"><span data-stu-id="2c0eb-127">Each file is implicitly a module.</span></span> <span data-ttu-id="2c0eb-128">Por lo tanto, hay dos módulos, `Module1` y `Module2`.</span><span class="sxs-lookup"><span data-stu-id="2c0eb-128">Therefore, there are two modules, `Module1` and `Module2`.</span></span> <span data-ttu-id="2c0eb-129">Un tipo privado y un tipo interno se definen en `Module1`.</span><span class="sxs-lookup"><span data-stu-id="2c0eb-129">A private type and an internal type are defined in `Module1`.</span></span> <span data-ttu-id="2c0eb-130">No se puede tener acceso a un tipo privado de `Module2`, pero puede del tipo interno.</span><span class="sxs-lookup"><span data-stu-id="2c0eb-130">The private type cannot be accessed from `Module2`, but the internal type can.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/access-control/snippet1.fs)]
    
<span data-ttu-id="2c0eb-131">El código siguiente comprueba la accesibilidad de los tipos creados en `Module1.fs`.</span><span class="sxs-lookup"><span data-stu-id="2c0eb-131">The following code tests the accessibility of the types created in `Module1.fs`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/access-control/snippet2.fs)]
    
## <a name="see-also"></a><span data-ttu-id="2c0eb-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="2c0eb-132">See Also</span></span>
[<span data-ttu-id="2c0eb-133">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="2c0eb-133">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="2c0eb-134">Firmas</span><span class="sxs-lookup"><span data-stu-id="2c0eb-134">Signatures</span></span>](signatures.md)
