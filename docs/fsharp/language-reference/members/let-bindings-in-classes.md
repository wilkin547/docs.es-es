---
title: Enlaces let en clases (F#)
description: "Obtenga información acerca de cómo definir campos privados y funciones privadas para las clases de F # mediante enlaces 'let' en la definición de clase."
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: c4511a541403dde517acaf902e86de8d48f13781
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="let-bindings-in-classes"></a><span data-ttu-id="ab89b-103">Enlaces let en clases</span><span class="sxs-lookup"><span data-stu-id="ab89b-103">let Bindings in Classes</span></span>

<span data-ttu-id="ab89b-104">Puede definir campos privados y funciones privadas para las clases de F # mediante `let` enlaces en la definición de clase.</span><span class="sxs-lookup"><span data-stu-id="ab89b-104">You can define private fields and private functions for F# classes by using `let` bindings in the class definition.</span></span>


## <a name="syntax"></a><span data-ttu-id="ab89b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ab89b-105">Syntax</span></span>

```fsharp
// Field.
[static] let [ mutable ] binding1 [ and ... binding-n ]

// Function.
[static] let [ rec ] binding1 [ and ... binding-n ]
```

## <a name="remarks"></a><span data-ttu-id="ab89b-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ab89b-106">Remarks</span></span>
<span data-ttu-id="ab89b-107">La sintaxis anterior aparece después de las declaraciones de encabezado y la herencia de clase pero antes de las definiciones de miembros.</span><span class="sxs-lookup"><span data-stu-id="ab89b-107">The previous syntax appears after the class heading and inheritance declarations but before any member definitions.</span></span> <span data-ttu-id="ab89b-108">La sintaxis es similar al de `let` enlaces fuera de las clases, pero los nombres definidos en una clase tienen un ámbito limitado a la clase.</span><span class="sxs-lookup"><span data-stu-id="ab89b-108">The syntax is like that of `let` bindings outside of classes, but the names defined in a class have a scope that is limited to the class.</span></span> <span data-ttu-id="ab89b-109">Un `let` enlace crea un campo privado o una función; para exponer los datos o funciones públicamente, declaran una propiedad o un método de miembro.</span><span class="sxs-lookup"><span data-stu-id="ab89b-109">A `let` binding creates a private field or function; to expose data or functions publicly, declare a property or a member method.</span></span>

<span data-ttu-id="ab89b-110">A `let` el enlace que no es estático se denomina una instancia `let` enlace.</span><span class="sxs-lookup"><span data-stu-id="ab89b-110">A `let` binding that is not static is called an instance `let` binding.</span></span> <span data-ttu-id="ab89b-111">Instancia `let` enlaces ejecutan cuando se crean los objetos.</span><span class="sxs-lookup"><span data-stu-id="ab89b-111">Instance `let` bindings execute when objects are created.</span></span> <span data-ttu-id="ab89b-112">Estática `let` enlaces forman parte del inicializador estático de la clase, que se garantiza que se ejecutará antes de que el tipo se usa por primera vez.</span><span class="sxs-lookup"><span data-stu-id="ab89b-112">Static `let` bindings are part of the static initializer for the class, which is guaranteed to execute before the type is first used.</span></span>

<span data-ttu-id="ab89b-113">El código dentro de la instancia `let` enlaces puedan utilizar los parámetros del constructor primario.</span><span class="sxs-lookup"><span data-stu-id="ab89b-113">The code within instance `let` bindings can use the primary constructor's parameters.</span></span>

<span data-ttu-id="ab89b-114">No se permiten los atributos y modificadores de accesibilidad en `let` enlaces en clases.</span><span class="sxs-lookup"><span data-stu-id="ab89b-114">Attributes and accessibility modifiers are not permitted on `let` bindings in classes.</span></span>

<span data-ttu-id="ab89b-115">Los ejemplos de código siguientes muestran varios tipos de `let` enlaces en clases.</span><span class="sxs-lookup"><span data-stu-id="ab89b-115">The following code examples illustrate several types of `let` bindings in classes.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3001.fs)]

<span data-ttu-id="ab89b-116">La salida es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="ab89b-116">The output is as follows.</span></span>

```
10 52 1 204
```

## <a name="alternative-ways-to-create-fields"></a><span data-ttu-id="ab89b-117">Maneras alternativas de crear campos</span><span class="sxs-lookup"><span data-stu-id="ab89b-117">Alternative Ways to Create Fields</span></span>
<span data-ttu-id="ab89b-118">También puede usar el `val` palabra clave que se va a crear un campo privado.</span><span class="sxs-lookup"><span data-stu-id="ab89b-118">You can also use the `val` keyword to create a private field.</span></span> <span data-ttu-id="ab89b-119">Cuando se usa el `val` palabra clave, el campo no tiene un valor cuando se crea el objeto, pero en su lugar se inicializa con un valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="ab89b-119">When using the `val` keyword, the field is not given a value when the object is created, but instead is initialized with a default value.</span></span> <span data-ttu-id="ab89b-120">Para obtener más información, consulte [campos explícitos: val (palabra clave)](explicit-fields-the-val-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="ab89b-120">For more information, see [Explicit Fields: The val Keyword](explicit-fields-the-val-keyword.md).</span></span>

<span data-ttu-id="ab89b-121">También puede definir campos privados en una clase con una definición de miembro y agregando la palabra clave `private` a la definición.</span><span class="sxs-lookup"><span data-stu-id="ab89b-121">You can also define private fields in a class by using a member definition and adding the keyword `private` to the definition.</span></span> <span data-ttu-id="ab89b-122">Esto puede ser útil si espera que cambie la accesibilidad de un miembro sin volver a escribir el código.</span><span class="sxs-lookup"><span data-stu-id="ab89b-122">This can be useful if you expect to change the accessibility of a member without rewriting your code.</span></span> <span data-ttu-id="ab89b-123">Para más información, vea [Access Control](../access-control.md) (Control de acceso).</span><span class="sxs-lookup"><span data-stu-id="ab89b-123">For more information, see [Access Control](../access-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ab89b-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="ab89b-124">See Also</span></span>
[<span data-ttu-id="ab89b-125">Miembros</span><span class="sxs-lookup"><span data-stu-id="ab89b-125">Members</span></span>](index.md)

<span data-ttu-id="ab89b-126">[`do` Bindings in Classes](do-bindings-in-classes.md) (Enlaces `do` en clases)</span><span class="sxs-lookup"><span data-stu-id="ab89b-126">[`do` Bindings in Classes](do-bindings-in-classes.md)</span></span>

[<span data-ttu-id="ab89b-127">`let` Enlaces</span><span class="sxs-lookup"><span data-stu-id="ab89b-127">`let` Bindings</span></span>](../functions/let-bindings.md)
