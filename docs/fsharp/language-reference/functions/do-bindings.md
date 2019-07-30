---
title: do (Enlaces)
description: Obtenga información sobre F# cómo se usa un enlace ' do ' para ejecutar código sin definir una función o un valor.
ms.date: 05/16/2016
ms.openlocfilehash: f98f523296bfaceeda35d4861eafbfeaa5a60c32
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630532"
---
# <a name="do-bindings"></a><span data-ttu-id="1ba03-103">do (Enlaces)</span><span class="sxs-lookup"><span data-stu-id="1ba03-103">do Bindings</span></span>

<span data-ttu-id="1ba03-104">Un `do` enlace se utiliza para ejecutar código sin definir una función o un valor.</span><span class="sxs-lookup"><span data-stu-id="1ba03-104">A `do` binding is used to execute code without defining a function or value.</span></span> <span data-ttu-id="1ba03-105">Además, los enlaces do se pueden usar en las clases, vea [ `do` enlaces en clases](../members/do-bindings-in-classes.md).</span><span class="sxs-lookup"><span data-stu-id="1ba03-105">Also, do bindings can be used in classes, see [`do` Bindings in Classes](../members/do-bindings-in-classes.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="1ba03-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1ba03-106">Syntax</span></span>

```fsharp
[ attributes ]
[ do ]expression
```

## <a name="remarks"></a><span data-ttu-id="1ba03-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1ba03-107">Remarks</span></span>

<span data-ttu-id="1ba03-108">Use un `do` enlace cuando desee ejecutar código independientemente de una definición de función o valor.</span><span class="sxs-lookup"><span data-stu-id="1ba03-108">Use a `do` binding when you want to execute code independently of a function or value definition.</span></span> <span data-ttu-id="1ba03-109">La expresión de un `do` enlace debe devolver `unit`.</span><span class="sxs-lookup"><span data-stu-id="1ba03-109">The expression in a `do` binding must return `unit`.</span></span> <span data-ttu-id="1ba03-110">El código de un enlace de `do` nivel superior se ejecuta cuando se inicializa el módulo.</span><span class="sxs-lookup"><span data-stu-id="1ba03-110">Code in a top-level `do` binding is executed when the module is initialized.</span></span> <span data-ttu-id="1ba03-111">La palabra `do` clave es opcional.</span><span class="sxs-lookup"><span data-stu-id="1ba03-111">The keyword `do` is optional.</span></span>

<span data-ttu-id="1ba03-112">Los atributos se pueden aplicar a un enlace de `do` nivel superior.</span><span class="sxs-lookup"><span data-stu-id="1ba03-112">Attributes can be applied to a top-level `do` binding.</span></span> <span data-ttu-id="1ba03-113">Por ejemplo, si el programa utiliza la interoperabilidad com, es posible que `STAThread` desee aplicar el atributo a su programa.</span><span class="sxs-lookup"><span data-stu-id="1ba03-113">For example, if your program uses COM interop, you might want to apply the `STAThread` attribute to your program.</span></span> <span data-ttu-id="1ba03-114">Para ello, puede usar un atributo en un `do` enlace, tal y como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="1ba03-114">You can do this by using an attribute on a `do` binding, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet201.fs)]

## <a name="see-also"></a><span data-ttu-id="1ba03-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="1ba03-115">See also</span></span>

- [<span data-ttu-id="1ba03-116">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="1ba03-116">F# Language Reference</span></span>](../index.md)
- [<span data-ttu-id="1ba03-117">Funciones</span><span class="sxs-lookup"><span data-stu-id="1ba03-117">Functions</span></span>](index.md)
