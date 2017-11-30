---
title: Analizar otras cadenas en .NET
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: edd48993f50ec8b91ba7941a682d7de9f22aa12e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="parsing-other-strings-in-net"></a><span data-ttu-id="72e4a-102">Analizar otras cadenas en .NET</span><span class="sxs-lookup"><span data-stu-id="72e4a-102">Parsing Other Strings in .NET</span></span>
<span data-ttu-id="72e4a-103">Además de numéricos y <xref:System.DateTime> cadenas, también puede analizar cadenas que representan los tipos de <xref:System.Char>, <xref:System.Boolean>, y <xref:System.Enum> en tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="72e4a-103">In addition to numeric and <xref:System.DateTime> strings, you can also parse strings that represent the types <xref:System.Char>, <xref:System.Boolean>, and <xref:System.Enum> into data types.</span></span>  
  
## <a name="char"></a><span data-ttu-id="72e4a-104">Char</span><span class="sxs-lookup"><span data-stu-id="72e4a-104">Char</span></span>  
 <span data-ttu-id="72e4a-105">El método de análisis estático asociado con el tipo de datos **Char** es útil para convertir una cadena que contiene un único carácter en su valor Unicode.</span><span class="sxs-lookup"><span data-stu-id="72e4a-105">The static parse method associated with the **Char** data type is useful for converting a string that contains a single character into its Unicode value.</span></span> <span data-ttu-id="72e4a-106">En el ejemplo de código siguiente se analiza una cadena en un carácter Unicode.</span><span class="sxs-lookup"><span data-stu-id="72e4a-106">The following code example parses a string into a Unicode character.</span></span>  
  
 [!code-cpp[Conceptual.String.Parse#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#2)]
 [!code-csharp[Conceptual.String.Parse#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#2)]
 [!code-vb[Conceptual.String.Parse#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#2)]  
  
## <a name="boolean"></a><span data-ttu-id="72e4a-107">Booleano</span><span class="sxs-lookup"><span data-stu-id="72e4a-107">Boolean</span></span>  
 <span data-ttu-id="72e4a-108">El **booleano** tipo de datos contiene un **analizar** método que puede utilizar para convertir una cadena que representa un valor booleano en un real **booleano** tipo.</span><span class="sxs-lookup"><span data-stu-id="72e4a-108">The **Boolean** data type contains a **Parse** method that you can use to convert a string that represents a Boolean value into an actual **Boolean** type.</span></span> <span data-ttu-id="72e4a-109">Este método no distingue mayúsculas de minúsculas y puede analizar correctamente una cadena que contenga "True" o "False".</span><span class="sxs-lookup"><span data-stu-id="72e4a-109">This method is not case-sensitive and can successfully parse a string containing "True" or "False."</span></span> <span data-ttu-id="72e4a-110">El **analizar** método asociado a la **booleano** tipo también puede analizar cadenas que se rodeado por espacios en blanco.</span><span class="sxs-lookup"><span data-stu-id="72e4a-110">The **Parse** method associated with the **Boolean** type can also parse strings that are surrounded by white spaces.</span></span> <span data-ttu-id="72e4a-111">Si se pasa cualquier otra cadena, un <xref:System.FormatException> se produce.</span><span class="sxs-lookup"><span data-stu-id="72e4a-111">If any other string is passed, a <xref:System.FormatException> is thrown.</span></span>  
  
 <span data-ttu-id="72e4a-112">El siguiente ejemplo de código utiliza el **analizar** método para convertir una cadena en un valor booleano.</span><span class="sxs-lookup"><span data-stu-id="72e4a-112">The following code example uses the **Parse** method to convert a string into a Boolean value.</span></span>  
  
 [!code-cpp[Conceptual.String.Parse#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#3)]
 [!code-csharp[Conceptual.String.Parse#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#3)]
 [!code-vb[Conceptual.String.Parse#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#3)]  
  
## <a name="enumeration"></a><span data-ttu-id="72e4a-113">Enumeración</span><span class="sxs-lookup"><span data-stu-id="72e4a-113">Enumeration</span></span>  
 <span data-ttu-id="72e4a-114">Puede usar el método **Parse** estático para inicializar un tipo de enumeración en el valor de una cadena.</span><span class="sxs-lookup"><span data-stu-id="72e4a-114">You can use the static **Parse** method to initialize an enumeration type to the value of a string.</span></span> <span data-ttu-id="72e4a-115">Este método acepta el tipo de enumeración que se va a analizar, la cadena para analizar y una marca booleana opcional que indica si el análisis distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="72e4a-115">This method accepts the enumeration type you are parsing, the string to parse, and an optional Boolean flag indicating whether or not the parse is case-sensitive.</span></span> <span data-ttu-id="72e4a-116">La cadena que se va a analizar puede contener varios valores separados por comas, que pueden ir precedidos o seguidos de uno o varios espacios vacíos (también denominados espacios en blanco).</span><span class="sxs-lookup"><span data-stu-id="72e4a-116">The string you are parsing can contain several values separated by commas, which can be preceded or followed by one or more empty spaces (also called white spaces).</span></span> <span data-ttu-id="72e4a-117">Cuando la cadena contiene varios valores, el valor del objeto devuelto es el valor de todos los valores especificados combinados con una operación OR bit a bit.</span><span class="sxs-lookup"><span data-stu-id="72e4a-117">When the string contains multiple values, the value of the returned object is the value of all specified values combined with a bitwise OR operation.</span></span>  
  
 <span data-ttu-id="72e4a-118">En el ejemplo siguiente se usa el **analizar** método para convertir una representación de cadena en un valor de enumeración.</span><span class="sxs-lookup"><span data-stu-id="72e4a-118">The following example uses the **Parse** method to convert a string representation into an enumeration value.</span></span> <span data-ttu-id="72e4a-119">El <xref:System.DayOfWeek> enumeración se inicializa en **el jueves** de una cadena.</span><span class="sxs-lookup"><span data-stu-id="72e4a-119">The <xref:System.DayOfWeek> enumeration is initialized to **Thursday** from a string.</span></span>  
  
 [!code-cpp[Conceptual.String.Parse#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#4)]
 [!code-csharp[Conceptual.String.Parse#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#4)]
 [!code-vb[Conceptual.String.Parse#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="72e4a-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="72e4a-120">See Also</span></span>  
 [<span data-ttu-id="72e4a-121">Analizar cadenas</span><span class="sxs-lookup"><span data-stu-id="72e4a-121">Parsing Strings</span></span>](../../../docs/standard/base-types/parsing-strings.md)  
 [<span data-ttu-id="72e4a-122">Aplicación de formato a tipos</span><span class="sxs-lookup"><span data-stu-id="72e4a-122">Formatting Types</span></span>](../../../docs/standard/base-types/formatting-types.md)  
 [<span data-ttu-id="72e4a-123">Conversión de tipos en .NET</span><span class="sxs-lookup"><span data-stu-id="72e4a-123">Type Conversion in the .NET</span></span>](../../../docs/standard/base-types/type-conversion.md)
