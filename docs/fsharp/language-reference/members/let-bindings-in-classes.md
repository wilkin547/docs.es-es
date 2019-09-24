---
title: Enlaces let en clases
description: Obtenga información sobre cómo definir los campos privados y las F# funciones privadas para las clases mediante los enlaces ' Let ' en la definición de clase.
ms.date: 05/16/2016
ms.openlocfilehash: 1366ab8f1f4f606fe5947a8fc4df10de49346b3e
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216531"
---
# <a name="let-bindings-in-classes"></a><span data-ttu-id="a08e7-103">Enlaces let en clases</span><span class="sxs-lookup"><span data-stu-id="a08e7-103">let Bindings in Classes</span></span>

<span data-ttu-id="a08e7-104">Puede definir campos privados y funciones privadas para F# las clases mediante el `let` uso de enlaces en la definición de clase.</span><span class="sxs-lookup"><span data-stu-id="a08e7-104">You can define private fields and private functions for F# classes by using `let` bindings in the class definition.</span></span>

## <a name="syntax"></a><span data-ttu-id="a08e7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a08e7-105">Syntax</span></span>

```fsharp
// Field.
[static] let [ mutable ] binding1 [ and ... binding-n ]

// Function.
[static] let [ rec ] binding1 [ and ... binding-n ]
```

## <a name="remarks"></a><span data-ttu-id="a08e7-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a08e7-106">Remarks</span></span>

<span data-ttu-id="a08e7-107">La sintaxis anterior aparece después del encabezado de clase y las declaraciones de herencia, pero antes de cualquier definición de miembro.</span><span class="sxs-lookup"><span data-stu-id="a08e7-107">The previous syntax appears after the class heading and inheritance declarations but before any member definitions.</span></span> <span data-ttu-id="a08e7-108">La sintaxis es similar a la `let` de los enlaces fuera de las clases, pero los nombres definidos en una clase tienen un ámbito limitado a la clase.</span><span class="sxs-lookup"><span data-stu-id="a08e7-108">The syntax is like that of `let` bindings outside of classes, but the names defined in a class have a scope that is limited to the class.</span></span> <span data-ttu-id="a08e7-109">Un `let` enlace crea un campo o una función privados; para exponer datos o funciones públicamente, declare una propiedad o un método de miembro.</span><span class="sxs-lookup"><span data-stu-id="a08e7-109">A `let` binding creates a private field or function; to expose data or functions publicly, declare a property or a member method.</span></span>

<span data-ttu-id="a08e7-110">Un `let` enlace que no es estático se denomina enlace de `let` instancia.</span><span class="sxs-lookup"><span data-stu-id="a08e7-110">A `let` binding that is not static is called an instance `let` binding.</span></span> <span data-ttu-id="a08e7-111">Los `let` enlaces de instancia se ejecutan cuando se crean los objetos.</span><span class="sxs-lookup"><span data-stu-id="a08e7-111">Instance `let` bindings execute when objects are created.</span></span> <span data-ttu-id="a08e7-112">Los `let` enlaces estáticos forman parte del inicializador estático de la clase, que se garantiza que se ejecuta antes de que se use por primera vez el tipo.</span><span class="sxs-lookup"><span data-stu-id="a08e7-112">Static `let` bindings are part of the static initializer for the class, which is guaranteed to execute before the type is first used.</span></span>

<span data-ttu-id="a08e7-113">El código incluido en `let` los enlaces de instancia puede usar los parámetros del constructor principal.</span><span class="sxs-lookup"><span data-stu-id="a08e7-113">The code within instance `let` bindings can use the primary constructor's parameters.</span></span>

<span data-ttu-id="a08e7-114">Los atributos y los modificadores de accesibilidad no `let` se permiten en los enlaces de clases.</span><span class="sxs-lookup"><span data-stu-id="a08e7-114">Attributes and accessibility modifiers are not permitted on `let` bindings in classes.</span></span>

<span data-ttu-id="a08e7-115">En los siguientes ejemplos de código se muestran `let` varios tipos de enlaces en las clases.</span><span class="sxs-lookup"><span data-stu-id="a08e7-115">The following code examples illustrate several types of `let` bindings in classes.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3001.fs)]

<span data-ttu-id="a08e7-116">La salida es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="a08e7-116">The output is as follows.</span></span>

```console
10 52 1 204
```

## <a name="alternative-ways-to-create-fields"></a><span data-ttu-id="a08e7-117">Maneras alternativas de crear campos</span><span class="sxs-lookup"><span data-stu-id="a08e7-117">Alternative Ways to Create Fields</span></span>

<span data-ttu-id="a08e7-118">También puede usar la `val` palabra clave para crear un campo privado.</span><span class="sxs-lookup"><span data-stu-id="a08e7-118">You can also use the `val` keyword to create a private field.</span></span> <span data-ttu-id="a08e7-119">Cuando se usa `val` la palabra clave, el campo no recibe un valor cuando se crea el objeto, sino que se inicializa con un valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="a08e7-119">When using the `val` keyword, the field is not given a value when the object is created, but instead is initialized with a default value.</span></span> <span data-ttu-id="a08e7-120">Para obtener más información, [vea campos explícitos: Palabra clave](explicit-fields-the-val-keyword.md)Val.</span><span class="sxs-lookup"><span data-stu-id="a08e7-120">For more information, see [Explicit Fields: The val Keyword](explicit-fields-the-val-keyword.md).</span></span>

<span data-ttu-id="a08e7-121">También puede definir campos privados en una clase utilizando una definición de miembro y agregando la palabra `private` clave a la definición.</span><span class="sxs-lookup"><span data-stu-id="a08e7-121">You can also define private fields in a class by using a member definition and adding the keyword `private` to the definition.</span></span> <span data-ttu-id="a08e7-122">Esto puede ser útil si espera cambiar la accesibilidad de un miembro sin reescribir el código.</span><span class="sxs-lookup"><span data-stu-id="a08e7-122">This can be useful if you expect to change the accessibility of a member without rewriting your code.</span></span> <span data-ttu-id="a08e7-123">Para más información, vea [Access Control](../access-control.md) (Control de acceso).</span><span class="sxs-lookup"><span data-stu-id="a08e7-123">For more information, see [Access Control](../access-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a08e7-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="a08e7-124">See also</span></span>

- [<span data-ttu-id="a08e7-125">Miembros</span><span class="sxs-lookup"><span data-stu-id="a08e7-125">Members</span></span>](index.md)
- <span data-ttu-id="a08e7-126">[`do` Bindings in Classes](do-bindings-in-classes.md) (Enlaces `do` en clases)</span><span class="sxs-lookup"><span data-stu-id="a08e7-126">[`do` Bindings in Classes](do-bindings-in-classes.md)</span></span>
- [<span data-ttu-id="a08e7-127">`let`Enlaces</span><span class="sxs-lookup"><span data-stu-id="a08e7-127">`let` Bindings</span></span>](../functions/let-bindings.md)
