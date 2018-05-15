---
title: Operadores condicionales null (C# y Visual Basic)
ms.date: 04/03/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- null-conditional operators [C#]
- null-conditional operators [Visual Basic]
- ?. operator [C#]
- ?. operator [Visual Basic]
- ?[] operator [C#]
- ?[] operator [Visual Basic]
ms.assetid: 9c7b2c8f-a785-44ca-836c-407bfb6d27f5
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 3ffeaa3c2088d0bb2c000704cfe312b0f9453b68
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2018
---
# <a name="-and--null-conditional-operators-c-and-visual-basic"></a><span data-ttu-id="e8586-102">?.</span><span class="sxs-lookup"><span data-stu-id="e8586-102">?.</span></span> <span data-ttu-id="e8586-103">y ?[]: operadores condicionales NULL (C# y Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e8586-103">and ?[] null-conditional Operators (C# and Visual Basic)</span></span>
<span data-ttu-id="e8586-104">Se utiliza para probar si hay valores null antes de realizar una operación de acceso a miembros (`?.`) o índice (`?[]`).</span><span class="sxs-lookup"><span data-stu-id="e8586-104">Used to test for null before performing a member access (`?.`) or index (`?[]`) operation.</span></span>  <span data-ttu-id="e8586-105">Estos operadores ayudan a escribir menos código para controlar las comprobaciones de null, especialmente para descender en estructuras de datos.</span><span class="sxs-lookup"><span data-stu-id="e8586-105">These operators help you write less code to handle null checks, especially for descending into data structures.</span></span>  
  
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
  
 <span data-ttu-id="e8586-106">Los operadores de condición NULL se cortocircuitan.</span><span class="sxs-lookup"><span data-stu-id="e8586-106">The null-condition operators are short-circuiting.</span></span>  <span data-ttu-id="e8586-107">Si una operación en una cadena de la operación de índice y de acceso a miembros condicional devuelve null, se detiene el resto de la ejecución de la cadena.</span><span class="sxs-lookup"><span data-stu-id="e8586-107">If one operation in a chain of conditional member access and index operation returns null, then the rest of the chain’s execution stops.</span></span>  <span data-ttu-id="e8586-108">En el ejemplo siguiente, `E` no se ejecuta si `A`, `B` o `C` se evalúan como NULL.</span><span class="sxs-lookup"><span data-stu-id="e8586-108">In the following example, `E` doesn't execute if `A`, `B`, or `C` evaluates to null.</span></span>
  
```csharp
A?.B?.C?.Do(E);
A?.B?.C?[E];
```

```vb
A?.B?.C?.Do(E);
A?.B?.C?(E);
```  
  
 <span data-ttu-id="e8586-109">Otro uso para el acceso a miembros de condición null es invocar delegados de manera segura para los subprocesos con mucho menos código.</span><span class="sxs-lookup"><span data-stu-id="e8586-109">Another use for the null-condition member access is invoking delegates in a thread-safe way with much less code.</span></span>  <span data-ttu-id="e8586-110">La antigua manera de hacerlo requiere un código parecido a este:</span><span class="sxs-lookup"><span data-stu-id="e8586-110">The old way requires code like the following:</span></span>  
  
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
  
 <span data-ttu-id="e8586-111">La nueva manera es mucho más sencilla:</span><span class="sxs-lookup"><span data-stu-id="e8586-111">The new way is much simpler:</span></span>  
  
```csharp
PropertyChanged?.Invoke(e)  
```  

```vb
PropertyChanged?.Invoke(e)
```  
  
 <span data-ttu-id="e8586-112">La nueva forma de hacerlo es segura para los subprocesos porque el compilador genera código para evaluar `PropertyChanged` solo una vez, manteniendo el resultado en una variable temporal.</span><span class="sxs-lookup"><span data-stu-id="e8586-112">The new way is thread-safe because the compiler generates code to evaluate `PropertyChanged` one time only, keeping the result in a temporary variable.</span></span>  
  
 <span data-ttu-id="e8586-113">Debe llamar explícitamente al método `Invoke` porque no hay ninguna sintaxis de invocación del delegado null condicional `PropertyChanged?(e)`.</span><span class="sxs-lookup"><span data-stu-id="e8586-113">You need to explicitly call the `Invoke` method because there is no null-conditional delegate invocation syntax `PropertyChanged?(e)`.</span></span>  
  
## <a name="language-specifications"></a><span data-ttu-id="e8586-114">Especificaciones del lenguaje</span><span class="sxs-lookup"><span data-stu-id="e8586-114">Language Specifications</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
 <span data-ttu-id="e8586-115">Para obtener más información, vea [Referencia del lenguaje Visual Basic](../../../visual-basic/language-reference/index.md).</span><span class="sxs-lookup"><span data-stu-id="e8586-115">For more information, see the [Visual Basic Language Reference](../../../visual-basic/language-reference/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8586-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="e8586-116">See Also</span></span>  
 [<span data-ttu-id="e8586-117">?? (operador de uso combinado de NULL)</span><span class="sxs-lookup"><span data-stu-id="e8586-117">?? (null-coalescing operator)</span></span>](null-conditional-operator.md)  
 [<span data-ttu-id="e8586-118">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="e8586-118">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="e8586-119">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="e8586-119">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="e8586-120">Referencia del lenguaje Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e8586-120">Visual Basic Language Reference</span></span>](../../../visual-basic/language-reference/index.md)  
 [<span data-ttu-id="e8586-121">Guía de programación en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e8586-121">Visual Basic Programming Guide</span></span>](../../../visual-basic/programming-guide/index.md)
