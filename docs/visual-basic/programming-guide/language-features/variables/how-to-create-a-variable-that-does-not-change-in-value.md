---
title: Procedimiento para crear una variable que no cambia de valor
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], read-only
- variables [Visual Basic], constant value
ms.assetid: 86b59266-25df-4635-ae15-9b59c411d036
ms.openlocfilehash: 04e08784b5cfbdeb6db73b9b00fe9afa201bd06d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410521"
---
# <a name="how-to-create-a-variable-that-does-not-change-in-value-visual-basic"></a><span data-ttu-id="d0777-102">Cómo: Crear una variable que no cambia de valor (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d0777-102">How to: Create a Variable that Does Not Change in Value (Visual Basic)</span></span>

<span data-ttu-id="d0777-103">La noción de una variable que no cambia su valor podría parecer contradictoria.</span><span class="sxs-lookup"><span data-stu-id="d0777-103">The notion of a variable that does not change its value might appear to be contradictory.</span></span> <span data-ttu-id="d0777-104">Pero hay situaciones en las que una constante no es factible y resulta útil tener una variable con un valor fijo.</span><span class="sxs-lookup"><span data-stu-id="d0777-104">But there are situations when a constant is not feasible and it is useful to have a variable with a fixed value.</span></span> <span data-ttu-id="d0777-105">En tal caso, puede definir una variable miembro con la palabra clave [ReadOnly](../../../language-reference/modifiers/readonly.md) .</span><span class="sxs-lookup"><span data-stu-id="d0777-105">In such a case you can define a member variable with the [ReadOnly](../../../language-reference/modifiers/readonly.md) keyword.</span></span>

<span data-ttu-id="d0777-106">No se puede usar la [instrucción const](../../../language-reference/statements/const-statement.md) para declarar y asignar un valor constante en las siguientes circunstancias:</span><span class="sxs-lookup"><span data-stu-id="d0777-106">You cannot use the [Const Statement](../../../language-reference/statements/const-statement.md) to declare and assign a constant value in the following circumstances:</span></span>

- <span data-ttu-id="d0777-107">La `Const` instrucción no acepta el tipo de datos que desea usar</span><span class="sxs-lookup"><span data-stu-id="d0777-107">The `Const` statement does not accept the data type you want to use</span></span>

- <span data-ttu-id="d0777-108">No conoce el valor en tiempo de compilación</span><span class="sxs-lookup"><span data-stu-id="d0777-108">You do not know the value at compile time</span></span>

- <span data-ttu-id="d0777-109">No se puede calcular el valor constante en tiempo de compilación</span><span class="sxs-lookup"><span data-stu-id="d0777-109">You are unable to compute the constant value at compile time</span></span>

### <a name="to-create-a-variable-that-does-not-change-in-value"></a><span data-ttu-id="d0777-110">Para crear una variable que no cambie de valor</span><span class="sxs-lookup"><span data-stu-id="d0777-110">To create a variable that does not change in value</span></span>

1. <span data-ttu-id="d0777-111">En el nivel de módulo, declare una variable miembro con la [instrucción Dim](../../../language-reference/statements/dim-statement.md)e incluya la palabra clave [ReadOnly](../../../language-reference/modifiers/readonly.md) .</span><span class="sxs-lookup"><span data-stu-id="d0777-111">At module level, declare a member variable with the [Dim Statement](../../../language-reference/statements/dim-statement.md), and include the [ReadOnly](../../../language-reference/modifiers/readonly.md) keyword.</span></span>

    ```vb
    Dim ReadOnly timeStarted
    ```

    <span data-ttu-id="d0777-112">Solo se puede especificar `ReadOnly` en una variable miembro.</span><span class="sxs-lookup"><span data-stu-id="d0777-112">You can specify `ReadOnly` only on a member variable.</span></span> <span data-ttu-id="d0777-113">Esto significa que debe definir la variable en el nivel de módulo, fuera de cualquier procedimiento.</span><span class="sxs-lookup"><span data-stu-id="d0777-113">This means you must define the variable at module level, outside of any procedure.</span></span>

2. <span data-ttu-id="d0777-114">Si puede calcular el valor en una sola instrucción en tiempo de compilación, use una cláusula de inicialización en la `Dim` instrucción.</span><span class="sxs-lookup"><span data-stu-id="d0777-114">If you can compute the value in a single statement at compile time, use an initialization clause in the `Dim` statement.</span></span> <span data-ttu-id="d0777-115">Siga la cláusula [as](../../../language-reference/statements/as-clause.md) con un signo igual ( `=` ), seguido de una expresión.</span><span class="sxs-lookup"><span data-stu-id="d0777-115">Follow the [As](../../../language-reference/statements/as-clause.md) clause with an equal sign (`=`), followed by an expression.</span></span> <span data-ttu-id="d0777-116">Asegúrese de que el compilador puede evaluar esta expresión en un valor constante.</span><span class="sxs-lookup"><span data-stu-id="d0777-116">Be sure the compiler can evaluate this expression to a constant value.</span></span>

    ```vb
    Dim ReadOnly timeStarted As Date = Now
    ```

    <span data-ttu-id="d0777-117">Puede asignar un valor a una `ReadOnly` variable solo una vez.</span><span class="sxs-lookup"><span data-stu-id="d0777-117">You can assign a value to a `ReadOnly` variable only once.</span></span> <span data-ttu-id="d0777-118">Una vez hecho esto, ningún código puede cambiar su valor.</span><span class="sxs-lookup"><span data-stu-id="d0777-118">Once you do so, no code can ever change its value.</span></span>

    <span data-ttu-id="d0777-119">Si no conoce el valor en tiempo de compilación o no puede calcularlo en tiempo de compilación en una sola instrucción, puede asignarlo en tiempo de ejecución en un constructor.</span><span class="sxs-lookup"><span data-stu-id="d0777-119">If you do not know the value at compile time, or cannot compute it at compile time in a single statement, you can still assign it at run time in a constructor.</span></span> <span data-ttu-id="d0777-120">Para ello, debe declarar la `ReadOnly` variable en el nivel de clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="d0777-120">To do this, you must declare the `ReadOnly` variable at class or structure level.</span></span> <span data-ttu-id="d0777-121">En el constructor de esa clase o estructura, calcule el valor fijo de la variable y asígnelo a la variable antes de volver del constructor.</span><span class="sxs-lookup"><span data-stu-id="d0777-121">In the constructor for that class or structure, compute the variable's fixed value, and assign it to the variable before returning from the constructor.</span></span>

## <a name="see-also"></a><span data-ttu-id="d0777-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d0777-122">See also</span></span>

- [<span data-ttu-id="d0777-123">WriteOnly</span><span class="sxs-lookup"><span data-stu-id="d0777-123">WriteOnly</span></span>](../../../language-reference/modifiers/writeonly.md)
- [<span data-ttu-id="d0777-124">Instrucción Const</span><span class="sxs-lookup"><span data-stu-id="d0777-124">Const Statement</span></span>](../../../language-reference/statements/const-statement.md)
