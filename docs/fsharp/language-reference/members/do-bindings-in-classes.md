---
title: Enlaces do en clases (F#)
description: "Obtenga información acerca de cómo usar un 'do' enlace en una definición de clase, que lleva a cabo acciones cuando se construye el objeto o cuando se utiliza primero el tipo de F #."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 78987cb8-bdba-46e2-b5b2-994c83fe42c4
ms.openlocfilehash: f9582338306d87c3dd799425083037cc95b31b1e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="do-bindings-in-classes"></a><span data-ttu-id="eb070-104">Enlaces do en clases</span><span class="sxs-lookup"><span data-stu-id="eb070-104">do Bindings in Classes</span></span>

<span data-ttu-id="eb070-105">A `do` enlace en una definición de clase realiza acciones cuando se construye el objeto o, para una variable static `do` enlace, cuando se usa el tipo en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="eb070-105">A `do` binding in a class definition performs actions when the object is constructed or, for a static `do` binding, when the type is first used.</span></span>


## <a name="syntax"></a><span data-ttu-id="eb070-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eb070-106">Syntax</span></span>

```fsharp
[static] do expression
```

## <a name="remarks"></a><span data-ttu-id="eb070-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="eb070-107">Remarks</span></span>
<span data-ttu-id="eb070-108">A `do` enlace aparece junto con o después de `let` enlaces pero antes de las definiciones de miembro en una definición de clase.</span><span class="sxs-lookup"><span data-stu-id="eb070-108">A `do` binding appears together with or after `let` bindings but before member definitions in a class definition.</span></span> <span data-ttu-id="eb070-109">Aunque la `do` palabra clave es opcional para `do` enlaces en el nivel de módulo, no es opcional para `do` enlaces en una definición de clase.</span><span class="sxs-lookup"><span data-stu-id="eb070-109">Although the `do` keyword is optional for `do` bindings at the module level, it is not optional for `do` bindings in a class definition.</span></span>

<span data-ttu-id="eb070-110">Para la construcción de todos los objetos de cualquier tipo, no estático determinado `do` enlaces y no estático `let` enlaces se ejecutan en el orden en que aparecen en la definición de clase.</span><span class="sxs-lookup"><span data-stu-id="eb070-110">For the construction of every object of any given type, non-static `do` bindings and non-static `let` bindings are executed in the order in which they appear in the class definition.</span></span> <span data-ttu-id="eb070-111">Varios `do` enlaces pueden producirse en un tipo.</span><span class="sxs-lookup"><span data-stu-id="eb070-111">Multiple `do` bindings can occur in one type.</span></span> <span data-ttu-id="eb070-112">No estático `let` enlaces y no estático `do` enlaces se convierten en el cuerpo del constructor primario.</span><span class="sxs-lookup"><span data-stu-id="eb070-112">The non-static `let` bindings and the non-static `do` bindings become the body of the primary constructor.</span></span> <span data-ttu-id="eb070-113">El código de no estático `do` sección de enlaces puede hacer referencia a los parámetros del constructor primario y los valores o funciones que se definen en la `let` sección de enlaces.</span><span class="sxs-lookup"><span data-stu-id="eb070-113">The code in the non-static `do` bindings section can reference the primary constructor parameters and any values or functions that are defined in the `let` bindings section.</span></span>

<span data-ttu-id="eb070-114">No estáticos `do` enlaces pueden tener acceso a los miembros de la clase siempre y cuando la clase tiene un identificador propio que se define mediante una `as` palabra clave en la clase de encabezado y, a continuación, siempre y cuando todos los usos de esos miembros se califican con el identificador propio para la clase.</span><span class="sxs-lookup"><span data-stu-id="eb070-114">Non-static `do` bindings can access members of the class as long as the class has a self identifier that is defined by an `as` keyword in the class heading, and as long as all uses of those members are qualified with the self identifier for the class.</span></span>

<span data-ttu-id="eb070-115">Porque `let` enlaces inicializan los campos privados de una clase, que a menudo es necesario para garantizar que los miembros se comportan según lo esperado, `do` enlaces normalmente se colocan después `let` enlaces para que el código en el `do` can de enlace ejecutar con un objeto totalmente inicializado.</span><span class="sxs-lookup"><span data-stu-id="eb070-115">Because `let` bindings initialize the private fields of a class, which is often necessary to guarantee that members behave as expected, `do` bindings are usually put after `let` bindings so that code in the `do` binding can execute with a fully initialized object.</span></span> <span data-ttu-id="eb070-116">Si el código intenta utilizar a un miembro antes de que finalice la inicialización, se produce una excepción InvalidOperationException.</span><span class="sxs-lookup"><span data-stu-id="eb070-116">If your code attempts to use a member before the initialization is complete, an InvalidOperationException is raised.</span></span>

<span data-ttu-id="eb070-117">Estática `do` enlaces pueden hacer referencia a miembros estáticos o campos de los clase pero no los miembros o campos de instancia.</span><span class="sxs-lookup"><span data-stu-id="eb070-117">Static `do` bindings can reference static members or fields of the enclosing class but not instance members or fields.</span></span> <span data-ttu-id="eb070-118">Estática `do` enlaces pasan a formar parte del inicializador estático de la clase, que se garantiza que se ejecutará antes de que se usa la clase por primera vez.</span><span class="sxs-lookup"><span data-stu-id="eb070-118">Static `do` bindings become part of the static initializer for the class, which is guaranteed to execute before the class is first used.</span></span>

<span data-ttu-id="eb070-119">Se omiten los atributos para `do` los enlaces de tipos.</span><span class="sxs-lookup"><span data-stu-id="eb070-119">Attributes are ignored for `do` bindings in types.</span></span> <span data-ttu-id="eb070-120">Si un atributo no es necesario para el código que se ejecuta en un `do` de enlace, se debe aplicar al constructor primario.</span><span class="sxs-lookup"><span data-stu-id="eb070-120">If an attribute is required for code that executes in a `do` binding, it must be applied to the primary constructor.</span></span>

<span data-ttu-id="eb070-121">En el código siguiente, una clase tiene una variable static `do` enlace y no estático `do` enlace.</span><span class="sxs-lookup"><span data-stu-id="eb070-121">In the following code, a class has a static `do` binding and a non-static `do` binding.</span></span> <span data-ttu-id="eb070-122">El objeto tiene un constructor que tiene dos parámetros, `a` y `b`, y dos campos privados se definen en el `let` enlaces para la clase.</span><span class="sxs-lookup"><span data-stu-id="eb070-122">The object has a constructor that has two parameters, `a` and `b`, and two private fields are defined in the `let` bindings for the class.</span></span> <span data-ttu-id="eb070-123">También se definen dos propiedades.</span><span class="sxs-lookup"><span data-stu-id="eb070-123">Two properties are also defined.</span></span> <span data-ttu-id="eb070-124">Todas ellas están en ámbito no estático `do` sección de enlaces, tal y como se muestra en la línea que imprime todos esos valores.</span><span class="sxs-lookup"><span data-stu-id="eb070-124">All of these are in scope in the non-static `do` bindings section, as is illustrated by the line that prints all those values.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3101.fs)]

<span data-ttu-id="eb070-125">La salida es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="eb070-125">The output is as follows.</span></span>

```console
Initializing MyType.
Initializing object 1 2 2 4 8 16
```

## <a name="see-also"></a><span data-ttu-id="eb070-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="eb070-126">See Also</span></span>
[<span data-ttu-id="eb070-127">Miembros</span><span class="sxs-lookup"><span data-stu-id="eb070-127">Members</span></span>](index.md)

[<span data-ttu-id="eb070-128">Clases</span><span class="sxs-lookup"><span data-stu-id="eb070-128">Classes</span></span>](../classes.md)

[<span data-ttu-id="eb070-129">Constructores</span><span class="sxs-lookup"><span data-stu-id="eb070-129">Constructors</span></span>](constructors.md)

<span data-ttu-id="eb070-130">[`let` Bindings in Classes](let-bindings-in-classes.md) (Enlaces `let` en clases)</span><span class="sxs-lookup"><span data-stu-id="eb070-130">[`let` Bindings in Classes](let-bindings-in-classes.md)</span></span>

[<span data-ttu-id="eb070-131">`do`Enlaces</span><span class="sxs-lookup"><span data-stu-id="eb070-131">`do` Bindings</span></span>](../functions/do-Bindings.md)
