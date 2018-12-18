---
title: 'value: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- value_CSharpKeyword
helpviewer_keywords:
- value keyword [C#]
ms.assetid: c99d6468-687f-4a46-89b4-a95e1b00bf6d
ms.openlocfilehash: f0b9e2927eb288a27f926a740a967742b8cdaa9e
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236471"
---
# <a name="value-c-reference"></a><span data-ttu-id="eeb17-102">value (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="eeb17-102">value (C# Reference)</span></span>
<span data-ttu-id="eeb17-103">La palabra clave contextual `value` se usa en el descriptor de acceso set de las declaraciones de propiedad normales.</span><span class="sxs-lookup"><span data-stu-id="eeb17-103">The contextual keyword `value` is used in the set accessor in ordinary property declarations.</span></span> <span data-ttu-id="eeb17-104">Es similar a un parámetro de entrada de un método.</span><span class="sxs-lookup"><span data-stu-id="eeb17-104">It is similar to an input parameter on a method.</span></span> <span data-ttu-id="eeb17-105">El término `value` hace referencia al valor que el código de cliente intenta asignar a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="eeb17-105">The word `value` references the value that client code is attempting to assign to the property.</span></span> <span data-ttu-id="eeb17-106">En el ejemplo siguiente, `MyDerivedClass` tiene una propiedad denominada `Name` que usa el parámetro `value` para asignar una nueva cadena al campo de respaldo `name`.</span><span class="sxs-lookup"><span data-stu-id="eeb17-106">In the following example, `MyDerivedClass` has a property called `Name` that uses the `value` parameter to assign a new string to the backing field `name`.</span></span> <span data-ttu-id="eeb17-107">Desde el punto de vista del código de cliente, la operación se escribe como una simple asignación.</span><span class="sxs-lookup"><span data-stu-id="eeb17-107">From the point of view of client code, the operation is written as a simple assignment.</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#26](../../../csharp/language-reference/keywords/codesnippet/CSharp/value_1.cs)]  
  
 <span data-ttu-id="eeb17-108">Para obtener más información sobre el uso de `value`, vea [Propiedades](../../../csharp/programming-guide/classes-and-structs/properties.md).</span><span class="sxs-lookup"><span data-stu-id="eeb17-108">For more information about the use of `value`, see [Properties](../../../csharp/programming-guide/classes-and-structs/properties.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="eeb17-109">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="eeb17-109">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="eeb17-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="eeb17-110">See Also</span></span>

- [<span data-ttu-id="eeb17-111">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="eeb17-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="eeb17-112">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="eeb17-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="eeb17-113">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="eeb17-113">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
