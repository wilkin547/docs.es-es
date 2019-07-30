---
title: Enlaces let en clases
description: Obtenga información sobre cómo definir los campos privados y las F# funciones privadas para las clases mediante los enlaces ' Let ' en la definición de clase.
ms.date: 05/16/2016
ms.openlocfilehash: 0086d3a91f85395c2bd0555f978c5d951c363357
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627487"
---
# <a name="let-bindings-in-classes"></a><span data-ttu-id="5c023-103">Enlaces let en clases</span><span class="sxs-lookup"><span data-stu-id="5c023-103">let Bindings in Classes</span></span>

<span data-ttu-id="5c023-104">Puede definir campos privados y funciones privadas para F# las clases mediante el `let` uso de enlaces en la definición de clase.</span><span class="sxs-lookup"><span data-stu-id="5c023-104">You can define private fields and private functions for F# classes by using `let` bindings in the class definition.</span></span>

## <a name="syntax"></a><span data-ttu-id="5c023-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5c023-105">Syntax</span></span>

```fsharp
// Field.
[static] let [ mutable ] binding1 [ and ... binding-n ]

// Function.
[static] let [ rec ] binding1 [ and ... binding-n ]
```

## <a name="remarks"></a><span data-ttu-id="5c023-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5c023-106">Remarks</span></span>

<span data-ttu-id="5c023-107">La sintaxis anterior aparece después del encabezado de clase y las declaraciones de herencia, pero antes de cualquier definición de miembro.</span><span class="sxs-lookup"><span data-stu-id="5c023-107">The previous syntax appears after the class heading and inheritance declarations but before any member definitions.</span></span> <span data-ttu-id="5c023-108">La sintaxis es similar a la `let` de los enlaces fuera de las clases, pero los nombres definidos en una clase tienen un ámbito limitado a la clase.</span><span class="sxs-lookup"><span data-stu-id="5c023-108">The syntax is like that of `let` bindings outside of classes, but the names defined in a class have a scope that is limited to the class.</span></span> <span data-ttu-id="5c023-109">Un `let` enlace crea un campo o una función privados; para exponer datos o funciones públicamente, declare una propiedad o un método de miembro.</span><span class="sxs-lookup"><span data-stu-id="5c023-109">A `let` binding creates a private field or function; to expose data or functions publicly, declare a property or a member method.</span></span>

<span data-ttu-id="5c023-110">Un `let` enlace que no es estático se denomina enlace de `let` instancia.</span><span class="sxs-lookup"><span data-stu-id="5c023-110">A `let` binding that is not static is called an instance `let` binding.</span></span> <span data-ttu-id="5c023-111">Los `let` enlaces de instancia se ejecutan cuando se crean los objetos.</span><span class="sxs-lookup"><span data-stu-id="5c023-111">Instance `let` bindings execute when objects are created.</span></span> <span data-ttu-id="5c023-112">Los `let` enlaces estáticos forman parte del inicializador estático de la clase, que se garantiza que se ejecuta antes de que se use por primera vez el tipo.</span><span class="sxs-lookup"><span data-stu-id="5c023-112">Static `let` bindings are part of the static initializer for the class, which is guaranteed to execute before the type is first used.</span></span>

<span data-ttu-id="5c023-113">El código incluido en `let` los enlaces de instancia puede usar los parámetros del constructor principal.</span><span class="sxs-lookup"><span data-stu-id="5c023-113">The code within instance `let` bindings can use the primary constructor's parameters.</span></span>

<span data-ttu-id="5c023-114">Los atributos y los modificadores de accesibilidad no `let` se permiten en los enlaces de clases.</span><span class="sxs-lookup"><span data-stu-id="5c023-114">Attributes and accessibility modifiers are not permitted on `let` bindings in classes.</span></span>

<span data-ttu-id="5c023-115">En los siguientes ejemplos de código se muestran `let` varios tipos de enlaces en las clases.</span><span class="sxs-lookup"><span data-stu-id="5c023-115">The following code examples illustrate several types of `let` bindings in classes.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3001.fs)]

<span data-ttu-id="5c023-116">La salida es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="5c023-116">The output is as follows.</span></span>

```
10 52 1 204
```

## <a name="alternative-ways-to-create-fields"></a><span data-ttu-id="5c023-117">Maneras alternativas de crear campos</span><span class="sxs-lookup"><span data-stu-id="5c023-117">Alternative Ways to Create Fields</span></span>

<span data-ttu-id="5c023-118">También puede usar la `val` palabra clave para crear un campo privado.</span><span class="sxs-lookup"><span data-stu-id="5c023-118">You can also use the `val` keyword to create a private field.</span></span> <span data-ttu-id="5c023-119">Cuando se usa `val` la palabra clave, el campo no recibe un valor cuando se crea el objeto, sino que se inicializa con un valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="5c023-119">When using the `val` keyword, the field is not given a value when the object is created, but instead is initialized with a default value.</span></span> <span data-ttu-id="5c023-120">Para obtener más información, [vea campos explícitos: Palabra clave](explicit-fields-the-val-keyword.md)Val.</span><span class="sxs-lookup"><span data-stu-id="5c023-120">For more information, see [Explicit Fields: The val Keyword](explicit-fields-the-val-keyword.md).</span></span>

<span data-ttu-id="5c023-121">También puede definir campos privados en una clase utilizando una definición de miembro y agregando la palabra `private` clave a la definición.</span><span class="sxs-lookup"><span data-stu-id="5c023-121">You can also define private fields in a class by using a member definition and adding the keyword `private` to the definition.</span></span> <span data-ttu-id="5c023-122">Esto puede ser útil si espera cambiar la accesibilidad de un miembro sin reescribir el código.</span><span class="sxs-lookup"><span data-stu-id="5c023-122">This can be useful if you expect to change the accessibility of a member without rewriting your code.</span></span> <span data-ttu-id="5c023-123">Para más información, vea [Access Control](../access-control.md) (Control de acceso).</span><span class="sxs-lookup"><span data-stu-id="5c023-123">For more information, see [Access Control](../access-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5c023-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="5c023-124">See also</span></span>

- [<span data-ttu-id="5c023-125">Miembros</span><span class="sxs-lookup"><span data-stu-id="5c023-125">Members</span></span>](index.md)
- <span data-ttu-id="5c023-126">[`do` Bindings in Classes](do-bindings-in-classes.md) (Enlaces `do` en clases)</span><span class="sxs-lookup"><span data-stu-id="5c023-126">[`do` Bindings in Classes](do-bindings-in-classes.md)</span></span>
- [<span data-ttu-id="5c023-127">`let`Enlaces</span><span class="sxs-lookup"><span data-stu-id="5c023-127">`let` Bindings</span></span>](../functions/let-bindings.md)
