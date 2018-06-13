---
title: Propiedades indizadas (F#)
description: 'Obtenga información acerca de las propiedades indizadas de F #, que son propiedades que proporcionan acceso de matriz a los datos ordenados.'
ms.date: 05/16/2016
ms.openlocfilehash: 503cef9693cfe5e13d4e2d19a721d65bff1ce749
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2018
ms.locfileid: "34235946"
---
# <a name="indexed-properties"></a><span data-ttu-id="2070e-103">Propiedades indizadas</span><span class="sxs-lookup"><span data-stu-id="2070e-103">Indexed Properties</span></span>

<span data-ttu-id="2070e-104">*Propiedades indizadas* propiedades que proporcionan acceso de la matriz a se ordenan los datos.</span><span class="sxs-lookup"><span data-stu-id="2070e-104">*Indexed properties* are properties that provide array-like access to ordered data.</span></span> <span data-ttu-id="2070e-105">Provienen de tres formas:</span><span class="sxs-lookup"><span data-stu-id="2070e-105">They come in three forms:</span></span>

* `Item`
* `Ordinal`
* `Cardinal`

<span data-ttu-id="2070e-106">Un miembro de F # debe denominarse uno de estos tres nombres para proporcionar acceso a la matriz.</span><span class="sxs-lookup"><span data-stu-id="2070e-106">An F# member must be named one of these three names to provide array-like access.</span></span> <span data-ttu-id="2070e-107">`IndexerName` se utiliza para representar cualquiera de las tres opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="2070e-107">`IndexerName` is used to represent any of the three options below:</span></span>


## <a name="syntax"></a><span data-ttu-id="2070e-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2070e-108">Syntax</span></span>

```fsharp
// Indexed property that has both get and set defined.
member self-identifier.IndexerName
    with get(index-variable) =
        get-function-body
    and set index-variablesvalue-variables =
        set-function-body

// Indexed property that has get only.
member self-identifier.IndexerName(index-variable) =
    get-function-body

// Alternative syntax for indexed property with get only
member self-identifier.IndexerName
    with get(index-variables) =
        get-function-body

// Indexed property that has set only.
member self-identifier.IndexerName
    with set index-variablesvalue-variables = 
        set-function-body
```

## <a name="remarks"></a><span data-ttu-id="2070e-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2070e-109">Remarks</span></span>
<span data-ttu-id="2070e-110">Las formas de la sintaxis anterior muestran cómo definir propiedades indizadas que tienen tanto una `get` y un `set` método, tienen un `get` método únicamente, o tiene un `set` método solo.</span><span class="sxs-lookup"><span data-stu-id="2070e-110">The forms of the previous syntax show how to define indexed properties that have both a `get` and a `set` method, have a `get` method only, or have a `set` method only.</span></span> <span data-ttu-id="2070e-111">También puede combinar ambos la sintaxis mostrada para get únicamente y la sintaxis mostrada para set únicamente y generar una propiedad que tenga get y set.</span><span class="sxs-lookup"><span data-stu-id="2070e-111">You can also combine both the syntax shown for get only and the syntax shown for set only, and produce a property that has both get and set.</span></span> <span data-ttu-id="2070e-112">Esta última forma permite colocar los atributos y modificadores de accesibilidad diferente en la operación get y establecer métodos.</span><span class="sxs-lookup"><span data-stu-id="2070e-112">This latter form allows you to put different accessibility modifiers and attributes on the get and set methods.</span></span>

<span data-ttu-id="2070e-113">Cuando el *IndexerName* es `Item`, el compilador trata la propiedad como una propiedad indizada predeterminada.</span><span class="sxs-lookup"><span data-stu-id="2070e-113">When the *IndexerName* is `Item`, the compiler treats the property as a default indexed property.</span></span> <span data-ttu-id="2070e-114">A *propiedad indizada predeterminada* es una propiedad que se puede tener acceso mediante sintaxis parecida a la matriz en la instancia del objeto.</span><span class="sxs-lookup"><span data-stu-id="2070e-114">A *default indexed property* is a property that you can access by using array-like syntax on the object instance.</span></span> <span data-ttu-id="2070e-115">Por ejemplo, si `obj` es un objeto del tipo que define esta propiedad, la sintaxis `obj.[index]` se usa para tener acceso a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="2070e-115">For example, if `obj` is an object of the type that defines this property, the syntax `obj.[index]` is used to access the property.</span></span>

<span data-ttu-id="2070e-116">La sintaxis para tener acceso a una propiedad indizada no predeterminada consiste en proporcionar el nombre de la propiedad y el índice entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="2070e-116">The syntax for accessing a nondefault indexed property is to provide the name of the property and the index in parentheses.</span></span> <span data-ttu-id="2070e-117">Por ejemplo, si la propiedad es `Ordinal`, se escribe `obj.Ordinal(index)` para tener acceso a él.</span><span class="sxs-lookup"><span data-stu-id="2070e-117">For example, if the property is `Ordinal`, you write `obj.Ordinal(index)` to access it.</span></span>

<span data-ttu-id="2070e-118">Independientemente de qué forma utilice, debe utilizar siempre el formulario currificado para el `set` método en una propiedad indizada.</span><span class="sxs-lookup"><span data-stu-id="2070e-118">Regardless of which form you use, you should always use the curried form for the `set` method on an indexed property.</span></span> <span data-ttu-id="2070e-119">Para obtener información acerca de las funciones currificadas, vea [funciones](../functions/index.md).</span><span class="sxs-lookup"><span data-stu-id="2070e-119">For information about curried functions, see [Functions](../functions/index.md).</span></span>

## <a name="example"></a><span data-ttu-id="2070e-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2070e-120">Example</span></span>

<span data-ttu-id="2070e-121">En el ejemplo de código siguiente se muestra la definición y el uso del valor predeterminado y las propiedades indizadas no predeterminadas que tienen get y set métodos.</span><span class="sxs-lookup"><span data-stu-id="2070e-121">The following code example illustrates the definition and use of default and non-default indexed properties that have get and set methods.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3301.fs)]

