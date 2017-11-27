---
title: Enlaces do (F#)
description: "Obtenga información acerca de cómo un 'do' enlace de F # se usa para ejecutar el código sin tener que definir una función o un valor."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 4c1057a3-3aa1-4b64-b46a-25ffe33f0be9
ms.openlocfilehash: f2563d384b67c005c96c2ff487c786476d385e70
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="do-bindings"></a><span data-ttu-id="025d7-104">do (Enlaces)</span><span class="sxs-lookup"><span data-stu-id="025d7-104">do Bindings</span></span>

<span data-ttu-id="025d7-105">Un `do` enlace se usa para ejecutar el código sin tener que definir una función o un valor.</span><span class="sxs-lookup"><span data-stu-id="025d7-105">A `do` binding is used to execute code without defining a function or value.</span></span> <span data-ttu-id="025d7-106">Además, ¿se pueden ser los enlaces se usa en clases, consulte [ `do` enlaces en clases](../members/do-bindings-in-classes.md).</span><span class="sxs-lookup"><span data-stu-id="025d7-106">Also, do bindings can be used in classes, see [`do` Bindings in Classes](../members/do-bindings-in-classes.md).</span></span>


## <a name="syntax"></a><span data-ttu-id="025d7-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="025d7-107">Syntax</span></span>

```fsharp
[ attributes ]
[ do ]expression
```

## <a name="remarks"></a><span data-ttu-id="025d7-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="025d7-108">Remarks</span></span>
<span data-ttu-id="025d7-109">Use un `do` cuando desee ejecutar código independientemente de una definición de función o un valor de enlace.</span><span class="sxs-lookup"><span data-stu-id="025d7-109">Use a `do` binding when you want to execute code independently of a function or value definition.</span></span> <span data-ttu-id="025d7-110">La expresión en una `do` enlace debe devolver `unit`.</span><span class="sxs-lookup"><span data-stu-id="025d7-110">The expression in a `do` binding must return `unit`.</span></span> <span data-ttu-id="025d7-111">Código en un nivel superior `do` enlace se ejecuta cuando se inicializa el módulo.</span><span class="sxs-lookup"><span data-stu-id="025d7-111">Code in a top-level `do` binding is executed when the module is initialized.</span></span> <span data-ttu-id="025d7-112">La palabra clave `do` es opcional.</span><span class="sxs-lookup"><span data-stu-id="025d7-112">The keyword `do` is optional.</span></span>

<span data-ttu-id="025d7-113">Se pueden aplicar atributos a un nivel superior `do` enlace.</span><span class="sxs-lookup"><span data-stu-id="025d7-113">Attributes can be applied to a top-level `do` binding.</span></span> <span data-ttu-id="025d7-114">Por ejemplo, si el programa utiliza la interoperabilidad COM, puede aplicar el `STAThread` de atributo para el programa.</span><span class="sxs-lookup"><span data-stu-id="025d7-114">For example, if your program uses COM interop, you might want to apply the `STAThread` attribute to your program.</span></span> <span data-ttu-id="025d7-115">Puede hacerlo mediante el uso de un atributo en un `do` de enlace, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="025d7-115">You can do this by using an attribute on a `do` binding, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet201.fs)]
    
## <a name="see-also"></a><span data-ttu-id="025d7-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="025d7-116">See Also</span></span>
[<span data-ttu-id="025d7-117">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="025d7-117">F# Language Reference</span></span>](../index.md)

[<span data-ttu-id="025d7-118">Funciones</span><span class="sxs-lookup"><span data-stu-id="025d7-118">Functions</span></span>](index.md)

