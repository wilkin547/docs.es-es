---
title: object (Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- object_CSharpKeyword
- object
helpviewer_keywords:
- object keyword [C#]
ms.assetid: 93f60c0b-e17a-40a9-9362-cca5fb77b0e7
caps.latest.revision: 16
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 0fcced75d3a86fd700e642e48b7e325e554cae53
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="object-c-reference"></a><span data-ttu-id="dacdf-102">object (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="dacdf-102">object (C# Reference)</span></span>
<span data-ttu-id="dacdf-103">El tipo `object` es un alias de <xref:System.Object> en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="dacdf-103">The `object` type is an alias for <xref:System.Object> in the .NET Framework.</span></span> <span data-ttu-id="dacdf-104">En el sistema de tipos unificado de C#, todos los tipos, los predefinidos y los definidos por el usuario, los tipos de referencia y los tipos de valores, heredan directa o indirectamente de <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="dacdf-104">In the unified type system of C#, all types, predefined and user-defined, reference types and value types, inherit directly or indirectly from <xref:System.Object>.</span></span> <span data-ttu-id="dacdf-105">Puede asignar valores de cualquier tipo a las variables de tipo `object`.</span><span class="sxs-lookup"><span data-stu-id="dacdf-105">You can assign values of any type to variables of type `object`.</span></span> <span data-ttu-id="dacdf-106">Cuando una variable de un tipo de valor se convierte en objeto, se dice que se aplica la *conversión boxing*.</span><span class="sxs-lookup"><span data-stu-id="dacdf-106">When a variable of a value type is converted to object, it is said to be *boxed*.</span></span> <span data-ttu-id="dacdf-107">Cuando una variable de tipo de objeto se convierte en un tipo de valor, se dice que se aplica la *conversión unboxing*.</span><span class="sxs-lookup"><span data-stu-id="dacdf-107">When a variable of type object is converted to a value type, it is said to be *unboxed*.</span></span> <span data-ttu-id="dacdf-108">Para obtener más información, vea [Boxing and Unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md) (Conversión boxing y conversión unboxing [Guía de programación de C#]).</span><span class="sxs-lookup"><span data-stu-id="dacdf-108">For more information, see [Boxing and Unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="dacdf-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dacdf-109">Example</span></span>  
 <span data-ttu-id="dacdf-110">El siguiente ejemplo muestra cómo las variables de tipo `object` pueden aceptar valores de cualquier tipo de datos y cómo las variables de tipo `object` pueden usar métodos en <xref:System.Object> desde .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="dacdf-110">The following sample shows how variables of type `object` can accept values of any data type and how variables of type `object` can use methods on <xref:System.Object> from the .NET Framework.</span></span>  
  
 [!code-csharp[csrefKeywordsTypes#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/object_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="dacdf-111">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="dacdf-111">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="dacdf-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="dacdf-112">See Also</span></span>  
 [<span data-ttu-id="dacdf-113">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="dacdf-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="dacdf-114">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="dacdf-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="dacdf-115">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="dacdf-115">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="dacdf-116">Tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="dacdf-116">Reference Types</span></span>](../../../csharp/language-reference/keywords/reference-types.md)  
 [<span data-ttu-id="dacdf-117">Tipos de valor</span><span class="sxs-lookup"><span data-stu-id="dacdf-117">Value Types</span></span>](../../../csharp/language-reference/keywords/value-types.md)
