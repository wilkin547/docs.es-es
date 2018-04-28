---
title: Propiedades indizadas (F#)
description: 'Obtenga información acerca de las propiedades indizadas de F #, que son propiedades que proporcionan acceso de matriz a los datos ordenados.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 39396b3a5ec43f9a8ab0df96afeb69e05801c752
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="indexed-properties"></a><span data-ttu-id="28d30-103">Propiedades indizadas</span><span class="sxs-lookup"><span data-stu-id="28d30-103">Indexed Properties</span></span>

<span data-ttu-id="28d30-104">*Propiedades indizadas* propiedades que proporcionan acceso de la matriz a se ordenan los datos.</span><span class="sxs-lookup"><span data-stu-id="28d30-104">*Indexed properties* are properties that provide array-like access to ordered data.</span></span>


## <a name="syntax"></a><span data-ttu-id="28d30-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="28d30-105">Syntax</span></span>

```fsharp
// Indexed property that has both get and set defined.
member self-identifier.PropertyName
    with get(index-variable) =
        get-function-body
    and set index-variablesvalue-variables =
        set-function-body

// Indexed property that has get only.
member self-identifier.PropertyName(index-variable) =
    get-function-body

// Alternative syntax for indexed property with get only
member self-identifier.PropertyName
    with get(index-variables) =
        get-function-body

// Indexed property that has set only.
member self-identifier.PropertyName
    with set index-variablesvalue-variables = 
        set-function-body
```

## <a name="remarks"></a><span data-ttu-id="28d30-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="28d30-106">Remarks</span></span>
<span data-ttu-id="28d30-107">Las tres formas de la sintaxis anterior muestran cómo definir propiedades indizadas que tienen tanto una `get` y un `set` método, tienen un `get` método únicamente, o tiene un `set` método solo.</span><span class="sxs-lookup"><span data-stu-id="28d30-107">The three forms of the previous syntax show how to define indexed properties that have both a `get` and a `set` method, have a `get` method only, or have a `set` method only.</span></span> <span data-ttu-id="28d30-108">También puede combinar ambos la sintaxis mostrada para get únicamente y la sintaxis mostrada para set únicamente y generar una propiedad que tenga get y set.</span><span class="sxs-lookup"><span data-stu-id="28d30-108">You can also combine both the syntax shown for get only and the syntax shown for set only, and produce a property that has both get and set.</span></span> <span data-ttu-id="28d30-109">Esta última forma permite colocar los atributos y modificadores de accesibilidad diferente en la operación get y establecer métodos.</span><span class="sxs-lookup"><span data-stu-id="28d30-109">This latter form allows you to put different accessibility modifiers and attributes on the get and set methods.</span></span>

<span data-ttu-id="28d30-110">Cuando el *PropertyName* es `Item`, el compilador trata la propiedad como una propiedad indizada predeterminada.</span><span class="sxs-lookup"><span data-stu-id="28d30-110">When the *PropertyName* is `Item`, the compiler treats the property as a default indexed property.</span></span> <span data-ttu-id="28d30-111">A *propiedad indizada predeterminada* es una propiedad que se puede tener acceso mediante sintaxis parecida a la matriz en la instancia del objeto.</span><span class="sxs-lookup"><span data-stu-id="28d30-111">A *default indexed property* is a property that you can access by using array-like syntax on the object instance.</span></span> <span data-ttu-id="28d30-112">Por ejemplo, si `obj` es un objeto del tipo que define esta propiedad, la sintaxis `obj.[index]` se usa para tener acceso a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="28d30-112">For example, if `obj` is an object of the type that defines this property, the syntax `obj.[index]` is used to access the property.</span></span>

<span data-ttu-id="28d30-113">La sintaxis para tener acceso a una propiedad indizada no predeterminada consiste en proporcionar el nombre de la propiedad y el índice entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="28d30-113">The syntax for accessing a nondefault indexed property is to provide the name of the property and the index in parentheses.</span></span> <span data-ttu-id="28d30-114">Por ejemplo, si la propiedad es `Ordinal`, se escribe `obj.Ordinal(index)` para tener acceso a él.</span><span class="sxs-lookup"><span data-stu-id="28d30-114">For example, if the property is `Ordinal`, you write `obj.Ordinal(index)` to access it.</span></span>

<span data-ttu-id="28d30-115">Independientemente de qué forma utilice, debe utilizar siempre el formulario currificado para el `set` método en una propiedad indizada.</span><span class="sxs-lookup"><span data-stu-id="28d30-115">Regardless of which form you use, you should always use the curried form for the `set` method on an indexed property.</span></span> <span data-ttu-id="28d30-116">Para obtener información acerca de las funciones currificadas, vea [funciones](../functions/index.md).</span><span class="sxs-lookup"><span data-stu-id="28d30-116">For information about curried functions, see [Functions](../functions/index.md).</span></span>

## <a name="example"></a><span data-ttu-id="28d30-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="28d30-117">Example</span></span>

<span data-ttu-id="28d30-118">En el ejemplo de código siguiente se muestra la definición y el uso del valor predeterminado y las propiedades indizadas no predeterminadas que tienen get y set métodos.</span><span class="sxs-lookup"><span data-stu-id="28d30-118">The following code example illustrates the definition and use of default and non-default indexed properties that have get and set methods.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3301.fs)]

## <a name="output"></a><span data-ttu-id="28d30-119">Salida</span><span class="sxs-lookup"><span data-stu-id="28d30-119">Output</span></span>

```
ONE two three four five six seven eight nine ten
ONE first two second three third four fourth five fifth six 6th
seven seventh eight eighth nine ninth ten tenth
```

## <a name="indexed-properties-with-multiple-index-variables"></a><span data-ttu-id="28d30-120">Propiedades indizadas con varias Variables de índice</span><span class="sxs-lookup"><span data-stu-id="28d30-120">Indexed Properties with Multiple Index Variables</span></span>
<span data-ttu-id="28d30-121">Propiedades indizadas pueden tener más de una variable de índice.</span><span class="sxs-lookup"><span data-stu-id="28d30-121">Indexed properties can have more than one index variable.</span></span> <span data-ttu-id="28d30-122">En ese caso, las variables están separadas por comas cuando se utiliza la propiedad.</span><span class="sxs-lookup"><span data-stu-id="28d30-122">In that case, the variables are separated by commas when the property is used.</span></span> <span data-ttu-id="28d30-123">El método set de esta propiedad debe tener dos argumentos currificadas, el primero de los cuales es una tupla que contiene las claves y el segundo de los cuales es el valor que se va a establecer.</span><span class="sxs-lookup"><span data-stu-id="28d30-123">The set method in such a property must have two curried arguments, the first of which is a tuple containing the keys, and the second of which is the value being set.</span></span>

<span data-ttu-id="28d30-124">El código siguiente muestra el uso de una propiedad indizada con varias variables de índice.</span><span class="sxs-lookup"><span data-stu-id="28d30-124">The following code demonstrates the use of an indexed property with multiple index variables.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3302.fs)]
    
## <a name="see-also"></a><span data-ttu-id="28d30-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="28d30-125">See Also</span></span>
[<span data-ttu-id="28d30-126">Miembros</span><span class="sxs-lookup"><span data-stu-id="28d30-126">Members</span></span>](index.md)
