---
title: Relleno de cadenas en .NET
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: ea903c1f950e7c226e043c1fa7276a66126b2512
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="padding-strings-in-net"></a><span data-ttu-id="78152-102">Relleno de cadenas en .NET</span><span class="sxs-lookup"><span data-stu-id="78152-102">Padding Strings in .NET</span></span>
<span data-ttu-id="78152-103">Use uno de los siguientes métodos <xref:System.String> para crear una cadena que conste de una cadena original rellenada con caracteres iniciales o finales hasta una longitud total especificada.</span><span class="sxs-lookup"><span data-stu-id="78152-103">Use one of the following <xref:System.String> methods to create a new string that consists of an original string that is padded with leading or trailing characters to a specified total length.</span></span> <span data-ttu-id="78152-104">El carácter de relleno puede ser un espacio o un carácter especificado y, por tanto, parece que está alineado a la derecha o a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="78152-104">The padding character can be spaces or a specified character, and consequently appears to be either right-aligned or left-aligned.</span></span>  
  
|<span data-ttu-id="78152-105">Nombre del método</span><span class="sxs-lookup"><span data-stu-id="78152-105">Method name</span></span>|<span data-ttu-id="78152-106">Usar</span><span class="sxs-lookup"><span data-stu-id="78152-106">Use</span></span>|  
|-----------------|---------|  
|<xref:System.String.PadLeft%2A?displayProperty=nameWithType>|<span data-ttu-id="78152-107">Rellena una cadena con caracteres iniciales hasta una longitud total especificada.</span><span class="sxs-lookup"><span data-stu-id="78152-107">Pads a string with leading characters to a specified total length.</span></span>|  
|<xref:System.String.PadRight%2A?displayProperty=nameWithType>|<span data-ttu-id="78152-108">Rellena una cadena con caracteres finales hasta una longitud total especificada.</span><span class="sxs-lookup"><span data-stu-id="78152-108">Pads a string with trailing characters to a specified total length.</span></span>|  
  
## <a name="padleft"></a><span data-ttu-id="78152-109">PadLeft</span><span class="sxs-lookup"><span data-stu-id="78152-109">PadLeft</span></span>  
 <span data-ttu-id="78152-110">El método <xref:System.String.PadLeft%2A?displayProperty=nameWithType> crea una cadena mediante la concatenación de suficientes caracteres de relleno iniciales con una cadena original para alcanzar la longitud total especificada.</span><span class="sxs-lookup"><span data-stu-id="78152-110">The <xref:System.String.PadLeft%2A?displayProperty=nameWithType> method creates a new string by concatenating enough leading pad characters to an original string to achieve a specified total length.</span></span> <span data-ttu-id="78152-111">El método <xref:System.String.PadLeft%28System.Int32%29?displayProperty=nameWithType> usa el espacio en blanco como carácter de relleno y el método <xref:System.String.PadLeft%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> le permite especificar su propio carácter de relleno.</span><span class="sxs-lookup"><span data-stu-id="78152-111">The <xref:System.String.PadLeft%28System.Int32%29?displayProperty=nameWithType> method uses white space as the padding character and the <xref:System.String.PadLeft%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> method enables you to specify your own padding character.</span></span>  
  
 <span data-ttu-id="78152-112">En el ejemplo de código siguiente se usa el método <xref:System.String.PadLeft%2A> para crear una cadena con una longitud de veinte caracteres.</span><span class="sxs-lookup"><span data-stu-id="78152-112">The following code example uses the <xref:System.String.PadLeft%2A> method to create a new string that is twenty characters long.</span></span> <span data-ttu-id="78152-113">En el ejemplo se muestra "`--------Hello World!`" en la consola.</span><span class="sxs-lookup"><span data-stu-id="78152-113">The example displays "`--------Hello World!`" to the console.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/padding.cpp#3)]
 [!code-csharp[Conceptual.String.BasicOps#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/padding.cs#3)]
 [!code-vb[Conceptual.String.BasicOps#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/padding.vb#3)]  
  
## <a name="padright"></a><span data-ttu-id="78152-114">PadRight</span><span class="sxs-lookup"><span data-stu-id="78152-114">PadRight</span></span>  
 <span data-ttu-id="78152-115">El método <xref:System.String.PadRight%2A?displayProperty=nameWithType> crea una cadena mediante la concatenación de suficientes caracteres de relleno finales con una cadena original para alcanzar la longitud total especificada.</span><span class="sxs-lookup"><span data-stu-id="78152-115">The <xref:System.String.PadRight%2A?displayProperty=nameWithType> method creates a new string by concatenating enough trailing pad characters to an original string to achieve a specified total length.</span></span> <span data-ttu-id="78152-116">El método <xref:System.String.PadRight%28System.Int32%29?displayProperty=nameWithType> usa el espacio en blanco como carácter de relleno y el método <xref:System.String.PadRight%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> le permite especificar su propio carácter de relleno.</span><span class="sxs-lookup"><span data-stu-id="78152-116">The <xref:System.String.PadRight%28System.Int32%29?displayProperty=nameWithType> method uses white space as the padding character and the <xref:System.String.PadRight%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> method enables you to specify your own padding character.</span></span>  
  
 <span data-ttu-id="78152-117">En el ejemplo de código siguiente se usa el método <xref:System.String.PadRight%2A> para crear una cadena con una longitud de veinte caracteres.</span><span class="sxs-lookup"><span data-stu-id="78152-117">The following code example uses the <xref:System.String.PadRight%2A> method to create a new string that is twenty characters long.</span></span> <span data-ttu-id="78152-118">En el ejemplo se muestra "`Hello World!--------`" en la consola.</span><span class="sxs-lookup"><span data-stu-id="78152-118">The example displays "`Hello World!--------`" to the console.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/padding.cpp#4)]
 [!code-csharp[Conceptual.String.BasicOps#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/padding.cs#4)]
 [!code-vb[Conceptual.String.BasicOps#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/padding.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="78152-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="78152-119">See Also</span></span>  
 [<span data-ttu-id="78152-120">Operaciones básicas de cadenas</span><span class="sxs-lookup"><span data-stu-id="78152-120">Basic String Operations</span></span>](../../../docs/standard/base-types/basic-string-operations.md)
