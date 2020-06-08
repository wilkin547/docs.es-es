---
title: Analizar otras cadenas en .NET
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Char data type, parsing strings
- enumerations [.NET Framework], parsing strings
- base types, parsing strings
- parsing strings, other strings
- Boolean data type, parsing strings
ms.assetid: d139bc00-3c4e-4d78-ac9a-5c951b258d28
ms.openlocfilehash: a3503e0e499c6010fcc3d8669fa5c1eaf2dbf570
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84277549"
---
# <a name="parsing-other-strings-in-net"></a><span data-ttu-id="fdc64-102">Analizar otras cadenas en .NET</span><span class="sxs-lookup"><span data-stu-id="fdc64-102">Parsing Other Strings in .NET</span></span>
<span data-ttu-id="fdc64-103">Además de cadenas numéricas y <xref:System.DateTime>, puede analizar cadenas que representan los tipos <xref:System.Char>, <xref:System.Boolean> y <xref:System.Enum> en tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="fdc64-103">In addition to numeric and <xref:System.DateTime> strings, you can also parse strings that represent the types <xref:System.Char>, <xref:System.Boolean>, and <xref:System.Enum> into data types.</span></span>  
  
## <a name="char"></a><span data-ttu-id="fdc64-104">Char</span><span class="sxs-lookup"><span data-stu-id="fdc64-104">Char</span></span>  
 <span data-ttu-id="fdc64-105">El método de análisis estático asociado con el tipo de datos **Char** es útil para convertir una cadena que contiene un único carácter en su valor Unicode.</span><span class="sxs-lookup"><span data-stu-id="fdc64-105">The static parse method associated with the **Char** data type is useful for converting a string that contains a single character into its Unicode value.</span></span> <span data-ttu-id="fdc64-106">En el ejemplo de código siguiente se analiza una cadena en un carácter Unicode.</span><span class="sxs-lookup"><span data-stu-id="fdc64-106">The following code example parses a string into a Unicode character.</span></span>  
  
 [!code-cpp[Conceptual.String.Parse#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#2)]
 [!code-csharp[Conceptual.String.Parse#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#2)]
 [!code-vb[Conceptual.String.Parse#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#2)]  
  
## <a name="boolean"></a><span data-ttu-id="fdc64-107">Booleano</span><span class="sxs-lookup"><span data-stu-id="fdc64-107">Boolean</span></span>  
 <span data-ttu-id="fdc64-108">El tipo de datos **Boolean** contiene un método **Parse** que se puede usar para convertir una cadena que representa un valor Boolean en un tipo **Boolean** real.</span><span class="sxs-lookup"><span data-stu-id="fdc64-108">The **Boolean** data type contains a **Parse** method that you can use to convert a string that represents a Boolean value into an actual **Boolean** type.</span></span> <span data-ttu-id="fdc64-109">Este método no distingue mayúsculas de minúsculas y puede analizar correctamente una cadena que contenga "True" o "False".</span><span class="sxs-lookup"><span data-stu-id="fdc64-109">This method is not case-sensitive and can successfully parse a string containing "True" or "False."</span></span> <span data-ttu-id="fdc64-110">El método **Parse** asociado al tipo **Boolean** también puede analizar cadenas que estén rodeadas por espacios en blanco.</span><span class="sxs-lookup"><span data-stu-id="fdc64-110">The **Parse** method associated with the **Boolean** type can also parse strings that are surrounded by white spaces.</span></span> <span data-ttu-id="fdc64-111">Si se pasa otra cadena, se produce una excepción <xref:System.FormatException>.</span><span class="sxs-lookup"><span data-stu-id="fdc64-111">If any other string is passed, a <xref:System.FormatException> is thrown.</span></span>  
  
 <span data-ttu-id="fdc64-112">En el ejemplo de código siguiente se usa el método **Parse** para convertir una cadena en un valor Boolean.</span><span class="sxs-lookup"><span data-stu-id="fdc64-112">The following code example uses the **Parse** method to convert a string into a Boolean value.</span></span>  
  
 [!code-cpp[Conceptual.String.Parse#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#3)]
 [!code-csharp[Conceptual.String.Parse#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#3)]
 [!code-vb[Conceptual.String.Parse#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#3)]  
  
## <a name="enumeration"></a><span data-ttu-id="fdc64-113">Enumeración</span><span class="sxs-lookup"><span data-stu-id="fdc64-113">Enumeration</span></span>  
 <span data-ttu-id="fdc64-114">Puede usar el método **Parse** estático para inicializar un tipo de enumeración en el valor de una cadena.</span><span class="sxs-lookup"><span data-stu-id="fdc64-114">You can use the static **Parse** method to initialize an enumeration type to the value of a string.</span></span> <span data-ttu-id="fdc64-115">Este método acepta el tipo de enumeración que se está analizando, la cadena que se va a analizar y una marca Boolean opcional que indica si el análisis distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="fdc64-115">This method accepts the enumeration type you are parsing, the string to parse, and an optional Boolean flag indicating whether or not the parse is case-sensitive.</span></span> <span data-ttu-id="fdc64-116">La cadena que se va a analizar puede contener varios valores separados por comas, que pueden ir precedidos o seguidos de uno o varios espacios vacíos (también denominados espacios en blanco).</span><span class="sxs-lookup"><span data-stu-id="fdc64-116">The string you are parsing can contain several values separated by commas, which can be preceded or followed by one or more empty spaces (also called white spaces).</span></span> <span data-ttu-id="fdc64-117">Cuando la cadena contiene varios valores, el valor del objeto devuelto es el valor de todos los valores especificados combinados con una operación OR bit a bit.</span><span class="sxs-lookup"><span data-stu-id="fdc64-117">When the string contains multiple values, the value of the returned object is the value of all specified values combined with a bitwise OR operation.</span></span>  
  
 <span data-ttu-id="fdc64-118">En el ejemplo siguiente se usa el método **Parse** para convertir una representación de cadena en un valor de enumeración.</span><span class="sxs-lookup"><span data-stu-id="fdc64-118">The following example uses the **Parse** method to convert a string representation into an enumeration value.</span></span> <span data-ttu-id="fdc64-119">La enumeración <xref:System.DayOfWeek> se inicializa en **Thursday** desde una cadena.</span><span class="sxs-lookup"><span data-stu-id="fdc64-119">The <xref:System.DayOfWeek> enumeration is initialized to **Thursday** from a string.</span></span>  
  
 [!code-cpp[Conceptual.String.Parse#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#4)]
 [!code-csharp[Conceptual.String.Parse#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#4)]
 [!code-vb[Conceptual.String.Parse#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="fdc64-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="fdc64-120">See also</span></span>

- [<span data-ttu-id="fdc64-121">Analizar cadenas</span><span class="sxs-lookup"><span data-stu-id="fdc64-121">Parsing Strings</span></span>](parsing-strings.md)
- [<span data-ttu-id="fdc64-122">Aplicación de formato a tipos</span><span class="sxs-lookup"><span data-stu-id="fdc64-122">Formatting Types</span></span>](formatting-types.md)
- [<span data-ttu-id="fdc64-123">Conversión de tipos en .NET</span><span class="sxs-lookup"><span data-stu-id="fdc64-123">Type Conversion in the .NET</span></span>](type-conversion.md)
