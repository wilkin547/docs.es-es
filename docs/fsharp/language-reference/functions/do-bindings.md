---
title: Enlaces do (F#)
description: "Obtenga información acerca de cómo un 'do' enlace de F # se usa para ejecutar el código sin tener que definir una función o un valor."
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 4c63da0c5e2f4130d59f9efa6bc54a55e5fe9fd8
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="do-bindings"></a><span data-ttu-id="e68ae-103">do (Enlaces)</span><span class="sxs-lookup"><span data-stu-id="e68ae-103">do Bindings</span></span>

<span data-ttu-id="e68ae-104">Un `do` enlace se usa para ejecutar el código sin tener que definir una función o un valor.</span><span class="sxs-lookup"><span data-stu-id="e68ae-104">A `do` binding is used to execute code without defining a function or value.</span></span> <span data-ttu-id="e68ae-105">Además, ¿se pueden ser los enlaces se usa en clases, consulte [ `do` enlaces en clases](../members/do-bindings-in-classes.md).</span><span class="sxs-lookup"><span data-stu-id="e68ae-105">Also, do bindings can be used in classes, see [`do` Bindings in Classes](../members/do-bindings-in-classes.md).</span></span>


## <a name="syntax"></a><span data-ttu-id="e68ae-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e68ae-106">Syntax</span></span>

```fsharp
[ attributes ]
[ do ]expression
```

## <a name="remarks"></a><span data-ttu-id="e68ae-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e68ae-107">Remarks</span></span>
<span data-ttu-id="e68ae-108">Use un `do` cuando desee ejecutar código independientemente de una definición de función o un valor de enlace.</span><span class="sxs-lookup"><span data-stu-id="e68ae-108">Use a `do` binding when you want to execute code independently of a function or value definition.</span></span> <span data-ttu-id="e68ae-109">La expresión en una `do` enlace debe devolver `unit`.</span><span class="sxs-lookup"><span data-stu-id="e68ae-109">The expression in a `do` binding must return `unit`.</span></span> <span data-ttu-id="e68ae-110">Código en un nivel superior `do` enlace se ejecuta cuando se inicializa el módulo.</span><span class="sxs-lookup"><span data-stu-id="e68ae-110">Code in a top-level `do` binding is executed when the module is initialized.</span></span> <span data-ttu-id="e68ae-111">La palabra clave `do` es opcional.</span><span class="sxs-lookup"><span data-stu-id="e68ae-111">The keyword `do` is optional.</span></span>

<span data-ttu-id="e68ae-112">Se pueden aplicar atributos a un nivel superior `do` enlace.</span><span class="sxs-lookup"><span data-stu-id="e68ae-112">Attributes can be applied to a top-level `do` binding.</span></span> <span data-ttu-id="e68ae-113">Por ejemplo, si el programa utiliza la interoperabilidad COM, puede aplicar el `STAThread` de atributo para el programa.</span><span class="sxs-lookup"><span data-stu-id="e68ae-113">For example, if your program uses COM interop, you might want to apply the `STAThread` attribute to your program.</span></span> <span data-ttu-id="e68ae-114">Puede hacerlo mediante el uso de un atributo en un `do` de enlace, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="e68ae-114">You can do this by using an attribute on a `do` binding, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet201.fs)]
    
## <a name="see-also"></a><span data-ttu-id="e68ae-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="e68ae-115">See Also</span></span>
[<span data-ttu-id="e68ae-116">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="e68ae-116">F# Language Reference</span></span>](../index.md)

[<span data-ttu-id="e68ae-117">Funciones</span><span class="sxs-lookup"><span data-stu-id="e68ae-117">Functions</span></span>](index.md)

