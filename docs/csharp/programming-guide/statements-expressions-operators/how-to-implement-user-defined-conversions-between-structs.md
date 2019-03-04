---
title: 'Procedimiento Implementar conversiones definidas por el usuario entre structs: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- user-defined conversions [C#]
ms.assetid: 97839aef-8fbc-40d5-9769-6b569bc2710b
ms.openlocfilehash: bc792562b4849d402e03328e50dedac030520011
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/01/2019
ms.locfileid: "57201149"
---
# <a name="how-to-implement-user-defined-conversions-between-structs-c-programming-guide"></a><span data-ttu-id="fe106-102">Procedimiento Implementar conversiones definidas por el usuario entre structs (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="fe106-102">How to: Implement User-Defined Conversions Between Structs (C# Programming Guide)</span></span>
<span data-ttu-id="fe106-103">Este ejemplo define dos structs, `RomanNumeral` y `BinaryNumeral`, y muestra conversiones entre ellos.</span><span class="sxs-lookup"><span data-stu-id="fe106-103">This example defines two structs, `RomanNumeral` and `BinaryNumeral`, and demonstrates conversions between them.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fe106-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fe106-104">Example</span></span>  
 [!code-csharp[csProgGuideStatements#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#13)]  
  
## <a name="robust-programming"></a><span data-ttu-id="fe106-105">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="fe106-105">Robust Programming</span></span>  
  
-   <span data-ttu-id="fe106-106">En el ejemplo anterior, la instrucción:</span><span class="sxs-lookup"><span data-stu-id="fe106-106">In the previous example, the statement:</span></span>  
  
     [!code-csharp[csProgGuideStatements#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#14)]  
  
     <span data-ttu-id="fe106-107">realiza una conversión de `RomanNumeral` a `BinaryNumeral`.</span><span class="sxs-lookup"><span data-stu-id="fe106-107">performs a conversion from a `RomanNumeral` to a `BinaryNumeral`.</span></span> <span data-ttu-id="fe106-108">Como no existe una conversión directa de `RomanNumeral` a `BinaryNumeral`, se usa una conversión explícita de un `RomanNumeral` a un `int`, y otra conversión explícita para convertir de un `int` a un `BinaryNumeral`.</span><span class="sxs-lookup"><span data-stu-id="fe106-108">Because there is no direct conversion from `RomanNumeral` to `BinaryNumeral`, a cast is used to convert from a `RomanNumeral` to an `int`, and another cast to convert from an `int` to a `BinaryNumeral`.</span></span>  
  
-   <span data-ttu-id="fe106-109">Además la instrucción</span><span class="sxs-lookup"><span data-stu-id="fe106-109">Also the statement</span></span>  
  
     [!code-csharp[csProgGuideStatements#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#15)]  
  
     <span data-ttu-id="fe106-110">realiza una conversión de `BinaryNumeral` a `RomanNumeral`.</span><span class="sxs-lookup"><span data-stu-id="fe106-110">performs a conversion from a `BinaryNumeral` to a `RomanNumeral`.</span></span> <span data-ttu-id="fe106-111">Como `RomanNumeral` define una conversión implícita desde `BinaryNumeral`, no se requiere ninguna conversión explícita.</span><span class="sxs-lookup"><span data-stu-id="fe106-111">Because `RomanNumeral` defines an implicit conversion from `BinaryNumeral`, no cast is required.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe106-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="fe106-112">See also</span></span>

- [<span data-ttu-id="fe106-113">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="fe106-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="fe106-114">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="fe106-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="fe106-115">Operadores de conversión</span><span class="sxs-lookup"><span data-stu-id="fe106-115">Conversion Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)
