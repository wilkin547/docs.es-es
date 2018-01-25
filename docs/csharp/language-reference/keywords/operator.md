---
title: operator (Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- operator_CSharpKeyword
- operator
helpviewer_keywords: operator keyword [C#]
ms.assetid: 59218cce-e90e-42f6-a6bb-30300981b86a
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 1d035319318a710ccee62a0c64ce5981767a21ca
ms.sourcegitcommit: 8bde7a3432f30fc771079744955c75c58c4eb393
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/20/2018
---
# <a name="operator-c-reference"></a><span data-ttu-id="3b4e9-102">operator (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="3b4e9-102">operator (C# Reference)</span></span>
<span data-ttu-id="3b4e9-103">Use la palabra clave `operator` para sobrecargar un operador integrado o proporcionar una conversión definida por el usuario en una declaración de clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="3b4e9-103">Use the `operator` keyword to overload a built-in operator or to provide a user-defined conversion in a class or struct declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3b4e9-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3b4e9-104">Example</span></span>  
 <span data-ttu-id="3b4e9-105">La siguiente es una clase muy simplificada para números fraccionarios.</span><span class="sxs-lookup"><span data-stu-id="3b4e9-105">The following is a very simplified class for fractional numbers.</span></span> <span data-ttu-id="3b4e9-106">Sobrecarga los operadores `+` y `*` para realizar multiplicaciones y sumas fraccionarias, y también proporciona un operador de conversión que convierte un tipo `Fraction` en un tipo `double`.</span><span class="sxs-lookup"><span data-stu-id="3b4e9-106">It overloads the `+` and `*` operators to perform fractional addition and multiplication, and also provides a conversion operator that converts a `Fraction` type to a `double` type.</span></span>  
  
 [!code-csharp[csrefKeywordsConversion#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/operator_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="3b4e9-107">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="3b4e9-107">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3b4e9-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="3b4e9-108">See Also</span></span>  
 [<span data-ttu-id="3b4e9-109">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="3b4e9-109">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="3b4e9-110">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="3b4e9-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="3b4e9-111">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="3b4e9-111">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="3b4e9-112">implicit</span><span class="sxs-lookup"><span data-stu-id="3b4e9-112">implicit</span></span>](../../../csharp/language-reference/keywords/implicit.md)  
 [<span data-ttu-id="3b4e9-113">explicit</span><span class="sxs-lookup"><span data-stu-id="3b4e9-113">explicit</span></span>](../../../csharp/language-reference/keywords/explicit.md)  
 [<span data-ttu-id="3b4e9-114">Cómo: Implementar conversiones definidas por el usuario entre structs</span><span class="sxs-lookup"><span data-stu-id="3b4e9-114">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)
