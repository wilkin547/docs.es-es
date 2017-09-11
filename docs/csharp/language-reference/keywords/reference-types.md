---
title: Tipos de referencia (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- cs.referencetypes
dev_langs:
- CSharp
helpviewer_keywords:
- reference types [C#]
- C# language, reference types
- types [C#], reference types
ms.assetid: 801cf030-6e2d-4a0d-9daf-1431b0c31f47
caps.latest.revision: 15
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
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ed7b9c8ed4aa1136c09049c8ffd6c68beeeb2a48
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="reference-types-c-reference"></a><span data-ttu-id="529a6-102">Tipos de referencia (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="529a6-102">Reference Types (C# Reference)</span></span>
<span data-ttu-id="529a6-103">Hay dos clases de tipos en C#: tipos de referencia y tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="529a6-103">There are two kinds of types in C#: reference types and value types.</span></span> <span data-ttu-id="529a6-104">Las variables de tipos de referencia almacenan referencias en sus datos (objetos), mientras que las variables de tipos de valor contienen directamente los datos.</span><span class="sxs-lookup"><span data-stu-id="529a6-104">Variables of reference types store references to their data (objects), while variables of value types directly contain their data.</span></span> <span data-ttu-id="529a6-105">Con los tipos de referencia, dos variables pueden hacer referencia al mismo objeto y, por lo tanto, las operaciones en una variable pueden afectar al objeto al que hace referencia la otra variable.</span><span class="sxs-lookup"><span data-stu-id="529a6-105">With reference types, two variables can reference the same object; therefore, operations on one variable can affect the object referenced by the other variable.</span></span> <span data-ttu-id="529a6-106">Con los tipos de valor, cada variable tiene su propia copia de los datos y no es posible que las operaciones en una variable afecten a la otra (excepto en el caso de las variables de parámetro ref y out, consulte [ref](../../../csharp/language-reference/keywords/ref.md) y [Modificador del parámetro out](../../../csharp/language-reference/keywords/out-parameter-modifier.md)).</span><span class="sxs-lookup"><span data-stu-id="529a6-106">With value types, each variable has its own copy of the data, and it is not possible for operations on one variable to affect the other (except in the case of ref and out parameter variables, see [ref](../../../csharp/language-reference/keywords/ref.md) and [out parameter modifier](../../../csharp/language-reference/keywords/out-parameter-modifier.md)).</span></span>  
  
 <span data-ttu-id="529a6-107">Las palabras clave siguientes se usan para declarar tipos de referencia:</span><span class="sxs-lookup"><span data-stu-id="529a6-107">The following keywords are used to declare reference types:</span></span>  
  
-   [<span data-ttu-id="529a6-108">class</span><span class="sxs-lookup"><span data-stu-id="529a6-108">class</span></span>](../../../csharp/language-reference/keywords/class.md)  
  
-   [<span data-ttu-id="529a6-109">interface</span><span class="sxs-lookup"><span data-stu-id="529a6-109">interface</span></span>](../../../csharp/language-reference/keywords/interface.md)  
  
-   [<span data-ttu-id="529a6-110">delegate</span><span class="sxs-lookup"><span data-stu-id="529a6-110">delegate</span></span>](../../../csharp/language-reference/keywords/delegate.md)  
  
 <span data-ttu-id="529a6-111">C# también proporciona los siguientes tipos de referencia integrados:</span><span class="sxs-lookup"><span data-stu-id="529a6-111">C# also provides the following built-in reference types:</span></span>  
  
-   [<span data-ttu-id="529a6-112">dynamic</span><span class="sxs-lookup"><span data-stu-id="529a6-112">dynamic</span></span>](../../../csharp/language-reference/keywords/dynamic.md)  
  
-   [<span data-ttu-id="529a6-113">object</span><span class="sxs-lookup"><span data-stu-id="529a6-113">object</span></span>](../../../csharp/language-reference/keywords/object.md)  
  
-   [<span data-ttu-id="529a6-114">string</span><span class="sxs-lookup"><span data-stu-id="529a6-114">string</span></span>](../../../csharp/language-reference/keywords/string.md)  
  
## <a name="see-also"></a><span data-ttu-id="529a6-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="529a6-115">See Also</span></span>  
 <span data-ttu-id="529a6-116">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="529a6-116">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="529a6-117">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="529a6-117">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="529a6-118">[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="529a6-118">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="529a6-119">[Types](../../../csharp/language-reference/keywords/types.md)  (Tipos [Referencia de C#])</span><span class="sxs-lookup"><span data-stu-id="529a6-119">[Types](../../../csharp/language-reference/keywords/types.md) </span></span>  
 [<span data-ttu-id="529a6-120">Tipos de valor</span><span class="sxs-lookup"><span data-stu-id="529a6-120">Value Types</span></span>](../../../csharp/language-reference/keywords/value-types.md)

