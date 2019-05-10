---
title: Procedimiento Crear una Variable que no cambia de valor (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], read-only
- variables [Visual Basic], constant value
ms.assetid: 86b59266-25df-4635-ae15-9b59c411d036
ms.openlocfilehash: 3a9fa93b69c9abb42b2dd7eae623048f3628999e
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64663572"
---
# <a name="how-to-create-a-variable-that-does-not-change-in-value-visual-basic"></a><span data-ttu-id="bf0ca-102">Procedimiento Crear una Variable que no cambia de valor (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bf0ca-102">How to: Create a Variable that Does Not Change in Value (Visual Basic)</span></span>
<span data-ttu-id="bf0ca-103">La noción de una variable que no cambia su valor podría parecer contradictorios.</span><span class="sxs-lookup"><span data-stu-id="bf0ca-103">The notion of a variable that does not change its value might appear to be contradictory.</span></span> <span data-ttu-id="bf0ca-104">Pero existen situaciones en una constante no es factible y resulta útil disponer de una variable con un valor fijo.</span><span class="sxs-lookup"><span data-stu-id="bf0ca-104">But there are situations when a constant is not feasible and it is useful to have a variable with a fixed value.</span></span> <span data-ttu-id="bf0ca-105">En este caso puede definir una variable miembro con el [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) palabra clave.</span><span class="sxs-lookup"><span data-stu-id="bf0ca-105">In such a case you can define a member variable with the [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) keyword.</span></span>  
  
 <span data-ttu-id="bf0ca-106">No puede usar el [instrucción Const](../../../../visual-basic/language-reference/statements/const-statement.md) para declarar y asignar un valor constante en las siguientes circunstancias:</span><span class="sxs-lookup"><span data-stu-id="bf0ca-106">You cannot use the [Const Statement](../../../../visual-basic/language-reference/statements/const-statement.md) to declare and assign a constant value in the following circumstances:</span></span>  
  
- <span data-ttu-id="bf0ca-107">El `Const` instrucción no acepta el tipo de datos que desea usar</span><span class="sxs-lookup"><span data-stu-id="bf0ca-107">The `Const` statement does not accept the data type you want to use</span></span>  
  
- <span data-ttu-id="bf0ca-108">Se desconoce el valor en tiempo de compilación</span><span class="sxs-lookup"><span data-stu-id="bf0ca-108">You do not know the value at compile time</span></span>  
  
- <span data-ttu-id="bf0ca-109">No puede calcular el valor constante en tiempo de compilación</span><span class="sxs-lookup"><span data-stu-id="bf0ca-109">You are unable to compute the constant value at compile time</span></span>  
  
### <a name="to-create-a-variable-that-does-not-change-in-value"></a><span data-ttu-id="bf0ca-110">Para crear una variable que no cambia de valor</span><span class="sxs-lookup"><span data-stu-id="bf0ca-110">To create a variable that does not change in value</span></span>  
  
1. <span data-ttu-id="bf0ca-111">En el nivel de módulo, declare una variable miembro con el [instrucción Dim](../../../../visual-basic/language-reference/statements/dim-statement.md)e incluyen el [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) palabra clave.</span><span class="sxs-lookup"><span data-stu-id="bf0ca-111">At module level, declare a member variable with the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md), and include the [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) keyword.</span></span>  
  
    ```  
    Dim ReadOnly timeStarted  
    ```  
  
     <span data-ttu-id="bf0ca-112">Puede especificar `ReadOnly` solo en una variable de miembro.</span><span class="sxs-lookup"><span data-stu-id="bf0ca-112">You can specify `ReadOnly` only on a member variable.</span></span> <span data-ttu-id="bf0ca-113">Esto significa que debe definir la variable en el nivel de módulo, fuera de cualquier procedimiento.</span><span class="sxs-lookup"><span data-stu-id="bf0ca-113">This means you must define the variable at module level, outside of any procedure.</span></span>  
  
2. <span data-ttu-id="bf0ca-114">Si se puede calcular el valor en una única instrucción en tiempo de compilación, utilice una cláusula de inicialización en el `Dim` instrucción.</span><span class="sxs-lookup"><span data-stu-id="bf0ca-114">If you can compute the value in a single statement at compile time, use an initialization clause in the `Dim` statement.</span></span> <span data-ttu-id="bf0ca-115">Siga el [como](../../../../visual-basic/language-reference/statements/as-clause.md) cláusula con un signo igual (`=`), seguido de una expresión.</span><span class="sxs-lookup"><span data-stu-id="bf0ca-115">Follow the [As](../../../../visual-basic/language-reference/statements/as-clause.md) clause with an equal sign (`=`), followed by an expression.</span></span> <span data-ttu-id="bf0ca-116">Asegúrese de que el compilador puede evaluar esta expresión en un valor constante.</span><span class="sxs-lookup"><span data-stu-id="bf0ca-116">Be sure the compiler can evaluate this expression to a constant value.</span></span>  
  
    ```  
    Dim ReadOnly timeStarted As Date = Now  
    ```  
  
     <span data-ttu-id="bf0ca-117">Puede asignar un valor a un `ReadOnly` variable sólo una vez.</span><span class="sxs-lookup"><span data-stu-id="bf0ca-117">You can assign a value to a `ReadOnly` variable only once.</span></span> <span data-ttu-id="bf0ca-118">Una vez hecho esto, ningún código nunca puede cambiar su valor.</span><span class="sxs-lookup"><span data-stu-id="bf0ca-118">Once you do so, no code can ever change its value.</span></span>  
  
     <span data-ttu-id="bf0ca-119">Si no conoce el valor en tiempo de compilación, o no se puede calcular en tiempo de compilación en una sola instrucción, se puede asignar en tiempo de ejecución en un constructor.</span><span class="sxs-lookup"><span data-stu-id="bf0ca-119">If you do not know the value at compile time, or cannot compute it at compile time in a single statement, you can still assign it at run time in a constructor.</span></span> <span data-ttu-id="bf0ca-120">Para ello, debe declarar la `ReadOnly` variable en el nivel de clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="bf0ca-120">To do this, you must declare the `ReadOnly` variable at class or structure level.</span></span> <span data-ttu-id="bf0ca-121">En el constructor para esa clase o estructura, calcular el valor fijo de la variable y asigne a la variable antes de devolver desde el constructor.</span><span class="sxs-lookup"><span data-stu-id="bf0ca-121">In the constructor for that class or structure, compute the variable's fixed value, and assign it to the variable before returning from the constructor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf0ca-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="bf0ca-122">See also</span></span>

- [<span data-ttu-id="bf0ca-123">WriteOnly</span><span class="sxs-lookup"><span data-stu-id="bf0ca-123">WriteOnly</span></span>](../../../../visual-basic/language-reference/modifiers/writeonly.md)
- [<span data-ttu-id="bf0ca-124">Const (instrucción)</span><span class="sxs-lookup"><span data-stu-id="bf0ca-124">Const Statement</span></span>](../../../../visual-basic/language-reference/statements/const-statement.md)
