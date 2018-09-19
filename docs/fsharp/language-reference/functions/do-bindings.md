---
title: Enlaces do (F#)
description: "Obtenga información sobre cómo un 'do', enlace de F # se usa para ejecutar código sin definir una función o un valor."
ms.date: 05/16/2016
ms.openlocfilehash: 78dbf8da0fe40b5af566ad98693df1109eede7e4
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "45973149"
---
# <a name="do-bindings"></a><span data-ttu-id="f3c31-103">do (Enlaces)</span><span class="sxs-lookup"><span data-stu-id="f3c31-103">do Bindings</span></span>

<span data-ttu-id="f3c31-104">Un `do` enlace se usa para ejecutar código sin definir una función o un valor.</span><span class="sxs-lookup"><span data-stu-id="f3c31-104">A `do` binding is used to execute code without defining a function or value.</span></span> <span data-ttu-id="f3c31-105">Además, ¿se pueden ser los enlaces se usa en clases, vea [ `do` Bindings in Classes](../members/do-bindings-in-classes.md).</span><span class="sxs-lookup"><span data-stu-id="f3c31-105">Also, do bindings can be used in classes, see [`do` Bindings in Classes](../members/do-bindings-in-classes.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="f3c31-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f3c31-106">Syntax</span></span>

```fsharp
[ attributes ]
[ do ]expression
```

## <a name="remarks"></a><span data-ttu-id="f3c31-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f3c31-107">Remarks</span></span>

<span data-ttu-id="f3c31-108">Use un `do` enlace cuando desea ejecutar código de manera independiente de una definición de función o valor.</span><span class="sxs-lookup"><span data-stu-id="f3c31-108">Use a `do` binding when you want to execute code independently of a function or value definition.</span></span> <span data-ttu-id="f3c31-109">La expresión en un `do` enlace debe devolver `unit`.</span><span class="sxs-lookup"><span data-stu-id="f3c31-109">The expression in a `do` binding must return `unit`.</span></span> <span data-ttu-id="f3c31-110">El código en un nivel superior `do` enlace se ejecuta cuando se inicializa el módulo.</span><span class="sxs-lookup"><span data-stu-id="f3c31-110">Code in a top-level `do` binding is executed when the module is initialized.</span></span> <span data-ttu-id="f3c31-111">La palabra clave `do` es opcional.</span><span class="sxs-lookup"><span data-stu-id="f3c31-111">The keyword `do` is optional.</span></span>

<span data-ttu-id="f3c31-112">Se pueden aplicar atributos a un nivel superior `do` enlace.</span><span class="sxs-lookup"><span data-stu-id="f3c31-112">Attributes can be applied to a top-level `do` binding.</span></span> <span data-ttu-id="f3c31-113">Por ejemplo, si el programa utiliza la interoperabilidad COM, es posible que desee aplicar el `STAThread` atributo al programa.</span><span class="sxs-lookup"><span data-stu-id="f3c31-113">For example, if your program uses COM interop, you might want to apply the `STAThread` attribute to your program.</span></span> <span data-ttu-id="f3c31-114">Puede hacerlo mediante el uso de un atributo en un `do` de enlace, tal como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="f3c31-114">You can do this by using an attribute on a `do` binding, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet201.fs)]

## <a name="see-also"></a><span data-ttu-id="f3c31-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="f3c31-115">See also</span></span>

- [<span data-ttu-id="f3c31-116">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="f3c31-116">F# Language Reference</span></span>](../index.md)
- [<span data-ttu-id="f3c31-117">Funciones</span><span class="sxs-lookup"><span data-stu-id="f3c31-117">Functions</span></span>](index.md)
