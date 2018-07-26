---
title: object (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- object_CSharpKeyword
- object
helpviewer_keywords:
- object keyword [C#]
ms.assetid: 93f60c0b-e17a-40a9-9362-cca5fb77b0e7
ms.openlocfilehash: 67eaf7f1fd2f01e433395ed21701c3b7fad7c7b4
ms.sourcegitcommit: 2d8b7488d94101b534ca3e9780b1c1e840233405
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2018
ms.locfileid: "39199256"
---
# <a name="object-c-reference"></a><span data-ttu-id="f36ea-102">object (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="f36ea-102">object (C# Reference)</span></span>
<span data-ttu-id="f36ea-103">El tipo `object` es un alias de <xref:System.Object> en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f36ea-103">The `object` type is an alias for <xref:System.Object> in the .NET Framework.</span></span> <span data-ttu-id="f36ea-104">En el sistema de tipos unificado de C#, todos los tipos, los predefinidos y los definidos por el usuario, los tipos de referencia y los tipos de valores, heredan directa o indirectamente de <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="f36ea-104">In the unified type system of C#, all types, predefined and user-defined, reference types and value types, inherit directly or indirectly from <xref:System.Object>.</span></span> <span data-ttu-id="f36ea-105">Puede asignar valores de cualquier tipo a las variables de tipo `object`.</span><span class="sxs-lookup"><span data-stu-id="f36ea-105">You can assign values of any type to variables of type `object`.</span></span> <span data-ttu-id="f36ea-106">Cuando una variable de un tipo de valor se convierte en objeto, se dice que se aplica la *conversión boxing*.</span><span class="sxs-lookup"><span data-stu-id="f36ea-106">When a variable of a value type is converted to object, it is said to be *boxed*.</span></span> <span data-ttu-id="f36ea-107">Cuando una variable de tipo de objeto se convierte en un tipo de valor, se dice que se aplica la *conversión unboxing*.</span><span class="sxs-lookup"><span data-stu-id="f36ea-107">When a variable of type object is converted to a value type, it is said to be *unboxed*.</span></span> <span data-ttu-id="f36ea-108">Para obtener más información, vea [Boxing and Unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md) (Conversión boxing y conversión unboxing [Guía de programación de C#]).</span><span class="sxs-lookup"><span data-stu-id="f36ea-108">For more information, see [Boxing and Unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f36ea-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f36ea-109">Example</span></span>  
 <span data-ttu-id="f36ea-110">El siguiente ejemplo muestra cómo las variables de tipo `object` pueden aceptar valores de cualquier tipo de datos y cómo las variables de tipo `object` pueden usar métodos en <xref:System.Object> desde .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f36ea-110">The following sample shows how variables of type `object` can accept values of any data type and how variables of type `object` can use methods on <xref:System.Object> from the .NET Framework.</span></span>  
  
 [!code-csharp[csrefKeywordsTypes#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/object_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="f36ea-111">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="f36ea-111">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f36ea-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="f36ea-112">See Also</span></span>  
 [<span data-ttu-id="f36ea-113">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="f36ea-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="f36ea-114">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="f36ea-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="f36ea-115">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="f36ea-115">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="f36ea-116">Tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="f36ea-116">Reference Types</span></span>](../../../csharp/language-reference/keywords/reference-types.md)  
 [<span data-ttu-id="f36ea-117">Tipos de valor</span><span class="sxs-lookup"><span data-stu-id="f36ea-117">Value Types</span></span>](../../../csharp/language-reference/keywords/value-types.md)
