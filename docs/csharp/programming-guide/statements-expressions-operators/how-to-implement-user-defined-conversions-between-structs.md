---
title: "Cómo: Implementar conversiones definidas por el usuario entre structs (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: user-defined conversions [C#]
ms.assetid: 97839aef-8fbc-40d5-9769-6b569bc2710b
caps.latest.revision: "11"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 7d86cbd48347e6951f6b6883a385d80d68697c9c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-user-defined-conversions-between-structs-c-programming-guide"></a><span data-ttu-id="36009-102">Cómo: Implementar conversiones definidas por el usuario entre structs (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="36009-102">How to: Implement User-Defined Conversions Between Structs (C# Programming Guide)</span></span>
<span data-ttu-id="36009-103">Este ejemplo define dos structs, `RomanNumeral` y `BinaryNumeral`, y muestra conversiones entre ellos.</span><span class="sxs-lookup"><span data-stu-id="36009-103">This example defines two structs, `RomanNumeral` and `BinaryNumeral`, and demonstrates conversions between them.</span></span>  
  
## <a name="example"></a><span data-ttu-id="36009-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="36009-104">Example</span></span>  
 [!code-csharp[csProgGuideStatements#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_1.cs)]  
  
## <a name="robust-programming"></a><span data-ttu-id="36009-105">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="36009-105">Robust Programming</span></span>  
  
-   <span data-ttu-id="36009-106">En el ejemplo anterior, la instrucción:</span><span class="sxs-lookup"><span data-stu-id="36009-106">In the previous example, the statement:</span></span>  
  
     [!code-csharp[csProgGuideStatements#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_2.cs)]  
  
     <span data-ttu-id="36009-107">realiza una conversión de `RomanNumeral` a `BinaryNumeral`.</span><span class="sxs-lookup"><span data-stu-id="36009-107">performs a conversion from a `RomanNumeral` to a `BinaryNumeral`.</span></span> <span data-ttu-id="36009-108">Como no existe una conversión directa de `RomanNumeral` a `BinaryNumeral`, se usa una conversión explícita de un `RomanNumeral` a un `int`, y otra conversión explícita para convertir de un `int` a un `BinaryNumeral`.</span><span class="sxs-lookup"><span data-stu-id="36009-108">Because there is no direct conversion from `RomanNumeral` to `BinaryNumeral`, a cast is used to convert from a `RomanNumeral` to an `int`, and another cast to convert from an `int` to a `BinaryNumeral`.</span></span>  
  
-   <span data-ttu-id="36009-109">Además la instrucción</span><span class="sxs-lookup"><span data-stu-id="36009-109">Also the statement</span></span>  
  
     [!code-csharp[csProgGuideStatements#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_3.cs)]  
  
     <span data-ttu-id="36009-110">realiza una conversión de `BinaryNumeral` a `RomanNumeral`.</span><span class="sxs-lookup"><span data-stu-id="36009-110">performs a conversion from a `BinaryNumeral` to a `RomanNumeral`.</span></span> <span data-ttu-id="36009-111">Como `RomanNumeral` define una conversión implícita desde `BinaryNumeral`, no se requiere ninguna conversión explícita.</span><span class="sxs-lookup"><span data-stu-id="36009-111">Because `RomanNumeral` defines an implicit conversion from `BinaryNumeral`, no cast is required.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36009-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="36009-112">See Also</span></span>  
 [<span data-ttu-id="36009-113">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="36009-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="36009-114">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="36009-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="36009-115">Operadores de conversión</span><span class="sxs-lookup"><span data-stu-id="36009-115">Conversion Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)
