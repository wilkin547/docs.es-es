---
title: 'Utilizar operadores de conversión: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- conversions [C#], operators
- conversion operators [C#]
- operators [C#], conversion
- user-defined conversions [C#]
- implicit conversion operators [C#]
- explicit conversion operators [C#]
ms.assetid: caf36e89-c6c0-4b87-9f9e-85780a45c9a4
ms.openlocfilehash: 888339661ba1cb2e0b702f284d9f27b3217e74c1
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56973163"
---
# <a name="using-conversion-operators-c-programming-guide"></a><span data-ttu-id="3ae93-102">Utilizar operadores de conversión (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="3ae93-102">Using Conversion Operators (C# Programming Guide)</span></span>
<span data-ttu-id="3ae93-103">Puede usar los operadores de conversión `implicit`, que son más fáciles de usar, o los operadores de conversión `explicit`, que indican claramente a cualquiera que lea el código que está convirtiendo un tipo.</span><span class="sxs-lookup"><span data-stu-id="3ae93-103">You can use `implicit` conversion operators, which are easier to use, or `explicit` conversion operators, which clearly indicate to anyone reading the code that you're converting a type.</span></span> <span data-ttu-id="3ae93-104">En este tema se muestran ambos tipos de operadores de conversión.</span><span class="sxs-lookup"><span data-stu-id="3ae93-104">This topic demonstrates both types of conversion operator.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3ae93-105">Para obtener información sobre las conversiones de tipos simples, consulte [Cómo: Convertir una cadena en un número](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md), [Cómo: Convertir una matriz de bytes en un valor int](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md), [Cómo: Convertir cadenas hexadecimales en tipos numéricos](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md), o bien <xref:System.Convert>.</span><span class="sxs-lookup"><span data-stu-id="3ae93-105">For information about simple type conversions, see [How to: Convert a String to a Number](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md), [How to: Convert a byte Array to an int](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md), [How to: Convert Between Hexadecimal Strings and Numeric Types](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md), or <xref:System.Convert>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3ae93-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3ae93-106">Example</span></span>  
 <span data-ttu-id="3ae93-107">Este es un ejemplo de un operador de conversión explícita.</span><span class="sxs-lookup"><span data-stu-id="3ae93-107">This is an example of an explicit conversion operator.</span></span> <span data-ttu-id="3ae93-108">Este operador convierte el tipo <xref:System.Byte> en un tipo de valor denominado `Digit`.</span><span class="sxs-lookup"><span data-stu-id="3ae93-108">This operator converts from the type <xref:System.Byte> to a value type called `Digit`.</span></span> <span data-ttu-id="3ae93-109">Como no todos los bytes se pueden convertir en valores de tipo digit, la conversión es explícita, lo que significa que se debe usar una conversión, como se muestra en el método `Main`.</span><span class="sxs-lookup"><span data-stu-id="3ae93-109">Because not all bytes can be converted to a digit, the conversion is explicit, meaning that a cast must be used, as shown in the `Main` method.</span></span>  
  
 [!code-csharp[csProgGuideStatements#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#11)]  
  
## <a name="example"></a><span data-ttu-id="3ae93-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3ae93-110">Example</span></span>  
 <span data-ttu-id="3ae93-111">En este ejemplo se muestra un operador de conversión implícita mediante la definición de un operador de conversión que deshace lo que hizo el ejemplo anterior: convierte una clase de valor denominada `Digit` en el tipo entero <xref:System.Byte>.</span><span class="sxs-lookup"><span data-stu-id="3ae93-111">This example demonstrates an implicit conversion operator by defining a conversion operator that undoes what the previous example did: it converts from a value class called `Digit` to the integral <xref:System.Byte> type.</span></span> <span data-ttu-id="3ae93-112">Dado que cualquier dígito se puede convertir en <xref:System.Byte>, no hay ninguna necesidad de obligar a los usuarios a que definan explícitamente la conversión.</span><span class="sxs-lookup"><span data-stu-id="3ae93-112">Because any digit can be converted to a <xref:System.Byte>, there's no need to force users to be explicit about the conversion.</span></span>  
  
 [!code-csharp[csProgGuideStatements#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#12)]  
  
## <a name="see-also"></a><span data-ttu-id="3ae93-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="3ae93-113">See also</span></span>

- [<span data-ttu-id="3ae93-114">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="3ae93-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="3ae93-115">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="3ae93-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="3ae93-116">Operadores de conversión</span><span class="sxs-lookup"><span data-stu-id="3ae93-116">Conversion Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)
- [<span data-ttu-id="3ae93-117">is</span><span class="sxs-lookup"><span data-stu-id="3ae93-117">is</span></span>](../../../csharp/language-reference/keywords/is.md)
