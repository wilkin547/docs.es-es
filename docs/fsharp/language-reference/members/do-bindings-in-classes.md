---
title: Enlaces do en clases
description: Obtenga información sobre cómo usar F# un enlace ' do ' en una definición de clase, que realiza acciones cuando se construye el objeto o cuando se usa el tipo por primera vez.
ms.date: 05/16/2016
ms.openlocfilehash: ced4f1bb17d9e23bf51cc79b5a275cc334cca013
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627587"
---
# <a name="do-bindings-in-classes"></a><span data-ttu-id="28958-103">Enlaces do en clases</span><span class="sxs-lookup"><span data-stu-id="28958-103">do Bindings in Classes</span></span>

<span data-ttu-id="28958-104">Un `do` enlace en una definición de clase realiza acciones cuando se construye el objeto o, para un `do` enlace estático, cuando se usa por primera vez el tipo.</span><span class="sxs-lookup"><span data-stu-id="28958-104">A `do` binding in a class definition performs actions when the object is constructed or, for a static `do` binding, when the type is first used.</span></span>

## <a name="syntax"></a><span data-ttu-id="28958-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="28958-105">Syntax</span></span>

```fsharp
[static] do expression
```

## <a name="remarks"></a><span data-ttu-id="28958-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="28958-106">Remarks</span></span>

<span data-ttu-id="28958-107">Un `do` enlace aparece junto con los enlaces `let` o después, pero antes de las definiciones de miembro en una definición de clase.</span><span class="sxs-lookup"><span data-stu-id="28958-107">A `do` binding appears together with or after `let` bindings but before member definitions in a class definition.</span></span> <span data-ttu-id="28958-108">Aunque la `do` palabra clave es opcional `do` para los enlaces en el nivel de módulo, no es opcional `do` para los enlaces en una definición de clase.</span><span class="sxs-lookup"><span data-stu-id="28958-108">Although the `do` keyword is optional for `do` bindings at the module level, it is not optional for `do` bindings in a class definition.</span></span>

<span data-ttu-id="28958-109">Para la construcción de cada objeto de un tipo determinado, los enlaces no `do` estáticos y los enlaces no `let` estáticos se ejecutan en el orden en que aparecen en la definición de clase.</span><span class="sxs-lookup"><span data-stu-id="28958-109">For the construction of every object of any given type, non-static `do` bindings and non-static `let` bindings are executed in the order in which they appear in the class definition.</span></span> <span data-ttu-id="28958-110">Pueden `do` producirse varios enlaces en un tipo.</span><span class="sxs-lookup"><span data-stu-id="28958-110">Multiple `do` bindings can occur in one type.</span></span> <span data-ttu-id="28958-111">Los enlaces no estáticos `let` y los enlaces no estáticos `do` se convierten en el cuerpo del constructor principal.</span><span class="sxs-lookup"><span data-stu-id="28958-111">The non-static `let` bindings and the non-static `do` bindings become the body of the primary constructor.</span></span> <span data-ttu-id="28958-112">El código de la sección de enlaces `do` no estáticos puede hacer referencia a los parámetros del constructor principal y a los valores o funciones que `let` se definen en la sección de enlaces.</span><span class="sxs-lookup"><span data-stu-id="28958-112">The code in the non-static `do` bindings section can reference the primary constructor parameters and any values or functions that are defined in the `let` bindings section.</span></span>

<span data-ttu-id="28958-113">Los enlaces no `do` estáticos pueden tener acceso a los miembros de la clase siempre que la clase tenga un identificador propio definido por una `as` palabra clave en el encabezado de la clase, y siempre y cuando todos los usos de esos miembros estén calificados con el propio identificador de la clase.</span><span class="sxs-lookup"><span data-stu-id="28958-113">Non-static `do` bindings can access members of the class as long as the class has a self identifier that is defined by an `as` keyword in the class heading, and as long as all uses of those members are qualified with the self identifier for the class.</span></span>

