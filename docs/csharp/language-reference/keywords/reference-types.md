---
title: Tipos de referencia (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- cs.referencetypes
helpviewer_keywords:
- reference types [C#]
- C# language, reference types
- types [C#], reference types
ms.assetid: 801cf030-6e2d-4a0d-9daf-1431b0c31f47
ms.openlocfilehash: cca9826c658581be38866410d5f966b1c7c35772
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33267344"
---
# <a name="reference-types-c-reference"></a><span data-ttu-id="52d13-102">Tipos de referencia (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="52d13-102">Reference Types (C# Reference)</span></span>
<span data-ttu-id="52d13-103">Hay dos clases de tipos en C#: tipos de referencia y tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="52d13-103">There are two kinds of types in C#: reference types and value types.</span></span> <span data-ttu-id="52d13-104">Las variables de tipos de referencia almacenan referencias en sus datos (objetos), mientras que las variables de tipos de valor contienen directamente los datos.</span><span class="sxs-lookup"><span data-stu-id="52d13-104">Variables of reference types store references to their data (objects), while variables of value types directly contain their data.</span></span> <span data-ttu-id="52d13-105">Con los tipos de referencia, dos variables pueden hacer referencia al mismo objeto y, por lo tanto, las operaciones en una variable pueden afectar al objeto al que hace referencia la otra variable.</span><span class="sxs-lookup"><span data-stu-id="52d13-105">With reference types, two variables can reference the same object; therefore, operations on one variable can affect the object referenced by the other variable.</span></span> <span data-ttu-id="52d13-106">Con los tipos de valor, cada variable tiene su propia copia de los datos, y no es posible que las operaciones en una variable afecten a la otra (excepto en el caso de las variables de parámetro in, ref y out, consulte el modificador de parámetro [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md), [ref](../../../csharp/language-reference/keywords/ref.md) y [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md)).</span><span class="sxs-lookup"><span data-stu-id="52d13-106">With value types, each variable has its own copy of the data, and it is not possible for operations on one variable to affect the other (except in the case of in, ref and out parameter variables; see [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md), [ref](../../../csharp/language-reference/keywords/ref.md) and [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) parameter modifier).</span></span>  
  
 <span data-ttu-id="52d13-107">Las palabras clave siguientes se usan para declarar tipos de referencia:</span><span class="sxs-lookup"><span data-stu-id="52d13-107">The following keywords are used to declare reference types:</span></span>  
  
-   [<span data-ttu-id="52d13-108">class</span><span class="sxs-lookup"><span data-stu-id="52d13-108">class</span></span>](../../../csharp/language-reference/keywords/class.md)  
  
-   [<span data-ttu-id="52d13-109">interface</span><span class="sxs-lookup"><span data-stu-id="52d13-109">interface</span></span>](../../../csharp/language-reference/keywords/interface.md)  
  
-   [<span data-ttu-id="52d13-110">delegate</span><span class="sxs-lookup"><span data-stu-id="52d13-110">delegate</span></span>](../../../csharp/language-reference/keywords/delegate.md)  
  
 <span data-ttu-id="52d13-111">C# también proporciona los siguientes tipos de referencia integrados:</span><span class="sxs-lookup"><span data-stu-id="52d13-111">C# also provides the following built-in reference types:</span></span>  
  
-   [<span data-ttu-id="52d13-112">dynamic</span><span class="sxs-lookup"><span data-stu-id="52d13-112">dynamic</span></span>](../../../csharp/language-reference/keywords/dynamic.md)  
  
-   [<span data-ttu-id="52d13-113">object</span><span class="sxs-lookup"><span data-stu-id="52d13-113">object</span></span>](../../../csharp/language-reference/keywords/object.md)  
  
-   [<span data-ttu-id="52d13-114">string</span><span class="sxs-lookup"><span data-stu-id="52d13-114">string</span></span>](../../../csharp/language-reference/keywords/string.md)  
  
## <a name="see-also"></a><span data-ttu-id="52d13-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="52d13-115">See Also</span></span>  
 [<span data-ttu-id="52d13-116">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="52d13-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="52d13-117">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="52d13-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="52d13-118">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="52d13-118">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="52d13-119">Tipos</span><span class="sxs-lookup"><span data-stu-id="52d13-119">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
 [<span data-ttu-id="52d13-120">Tipos de valor</span><span class="sxs-lookup"><span data-stu-id="52d13-120">Value Types</span></span>](../../../csharp/language-reference/keywords/value-types.md)
