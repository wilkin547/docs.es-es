---
title: Relleno de cadenas en .NET
description: Aprenda a rellenar cadenas en .NET. Use los métodos String.PadLeft y String.PadRight para agregar caracteres iniciales o finales hasta alcanzar la longitud total especificada.
ms.date: 03/15/2018
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- strings [.NET], padding
- white space
- PadRight method
- PadLeft method
- padding strings
ms.assetid: 84a9f142-3244-4c90-ba02-21af9bbaff71
ms.openlocfilehash: 9931db1e76e3737ab3803400928169b30c3ecbda
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94822950"
---
# <a name="padding-strings-in-net"></a><span data-ttu-id="337f7-104">Relleno de cadenas en .NET</span><span class="sxs-lookup"><span data-stu-id="337f7-104">Padding Strings in .NET</span></span>

<span data-ttu-id="337f7-105">Use uno de los siguientes métodos <xref:System.String> para crear una cadena que conste de una cadena original rellenada con caracteres iniciales o finales hasta una longitud total especificada.</span><span class="sxs-lookup"><span data-stu-id="337f7-105">Use one of the following <xref:System.String> methods to create a new string that consists of an original string that is padded with leading or trailing characters to a specified total length.</span></span> <span data-ttu-id="337f7-106">El carácter de relleno puede ser un espacio o un carácter especificado.</span><span class="sxs-lookup"><span data-stu-id="337f7-106">The padding character can be a space or a specified character.</span></span> <span data-ttu-id="337f7-107">La cadena resultante aparece alineada a la derecha o bien a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="337f7-107">The resulting string appears to be either right-aligned or left-aligned.</span></span> <span data-ttu-id="337f7-108">Si la longitud de la cadena original ya es igual o mayor que la longitud total deseada, los métodos de relleno devuelven la cadena original sin modificarla. Para obtener más información, vea las secciones **Devoluciones** de las dos sobrecargas de los métodos <xref:System.String.PadLeft%2A?displayProperty=nameWithType> y <xref:System.String.PadRight%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="337f7-108">If the original string's length is already equal to or greater than the desired total length, the padding methods return the original string unchanged; for more information, see the **Returns** sections of the two overloads of the <xref:System.String.PadLeft%2A?displayProperty=nameWithType> and <xref:System.String.PadRight%2A?displayProperty=nameWithType> methods.</span></span>
  
|<span data-ttu-id="337f7-109">Nombre del método</span><span class="sxs-lookup"><span data-stu-id="337f7-109">Method name</span></span>|<span data-ttu-id="337f7-110">Usar</span><span class="sxs-lookup"><span data-stu-id="337f7-110">Use</span></span>|  
|-----------------|---------|  
|<xref:System.String.PadLeft%2A?displayProperty=nameWithType>|<span data-ttu-id="337f7-111">Rellena una cadena con caracteres iniciales hasta una longitud total especificada.</span><span class="sxs-lookup"><span data-stu-id="337f7-111">Pads a string with leading characters to a specified total length.</span></span>|  
|<xref:System.String.PadRight%2A?displayProperty=nameWithType>|<span data-ttu-id="337f7-112">Rellena una cadena con caracteres finales hasta una longitud total especificada.</span><span class="sxs-lookup"><span data-stu-id="337f7-112">Pads a string with trailing characters to a specified total length.</span></span>|  
  
## <a name="padleft"></a><span data-ttu-id="337f7-113">PadLeft</span><span class="sxs-lookup"><span data-stu-id="337f7-113">PadLeft</span></span>  
 <span data-ttu-id="337f7-114">El método <xref:System.String.PadLeft%2A?displayProperty=nameWithType> crea una cadena mediante la concatenación de suficientes caracteres de relleno iniciales con una cadena original para alcanzar la longitud total especificada.</span><span class="sxs-lookup"><span data-stu-id="337f7-114">The <xref:System.String.PadLeft%2A?displayProperty=nameWithType> method creates a new string by concatenating enough leading pad characters to an original string to achieve a specified total length.</span></span> <span data-ttu-id="337f7-115">El método <xref:System.String.PadLeft%28System.Int32%29?displayProperty=nameWithType> usa el espacio en blanco como carácter de relleno y el método <xref:System.String.PadLeft%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> le permite especificar su propio carácter de relleno.</span><span class="sxs-lookup"><span data-stu-id="337f7-115">The <xref:System.String.PadLeft%28System.Int32%29?displayProperty=nameWithType> method uses white space as the padding character and the <xref:System.String.PadLeft%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> method enables you to specify your own padding character.</span></span>  
  
 <span data-ttu-id="337f7-116">En el ejemplo de código siguiente se usa el método <xref:System.String.PadLeft%2A> para crear una cadena con una longitud de veinte caracteres.</span><span class="sxs-lookup"><span data-stu-id="337f7-116">The following code example uses the <xref:System.String.PadLeft%2A> method to create a new string that is twenty characters long.</span></span> <span data-ttu-id="337f7-117">En el ejemplo se muestra "`--------Hello World!`" en la consola.</span><span class="sxs-lookup"><span data-stu-id="337f7-117">The example displays "`--------Hello World!`" to the console.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/padding.cpp#3)]
 [!code-csharp[Conceptual.String.BasicOps#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/padding.cs#3)]
 [!code-vb[Conceptual.String.BasicOps#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/padding.vb#3)]  
  
## <a name="padright"></a><span data-ttu-id="337f7-118">PadRight</span><span class="sxs-lookup"><span data-stu-id="337f7-118">PadRight</span></span>  
 <span data-ttu-id="337f7-119">El método <xref:System.String.PadRight%2A?displayProperty=nameWithType> crea una cadena mediante la concatenación de suficientes caracteres de relleno finales con una cadena original para alcanzar la longitud total especificada.</span><span class="sxs-lookup"><span data-stu-id="337f7-119">The <xref:System.String.PadRight%2A?displayProperty=nameWithType> method creates a new string by concatenating enough trailing pad characters to an original string to achieve a specified total length.</span></span> <span data-ttu-id="337f7-120">El método <xref:System.String.PadRight%28System.Int32%29?displayProperty=nameWithType> usa el espacio en blanco como carácter de relleno y el método <xref:System.String.PadRight%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> le permite especificar su propio carácter de relleno.</span><span class="sxs-lookup"><span data-stu-id="337f7-120">The <xref:System.String.PadRight%28System.Int32%29?displayProperty=nameWithType> method uses white space as the padding character and the <xref:System.String.PadRight%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> method enables you to specify your own padding character.</span></span>  
  
 <span data-ttu-id="337f7-121">En el ejemplo de código siguiente se usa el método <xref:System.String.PadRight%2A> para crear una cadena con una longitud de veinte caracteres.</span><span class="sxs-lookup"><span data-stu-id="337f7-121">The following code example uses the <xref:System.String.PadRight%2A> method to create a new string that is twenty characters long.</span></span> <span data-ttu-id="337f7-122">En el ejemplo se muestra "`Hello World!--------`" en la consola.</span><span class="sxs-lookup"><span data-stu-id="337f7-122">The example displays "`Hello World!--------`" to the console.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/padding.cpp#4)]
 [!code-csharp[Conceptual.String.BasicOps#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/padding.cs#4)]
 [!code-vb[Conceptual.String.BasicOps#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/padding.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="337f7-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="337f7-123">See also</span></span>

- [<span data-ttu-id="337f7-124">Operaciones básicas de cadenas</span><span class="sxs-lookup"><span data-stu-id="337f7-124">Basic String Operations</span></span>](basic-string-operations.md)
