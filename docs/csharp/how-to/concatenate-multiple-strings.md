---
title: Procedimiento para concatenar varias cadenas (Guía de C#)
description: Hay varias maneras de concatenar cadenas en C#. Obtenga información sobre las opciones y las razones para las diferentes opciones.
ms.date: 02/20/2018
helpviewer_keywords:
- joining strings [C#]
- concatenating strings [C#]
- strings [C#], concatenation
ms.assetid: 8e16736f-4096-4f3f-be0f-9d4c3ff63520
ms.openlocfilehash: 9a0640a7ce73fa8454442cd301157bf5c265f9de
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713899"
---
# <a name="how-to-concatenate-multiple-strings-c-guide"></a><span data-ttu-id="46083-104">Procedimiento para concatenar varias cadenas (Guía de C#)</span><span class="sxs-lookup"><span data-stu-id="46083-104">How to concatenate multiple strings (C# Guide)</span></span>

<span data-ttu-id="46083-105">*Concatenación* es el proceso de anexar una cadena al final de otra cadena.</span><span class="sxs-lookup"><span data-stu-id="46083-105">*Concatenation* is the process of appending one string to the end of another string.</span></span> <span data-ttu-id="46083-106">Las cadenas se concatenan con el operador `+`.</span><span class="sxs-lookup"><span data-stu-id="46083-106">You concatenate strings by using the `+` operator.</span></span> <span data-ttu-id="46083-107">En el caso de los literales y las constantes de cadena, la concatenación se produce en tiempo de compilación, y no en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="46083-107">For string literals and string constants, concatenation occurs at compile time; no run-time concatenation occurs.</span></span> <span data-ttu-id="46083-108">En cambio, para las variables de cadena, la concatenación solo se produce en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="46083-108">For string variables, concatenation occurs only at run time.</span></span>

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

<span data-ttu-id="46083-109">En el ejemplo siguiente se usa la concatenación para dividir un literal de cadena larga en cadenas más pequeñas para mejorar la legibilidad del código fuente.</span><span class="sxs-lookup"><span data-stu-id="46083-109">The following example uses concatenation to split a long string literal into smaller strings in order to improve readability in the source code.</span></span> <span data-ttu-id="46083-110">Estas partes se concatenan en una sola cadena en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="46083-110">These parts are concatenated into a single string at compile time.</span></span> <span data-ttu-id="46083-111">No existe ningún costo de rendimiento en tiempo de ejecución independientemente del número de cadenas de que se trate.</span><span class="sxs-lookup"><span data-stu-id="46083-111">There is no run-time performance cost regardless of the number of strings involved.</span></span>  
  
 [!code-csharp-interactive[Combining strings at compile time](../../../samples/snippets/csharp/how-to/strings/Concatenate.cs#1)]  

<span data-ttu-id="46083-112">Para concatenar variables de cadena, puede usar los operadores `+` o `+=`, la [interpolación de cadena](../language-reference/tokens/interpolated.md) o los métodos <xref:System.String.Format%2A?displayProperty=nameWithType>, <xref:System.String.Concat%2A?displayProperty=nameWithType>, <xref:System.String.Join%2A?displayProperty=nameWithType> o <xref:System.Text.StringBuilder.Append%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="46083-112">To concatenate string variables, you can use the `+` or `+=` operators, [string interpolation](../language-reference/tokens/interpolated.md) or the <xref:System.String.Format%2A?displayProperty=nameWithType>, <xref:System.String.Concat%2A?displayProperty=nameWithType>, <xref:System.String.Join%2A?displayProperty=nameWithType> or <xref:System.Text.StringBuilder.Append%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="46083-113">El operador `+` es sencillo de usar y genera un código intuitivo.</span><span class="sxs-lookup"><span data-stu-id="46083-113">The `+` operator is easy to use and makes for intuitive code.</span></span> <span data-ttu-id="46083-114">Aunque use varios operadores `+` en una instrucción, el contenido de la cadena se copiará solo una vez.</span><span class="sxs-lookup"><span data-stu-id="46083-114">Even if you use several `+` operators in one statement, the string content is copied only once.</span></span> <span data-ttu-id="46083-115">En el código siguiente se muestran ejemplos del uso de los operadores `+` y `+=` para concatenar cadenas:</span><span class="sxs-lookup"><span data-stu-id="46083-115">The following code shows examples of using the `+` and `+=` operators to concatenate strings:</span></span>

[!code-csharp-interactive[combining strings using +](../../../samples/snippets/csharp/how-to/strings/Concatenate.cs#2)]  

<span data-ttu-id="46083-116">En algunas expresiones, es más fácil concatenar cadenas mediante la interpolación de cadena, como se muestra en este código:</span><span class="sxs-lookup"><span data-stu-id="46083-116">In some expressions, it's easier to concatenate strings using string interpolation, as the following code shows:</span></span>
  
[!code-csharp-interactive[building strings using string interpolation](../../../samples/snippets/csharp/how-to/strings/Concatenate.cs#3)]  
  
> [!NOTE]
> <span data-ttu-id="46083-117">En operaciones de concatenación de cadenas, el compilador de C# trata una cadena NULL igual que una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="46083-117">In string concatenation operations, the C# compiler treats a null string the same as an empty string.</span></span>

<span data-ttu-id="46083-118">Otro método para concatenar cadenas es <xref:System.String.Format%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="46083-118">Other method to concatenate strings is <xref:System.String.Format%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="46083-119">Este método funciona bien para compilar una cadena a partir de un número reducido de cadenas de componente.</span><span class="sxs-lookup"><span data-stu-id="46083-119">This method works well when you are building a string from a small number of component strings.</span></span>

<span data-ttu-id="46083-120">En otros casos, puede combinar cadenas en un bucle, donde no sabe cuántas cadenas de origen se combinan, y el número real de cadenas de origen puede ser bastante elevado.</span><span class="sxs-lookup"><span data-stu-id="46083-120">In other cases you may be combining strings in a loop, where you don't know how many source strings you are combining, and the actual number of source strings may be quite large.</span></span> <span data-ttu-id="46083-121">La clase <xref:System.Text.StringBuilder> se diseñó para estos escenarios.</span><span class="sxs-lookup"><span data-stu-id="46083-121">The <xref:System.Text.StringBuilder> class was designed for these scenarios.</span></span> <span data-ttu-id="46083-122">El código siguiente usa el método <xref:System.Text.StringBuilder.Append%2A> de la clase <xref:System.Text.StringBuilder> para concatenar cadenas.</span><span class="sxs-lookup"><span data-stu-id="46083-122">The following code uses the <xref:System.Text.StringBuilder.Append%2A> method of the <xref:System.Text.StringBuilder> class to concatenate strings.</span></span>  
  
[!code-csharp-interactive[string concatenation using string builder](../../../samples/snippets/csharp/how-to/strings/Concatenate.cs#4)]  

<span data-ttu-id="46083-123">Puede obtener más información sobre las [razones para elegir la concatenación de cadenas o sobre la clase `StringBuilder`](xref:System.Text.StringBuilder#StringAndSB).</span><span class="sxs-lookup"><span data-stu-id="46083-123">You can read more about the [reasons to choose string concatenation or the `StringBuilder` class](xref:System.Text.StringBuilder#StringAndSB).</span></span>

<span data-ttu-id="46083-124">Otra opción para combinar cadenas a partir de una colección consiste en usar el método <xref:System.String.Concat%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="46083-124">Another option to join strings from a collection is to use <xref:System.String.Concat%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="46083-125">Use el método <xref:System.String.Join%2A?displayProperty=nameWithType> si las cadenas de origen se deben separar con un delimitador.</span><span class="sxs-lookup"><span data-stu-id="46083-125">Use <xref:System.String.Join%2A?displayProperty=nameWithType> method if source strings should be separated by a delimeter.</span></span> <span data-ttu-id="46083-126">El código siguiente combina una matriz de palabras usando ambos métodos:</span><span class="sxs-lookup"><span data-stu-id="46083-126">The following code combines an array of words using both methods:</span></span>

[!code-csharp-interactive[concatenation of string collection](../../../samples/snippets/csharp/how-to/strings/Concatenate.cs#5)]

<span data-ttu-id="46083-127">Por último, puede usar [LINQ](../programming-guide/concepts/linq/index.md) y el método <xref:System.Linq.Enumerable.Aggregate%2A?displayProperty=nameWithType> para combinar cadenas a partir de una colección.</span><span class="sxs-lookup"><span data-stu-id="46083-127">At last, you can use [LINQ](../programming-guide/concepts/linq/index.md) and the <xref:System.Linq.Enumerable.Aggregate%2A?displayProperty=nameWithType> method to join strings from a collection.</span></span> <span data-ttu-id="46083-128">Este método combina las cadenas de origen mediante una expresión lambda.</span><span class="sxs-lookup"><span data-stu-id="46083-128">This method combines the source strings using a lambda expression.</span></span> <span data-ttu-id="46083-129">La expresión lambda realiza el trabajo de agregar cada cadena a la acumulación existente.</span><span class="sxs-lookup"><span data-stu-id="46083-129">The lambda expression does the work to add each string to the existing accumulation.</span></span> <span data-ttu-id="46083-130">En el ejemplo siguiente se combina una matriz de palabras mediante la adición de un espacio entre cada palabra de la matriz:</span><span class="sxs-lookup"><span data-stu-id="46083-130">The following example combines an array of words by adding a space between each word in the array:</span></span>

[!code-csharp-interactive[string concatenation using LINQ expressions](../../../samples/snippets/csharp/how-to/strings/Concatenate.cs#6)]  

<span data-ttu-id="46083-131">Eche un vistazo al código de nuestro [repositorio de GitHub](https://github.com/dotnet/samples/tree/master/snippets/csharp/how-to/strings) y pruebe estos ejemplos.</span><span class="sxs-lookup"><span data-stu-id="46083-131">You can try these samples by looking at the code in our [GitHub repository](https://github.com/dotnet/samples/tree/master/snippets/csharp/how-to/strings).</span></span> <span data-ttu-id="46083-132">O bien, puede descargar los ejemplos [como un archivo ZIP](https://github.com/dotnet/samples/raw/master/snippets/csharp/how-to/strings.zip).</span><span class="sxs-lookup"><span data-stu-id="46083-132">Or you can download the samples [as a zip file](https://github.com/dotnet/samples/raw/master/snippets/csharp/how-to/strings.zip).</span></span>

## <a name="see-also"></a><span data-ttu-id="46083-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="46083-133">See also</span></span>

- <xref:System.String>
- <xref:System.Text.StringBuilder>
- [<span data-ttu-id="46083-134">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="46083-134">C# Programming Guide</span></span>](../programming-guide/index.md)
- [<span data-ttu-id="46083-135">Cadenas</span><span class="sxs-lookup"><span data-stu-id="46083-135">Strings</span></span>](../programming-guide/strings/index.md)
