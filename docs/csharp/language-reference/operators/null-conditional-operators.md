---
title: 'Operadores condicionales NULL: Referencia de C#'
ms.custom: seodec18
ms.date: 04/03/2015
helpviewer_keywords:
- null-conditional operators [C#]
- ?. operator [C#]
- ?[] operator [C#]
ms.assetid: 9c7b2c8f-a785-44ca-836c-407bfb6d27f5
ms.openlocfilehash: 4189b07fd280192a4cb39400e4e77cef702c9d08
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53239558"
---
# <a name="-and--null-conditional-operators-c-and-visual-basic"></a><span data-ttu-id="6230a-102">?.</span><span class="sxs-lookup"><span data-stu-id="6230a-102">?.</span></span> <span data-ttu-id="6230a-103">y ?[]: operadores condicionales NULL (C# y Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6230a-103">and ?[] null-conditional Operators (C# and Visual Basic)</span></span>
<span data-ttu-id="6230a-104">Comprueba si el valor del operando izquierdo es null antes de realizar una operación de acceso a miembro (`?.`) o de índice (`?[]`); devuelve `null` si el operando izquierdo se evalúa como `null`.</span><span class="sxs-lookup"><span data-stu-id="6230a-104">Tests the value of the left-hand operand for null before performing a member access (`?.`) or index (`?[]`) operation; returns `null` if the left-hand operand evaluates to `null`.</span></span> 

<span data-ttu-id="6230a-105">Estos operadores ayudan a escribir menos código para controlar las comprobaciones de null, especialmente para descender en estructuras de datos.</span><span class="sxs-lookup"><span data-stu-id="6230a-105">These operators help you write less code to handle null checks, especially for descending into data structures.</span></span>  
  
```csharp  
int? length = customers?.Length; // null if customers is null   
Customer first = customers?[0];  // null if customers is null  
int? count = customers?[0]?.Orders?.Count();  // null if customers, the first customer, or Orders is null  
```  
  
 <span data-ttu-id="6230a-106">Los operadores de condición NULL se cortocircuitan.</span><span class="sxs-lookup"><span data-stu-id="6230a-106">The null-conditional operators are short-circuiting.</span></span>  <span data-ttu-id="6230a-107">Si una operación en una cadena de la operación de índice y de acceso a miembros condicional devuelve null, se detiene el resto de la ejecución de la cadena.</span><span class="sxs-lookup"><span data-stu-id="6230a-107">If one operation in a chain of conditional member access and index operations returns null, the rest of the chain’s execution stops.</span></span>  <span data-ttu-id="6230a-108">En el ejemplo siguiente, `E` no se ejecuta si `A`, `B` o `C` se evalúan como NULL.</span><span class="sxs-lookup"><span data-stu-id="6230a-108">In the following example, `E` doesn't execute if `A`, `B`, or `C` evaluates to null.</span></span>
  
```csharp
A?.B?.C?.Do(E);
A?.B?.C?[E];
```

 <span data-ttu-id="6230a-109">Otro uso para el acceso a miembros de condición null es invocar delegados de manera segura para los subprocesos con mucho menos código.</span><span class="sxs-lookup"><span data-stu-id="6230a-109">Another use for the null-conditional member access is invoking delegates in a thread-safe way with much less code.</span></span>  <span data-ttu-id="6230a-110">La antigua manera de hacerlo requiere un código parecido a este:</span><span class="sxs-lookup"><span data-stu-id="6230a-110">The old way requires code like the following:</span></span>  
  
```csharp  
var handler = this.PropertyChanged;  
if (handler != null)  
    handler(…);
```  
  
  
 <span data-ttu-id="6230a-111">La nueva manera es mucho más sencilla:</span><span class="sxs-lookup"><span data-stu-id="6230a-111">The new way is much simpler:</span></span>  
  
```csharp
PropertyChanged?.Invoke(…)  
```  

 <span data-ttu-id="6230a-112">La nueva forma de hacerlo es segura para los subprocesos porque el compilador genera código para evaluar `PropertyChanged` solo una vez, manteniendo el resultado en una variable temporal.</span><span class="sxs-lookup"><span data-stu-id="6230a-112">The new way is thread-safe because the compiler generates code to evaluate `PropertyChanged` one time only, keeping the result in a temporary variable.</span></span> <span data-ttu-id="6230a-113">Debe llamar explícitamente al método `Invoke` porque no hay ninguna sintaxis de invocación del delegado null condicional `PropertyChanged?(e)`.</span><span class="sxs-lookup"><span data-stu-id="6230a-113">You need to explicitly call the `Invoke` method because there is no null-conditional delegate invocation syntax `PropertyChanged?(e)`.</span></span>  
  
## <a name="language-specifications"></a><span data-ttu-id="6230a-114">Especificaciones del lenguaje</span><span class="sxs-lookup"><span data-stu-id="6230a-114">Language Specifications</span></span>  

<span data-ttu-id="6230a-115">Para obtener más información, vea la sección [Operador condicional de NULL](~/_csharplang/spec/expressions.md#null-conditional-operator) de la [Especificación del lenguaje C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="6230a-115">For more information, see [Null-conditional operator](~/_csharplang/spec/expressions.md#null-conditional-operator) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="6230a-116">La especificación del lenguaje es la fuente definitiva de la sintaxis y el uso de C#.</span><span class="sxs-lookup"><span data-stu-id="6230a-116">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6230a-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="6230a-117">See Also</span></span>

- [<span data-ttu-id="6230a-118">?? (operador de uso combinado de NULL)</span><span class="sxs-lookup"><span data-stu-id="6230a-118">?? (null-coalescing operator)</span></span>](null-coalescing-operator.md)  
- [<span data-ttu-id="6230a-119">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="6230a-119">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="6230a-120">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="6230a-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
