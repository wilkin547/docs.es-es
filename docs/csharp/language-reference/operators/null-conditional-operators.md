---
title: Operadores condicionales null (C# y Visual Basic)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 9c7b2c8f-a785-44ca-836c-407bfb6d27f5
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6118956a5681ddbeb110f6e01f090b85cdd65089
ms.openlocfilehash: 465a395a33c027132b7890e02d540438096e2073
ms.contentlocale: es-es
ms.lasthandoff: 08/23/2017

---
# <a name="null-conditional-operators-c-and-visual-basic"></a><span data-ttu-id="49d54-102">Operadores condicionales null (C# y Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="49d54-102">Null-conditional Operators (C# and Visual Basic)</span></span>
<span data-ttu-id="49d54-103">Se utiliza para probar si hay valores null antes de realizar una operación de acceso a miembros (`?.`) o índice (`?[`).</span><span class="sxs-lookup"><span data-stu-id="49d54-103">Used to test for null before performing a member access (`?.`) or index (`?[`) operation.</span></span>  <span data-ttu-id="49d54-104">Estos operadores ayudan a escribir menos código para controlar las comprobaciones de null, especialmente para descender en estructuras de datos.</span><span class="sxs-lookup"><span data-stu-id="49d54-104">These operators help you write less code to handle null checks, especially for descending into data structures.</span></span>  
  
```csharp  
int? length = customers?.Length; // null if customers is null   
Customer first = customers?[0];  // null if customers is null  
int? count = customers?[0]?.Orders?.Count();  // null if customers, the first customer, or Orders is null  
```  
  
```vb  
Dim length = customers?.Length  ' null if customers is null  
Dim first as Customer = customers?(0)  ' null if customers is null  
Dim count as Integer? = customers?(0)?.Orders?.Count()  ' null if customers, the first customer, or Orders is null  
```  
  
 <span data-ttu-id="49d54-105">El último ejemplo demuestra que los operadores de condición null se están cortocircuitando.</span><span class="sxs-lookup"><span data-stu-id="49d54-105">The last example demonstrates that the null-condition operators are short-circuiting.</span></span>  <span data-ttu-id="49d54-106">Si una operación en una cadena de la operación de índice y de acceso a miembros condicional devuelve null, se detiene el resto de la ejecución de la cadena.</span><span class="sxs-lookup"><span data-stu-id="49d54-106">If one operation in a chain of conditional member access and index operation returns null, then the rest of the chain’s execution stops.</span></span>  <span data-ttu-id="49d54-107">Seguirán ejecutándose las demás operaciones de menor prioridad en la expresión.</span><span class="sxs-lookup"><span data-stu-id="49d54-107">Other operations with lower precedence in the expression continue.</span></span>  <span data-ttu-id="49d54-108">Por ejemplo, `E` en la siguiente operación se ejecuta en la segunda línea y las operaciones `??` y `==` se ejecutan.</span><span class="sxs-lookup"><span data-stu-id="49d54-108">For example, `E` in the following executes in the second line, and the `??` and `==` operations execute.</span></span>  <span data-ttu-id="49d54-109">En la primera línea, `??` se cortocircuita y `E` no se ejecuta cuando el lado izquierdo se evalúa como no null.</span><span class="sxs-lookup"><span data-stu-id="49d54-109">In the first line, the `??` short circuits and `E` does not execute when the left side evaluates to non-null.</span></span>
  
```csharp
A?.B?.C?[0] ?? E  
A?.B?.C?[0] == E  
```

```vb
A?.B?.C?(0) ?? E  
A?.B?.C?(0) == E  
```  
  
 <span data-ttu-id="49d54-110">Otro uso para el acceso a miembros de condición null es invocar delegados de manera segura para los subprocesos con mucho menos código.</span><span class="sxs-lookup"><span data-stu-id="49d54-110">Another use for the null-condition member access is invoking delegates in a thread-safe way with much less code.</span></span>  <span data-ttu-id="49d54-111">La antigua manera de hacerlo requiere un código parecido a este:</span><span class="sxs-lookup"><span data-stu-id="49d54-111">The old way requires code like the following:</span></span>  
  
```csharp  
var handler = this.PropertyChanged;  
if (handler != null)  
    handler(…);
```  
  
```vb  
Dim handler = AddressOf(Me.PropertyChanged)  
If handler IsNot Nothing  
    Call handler(…)  
```  
  
 <span data-ttu-id="49d54-112">La nueva manera es mucho más sencilla:</span><span class="sxs-lookup"><span data-stu-id="49d54-112">The new way is much simpler:</span></span>  
  
```csharp
PropertyChanged?.Invoke(e)  
```  

```vb
PropertyChanged?.Invoke(e)
```  
  
 <span data-ttu-id="49d54-113">La nueva forma de hacerlo es segura para los subprocesos porque el compilador genera código para evaluar `PropertyChanged` solo una vez, manteniendo el resultado en una variable temporal.</span><span class="sxs-lookup"><span data-stu-id="49d54-113">The new way is thread-safe because the compiler generates code to evaluate `PropertyChanged` one time only, keeping the result in a temporary variable.</span></span>  
  
 <span data-ttu-id="49d54-114">Debe llamar explícitamente al método `Invoke` porque no hay ninguna sintaxis de invocación del delegado null condicional `PropertyChanged?(e)`.</span><span class="sxs-lookup"><span data-stu-id="49d54-114">You need to explicitly call the `Invoke` method because there is no null-conditional delegate invocation syntax `PropertyChanged?(e)`.</span></span>  <span data-ttu-id="49d54-115">Había muchas situaciones ambiguas de análisis para permitirlo.</span><span class="sxs-lookup"><span data-stu-id="49d54-115">There were too many ambiguous parsing situations to allow it.</span></span>  
  
## <a name="language-specifications"></a><span data-ttu-id="49d54-116">Especificaciones del lenguaje</span><span class="sxs-lookup"><span data-stu-id="49d54-116">Language Specifications</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
 <span data-ttu-id="49d54-117">Para obtener más información, vea [Referencia del lenguaje Visual Basic](../../../visual-basic/language-reference/index.md).</span><span class="sxs-lookup"><span data-stu-id="49d54-117">For more information, see the [Visual Basic Language Reference](../../../visual-basic/language-reference/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49d54-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="49d54-118">See Also</span></span>  
 <span data-ttu-id="49d54-119">[?? (operador de uso combinado de NULL)](null-conditional-operator.md) </span><span class="sxs-lookup"><span data-stu-id="49d54-119">[?? (null-coalescing operator)](null-conditional-operator.md) </span></span>  
 <span data-ttu-id="49d54-120">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="49d54-120">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="49d54-121">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="49d54-121">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="49d54-122">[Referencia del lenguaje Visual Basic](../../../visual-basic/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="49d54-122">[Visual Basic Language Reference](../../../visual-basic/language-reference/index.md) </span></span>  
 [<span data-ttu-id="49d54-123">Guía de programación en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="49d54-123">Visual Basic Programming Guide</span></span>](../../../visual-basic/programming-guide/index.md)

