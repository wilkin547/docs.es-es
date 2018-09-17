---
title: Utilizar operadores de conversión (Guía de programación de C#)
ms.date: 07/20/2015
helpviewer_keywords:
- conversions [C#], operators
- conversion operators [C#]
- operators [C#], conversion
- user-defined conversions [C#]
- implicit conversion operators [C#]
- explicit conversion operators [C#]
ms.assetid: caf36e89-c6c0-4b87-9f9e-85780a45c9a4
ms.openlocfilehash: 17a722f7160ae9cd03caa2dff9c4436fcf0f9d9e
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2018
ms.locfileid: "45593704"
---
# <a name="using-conversion-operators-c-programming-guide"></a><span data-ttu-id="35df2-102">Utilizar operadores de conversión (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="35df2-102">Using Conversion Operators (C# Programming Guide)</span></span>
<span data-ttu-id="35df2-103">Puede usar los operadores de conversión `implicit`, que son más fáciles de usar, o los operadores de conversión `explicit`, que indican claramente a cualquiera que lea el código que está convirtiendo un tipo.</span><span class="sxs-lookup"><span data-stu-id="35df2-103">You can use `implicit` conversion operators, which are easier to use, or `explicit` conversion operators, which clearly indicate to anyone reading the code that you're converting a type.</span></span> <span data-ttu-id="35df2-104">En este tema se muestran ambos tipos de operadores de conversión.</span><span class="sxs-lookup"><span data-stu-id="35df2-104">This topic demonstrates both types of conversion operator.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="35df2-105">Para obtener información sobre las conversiones de tipo simple, vea [Cómo: Convertir una cadena en un número](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md), [Cómo: Convertir una matriz de bytes en un valor int](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md), [Cómo: Convertir cadenas hexadecimales en tipos numéricos](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md) o <xref:System.Convert>.</span><span class="sxs-lookup"><span data-stu-id="35df2-105">For information about simple type conversions, see [How to: Convert a String to a Number](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md), [How to: Convert a byte Array to an int](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md), [How to: Convert Between Hexadecimal Strings and Numeric Types](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md), or <xref:System.Convert>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="35df2-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="35df2-106">Example</span></span>  
 <span data-ttu-id="35df2-107">Este es un ejemplo de un operador de conversión explícita.</span><span class="sxs-lookup"><span data-stu-id="35df2-107">This is an example of an explicit conversion operator.</span></span> <span data-ttu-id="35df2-108">Este operador convierte el tipo <xref:System.Byte> en un tipo de valor denominado `Digit`.</span><span class="sxs-lookup"><span data-stu-id="35df2-108">This operator converts from the type <xref:System.Byte> to a value type called `Digit`.</span></span> <span data-ttu-id="35df2-109">Como no todos los bytes se pueden convertir en valores de tipo digit, la conversión es explícita, lo que significa que se debe usar una conversión, como se muestra en el método `Main`.</span><span class="sxs-lookup"><span data-stu-id="35df2-109">Because not all bytes can be converted to a digit, the conversion is explicit, meaning that a cast must be used, as shown in the `Main` method.</span></span>  
  
 [!code-csharp[csProgGuideStatements#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-conversion-operators_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="35df2-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="35df2-110">Example</span></span>  
 <span data-ttu-id="35df2-111">En este ejemplo se muestra un operador de conversión implícita mediante la definición de un operador de conversión que deshace lo que hizo el ejemplo anterior: convierte una clase de valor denominada `Digit` en el tipo entero <xref:System.Byte>.</span><span class="sxs-lookup"><span data-stu-id="35df2-111">This example demonstrates an implicit conversion operator by defining a conversion operator that undoes what the previous example did: it converts from a value class called `Digit` to the integral <xref:System.Byte> type.</span></span> <span data-ttu-id="35df2-112">Dado que cualquier dígito se puede convertir en <xref:System.Byte>, no hay ninguna necesidad de obligar a los usuarios a que definan explícitamente la conversión.</span><span class="sxs-lookup"><span data-stu-id="35df2-112">Because any digit can be converted to a <xref:System.Byte>, there's no need to force users to be explicit about the conversion.</span></span>  
  
 [!code-csharp[csProgGuideStatements#12](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-conversion-operators_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="35df2-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="35df2-113">See Also</span></span>

- [<span data-ttu-id="35df2-114">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="35df2-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="35df2-115">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="35df2-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="35df2-116">Operadores de conversión</span><span class="sxs-lookup"><span data-stu-id="35df2-116">Conversion Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)  
- [<span data-ttu-id="35df2-117">is</span><span class="sxs-lookup"><span data-stu-id="35df2-117">is</span></span>](../../../csharp/language-reference/keywords/is.md)
