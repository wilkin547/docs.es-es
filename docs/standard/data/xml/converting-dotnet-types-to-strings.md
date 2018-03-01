---
title: Convertir tipos de .NET Framework en cadenas
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dc2e2b65-f623-4dc3-938b-d2a054d6832c
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 6ca134e13593fdacd759b0000e0e159f76ea067f
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="converting-net-framework-types-to-strings"></a><span data-ttu-id="a2718-102">Convertir tipos de .NET Framework en cadenas</span><span class="sxs-lookup"><span data-stu-id="a2718-102">Converting .NET Framework Types to Strings</span></span>
<span data-ttu-id="a2718-103">Si desea convertir un tipo de .NET Framework en una cadena, utilice el método **ToString**.</span><span class="sxs-lookup"><span data-stu-id="a2718-103">If you want to convert a .NET Framework type to a string, use the **ToString** method.</span></span> <span data-ttu-id="a2718-104">El método **ToString** devuelve una representación de cadena del tipo que se le pasa.</span><span class="sxs-lookup"><span data-stu-id="a2718-104">The **ToString** method returns a string representation of the type passed in.</span></span> <span data-ttu-id="a2718-105">En la tabla siguiente se enumeran los tipos de .NET Framework que devuelven una cadena en un formato que se asigna a las especificaciones de los esquemas XML (XSD).</span><span class="sxs-lookup"><span data-stu-id="a2718-105">The following table lists the .NET Framework types that return a string in a format that maps to the XML Schema (XSD) specifications.</span></span>  
  
|<span data-ttu-id="a2718-106">Tipo de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a2718-106">.NET Framework type</span></span>|<span data-ttu-id="a2718-107">Tipo de cadena devuelta</span><span class="sxs-lookup"><span data-stu-id="a2718-107">String type returned</span></span>|  
|-------------------------|--------------------------|  
|<span data-ttu-id="a2718-108">Booleano</span><span class="sxs-lookup"><span data-stu-id="a2718-108">Boolean</span></span>|<span data-ttu-id="a2718-109">"true", "false"</span><span class="sxs-lookup"><span data-stu-id="a2718-109">"true", "false"</span></span>|  
|<span data-ttu-id="a2718-110">Single.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="a2718-110">Single.PositiveInfinity</span></span>|<span data-ttu-id="a2718-111">"INF"</span><span class="sxs-lookup"><span data-stu-id="a2718-111">"INF"</span></span>|  
|<span data-ttu-id="a2718-112">Single.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="a2718-112">Single.NegativeInfinity</span></span>|<span data-ttu-id="a2718-113">"-INF"</span><span class="sxs-lookup"><span data-stu-id="a2718-113">"-INF"</span></span>|  
|<span data-ttu-id="a2718-114">Double.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="a2718-114">Double.PositiveInfinity</span></span>|<span data-ttu-id="a2718-115">"INF"</span><span class="sxs-lookup"><span data-stu-id="a2718-115">"INF"</span></span>|  
|<span data-ttu-id="a2718-116">Double.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="a2718-116">Double.NegativeInfinity</span></span>|<span data-ttu-id="a2718-117">"-INF"</span><span class="sxs-lookup"><span data-stu-id="a2718-117">"-INF"</span></span>|  
|<span data-ttu-id="a2718-118">DateTime</span><span class="sxs-lookup"><span data-stu-id="a2718-118">DateTime</span></span>|<span data-ttu-id="a2718-119">El formato es aaaa-MM-ddTHH:mm:sszzzzzz y sus subconjuntos.</span><span class="sxs-lookup"><span data-stu-id="a2718-119">Format is yyyy-MM-ddTHH:mm:sszzzzzz and its subsets.</span></span>|  
|<span data-ttu-id="a2718-120">Timespan</span><span class="sxs-lookup"><span data-stu-id="a2718-120">Timespan</span></span>|<span data-ttu-id="a2718-121">El formato es PnYnMnTnHnMnS, por ejemplo, `P2Y10M15DT10H30M20S` corresponde a una duración de 2 años, 10 meses, 15 días, 10 horas, 30 minutos y 20 segundos.</span><span class="sxs-lookup"><span data-stu-id="a2718-121">Format is PnYnMnTnHnMnS, for example, `P2Y10M15DT10H30M20S` is a duration of 2 years, 10 months, 15 days, 10hours, 30 minutes and 20 seconds.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a2718-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="a2718-122">See Also</span></span>  
 [<span data-ttu-id="a2718-123">Conversión de tipos de datos XML</span><span class="sxs-lookup"><span data-stu-id="a2718-123">Conversion of XML Data Types</span></span>](../../../../docs/standard/data/xml/conversion-of-xml-data-types.md)  
 [<span data-ttu-id="a2718-124">Conversión de cadenas en tipos de datos de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a2718-124">Converting Strings to .NET Framework Data Types</span></span>](../../../../docs/standard/data/xml/converting-strings-to-dotnet-data-types.md)
