---
title: 'Ejemplo de expresiones regulares: Cambiar formatos de fecha'
ms.date: 06/30/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- searching with regular expressions, examples
- parsing text with regular expressions, examples
- regular expressions, examples
- .NET regular expressions, examples
- regular expressions [.NET], examples
- pattern-matching with regular expressions, examples
ms.assetid: 5fcc75a5-09d7-45ae-a4c0-9ad6085ac83d
ms.openlocfilehash: b5eca8c294349fada9cfb1cb3ed8e2012edd8bda
ms.sourcegitcommit: 4a938327bad8b2e20cabd0f46a9dc50882596f13
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2020
ms.locfileid: "92889418"
---
# <a name="regular-expression-example-changing-date-formats"></a><span data-ttu-id="9adf8-102">Ejemplo de expresiones regulares: Cambiar formatos de fecha</span><span class="sxs-lookup"><span data-stu-id="9adf8-102">Regular Expression Example: Changing Date Formats</span></span>
<span data-ttu-id="9adf8-103">En el siguiente ejemplo de código, se usa el método <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType> para reemplazar las fechas con el formato *mm*/*dd*/*aa* con fechas que tienen el formato *dd*-*mm*-*aa* .</span><span class="sxs-lookup"><span data-stu-id="9adf8-103">The following code example uses the <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType> method to replace dates that have the form *mm*/*dd*/*yy* with dates that have the form *dd*-*mm*-*yy* .</span></span>  

[!INCLUDE [regex](../../../includes/regex.md)]

## <a name="example"></a><span data-ttu-id="9adf8-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9adf8-104">Example</span></span>  
 [!code-csharp[RegularExpressions.Examples.ChangeDateFormats#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/cs/Example_ChangeDateFormats1.cs#1)]
 [!code-vb[RegularExpressions.Examples.ChangeDateFormats#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/vb/Example_ChangeDateFormats1.vb#1)]  
  
 <span data-ttu-id="9adf8-105">El código siguiente muestra cómo se puede llamar al método `MDYToDMY` en una aplicación.</span><span class="sxs-lookup"><span data-stu-id="9adf8-105">The following code shows how the `MDYToDMY` method can be called in an application.</span></span>  
  
 [!code-csharp[RegularExpressions.Examples.ChangeDateFormats#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/cs/Example_ChangeDateFormats1.cs#2)]
 [!code-vb[RegularExpressions.Examples.ChangeDateFormats#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/vb/Example_ChangeDateFormats1.vb#2)]  
  
## <a name="comments"></a><span data-ttu-id="9adf8-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9adf8-106">Comments</span></span>  
 <span data-ttu-id="9adf8-107">El patrón de la expresión regular `\b(?<month>\d{1,2})/(?<day>\d{1,2})/(?<year>\d{2,4})\b` se interpreta como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="9adf8-107">The regular expression pattern  `\b(?<month>\d{1,2})/(?<day>\d{1,2})/(?<year>\d{2,4})\b` is interpreted as shown in the following table.</span></span>  
  
|<span data-ttu-id="9adf8-108">Modelo</span><span class="sxs-lookup"><span data-stu-id="9adf8-108">Pattern</span></span>|<span data-ttu-id="9adf8-109">Description</span><span class="sxs-lookup"><span data-stu-id="9adf8-109">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="9adf8-110">Iniciar la búsqueda de coincidencias en un límite de palabras.</span><span class="sxs-lookup"><span data-stu-id="9adf8-110">Begin the match at a word boundary.</span></span>|  
|`(?<month>\d{1,2})`|<span data-ttu-id="9adf8-111">Buscar coincidencias con uno o dos dígitos decimales.</span><span class="sxs-lookup"><span data-stu-id="9adf8-111">Match one or two decimal digits.</span></span> <span data-ttu-id="9adf8-112">Es el grupo `month` capturado.</span><span class="sxs-lookup"><span data-stu-id="9adf8-112">This is the `month` captured group.</span></span>|  
|`/`|<span data-ttu-id="9adf8-113">Buscar coincidencias con la barra diagonal.</span><span class="sxs-lookup"><span data-stu-id="9adf8-113">Match the slash mark.</span></span>|  
|`(?<day>\d{1,2})`|<span data-ttu-id="9adf8-114">Buscar coincidencias con uno o dos dígitos decimales.</span><span class="sxs-lookup"><span data-stu-id="9adf8-114">Match one or two decimal digits.</span></span> <span data-ttu-id="9adf8-115">Es el grupo `day` capturado.</span><span class="sxs-lookup"><span data-stu-id="9adf8-115">This is the `day` captured group.</span></span>|  
|`/`|<span data-ttu-id="9adf8-116">Buscar coincidencias con la barra diagonal.</span><span class="sxs-lookup"><span data-stu-id="9adf8-116">Match the slash mark.</span></span>|  
|`(?<year>\d{2,4})`|<span data-ttu-id="9adf8-117">Buscar coincidencias de dos a cuatro dígitos decimales.</span><span class="sxs-lookup"><span data-stu-id="9adf8-117">Match from two to four decimal digits.</span></span> <span data-ttu-id="9adf8-118">Es el grupo `year` capturado.</span><span class="sxs-lookup"><span data-stu-id="9adf8-118">This is the `year` captured group.</span></span>|  
|`\b`|<span data-ttu-id="9adf8-119">Finalizar la búsqueda de coincidencias en un límite de palabras.</span><span class="sxs-lookup"><span data-stu-id="9adf8-119">End the match at a word boundary.</span></span>|  
  
 <span data-ttu-id="9adf8-120">El patrón `${day}-${month}-${year}` define la cadena de reemplazo como se muestra en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="9adf8-120">The pattern `${day}-${month}-${year}` defines the replacement string as shown in the following table.</span></span>  
  
|<span data-ttu-id="9adf8-121">Modelo</span><span class="sxs-lookup"><span data-stu-id="9adf8-121">Pattern</span></span>|<span data-ttu-id="9adf8-122">Description</span><span class="sxs-lookup"><span data-stu-id="9adf8-122">Description</span></span>|  
|-------------|-----------------|  
|`$(day)`|<span data-ttu-id="9adf8-123">Agregar la cadena capturada por el grupo de captura `day`.</span><span class="sxs-lookup"><span data-stu-id="9adf8-123">Add the string captured by the `day` capturing group.</span></span>|  
|`-`|<span data-ttu-id="9adf8-124">Agregar un guión.</span><span class="sxs-lookup"><span data-stu-id="9adf8-124">Add a hyphen.</span></span>|  
|`$(month)`|<span data-ttu-id="9adf8-125">Agregar la cadena capturada por el grupo de captura `month`.</span><span class="sxs-lookup"><span data-stu-id="9adf8-125">Add the string captured by the `month` capturing group.</span></span>|  
|`-`|<span data-ttu-id="9adf8-126">Agregar un guión.</span><span class="sxs-lookup"><span data-stu-id="9adf8-126">Add a hyphen.</span></span>|  
|`$(year)`|<span data-ttu-id="9adf8-127">Agregar la cadena capturada por el grupo de captura `year`.</span><span class="sxs-lookup"><span data-stu-id="9adf8-127">Add the string captured by the `year` capturing group.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9adf8-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="9adf8-128">See also</span></span>

- [<span data-ttu-id="9adf8-129">Expresiones regulares de .NET</span><span class="sxs-lookup"><span data-stu-id="9adf8-129">.NET Regular Expressions</span></span>](regular-expressions.md)
