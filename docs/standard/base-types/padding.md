---
title: Relleno de cadenas en .NET
ms.date: 03/15/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- strings [.NET Framework], padding
- white space
- PadRight method
- PadLeft method
- padding strings
ms.assetid: 84a9f142-3244-4c90-ba02-21af9bbaff71
ms.openlocfilehash: 83d4b348c4de537d9a71363d34898a50a6a74cb3
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290401"
---
# <a name="padding-strings-in-net"></a><span data-ttu-id="3f2be-102">Relleno de cadenas en .NET</span><span class="sxs-lookup"><span data-stu-id="3f2be-102">Padding Strings in .NET</span></span>

<span data-ttu-id="3f2be-103">Use uno de los siguientes métodos <xref:System.String> para crear una cadena que conste de una cadena original rellenada con caracteres iniciales o finales hasta una longitud total especificada.</span><span class="sxs-lookup"><span data-stu-id="3f2be-103">Use one of the following <xref:System.String> methods to create a new string that consists of an original string that is padded with leading or trailing characters to a specified total length.</span></span> <span data-ttu-id="3f2be-104">El carácter de relleno puede ser un espacio o un carácter especificado.</span><span class="sxs-lookup"><span data-stu-id="3f2be-104">The padding character can be a space or a specified character.</span></span> <span data-ttu-id="3f2be-105">La cadena resultante aparece alineada a la derecha o bien a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="3f2be-105">The resulting string appears to be either right-aligned or left-aligned.</span></span> <span data-ttu-id="3f2be-106">Si la longitud de la cadena original ya es igual o mayor que la longitud total deseada, los métodos de relleno devuelven la cadena original sin modificarla. Para obtener más información, vea las secciones **Devoluciones** de las dos sobrecargas de los métodos <xref:System.String.PadLeft%2A?displayProperty=nameWithType> y <xref:System.String.PadRight%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3f2be-106">If the original string's length is already equal to or greater than the desired total length, the padding methods return the original string unchanged; for more information, see the **Returns** sections of the two overloads of the <xref:System.String.PadLeft%2A?displayProperty=nameWithType> and <xref:System.String.PadRight%2A?displayProperty=nameWithType> methods.</span></span>
  
|<span data-ttu-id="3f2be-107">Nombre del método</span><span class="sxs-lookup"><span data-stu-id="3f2be-107">Method name</span></span>|<span data-ttu-id="3f2be-108">Usar</span><span class="sxs-lookup"><span data-stu-id="3f2be-108">Use</span></span>|  
|-----------------|---------|  
|<xref:System.String.PadLeft%2A?displayProperty=nameWithType>|<span data-ttu-id="3f2be-109">Rellena una cadena con caracteres iniciales hasta una longitud total especificada.</span><span class="sxs-lookup"><span data-stu-id="3f2be-109">Pads a string with leading characters to a specified total length.</span></span>|  
|<xref:System.String.PadRight%2A?displayProperty=nameWithType>|<span data-ttu-id="3f2be-110">Rellena una cadena con caracteres finales hasta una longitud total especificada.</span><span class="sxs-lookup"><span data-stu-id="3f2be-110">Pads a string with trailing characters to a specified total length.</span></span>|  
  
## <a name="padleft"></a><span data-ttu-id="3f2be-111">PadLeft</span><span class="sxs-lookup"><span data-stu-id="3f2be-111">PadLeft</span></span>  
 <span data-ttu-id="3f2be-112">El método <xref:System.String.PadLeft%2A?displayProperty=nameWithType> crea una cadena mediante la concatenación de suficientes caracteres de relleno iniciales con una cadena original para alcanzar la longitud total especificada.</span><span class="sxs-lookup"><span data-stu-id="3f2be-112">The <xref:System.String.PadLeft%2A?displayProperty=nameWithType> method creates a new string by concatenating enough leading pad characters to an original string to achieve a specified total length.</span></span> <span data-ttu-id="3f2be-113">El método <xref:System.String.PadLeft%28System.Int32%29?displayProperty=nameWithType> usa el espacio en blanco como carácter de relleno y el método <xref:System.String.PadLeft%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> le permite especificar su propio carácter de relleno.</span><span class="sxs-lookup"><span data-stu-id="3f2be-113">The <xref:System.String.PadLeft%28System.Int32%29?displayProperty=nameWithType> method uses white space as the padding character and the <xref:System.String.PadLeft%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> method enables you to specify your own padding character.</span></span>  
  
 <span data-ttu-id="3f2be-114">En el ejemplo de código siguiente se usa el método <xref:System.String.PadLeft%2A> para crear una cadena con una longitud de veinte caracteres.</span><span class="sxs-lookup"><span data-stu-id="3f2be-114">The following code example uses the <xref:System.String.PadLeft%2A> method to create a new string that is twenty characters long.</span></span> <span data-ttu-id="3f2be-115">En el ejemplo se muestra "`--------Hello World!`" en la consola.</span><span class="sxs-lookup"><span data-stu-id="3f2be-115">The example displays "`--------Hello World!`" to the console.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/padding.cpp#3)]
 [!code-csharp[Conceptual.String.BasicOps#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/padding.cs#3)]
 [!code-vb[Conceptual.String.BasicOps#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/padding.vb#3)]  
  
## <a name="padright"></a><span data-ttu-id="3f2be-116">PadRight</span><span class="sxs-lookup"><span data-stu-id="3f2be-116">PadRight</span></span>  
 <span data-ttu-id="3f2be-117">El método <xref:System.String.PadRight%2A?displayProperty=nameWithType> crea una cadena mediante la concatenación de suficientes caracteres de relleno finales con una cadena original para alcanzar la longitud total especificada.</span><span class="sxs-lookup"><span data-stu-id="3f2be-117">The <xref:System.String.PadRight%2A?displayProperty=nameWithType> method creates a new string by concatenating enough trailing pad characters to an original string to achieve a specified total length.</span></span> <span data-ttu-id="3f2be-118">El método <xref:System.String.PadRight%28System.Int32%29?displayProperty=nameWithType> usa el espacio en blanco como carácter de relleno y el método <xref:System.String.PadRight%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> le permite especificar su propio carácter de relleno.</span><span class="sxs-lookup"><span data-stu-id="3f2be-118">The <xref:System.String.PadRight%28System.Int32%29?displayProperty=nameWithType> method uses white space as the padding character and the <xref:System.String.PadRight%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> method enables you to specify your own padding character.</span></span>  
  
 <span data-ttu-id="3f2be-119">En el ejemplo de código siguiente se usa el método <xref:System.String.PadRight%2A> para crear una cadena con una longitud de veinte caracteres.</span><span class="sxs-lookup"><span data-stu-id="3f2be-119">The following code example uses the <xref:System.String.PadRight%2A> method to create a new string that is twenty characters long.</span></span> <span data-ttu-id="3f2be-120">En el ejemplo se muestra "`Hello World!--------`" en la consola.</span><span class="sxs-lookup"><span data-stu-id="3f2be-120">The example displays "`Hello World!--------`" to the console.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/padding.cpp#4)]
 [!code-csharp[Conceptual.String.BasicOps#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/padding.cs#4)]
 [!code-vb[Conceptual.String.BasicOps#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/padding.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="3f2be-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="3f2be-121">See also</span></span>

- [<span data-ttu-id="3f2be-122">Operaciones básicas de cadenas</span><span class="sxs-lookup"><span data-stu-id="3f2be-122">Basic String Operations</span></span>](basic-string-operations.md)