<span data-ttu-id="28958-114">Dado `let` que los enlaces inicializan los campos privados de una clase, que a menudo es necesario para garantizar que los miembros `do` se comportan según lo `let` esperado, los enlaces normalmente se colocan después de los enlaces para que el `do` código del enlace pueda Ejecute con un objeto completamente inicializado.</span><span class="sxs-lookup"><span data-stu-id="28958-114">Because `let` bindings initialize the private fields of a class, which is often necessary to guarantee that members behave as expected, `do` bindings are usually put after `let` bindings so that code in the `do` binding can execute with a fully initialized object.</span></span> <span data-ttu-id="28958-115">Si el código intenta utilizar un miembro antes de que se complete la inicialización, se genera una excepción InvalidOperationException.</span><span class="sxs-lookup"><span data-stu-id="28958-115">If your code attempts to use a member before the initialization is complete, an InvalidOperationException is raised.</span></span>

<span data-ttu-id="28958-116">Los `do` enlaces estáticos pueden hacer referencia a los miembros o campos estáticos de la clase envolvente, pero no a los miembros o campos de instancia.</span><span class="sxs-lookup"><span data-stu-id="28958-116">Static `do` bindings can reference static members or fields of the enclosing class but not instance members or fields.</span></span> <span data-ttu-id="28958-117">Los `do` enlaces estáticos forman parte del inicializador estático de la clase, que se garantiza que se ejecuta antes de que se use por primera vez la clase.</span><span class="sxs-lookup"><span data-stu-id="28958-117">Static `do` bindings become part of the static initializer for the class, which is guaranteed to execute before the class is first used.</span></span>

<span data-ttu-id="28958-118">Los atributos se omiten para `do` los enlaces de los tipos.</span><span class="sxs-lookup"><span data-stu-id="28958-118">Attributes are ignored for `do` bindings in types.</span></span> <span data-ttu-id="28958-119">Si se requiere un atributo para el código que se ejecuta en `do` un enlace, debe aplicarse al constructor principal.</span><span class="sxs-lookup"><span data-stu-id="28958-119">If an attribute is required for code that executes in a `do` binding, it must be applied to the primary constructor.</span></span>

<span data-ttu-id="28958-120">En el código siguiente, una clase tiene un enlace `do` estático y un enlace no estático `do` .</span><span class="sxs-lookup"><span data-stu-id="28958-120">In the following code, a class has a static `do` binding and a non-static `do` binding.</span></span> <span data-ttu-id="28958-121">El objeto tiene un constructor que tiene dos parámetros, `a` y `b`, y dos campos privados se definen en los `let` enlaces de la clase.</span><span class="sxs-lookup"><span data-stu-id="28958-121">The object has a constructor that has two parameters, `a` and `b`, and two private fields are defined in the `let` bindings for the class.</span></span> <span data-ttu-id="28958-122">También se definen dos propiedades.</span><span class="sxs-lookup"><span data-stu-id="28958-122">Two properties are also defined.</span></span> <span data-ttu-id="28958-123">Todos se encuentran en el ámbito de la sección de enlaces `do` no estáticos, como se muestra en la línea que imprime todos esos valores.</span><span class="sxs-lookup"><span data-stu-id="28958-123">All of these are in scope in the non-static `do` bindings section, as is illustrated by the line that prints all those values.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3101.fs)]

<span data-ttu-id="28958-124">La salida es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="28958-124">The output is as follows.</span></span>

```console
Initializing MyType.
Initializing object 1 2 2 4 8 16
```

## <a name="see-also"></a><span data-ttu-id="28958-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="28958-125">See also</span></span>

- [<span data-ttu-id="28958-126">Miembros</span><span class="sxs-lookup"><span data-stu-id="28958-126">Members</span></span>](index.md)
- [<span data-ttu-id="28958-127">Clases</span><span class="sxs-lookup"><span data-stu-id="28958-127">Classes</span></span>](../classes.md)
- [<span data-ttu-id="28958-128">Constructores</span><span class="sxs-lookup"><span data-stu-id="28958-128">Constructors</span></span>](constructors.md)
- <span data-ttu-id="28958-129">[`let` Bindings in Classes](let-bindings-in-classes.md) (Enlaces `let` en clases)</span><span class="sxs-lookup"><span data-stu-id="28958-129">[`let` Bindings in Classes](let-bindings-in-classes.md)</span></span>
- [<span data-ttu-id="28958-130">`do`Enlaces</span><span class="sxs-lookup"><span data-stu-id="28958-130">`do` Bindings</span></span>](../functions/do-Bindings.md)
