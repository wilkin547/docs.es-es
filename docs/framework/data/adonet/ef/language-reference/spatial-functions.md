---
title: Funciones espaciales
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 90cb177d-88a0-45be-97e8-3b306283c6e0
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: c482c2f79c6416a4e748599c896280b426d31ce2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="spatial-functions"></a><span data-ttu-id="530f0-102">Funciones espaciales</span><span class="sxs-lookup"><span data-stu-id="530f0-102">Spatial Functions</span></span>
<span data-ttu-id="530f0-103">No existe ningún formato literal para los tipos espaciales.</span><span class="sxs-lookup"><span data-stu-id="530f0-103">There is no literal format for spatial types.</span></span> <span data-ttu-id="530f0-104">Sin embargo, puede usar las funciones canónicas de Entity Framework a las que se llama mediante cadenas en formato Well-Known Text.</span><span class="sxs-lookup"><span data-stu-id="530f0-104">However, you can use canonical Entity Framework functions that you call using strings in Well-Known Text format.</span></span> <span data-ttu-id="530f0-105">Por ejemplo, la siguiente llamada de función crea un punto de geometría:</span><span class="sxs-lookup"><span data-stu-id="530f0-105">For example, the following function call creates a geometry point:</span></span>  
  
```  
GeometryFromText('POINT (43 -73)')  
```  
  
 <span data-ttu-id="530f0-106">El [métodos de SpatialEdmFunctions](http://msdn.microsoft.com/library/hh749531.aspx) página enumera todos los métodos espaciales canónicos de Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="530f0-106">The [SpatialEdmFunctions Methods](http://msdn.microsoft.com/library/hh749531.aspx) page lists all spatial canonical Entity Framework methods.</span></span> <span data-ttu-id="530f0-107">Haga clic en un método de interés para ver qué parámetros se deben pasar a una función.</span><span class="sxs-lookup"><span data-stu-id="530f0-107">Click on a method of interest to see what parameters should be passed to a function.</span></span>
