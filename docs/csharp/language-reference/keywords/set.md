---
title: set (Referencia de C#)
ms.date: 03/10/2017
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- set
- set_CSharpKeyword
helpviewer_keywords:
- set keyword [C#]
ms.assetid: 30d7e4e5-cc2e-4635-a597-14a724879619
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b810280724dcf608859bfa455947a75ce64b7abe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="set-c-reference"></a><span data-ttu-id="fea6a-102">set (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="fea6a-102">set (C# Reference)</span></span>
<span data-ttu-id="fea6a-103">La palabra clave `set` define un método de *descriptor de acceso* en una propiedad o indexador que asigna el valor de la propiedad o del elemento del indexador.</span><span class="sxs-lookup"><span data-stu-id="fea6a-103">The `set` keyword defines an *accessor* method in a property or indexer that assigns a value to the property or the indexer element.</span></span> <span data-ttu-id="fea6a-104">Para obtener más información y ejemplos, vea [Propiedades](../../../csharp/programming-guide/classes-and-structs/properties.md), [Propiedades autoimplementadas](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md) e [Indexadores](../../../csharp/programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="fea6a-104">For more information and examples, see [Properties](../../../csharp/programming-guide/classes-and-structs/properties.md), [Auto-Implemented Properties](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md), and [Indexers](../../../csharp/programming-guide/indexers/index.md).</span></span>  
  
<span data-ttu-id="fea6a-105">En el ejemplo siguiente se definen unos descriptores de acceso `get` y `set` para una propiedad denominada `Seconds`.</span><span class="sxs-lookup"><span data-stu-id="fea6a-105">The following example defines both a `get` and a `set` accessor for a property named `Seconds`.</span></span> <span data-ttu-id="fea6a-106">Usa un campo privado denominado `_seconds` para respaldar el valor de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="fea6a-106">It uses a private field named `_seconds` to back the property value.</span></span>  
 
 [!code-csharp[set#1](../../../../samples/snippets/csharp/language-reference/keywords/get/get-1.cs)]  

<span data-ttu-id="fea6a-107">A menudo, el descriptor de acceso `set` consta de una única instrucción que devuelve un valor, como en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="fea6a-107">Often, the `set` accessor consists of a single statement that returns a value, as it did in the previous example.</span></span> <span data-ttu-id="fea6a-108">A partir de C# 7, se puede implementar el descriptor de acceso `set` como un miembro con forma de expresión.</span><span class="sxs-lookup"><span data-stu-id="fea6a-108">Starting with C# 7, you can implement the `set` accessor as an expression-bodied member.</span></span> <span data-ttu-id="fea6a-109">En el ejemplo siguiente se implementan los descriptores de acceso `get` y `set` como miembros con forma de expresión.</span><span class="sxs-lookup"><span data-stu-id="fea6a-109">The following example implements both the `get` and the `set` accessors as expression-bodied members.</span></span>

 [!code-csharp[set#3](../../../../samples/snippets/csharp/language-reference/keywords/get/get-3.cs)]   
    
<span data-ttu-id="fea6a-110">En los casos sencillos en los que los descriptores de acceso `get` y `set` de una propiedad no realizan ninguna operación aparte de establecer o recuperar un valor en un campo de respaldo privado, puede aprovechar la compatibilidad del compilador de C# con las propiedades implementadas automáticamente.</span><span class="sxs-lookup"><span data-stu-id="fea6a-110">For simple cases in which a property's `get` and `set` accessors perform no other operation than setting or retrieving a value in a private backing field, you can take advantage of the C# compiler's support for auto-implemented properties.</span></span> <span data-ttu-id="fea6a-111">En el ejemplo siguiente se implementa `Hours` como una propiedad implementada automáticamente.</span><span class="sxs-lookup"><span data-stu-id="fea6a-111">The following example implements `Hours` as an auto-implemented property.</span></span> 
  
 [!code-csharp[set#2](../../../../samples/snippets/csharp/language-reference/keywords/get/get-2.cs)]  
    
## <a name="c-language-specification"></a><span data-ttu-id="fea6a-112">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="fea6a-112">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fea6a-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="fea6a-113">See Also</span></span>  
 [<span data-ttu-id="fea6a-114">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="fea6a-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="fea6a-115">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="fea6a-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="fea6a-116">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="fea6a-116">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="fea6a-117">Propiedades</span><span class="sxs-lookup"><span data-stu-id="fea6a-117">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)
