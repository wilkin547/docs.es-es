---
title: Operadores condicionales NULL (Referencia de C#)
ms.date: 04/03/2015
helpviewer_keywords:
- null-conditional operators [C#]
- ?. operator [C#]
- ?[] operator [C#]
ms.assetid: 9c7b2c8f-a785-44ca-836c-407bfb6d27f5
ms.openlocfilehash: 823b9dc886bf2448ca9da4ac640bfe56f90d3ff3
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
ms.locfileid: "50194857"
---
# <a name="-and--null-conditional-operators-c-and-visual-basic"></a><span data-ttu-id="cf272-102">?.</span><span class="sxs-lookup"><span data-stu-id="cf272-102">?.</span></span> <span data-ttu-id="cf272-103">y ?[]: operadores condicionales NULL (C# y Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cf272-103">and ?[] null-conditional Operators (C# and Visual Basic)</span></span>
<span data-ttu-id="cf272-104">Comprueba si el valor del operando izquierdo es null antes de realizar una operación de acceso a miembro (`?.`) o de índice (`?[]`); devuelve `null` si el operando izquierdo se evalúa como `null`.</span><span class="sxs-lookup"><span data-stu-id="cf272-104">Tests the value of the left-hand operand for null before performing a member access (`?.`) or index (`?[]`) operation; returns `null` if the left-hand operand evaluates to `null`.</span></span> 

<span data-ttu-id="cf272-105">Estos operadores ayudan a escribir menos código para controlar las comprobaciones de null, especialmente para descender en estructuras de datos.</span><span class="sxs-lookup"><span data-stu-id="cf272-105">These operators help you write less code to handle null checks, especially for descending into data structures.</span></span>  
  
```csharp  
int? length = customers?.Length; // null if customers is null   
Customer first = customers?[0];  // null if customers is null  
int? count = customers?[0]?.Orders?.Count();  // null if customers, the first customer, or Orders is null  
```  
  
 <span data-ttu-id="cf272-106">Los operadores de condición NULL se cortocircuitan.</span><span class="sxs-lookup"><span data-stu-id="cf272-106">The null-conditional operators are short-circuiting.</span></span>  <span data-ttu-id="cf272-107">Si una operación en una cadena de la operación de índice y de acceso a miembros condicional devuelve null, se detiene el resto de la ejecución de la cadena.</span><span class="sxs-lookup"><span data-stu-id="cf272-107">If one operation in a chain of conditional member access and index operations returns null, the rest of the chain’s execution stops.</span></span>  <span data-ttu-id="cf272-108">En el ejemplo siguiente, `E` no se ejecuta si `A`, `B` o `C` se evalúan como NULL.</span><span class="sxs-lookup"><span data-stu-id="cf272-108">In the following example, `E` doesn't execute if `A`, `B`, or `C` evaluates to null.</span></span>
  
```csharp
A?.B?.C?.Do(E);
A?.B?.C?[E];
```

 <span data-ttu-id="cf272-109">Otro uso para el acceso a miembros de condición null es invocar delegados de manera segura para los subprocesos con mucho menos código.</span><span class="sxs-lookup"><span data-stu-id="cf272-109">Another use for the null-conditional member access is invoking delegates in a thread-safe way with much less code.</span></span>  <span data-ttu-id="cf272-110">La antigua manera de hacerlo requiere un código parecido a este:</span><span class="sxs-lookup"><span data-stu-id="cf272-110">The old way requires code like the following:</span></span>  
  
```csharp  
var handler = this.PropertyChanged;  
if (handler != null)  
    handler(…);
```  
  
  
 <span data-ttu-id="cf272-111">La nueva manera es mucho más sencilla:</span><span class="sxs-lookup"><span data-stu-id="cf272-111">The new way is much simpler:</span></span>  
  
```csharp
PropertyChanged?.Invoke(…)  
```  

 <span data-ttu-id="cf272-112">La nueva forma de hacerlo es segura para los subprocesos porque el compilador genera código para evaluar `PropertyChanged` solo una vez, manteniendo el resultado en una variable temporal.</span><span class="sxs-lookup"><span data-stu-id="cf272-112">The new way is thread-safe because the compiler generates code to evaluate `PropertyChanged` one time only, keeping the result in a temporary variable.</span></span> <span data-ttu-id="cf272-113">Debe llamar explícitamente al método `Invoke` porque no hay ninguna sintaxis de invocación del delegado null condicional `PropertyChanged?(e)`.</span><span class="sxs-lookup"><span data-stu-id="cf272-113">You need to explicitly call the `Invoke` method because there is no null-conditional delegate invocation syntax `PropertyChanged?(e)`.</span></span>  
  
## <a name="language-specifications"></a><span data-ttu-id="cf272-114">Especificaciones del lenguaje</span><span class="sxs-lookup"><span data-stu-id="cf272-114">Language Specifications</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="cf272-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="cf272-115">See Also</span></span>

- [<span data-ttu-id="cf272-116">?? (operador de uso combinado de NULL)</span><span class="sxs-lookup"><span data-stu-id="cf272-116">?? (null-coalescing operator)</span></span>](null-coalescing-operator.md)  
- [<span data-ttu-id="cf272-117">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="cf272-117">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="cf272-118">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="cf272-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