## <a name="output"></a><span data-ttu-id="2070e-122">Salida</span><span class="sxs-lookup"><span data-stu-id="2070e-122">Output</span></span>

```
ONE two three four five six seven eight nine ten
ONE first two second three third four fourth five fifth six 6th
seven seventh eight eighth nine ninth ten tenth
```

## <a name="indexed-properties-with-multiple-index-variables"></a><span data-ttu-id="2070e-123">Propiedades indizadas con varias Variables de índice</span><span class="sxs-lookup"><span data-stu-id="2070e-123">Indexed Properties with Multiple Index Variables</span></span>
<span data-ttu-id="2070e-124">Propiedades indizadas pueden tener más de una variable de índice.</span><span class="sxs-lookup"><span data-stu-id="2070e-124">Indexed properties can have more than one index variable.</span></span> <span data-ttu-id="2070e-125">En ese caso, las variables están separadas por comas cuando se utiliza la propiedad.</span><span class="sxs-lookup"><span data-stu-id="2070e-125">In that case, the variables are separated by commas when the property is used.</span></span> <span data-ttu-id="2070e-126">El método set de esta propiedad debe tener dos argumentos currificadas, el primero de los cuales es una tupla que contiene las claves y el segundo de los cuales es el valor que se va a establecer.</span><span class="sxs-lookup"><span data-stu-id="2070e-126">The set method in such a property must have two curried arguments, the first of which is a tuple containing the keys, and the second of which is the value being set.</span></span>

<span data-ttu-id="2070e-127">El código siguiente muestra el uso de una propiedad indizada con varias variables de índice.</span><span class="sxs-lookup"><span data-stu-id="2070e-127">The following code demonstrates the use of an indexed property with multiple index variables.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3302.fs)]
    
## <a name="see-also"></a><span data-ttu-id="2070e-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="2070e-128">See Also</span></span>
[<span data-ttu-id="2070e-129">Miembros</span><span class="sxs-lookup"><span data-stu-id="2070e-129">Members</span></span>](index.md)
