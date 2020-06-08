---
title: 'Procedimiento Determinar si una cadena representa un valor numérico: Guía de programación de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- numeric strings [C#]
- validating numeric input [C#]
- strings [C#], numeric
ms.assetid: a4e84e10-ea0a-489f-a868-503dded9d85f
ms.openlocfilehash: 37437460ea4c6ca216f2844d63af3688ccc984c6
ms.sourcegitcommit: a241301495a84cc8c64fe972330d16edd619868b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/01/2020
ms.locfileid: "84241726"
---
# <a name="how-to-determine-whether-a-string-represents-a-numeric-value-c-programming-guide"></a><span data-ttu-id="def9a-102">Procedimiento Determinar si una cadena representa un valor numérico (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="def9a-102">How to determine whether a string represents a numeric value (C# Programming Guide)</span></span>
<span data-ttu-id="def9a-103">Para determinar si una cadena es una representación válida de un tipo numérico especificado, use el método estático `TryParse` implementado por todos los tipos numéricos primitivos y también por tipos como <xref:System.DateTime> y <xref:System.Net.IPAddress>.</span><span class="sxs-lookup"><span data-stu-id="def9a-103">To determine whether a string is a valid representation of a specified numeric type, use the static `TryParse` method that is implemented by all primitive numeric types and also by types such as <xref:System.DateTime> and <xref:System.Net.IPAddress>.</span></span> <span data-ttu-id="def9a-104">En el ejemplo siguiente se muestra cómo determinar si "108" es un valor [int](../../language-reference/builtin-types/integral-numeric-types.md) válido.</span><span class="sxs-lookup"><span data-stu-id="def9a-104">The following example shows how to determine whether "108" is a valid [int](../../language-reference/builtin-types/integral-numeric-types.md).</span></span>  
  
```csharp  
int i = 0;
string s = "108";  
bool result = int.TryParse(s, out i); //i now = 108  
```  
  
 <span data-ttu-id="def9a-105">Si la cadena contiene caracteres no numéricos o el valor numérico es demasiado grande o demasiado pequeño para el tipo determinado que ha especificado, `TryParse` devuelve el valor false y establece el parámetro out en cero.</span><span class="sxs-lookup"><span data-stu-id="def9a-105">If the string contains nonnumeric characters or the numeric value is too large or too small for the particular type you have specified, `TryParse` returns false and sets the out parameter to zero.</span></span> <span data-ttu-id="def9a-106">De lo contrario, devuelve el valor true y establece el parámetro out en el valor numérico de la cadena.</span><span class="sxs-lookup"><span data-stu-id="def9a-106">Otherwise, it returns true and sets the out parameter to the numeric value of the string.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="def9a-107">Una cadena puede contener solamente caracteres numéricos pero no ser válida para el tipo cuyo método `TryParse` se está usando.</span><span class="sxs-lookup"><span data-stu-id="def9a-107">A string may contain only numeric characters and still not be valid for the type whose `TryParse` method that you use.</span></span> <span data-ttu-id="def9a-108">Por ejemplo, "256" no es un valor válido para `byte` pero sí para `int`.</span><span class="sxs-lookup"><span data-stu-id="def9a-108">For example, "256" is not a valid value for `byte` but it is valid for `int`.</span></span> <span data-ttu-id="def9a-109">"98,6" no es un valor válido para `int` pero sí para `decimal`.</span><span class="sxs-lookup"><span data-stu-id="def9a-109">"98.6" is not a valid value for `int` but it is a valid `decimal`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="def9a-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="def9a-110">Example</span></span>  
 <span data-ttu-id="def9a-111">En los ejemplos siguientes se muestra cómo usar `TryParse` con representaciones de cadena de los valores `long`, `byte` y `decimal`.</span><span class="sxs-lookup"><span data-stu-id="def9a-111">The following examples show how to use `TryParse` with string representations of `long`, `byte`, and `decimal` values.</span></span>  
  
 [!code-csharp[csProgGuideStrings#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStrings/CS/Strings.cs#14)]  
  
## <a name="robust-programming"></a><span data-ttu-id="def9a-112">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="def9a-112">Robust Programming</span></span>  
 <span data-ttu-id="def9a-113">Los tipos numéricos primitivos también implementan el método estático `Parse`, que produce una excepción si la cadena no es un número válido.</span><span class="sxs-lookup"><span data-stu-id="def9a-113">Primitive numeric types also implement the `Parse` static method, which throws an exception if the string is not a valid number.</span></span> <span data-ttu-id="def9a-114">`TryParse` es, en general, más eficaz porque simplemente devuelve false si el número no es válido.</span><span class="sxs-lookup"><span data-stu-id="def9a-114">`TryParse` is generally more efficient because it just returns false if the number is not valid.</span></span>  
  
## <a name="net-security"></a><span data-ttu-id="def9a-115">Seguridad de .NET</span><span class="sxs-lookup"><span data-stu-id="def9a-115">.NET Security</span></span>  
 <span data-ttu-id="def9a-116">Use siempre los métodos `TryParse` o `Parse` para validar los datos proporcionados por el usuario en controles como cuadros de texto y cuadros combinados.</span><span class="sxs-lookup"><span data-stu-id="def9a-116">Always use the `TryParse` or `Parse` methods to validate user input from controls such as text boxes and combo boxes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="def9a-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="def9a-117">See also</span></span>

- [<span data-ttu-id="def9a-118">Procedimiento Convertir una matriz de bytes en un valor int</span><span class="sxs-lookup"><span data-stu-id="def9a-118">How to convert a byte array to an int</span></span>](../types/how-to-convert-a-byte-array-to-an-int.md)
- [<span data-ttu-id="def9a-119">Procedimiento Convertir una cadena en un número</span><span class="sxs-lookup"><span data-stu-id="def9a-119">How to convert a string to a number</span></span>](../types/how-to-convert-a-string-to-a-number.md)
- [<span data-ttu-id="def9a-120">Procedimiento Convertir cadenas hexadecimales en tipos numéricos</span><span class="sxs-lookup"><span data-stu-id="def9a-120">How to convert between hexadecimal strings and numeric types</span></span>](../types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md)
- [<span data-ttu-id="def9a-121">Análisis de cadenas numéricas</span><span class="sxs-lookup"><span data-stu-id="def9a-121">Parsing Numeric Strings</span></span>](../../../standard/base-types/parsing-numeric.md)
- [<span data-ttu-id="def9a-122">Aplicación de formato a tipos</span><span class="sxs-lookup"><span data-stu-id="def9a-122">Formatting Types</span></span>](../../../standard/base-types/formatting-types.md)
