---
title: 'Cómo: Extraer un protocolo y un número de puerto de una dirección URL'
ms.date: 06/30/2020
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
ms.assetid: ab7f62b3-6d2c-4efb-8ac6-28600df5fd5c
ms.openlocfilehash: e6cf86d08ed971876f76413e0145c62b73d0d4a5
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94825096"
---
# <a name="how-to-extract-a-protocol-and-port-number-from-a-url"></a><span data-ttu-id="cb508-102">Cómo: Extraer un protocolo y un número de puerto de una dirección URL</span><span class="sxs-lookup"><span data-stu-id="cb508-102">How to: Extract a Protocol and Port Number from a URL</span></span>
<span data-ttu-id="cb508-103">En los siguientes ejemplos se extrae un protocolo y un número de puerto de una dirección URL.</span><span class="sxs-lookup"><span data-stu-id="cb508-103">The following example extracts a protocol and port number from a URL.</span></span>  

[!INCLUDE [regex](../../../includes/regex.md)]

## <a name="example"></a><span data-ttu-id="cb508-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cb508-104">Example</span></span>  
 <span data-ttu-id="cb508-105">El ejemplo usa el método <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> para devolver el protocolo seguido de dos puntos y del número de puerto.</span><span class="sxs-lookup"><span data-stu-id="cb508-105">The example uses the <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> method to return the protocol followed by a colon followed by the port number.</span></span>  
  
 [!code-csharp[RegularExpressions.Examples.Protocol#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/cs/Example.cs#1)]
 [!code-vb[RegularExpressions.Examples.Protocol#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/vb/Example.vb#1)]  
  
 <span data-ttu-id="cb508-106">El patrón de la expresión regular `^(?<proto>\w+)://[^/]+?(?<port>:\d+)?/` puede interpretarse como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="cb508-106">The regular expression pattern `^(?<proto>\w+)://[^/]+?(?<port>:\d+)?/` can be interpreted as shown in the following table.</span></span>  
  
|<span data-ttu-id="cb508-107">Modelo</span><span class="sxs-lookup"><span data-stu-id="cb508-107">Pattern</span></span>|<span data-ttu-id="cb508-108">Description</span><span class="sxs-lookup"><span data-stu-id="cb508-108">Description</span></span>|  
|-------------|-----------------|  
|`^`|<span data-ttu-id="cb508-109">Comenzar la búsqueda de coincidencia al principio de la cadena.</span><span class="sxs-lookup"><span data-stu-id="cb508-109">Begin the match at the start of the string.</span></span>|  
|`(?<proto>\w+)`|<span data-ttu-id="cb508-110">Buscar coincidencias con uno o más caracteres alfabéticos.</span><span class="sxs-lookup"><span data-stu-id="cb508-110">Match one or more word characters.</span></span> <span data-ttu-id="cb508-111">Asigne a este grupo el nombre `proto`.</span><span class="sxs-lookup"><span data-stu-id="cb508-111">Name this group `proto`.</span></span>|  
|`://`|<span data-ttu-id="cb508-112">Buscar coincidencias con un signo de dos puntos seguido por dos barras diagonales.</span><span class="sxs-lookup"><span data-stu-id="cb508-112">Match a colon followed by two slash marks.</span></span>|  
|`[^/]+?`|<span data-ttu-id="cb508-113">Buscar coincidencias con una o más apariciones (pero el menor número posible) de cualquier carácter que no sea una barra diagonal.</span><span class="sxs-lookup"><span data-stu-id="cb508-113">Match one or more occurrences (but as few as possible) of any character other than a slash mark.</span></span>|  
|`(?<port>:\d+)?`|<span data-ttu-id="cb508-114">Buscar una coincidencia con cero o una aparición de una coma seguida de uno o más caracteres decimales.</span><span class="sxs-lookup"><span data-stu-id="cb508-114">Match zero or one occurrence of a colon followed by one or more digit characters.</span></span> <span data-ttu-id="cb508-115">Asigne a este grupo el nombre `port`.</span><span class="sxs-lookup"><span data-stu-id="cb508-115">Name this group `port`.</span></span>|  
|`/`|<span data-ttu-id="cb508-116">Buscar una coincidencia con una barra diagonal.</span><span class="sxs-lookup"><span data-stu-id="cb508-116">Match a slash mark.</span></span>|  
  
 <span data-ttu-id="cb508-117">El método <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> expande la secuencia de reemplazo `${proto}${port}`, que concatena el valor de los dos grupos con nombre capturados en el patrón de expresión regular.</span><span class="sxs-lookup"><span data-stu-id="cb508-117">The <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> method expands the `${proto}${port}` replacement sequence, which concatenates the value of the two named groups captured in the regular expression pattern.</span></span> <span data-ttu-id="cb508-118">Resulta cómodo concatenar explícitamente las cadenas recuperadas del objeto de la colección devueltas por la propiedad <xref:System.Text.RegularExpressions.Match.Groups%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="cb508-118">It is a convenient alternative to explicitly concatenating the strings retrieved from the collection object returned by the <xref:System.Text.RegularExpressions.Match.Groups%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="cb508-119">El ejemplo usa el método <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> con dos sustituciones, `${proto}` y `${port}`, para incluir los grupos capturados en la cadena de salida.</span><span class="sxs-lookup"><span data-stu-id="cb508-119">The example uses the <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> method with two substitutions, `${proto}` and `${port}`, to include the captured groups in the output string.</span></span> <span data-ttu-id="cb508-120">En su lugar, puede recuperar los grupos capturados del objeto de coincidencia <xref:System.Text.RegularExpressions.GroupCollection>, como se muestra en el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="cb508-120">You can retrieve the captured groups from the match's <xref:System.Text.RegularExpressions.GroupCollection> object instead, as the following code shows.</span></span>  
  
 [!code-csharp[RegularExpressions.Examples.Protocol#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/cs/example2.cs#2)]
 [!code-vb[RegularExpressions.Examples.Protocol#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/vb/example2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="cb508-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="cb508-121">See also</span></span>

- [<span data-ttu-id="cb508-122">Expresiones regulares de .NET</span><span class="sxs-lookup"><span data-stu-id="cb508-122">.NET Regular Expressions</span></span>](regular-expressions.md)
