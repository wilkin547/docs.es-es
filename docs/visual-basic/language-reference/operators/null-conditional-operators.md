---
title: Operadores condicionales null (Visual Basic)
ms.date: 10/19/2018
helpviewer_keywords:
- null-conditional operators [Visual Basic]
- ?. operator [Visual Basic]
- ?[] operator [C#]
- ?[] operator [Visual Basic]
ms.openlocfilehash: d30d452a7c140a0c56529386b14ef3a3512df490
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54722158"
---
# <a name="-and--null-conditional-operators-visual-basic"></a><span data-ttu-id="9619a-102">?.</span><span class="sxs-lookup"><span data-stu-id="9619a-102">?.</span></span> <span data-ttu-id="9619a-103">¿y? operadores condicionales null () (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9619a-103">and ?() null-conditional operators (Visual Basic)</span></span>

<span data-ttu-id="9619a-104">Comprueba el valor del operando izquierdo es null (`Nothing`) antes de realizar un acceso a miembros (`?.`) o un índice (`?()`) devuelve la operación; `Nothing` si el operando izquierdo se evalúa como `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="9619a-104">Tests the value of the left-hand operand for null (`Nothing`) before performing a member access (`?.`) or index (`?()`) operation; returns `Nothing` if the left-hand operand evaluates to `Nothing`.</span></span> <span data-ttu-id="9619a-105">Tenga en cuenta que, en las expresiones que normalmente devolvería los tipos de valor, el operador condicional null devuelve un <xref:System.Nullable%601>.</span><span class="sxs-lookup"><span data-stu-id="9619a-105">Note that, in the expressions that would ordinarily return value types, the null-conditional operator returns a <xref:System.Nullable%601>.</span></span>

<span data-ttu-id="9619a-106">Estos operadores ayudan a escribir menos código para controlar las comprobaciones de valores null, especialmente cuando descender en estructuras de datos.</span><span class="sxs-lookup"><span data-stu-id="9619a-106">These operators help you write less code to handle null checks, especially when descending into data structures.</span></span> <span data-ttu-id="9619a-107">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9619a-107">For example:</span></span>

```vb
Dim length As Integer? = customers?.Length  ' Nothing if customers is Nothing  
Dim first As Customer = customers?(0)  ' Nothing if customers is Nothing  
Dim count As Integer? = customers?(0)?.Orders?.Count()  ' Nothing if customers, the first customer, or Orders is Nothing  
```

<span data-ttu-id="9619a-108">Para la comparación, el código alternativo para la primera de estas expresiones sin un operador condicional null es:</span><span class="sxs-lookup"><span data-stu-id="9619a-108">For comparison, the alternative code for the first of these expressions without a null-conditional operator is:</span></span>

```vb
Dim length As Integer
If customers IsNot Nothing Then
   length = customers.Length
End If
```

<span data-ttu-id="9619a-109">Los operadores de condición NULL se cortocircuitan.</span><span class="sxs-lookup"><span data-stu-id="9619a-109">The null-conditional operators are short-circuiting.</span></span>  <span data-ttu-id="9619a-110">Si una operación en una cadena de las operaciones de índice y de acceso de miembro condicional devuelve Nothing, se detiene el resto de la ejecución de la cadena.</span><span class="sxs-lookup"><span data-stu-id="9619a-110">If one operation in a chain of conditional member access and index operations returns Nothing, the rest of the chain’s execution stops.</span></span>  <span data-ttu-id="9619a-111">En el ejemplo siguiente, c (e) no se evalúa si `A`, `B`, o `C` se evalúa como Nothing.</span><span class="sxs-lookup"><span data-stu-id="9619a-111">In the following example, C(E) isn't evaluated if `A`, `B`, or `C` evaluates to Nothing.</span></span>

```vb
A?.B?.C?(E);
```

<span data-ttu-id="9619a-112">Otro uso de acceso a miembros condicional null es invocar delegados de manera segura para subprocesos con mucho menos código.</span><span class="sxs-lookup"><span data-stu-id="9619a-112">Another use for null-conditional member access is to invoke delegates in a thread-safe way with much less code.</span></span>  <span data-ttu-id="9619a-113">La antigua manera de hacerlo requiere un código parecido a este:</span><span class="sxs-lookup"><span data-stu-id="9619a-113">The old way requires code like the following:</span></span>  

```vb  
Dim handler = AddressOf(Me.PropertyChanged)  
If handler IsNot Nothing  
    Call handler(…)  
```

<span data-ttu-id="9619a-114">La nueva manera es mucho más sencilla:</span><span class="sxs-lookup"><span data-stu-id="9619a-114">The new way is much simpler:</span></span>  

```vb
PropertyChanged?.Invoke(…)
```

<span data-ttu-id="9619a-115">La nueva forma de hacerlo es segura para los subprocesos porque el compilador genera código para evaluar `PropertyChanged` solo una vez, manteniendo el resultado en una variable temporal.</span><span class="sxs-lookup"><span data-stu-id="9619a-115">The new way is thread-safe because the compiler generates code to evaluate `PropertyChanged` one time only, keeping the result in a temporary variable.</span></span> <span data-ttu-id="9619a-116">Debe llamar explícitamente al método `Invoke` porque no hay ninguna sintaxis de invocación del delegado null condicional `PropertyChanged?(e)`.</span><span class="sxs-lookup"><span data-stu-id="9619a-116">You need to explicitly call the `Invoke` method because there is no null-conditional delegate invocation syntax `PropertyChanged?(e)`.</span></span>  

## <a name="see-also"></a><span data-ttu-id="9619a-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="9619a-117">See also</span></span>

- [<span data-ttu-id="9619a-118">Operadores (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9619a-118">Operators (Visual Basic)</span></span>](index.md)
- [<span data-ttu-id="9619a-119">Guía de programación en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9619a-119">Visual Basic Programming Guide</span></span>](../../../visual-basic/programming-guide/index.md)
- [<span data-ttu-id="9619a-120">Referencia del lenguaje Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9619a-120">Visual Basic Language Reference</span></span>](../../../visual-basic/language-reference/index.md)
