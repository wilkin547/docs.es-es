---
title: Enlaces let en clases (F#)
description: "Obtenga información acerca de cómo definir campos privados y funciones privadas para las clases de F # mediante enlaces 'let' en la definición de clase."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 9d3710f5-68b1-4e4c-b02b-27fe018f20e8
ms.openlocfilehash: 1337cc0794e366e8c39745f5c45065362c9c38c9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="let-bindings-in-classes"></a><span data-ttu-id="db267-104">Enlaces let en clases</span><span class="sxs-lookup"><span data-stu-id="db267-104">let Bindings in Classes</span></span>

<span data-ttu-id="db267-105">Puede definir campos privados y funciones privadas para las clases de F # mediante `let` enlaces en la definición de clase.</span><span class="sxs-lookup"><span data-stu-id="db267-105">You can define private fields and private functions for F# classes by using `let` bindings in the class definition.</span></span>


## <a name="syntax"></a><span data-ttu-id="db267-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="db267-106">Syntax</span></span>

```fsharp
// Field.
[static] let [ mutable ] binding1 [ and ... binding-n ]

// Function.
[static] let [ rec ] binding1 [ and ... binding-n ]
```

## <a name="remarks"></a><span data-ttu-id="db267-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="db267-107">Remarks</span></span>
<span data-ttu-id="db267-108">La sintaxis anterior aparece después de las declaraciones de encabezado y la herencia de clase pero antes de las definiciones de miembros.</span><span class="sxs-lookup"><span data-stu-id="db267-108">The previous syntax appears after the class heading and inheritance declarations but before any member definitions.</span></span> <span data-ttu-id="db267-109">La sintaxis es similar al de `let` enlaces fuera de las clases, pero los nombres definidos en una clase tienen un ámbito limitado a la clase.</span><span class="sxs-lookup"><span data-stu-id="db267-109">The syntax is like that of `let` bindings outside of classes, but the names defined in a class have a scope that is limited to the class.</span></span> <span data-ttu-id="db267-110">Un `let` enlace crea un campo privado o una función; para exponer los datos o funciones públicamente, declaran una propiedad o un método de miembro.</span><span class="sxs-lookup"><span data-stu-id="db267-110">A `let` binding creates a private field or function; to expose data or functions publicly, declare a property or a member method.</span></span>

<span data-ttu-id="db267-111">A `let` el enlace que no es estático se denomina una instancia `let` enlace.</span><span class="sxs-lookup"><span data-stu-id="db267-111">A `let` binding that is not static is called an instance `let` binding.</span></span> <span data-ttu-id="db267-112">Instancia `let` enlaces ejecutan cuando se crean los objetos.</span><span class="sxs-lookup"><span data-stu-id="db267-112">Instance `let` bindings execute when objects are created.</span></span> <span data-ttu-id="db267-113">Estática `let` enlaces forman parte del inicializador estático de la clase, que se garantiza que se ejecutará antes de que el tipo se usa por primera vez.</span><span class="sxs-lookup"><span data-stu-id="db267-113">Static `let` bindings are part of the static initializer for the class, which is guaranteed to execute before the type is first used.</span></span>

<span data-ttu-id="db267-114">El código dentro de la instancia `let` enlaces puedan utilizar los parámetros del constructor primario.</span><span class="sxs-lookup"><span data-stu-id="db267-114">The code within instance `let` bindings can use the primary constructor's parameters.</span></span>

<span data-ttu-id="db267-115">No se permiten los atributos y modificadores de accesibilidad en `let` enlaces en clases.</span><span class="sxs-lookup"><span data-stu-id="db267-115">Attributes and accessibility modifiers are not permitted on `let` bindings in classes.</span></span>

<span data-ttu-id="db267-116">Los ejemplos de código siguientes muestran varios tipos de `let` enlaces en clases.</span><span class="sxs-lookup"><span data-stu-id="db267-116">The following code examples illustrate several types of `let` bindings in classes.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3001.fs)]

<span data-ttu-id="db267-117">La salida es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="db267-117">The output is as follows.</span></span>

```
10 52 1 204
```

## <a name="alternative-ways-to-create-fields"></a><span data-ttu-id="db267-118">Maneras alternativas de crear campos</span><span class="sxs-lookup"><span data-stu-id="db267-118">Alternative Ways to Create Fields</span></span>
<span data-ttu-id="db267-119">También puede usar el `val` palabra clave que se va a crear un campo privado.</span><span class="sxs-lookup"><span data-stu-id="db267-119">You can also use the `val` keyword to create a private field.</span></span> <span data-ttu-id="db267-120">Cuando se usa el `val` palabra clave, el campo no tiene un valor cuando se crea el objeto, pero en su lugar se inicializa con un valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="db267-120">When using the `val` keyword, the field is not given a value when the object is created, but instead is initialized with a default value.</span></span> <span data-ttu-id="db267-121">Para obtener más información, consulte [campos explícitos: val (palabra clave)](explicit-fields-the-val-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="db267-121">For more information, see [Explicit Fields: The val Keyword](explicit-fields-the-val-keyword.md).</span></span>

<span data-ttu-id="db267-122">También puede definir campos privados en una clase con una definición de miembro y agregando la palabra clave `private` a la definición.</span><span class="sxs-lookup"><span data-stu-id="db267-122">You can also define private fields in a class by using a member definition and adding the keyword `private` to the definition.</span></span> <span data-ttu-id="db267-123">Esto puede ser útil si espera que cambie la accesibilidad de un miembro sin volver a escribir el código.</span><span class="sxs-lookup"><span data-stu-id="db267-123">This can be useful if you expect to change the accessibility of a member without rewriting your code.</span></span> <span data-ttu-id="db267-124">Para más información, vea [Access Control](../access-control.md) (Control de acceso).</span><span class="sxs-lookup"><span data-stu-id="db267-124">For more information, see [Access Control](../access-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="db267-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="db267-125">See Also</span></span>
[<span data-ttu-id="db267-126">Miembros</span><span class="sxs-lookup"><span data-stu-id="db267-126">Members</span></span>](index.md)

<span data-ttu-id="db267-127">[`do` Bindings in Classes](do-bindings-in-classes.md) (Enlaces `do` en clases)</span><span class="sxs-lookup"><span data-stu-id="db267-127">[`do` Bindings in Classes](do-bindings-in-classes.md)</span></span>

[<span data-ttu-id="db267-128">`let`Enlaces</span><span class="sxs-lookup"><span data-stu-id="db267-128">`let` Bindings</span></span>](../functions/let-bindings.md)
