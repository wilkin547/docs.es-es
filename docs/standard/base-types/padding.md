---
title: Cadenas de relleno en .NET
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
- strings [.NET Framework], padding
- white space
- PadRight method
- PadLeft method
- padding strings
ms.assetid: 84a9f142-3244-4c90-ba02-21af9bbaff71
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 29cd40645cf06ac9babb4738259938a3da04a155
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="padding-strings-in-net"></a><span data-ttu-id="fac13-102">Cadenas de relleno en .NET</span><span class="sxs-lookup"><span data-stu-id="fac13-102">Padding Strings in .NET</span></span>
<span data-ttu-id="fac13-103">Utilice uno de los siguientes <xref:System.String> métodos para crear una nueva cadena que consta de una cadena original que se rellena con iniciales o finales de caracteres con la longitud total especificada.</span><span class="sxs-lookup"><span data-stu-id="fac13-103">Use one of the following <xref:System.String> methods to create a new string that consists of an original string that is padded with leading or trailing characters to a specified total length.</span></span> <span data-ttu-id="fac13-104">El carácter de relleno puede ser un espacio o un carácter especificado y, por tanto, parece que está alineado a la derecha o a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="fac13-104">The padding character can be spaces or a specified character, and consequently appears to be either right-aligned or left-aligned.</span></span>  
  
|<span data-ttu-id="fac13-105">Nombre del método</span><span class="sxs-lookup"><span data-stu-id="fac13-105">Method name</span></span>|<span data-ttu-id="fac13-106">Uso</span><span class="sxs-lookup"><span data-stu-id="fac13-106">Use</span></span>|  
|-----------------|---------|  
|<xref:System.String.PadLeft%2A?displayProperty=nameWithType>|<span data-ttu-id="fac13-107">Rellena una cadena con caracteres iniciales hasta una longitud total especificada.</span><span class="sxs-lookup"><span data-stu-id="fac13-107">Pads a string with leading characters to a specified total length.</span></span>|  
|<xref:System.String.PadRight%2A?displayProperty=nameWithType>|<span data-ttu-id="fac13-108">Rellena una cadena con caracteres finales hasta una longitud total especificada.</span><span class="sxs-lookup"><span data-stu-id="fac13-108">Pads a string with trailing characters to a specified total length.</span></span>|  
  
## <a name="padleft"></a><span data-ttu-id="fac13-109">PadLeft</span><span class="sxs-lookup"><span data-stu-id="fac13-109">PadLeft</span></span>  
 <span data-ttu-id="fac13-110">El <xref:System.String.PadLeft%2A?displayProperty=nameWithType> método crea una nueva cadena concatenando caracteres de relleno iniciales a una cadena original hasta alcanzar la longitud total especificada.</span><span class="sxs-lookup"><span data-stu-id="fac13-110">The <xref:System.String.PadLeft%2A?displayProperty=nameWithType> method creates a new string by concatenating enough leading pad characters to an original string to achieve a specified total length.</span></span> <span data-ttu-id="fac13-111">El <xref:System.String.PadLeft%28System.Int32%29?displayProperty=nameWithType> método usa el espacio en blanco como el carácter de relleno y el <xref:System.String.PadLeft%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> método le permite especificar su propio carácter de relleno.</span><span class="sxs-lookup"><span data-stu-id="fac13-111">The <xref:System.String.PadLeft%28System.Int32%29?displayProperty=nameWithType> method uses white space as the padding character and the <xref:System.String.PadLeft%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> method enables you to specify your own padding character.</span></span>  
  
 <span data-ttu-id="fac13-112">El siguiente ejemplo de código utiliza el <xref:System.String.PadLeft%2A> método para crear una nueva cadena que tiene veinte caracteres.</span><span class="sxs-lookup"><span data-stu-id="fac13-112">The following code example uses the <xref:System.String.PadLeft%2A> method to create a new string that is twenty characters long.</span></span> <span data-ttu-id="fac13-113">En el ejemplo se muestra "`--------Hello World!`" en la consola.</span><span class="sxs-lookup"><span data-stu-id="fac13-113">The example displays "`--------Hello World!`" to the console.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/padding.cpp#3)]
 [!code-csharp[Conceptual.String.BasicOps#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/padding.cs#3)]
 [!code-vb[Conceptual.String.BasicOps#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/padding.vb#3)]  
  
## <a name="padright"></a><span data-ttu-id="fac13-114">PadRight</span><span class="sxs-lookup"><span data-stu-id="fac13-114">PadRight</span></span>  
 <span data-ttu-id="fac13-115">El <xref:System.String.PadRight%2A?displayProperty=nameWithType> método crea una nueva cadena concatenando caracteres de relleno finales a una cadena original hasta alcanzar la longitud total especificada.</span><span class="sxs-lookup"><span data-stu-id="fac13-115">The <xref:System.String.PadRight%2A?displayProperty=nameWithType> method creates a new string by concatenating enough trailing pad characters to an original string to achieve a specified total length.</span></span> <span data-ttu-id="fac13-116">El <xref:System.String.PadRight%28System.Int32%29?displayProperty=nameWithType> método usa el espacio en blanco como el carácter de relleno y el <xref:System.String.PadRight%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> método le permite especificar su propio carácter de relleno.</span><span class="sxs-lookup"><span data-stu-id="fac13-116">The <xref:System.String.PadRight%28System.Int32%29?displayProperty=nameWithType> method uses white space as the padding character and the <xref:System.String.PadRight%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> method enables you to specify your own padding character.</span></span>  
  
 <span data-ttu-id="fac13-117">El siguiente ejemplo de código utiliza el <xref:System.String.PadRight%2A> método para crear una nueva cadena que tiene veinte caracteres.</span><span class="sxs-lookup"><span data-stu-id="fac13-117">The following code example uses the <xref:System.String.PadRight%2A> method to create a new string that is twenty characters long.</span></span> <span data-ttu-id="fac13-118">En el ejemplo se muestra "`Hello World!--------`" en la consola.</span><span class="sxs-lookup"><span data-stu-id="fac13-118">The example displays "`Hello World!--------`" to the console.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/padding.cpp#4)]
 [!code-csharp[Conceptual.String.BasicOps#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/padding.cs#4)]
 [!code-vb[Conceptual.String.BasicOps#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/padding.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="fac13-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="fac13-119">See Also</span></span>  
 [<span data-ttu-id="fac13-120">Operaciones básicas de cadenas</span><span class="sxs-lookup"><span data-stu-id="fac13-120">Basic String Operations</span></span>](../../../docs/standard/base-types/basic-string-operations.md)
