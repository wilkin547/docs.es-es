---
title: Enlaces do en clases (F#)
description: Obtenga información sobre cómo usar un 'do' enlace en una definición de clase, que realiza acciones cuando se construye el objeto o cuando se utiliza primero el tipo de F#.
ms.date: 05/16/2016
ms.openlocfilehash: e54a5bde52bf6973cc338c929ba99e6fd5b53127
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2018
ms.locfileid: "43801546"
---
# <a name="do-bindings-in-classes"></a><span data-ttu-id="8b717-103">Enlaces do en clases</span><span class="sxs-lookup"><span data-stu-id="8b717-103">do Bindings in Classes</span></span>

<span data-ttu-id="8b717-104">Un `do` enlace en una definición de clase realiza acciones cuando se construye el objeto o, para una variable static `do` enlace, cuando se usa el tipo en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="8b717-104">A `do` binding in a class definition performs actions when the object is constructed or, for a static `do` binding, when the type is first used.</span></span>

## <a name="syntax"></a><span data-ttu-id="8b717-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8b717-105">Syntax</span></span>

```fsharp
[static] do expression
```

## <a name="remarks"></a><span data-ttu-id="8b717-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8b717-106">Remarks</span></span>

<span data-ttu-id="8b717-107">Un `do` enlace aparece junto con, o después de `let` enlaces, pero antes de las definiciones de miembros en una definición de clase.</span><span class="sxs-lookup"><span data-stu-id="8b717-107">A `do` binding appears together with or after `let` bindings but before member definitions in a class definition.</span></span> <span data-ttu-id="8b717-108">Aunque el `do` es opcional para la palabra clave `do` enlaces en el nivel de módulo, no es opcional para `do` enlaces en una definición de clase.</span><span class="sxs-lookup"><span data-stu-id="8b717-108">Although the `do` keyword is optional for `do` bindings at the module level, it is not optional for `do` bindings in a class definition.</span></span>

<span data-ttu-id="8b717-109">Para la construcción de todos los objetos de cualquier dado el tipo, no estático `do` enlaces y no static `let` enlaces se ejecutan en el orden en que aparecen en la definición de clase.</span><span class="sxs-lookup"><span data-stu-id="8b717-109">For the construction of every object of any given type, non-static `do` bindings and non-static `let` bindings are executed in the order in which they appear in the class definition.</span></span> <span data-ttu-id="8b717-110">Varios `do` enlaces pueden producirse en un tipo.</span><span class="sxs-lookup"><span data-stu-id="8b717-110">Multiple `do` bindings can occur in one type.</span></span> <span data-ttu-id="8b717-111">No estático `let` enlaces y que no sea estático `do` enlaces se convierten en el cuerpo del constructor principal.</span><span class="sxs-lookup"><span data-stu-id="8b717-111">The non-static `let` bindings and the non-static `do` bindings become the body of the primary constructor.</span></span> <span data-ttu-id="8b717-112">El código en el que no sea estático `do` sección de enlaces puede hacer referencia a los parámetros del constructor principal y los valores o funciones que se definen en el `let` sección de enlaces.</span><span class="sxs-lookup"><span data-stu-id="8b717-112">The code in the non-static `do` bindings section can reference the primary constructor parameters and any values or functions that are defined in the `let` bindings section.</span></span>

<span data-ttu-id="8b717-113">No estáticos `do` enlaces pueden tener acceso a los miembros de la clase como la clase tiene un identificador propio que se define mediante una `as` palabra clave en la clase de encabezado y siempre y cuando todos los usos de esos miembros se califican con el identificador propio para la clase.</span><span class="sxs-lookup"><span data-stu-id="8b717-113">Non-static `do` bindings can access members of the class as long as the class has a self identifier that is defined by an `as` keyword in the class heading, and as long as all uses of those members are qualified with the self identifier for the class.</span></span>

<span data-ttu-id="8b717-114">Porque `let` enlaces inicializan los campos privados de una clase, que a menudo es necesario para garantizar que los miembros se comportan según lo previsto, `do` enlaces normalmente se colocan después `let` enlaces por lo que el código en el `do` enlace puede ejecutar con un objeto totalmente inicializado.</span><span class="sxs-lookup"><span data-stu-id="8b717-114">Because `let` bindings initialize the private fields of a class, which is often necessary to guarantee that members behave as expected, `do` bindings are usually put after `let` bindings so that code in the `do` binding can execute with a fully initialized object.</span></span> <span data-ttu-id="8b717-115">Si el código intenta usar a un miembro antes de completar la inicialización, se produce una excepción InvalidOperationException.</span><span class="sxs-lookup"><span data-stu-id="8b717-115">If your code attempts to use a member before the initialization is complete, an InvalidOperationException is raised.</span></span>

<span data-ttu-id="8b717-116">Estática `do` enlaces pueden hacer referencia a miembros estáticos o campos de la envolvente clase pero no miembros o campos de instancia.</span><span class="sxs-lookup"><span data-stu-id="8b717-116">Static `do` bindings can reference static members or fields of the enclosing class but not instance members or fields.</span></span> <span data-ttu-id="8b717-117">Estática `do` enlaces pasan a formar parte del inicializador estático para la clase, que siempre se ejecutará antes de la clase se usa por primera vez.</span><span class="sxs-lookup"><span data-stu-id="8b717-117">Static `do` bindings become part of the static initializer for the class, which is guaranteed to execute before the class is first used.</span></span>

<span data-ttu-id="8b717-118">Se omiten los atributos para `do` enlaces de tipos.</span><span class="sxs-lookup"><span data-stu-id="8b717-118">Attributes are ignored for `do` bindings in types.</span></span> <span data-ttu-id="8b717-119">Si un atributo no es necesario para el código que se ejecuta en un `do` de enlace, que debe aplicarse al constructor principal.</span><span class="sxs-lookup"><span data-stu-id="8b717-119">If an attribute is required for code that executes in a `do` binding, it must be applied to the primary constructor.</span></span>

<span data-ttu-id="8b717-120">En el código siguiente, una clase tiene un estático `do` enlace y un nestatické `do` enlace.</span><span class="sxs-lookup"><span data-stu-id="8b717-120">In the following code, a class has a static `do` binding and a non-static `do` binding.</span></span> <span data-ttu-id="8b717-121">El objeto tiene un constructor que tiene dos parámetros, `a` y `b`, y dos campos privados se definen en el `let` enlaces para la clase.</span><span class="sxs-lookup"><span data-stu-id="8b717-121">The object has a constructor that has two parameters, `a` and `b`, and two private fields are defined in the `let` bindings for the class.</span></span> <span data-ttu-id="8b717-122">También se definen dos propiedades.</span><span class="sxs-lookup"><span data-stu-id="8b717-122">Two properties are also defined.</span></span> <span data-ttu-id="8b717-123">Todos ellos están en el ámbito en el que no sea estático `do` sección de enlaces, tal como se muestra en la línea que imprime todos esos valores.</span><span class="sxs-lookup"><span data-stu-id="8b717-123">All of these are in scope in the non-static `do` bindings section, as is illustrated by the line that prints all those values.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3101.fs)]

<span data-ttu-id="8b717-124">La salida es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="8b717-124">The output is as follows.</span></span>

```console
Initializing MyType.
Initializing object 1 2 2 4 8 16
```

## <a name="see-also"></a><span data-ttu-id="8b717-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="8b717-125">See also</span></span>

- [<span data-ttu-id="8b717-126">Miembros</span><span class="sxs-lookup"><span data-stu-id="8b717-126">Members</span></span>](index.md)
- [<span data-ttu-id="8b717-127">Clases</span><span class="sxs-lookup"><span data-stu-id="8b717-127">Classes</span></span>](../classes.md)
- [<span data-ttu-id="8b717-128">Constructores</span><span class="sxs-lookup"><span data-stu-id="8b717-128">Constructors</span></span>](constructors.md)
- <span data-ttu-id="8b717-129">[`let` Bindings in Classes](let-bindings-in-classes.md) (Enlaces `let` en clases)</span><span class="sxs-lookup"><span data-stu-id="8b717-129">[`let` Bindings in Classes](let-bindings-in-classes.md)</span></span>
- [<span data-ttu-id="8b717-130">`do` enlaces</span><span class="sxs-lookup"><span data-stu-id="8b717-130">`do` Bindings</span></span>](../functions/do-Bindings.md)
