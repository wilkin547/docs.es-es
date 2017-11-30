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
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c3abe140e62f112a15a1ad1b1b2a79c14364b26d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="converting-net-framework-types-to-strings"></a><span data-ttu-id="c50f7-102">Convertir tipos de .NET Framework en cadenas</span><span class="sxs-lookup"><span data-stu-id="c50f7-102">Converting .NET Framework Types to Strings</span></span>
<span data-ttu-id="c50f7-103">Si desea convertir un tipo de .NET Framework en una cadena, utilice la **ToString** método.</span><span class="sxs-lookup"><span data-stu-id="c50f7-103">If you want to convert a .NET Framework type to a string, use the **ToString** method.</span></span> <span data-ttu-id="c50f7-104">El **ToString** método devuelve una representación de cadena del tipo pasado.</span><span class="sxs-lookup"><span data-stu-id="c50f7-104">The **ToString** method returns a string representation of the type passed in.</span></span> <span data-ttu-id="c50f7-105">En la tabla siguiente se enumeran los tipos de .NET Framework que devuelven una cadena en un formato que se asigna a las especificaciones de los esquemas XML (XSD).</span><span class="sxs-lookup"><span data-stu-id="c50f7-105">The following table lists the .NET Framework types that return a string in a format that maps to the XML Schema (XSD) specifications.</span></span>  
  
|<span data-ttu-id="c50f7-106">Tipo de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c50f7-106">.NET Framework type</span></span>|<span data-ttu-id="c50f7-107">Tipo de cadena devuelta</span><span class="sxs-lookup"><span data-stu-id="c50f7-107">String type returned</span></span>|  
|-------------------------|--------------------------|  
|<span data-ttu-id="c50f7-108">Boolean</span><span class="sxs-lookup"><span data-stu-id="c50f7-108">Boolean</span></span>|<span data-ttu-id="c50f7-109">"true", "false"</span><span class="sxs-lookup"><span data-stu-id="c50f7-109">"true", "false"</span></span>|  
|<span data-ttu-id="c50f7-110">Single.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="c50f7-110">Single.PositiveInfinity</span></span>|<span data-ttu-id="c50f7-111">"INF"</span><span class="sxs-lookup"><span data-stu-id="c50f7-111">"INF"</span></span>|  
|<span data-ttu-id="c50f7-112">Single.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="c50f7-112">Single.NegativeInfinity</span></span>|<span data-ttu-id="c50f7-113">"-INF"</span><span class="sxs-lookup"><span data-stu-id="c50f7-113">"-INF"</span></span>|  
|<span data-ttu-id="c50f7-114">Double.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="c50f7-114">Double.PositiveInfinity</span></span>|<span data-ttu-id="c50f7-115">"INF"</span><span class="sxs-lookup"><span data-stu-id="c50f7-115">"INF"</span></span>|  
|<span data-ttu-id="c50f7-116">Double.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="c50f7-116">Double.NegativeInfinity</span></span>|<span data-ttu-id="c50f7-117">"-INF"</span><span class="sxs-lookup"><span data-stu-id="c50f7-117">"-INF"</span></span>|  
|<span data-ttu-id="c50f7-118">DateTime</span><span class="sxs-lookup"><span data-stu-id="c50f7-118">DateTime</span></span>|<span data-ttu-id="c50f7-119">El formato es aaaa-MM-ddTHH:mm:sszzzzzz y sus subconjuntos.</span><span class="sxs-lookup"><span data-stu-id="c50f7-119">Format is yyyy-MM-ddTHH:mm:sszzzzzz and its subsets.</span></span>|  
|<span data-ttu-id="c50f7-120">Timespan</span><span class="sxs-lookup"><span data-stu-id="c50f7-120">Timespan</span></span>|<span data-ttu-id="c50f7-121">El formato es PnYnMnTnHnMnS, por ejemplo, `P2Y10M15DT10H30M20S` corresponde a una duración de 2 años, 10 meses, 15 días, 10 horas, 30 minutos y 20 segundos.</span><span class="sxs-lookup"><span data-stu-id="c50f7-121">Format is PnYnMnTnHnMnS, for example, `P2Y10M15DT10H30M20S` is a duration of 2 years, 10 months, 15 days, 10hours, 30 minutes and 20 seconds.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c50f7-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="c50f7-122">See Also</span></span>  
 [<span data-ttu-id="c50f7-123">Conversión de tipos de datos XML</span><span class="sxs-lookup"><span data-stu-id="c50f7-123">Conversion of XML Data Types</span></span>](../../../../docs/standard/data/xml/conversion-of-xml-data-types.md)  
 [<span data-ttu-id="c50f7-124">Convertir cadenas en tipos de datos de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c50f7-124">Converting Strings to .NET Framework Data Types</span></span>](../../../../docs/standard/data/xml/converting-strings-to-dotnet-data-types.md)
