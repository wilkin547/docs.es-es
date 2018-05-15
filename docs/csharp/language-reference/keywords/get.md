---
title: get (Referencia de C#)
ms.date: 03/10/2017
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- get_CSharpKeyword
- get
helpviewer_keywords:
- get keyword [C#]
ms.assetid: a52de048-fbe0-41b0-82ec-8e4ac04d3a71
caps.latest.revision: 11
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 3cdf639065ee5bf0cb9e920061557991c0a4b921
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="get-c-reference"></a><span data-ttu-id="a6f91-102">get (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="a6f91-102">get (C# Reference)</span></span>

<span data-ttu-id="a6f91-103">La palabra clave `get` define un método de *descriptor de acceso* en una propiedad o un indizador que devuelve el valor de la propiedad o el elemento del indizador.</span><span class="sxs-lookup"><span data-stu-id="a6f91-103">The `get` keyword defines an *accessor* method in a property or indexer that returns the property value or the indexer element.</span></span> <span data-ttu-id="a6f91-104">Para obtener más información, consulte [Properties](../../../csharp/programming-guide/classes-and-structs/properties.md) (Propiedades), [Auto-Implemented Properties](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md) (Propiedades implementadas automáticamente) e [Indexers](../../../csharp/programming-guide/indexers/index.md) (Indizadores).</span><span class="sxs-lookup"><span data-stu-id="a6f91-104">For more information, see [Properties](../../../csharp/programming-guide/classes-and-structs/properties.md), [Auto-Implemented Properties](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md) and [Indexers](../../../csharp/programming-guide/indexers/index.md).</span></span>  
  
<span data-ttu-id="a6f91-105">En el ejemplo siguiente se definen unos descriptores de acceso `get` y `set` para una propiedad denominada `Seconds`.</span><span class="sxs-lookup"><span data-stu-id="a6f91-105">The following example defines both a `get` and a `set` accessor for a property named `Seconds`.</span></span> <span data-ttu-id="a6f91-106">Usa un campo privado denominado `_seconds` para respaldar el valor de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="a6f91-106">It uses a private field named `_seconds` to back the property value.</span></span>  
 
 [!code-csharp[get#1](../../../../samples/snippets/csharp/language-reference/keywords/get/get-1.cs)]  
  
<span data-ttu-id="a6f91-107">A menudo, el descriptor de acceso `get` consta de una única instrucción que devuelve un valor, como en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="a6f91-107">Often, the `get` accessor consists of a single statement that returns a value, as it did in the previous example.</span></span> <span data-ttu-id="a6f91-108">A partir de C# 7.0, se puede implementar el descriptor de acceso `get` como un miembro con forma de expresión.</span><span class="sxs-lookup"><span data-stu-id="a6f91-108">Starting with C# 7.0, you can implement the `get` accessor as an expression-bodied member.</span></span> <span data-ttu-id="a6f91-109">En el ejemplo siguiente se implementan los descriptores de acceso `get` y `set` como miembros con forma de expresión.</span><span class="sxs-lookup"><span data-stu-id="a6f91-109">The following example implements both the `get` and the `set` accessor as expression-bodied members.</span></span>

 [!code-csharp[get#3](../../../../samples/snippets/csharp/language-reference/keywords/get/get-3.cs)]   
 
<span data-ttu-id="a6f91-110">En los casos sencillos en los que los descriptores de acceso `get` y `set` de una propiedad no realizan ninguna operación aparte de establecer o recuperar un valor en un campo de respaldo privado, puede aprovechar la compatibilidad del compilador de C# con las propiedades implementadas automáticamente.</span><span class="sxs-lookup"><span data-stu-id="a6f91-110">For simple cases in which a property's `get` and `set` accessors perform no other operation than setting or retrieving a value in a private backing field, you can take advantage of the C# compiler's support for auto-implemented properties.</span></span> <span data-ttu-id="a6f91-111">En el ejemplo siguiente se implementa `Hours` como una propiedad implementada automáticamente.</span><span class="sxs-lookup"><span data-stu-id="a6f91-111">The following example implements `Hours` as an auto-implemented property.</span></span> 
  
 [!code-csharp[get#2](../../../../samples/snippets/csharp/language-reference/keywords/get/get-2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="a6f91-112">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="a6f91-112">C# Language Specification</span></span>

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a6f91-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="a6f91-113">See Also</span></span>  
 [<span data-ttu-id="a6f91-114">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="a6f91-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="a6f91-115">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="a6f91-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 <span data-ttu-id="a6f91-116">[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md) [Propiedades](../../../csharp/programming-guide/classes-and-structs/properties.md)</span><span class="sxs-lookup"><span data-stu-id="a6f91-116">[C# Keywords](../../../csharp/language-reference/keywords/index.md) [Properties](../../../csharp/programming-guide/classes-and-structs/properties.md)</span></span>
