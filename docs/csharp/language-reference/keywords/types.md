---
title: Tipos (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- types [C#]
- data types [C#], type system
ms.assetid: 16b984df-f417-4e02-b1e6-4589d4a614ea
caps.latest.revision: 13
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
ms.openlocfilehash: 2816a5dd86e71641198a340b3a72094dffc93bdf
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="types-c-reference"></a><span data-ttu-id="7a5ae-102">Tipos (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="7a5ae-102">Types (C# Reference)</span></span>
<span data-ttu-id="7a5ae-103">El sistema de tipos de C# contiene las siguientes categorías:</span><span class="sxs-lookup"><span data-stu-id="7a5ae-103">The C# typing system contains the following categories:</span></span>  
  
-   [<span data-ttu-id="7a5ae-104">Tipos de valor</span><span class="sxs-lookup"><span data-stu-id="7a5ae-104">Value types</span></span>](../../../csharp/language-reference/keywords/value-types.md)  
  
-   [<span data-ttu-id="7a5ae-105">Tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="7a5ae-105">Reference types</span></span>](../../../csharp/language-reference/keywords/reference-types.md)  
  
-   [<span data-ttu-id="7a5ae-106">Tipos de puntero</span><span class="sxs-lookup"><span data-stu-id="7a5ae-106">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
  
 <span data-ttu-id="7a5ae-107">Las variables que son tipos de valor almacenan datos y las que son tipos de referencia almacenan referencias a los datos reales.</span><span class="sxs-lookup"><span data-stu-id="7a5ae-107">Variables that are value types store data, and those that are reference types store references to the actual data.</span></span> <span data-ttu-id="7a5ae-108">Los tipos de referencia también se conocen como objetos.</span><span class="sxs-lookup"><span data-stu-id="7a5ae-108">Reference types are also referred to as objects.</span></span> <span data-ttu-id="7a5ae-109">Los tipos de puntero se pueden usar solo en modo [unsafe](../../../csharp/language-reference/keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="7a5ae-109">Pointer types can be used only in [unsafe](../../../csharp/language-reference/keywords/unsafe.md) mode.</span></span>  
  
 <span data-ttu-id="7a5ae-110">Es posible convertir un tipo de valor en un tipo de referencia y volver a un tipo de valor mediante el uso de la [conversión boxing y unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md).</span><span class="sxs-lookup"><span data-stu-id="7a5ae-110">It is possible to convert a value type to a reference type, and back again to a value type, by using [boxing and unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md).</span></span> <span data-ttu-id="7a5ae-111">Con la excepción de un tipo de valor al que se le ha aplicado la conversión boxing, no se puede convertir un tipo de referencia en un tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="7a5ae-111">With the exception of a boxed value type, you cannot convert a reference type to a value type.</span></span>  
  
 <span data-ttu-id="7a5ae-112">En esta sección también se presenta [void](../../../csharp/language-reference/keywords/void.md).</span><span class="sxs-lookup"><span data-stu-id="7a5ae-112">This section also introduces [void](../../../csharp/language-reference/keywords/void.md).</span></span>  
  
 <span data-ttu-id="7a5ae-113">Los tipos de valor también aceptan valores NULL, lo que significa que pueden almacenar un estado sin valor adicional.</span><span class="sxs-lookup"><span data-stu-id="7a5ae-113">Value types are also nullable, which means they can store an additional non-value state.</span></span> <span data-ttu-id="7a5ae-114">Para obtener más información, vea [Nullable Types](../../../csharp/programming-guide/nullable-types/index.md) (Tipos que aceptan valores NULL [Guía de programación de C#]).</span><span class="sxs-lookup"><span data-stu-id="7a5ae-114">For more information, see [Nullable Types](../../../csharp/programming-guide/nullable-types/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a5ae-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="7a5ae-115">See Also</span></span>  
 <span data-ttu-id="7a5ae-116">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="7a5ae-116">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="7a5ae-117">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="7a5ae-117">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="7a5ae-118">[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="7a5ae-118">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="7a5ae-119">[Tablas de referencia para tipos](../../../csharp/language-reference/keywords/reference-tables-for-types.md) </span><span class="sxs-lookup"><span data-stu-id="7a5ae-119">[Reference Tables for Types](../../../csharp/language-reference/keywords/reference-tables-for-types.md) </span></span>  
 <span data-ttu-id="7a5ae-120">[Casting and Type Conversions](../../../csharp/programming-guide/types/casting-and-type-conversions.md)  (Conversiones de tipos [Guía de programación de C#])</span><span class="sxs-lookup"><span data-stu-id="7a5ae-120">[Casting and Type Conversions](../../../csharp/programming-guide/types/casting-and-type-conversions.md) </span></span>  
 [<span data-ttu-id="7a5ae-121">Tipos</span><span class="sxs-lookup"><span data-stu-id="7a5ae-121">Types</span></span>](../../../csharp/programming-guide/types/index.md)

