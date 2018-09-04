---
title: Funciones espaciales
ms.date: 03/30/2017
ms.assetid: 90cb177d-88a0-45be-97e8-3b306283c6e0
ms.openlocfilehash: ad6b722e84aae40354e30434b107752d02352645
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43559522"
---
# <a name="spatial-functions"></a><span data-ttu-id="55b67-102">Funciones espaciales</span><span class="sxs-lookup"><span data-stu-id="55b67-102">Spatial Functions</span></span>
<span data-ttu-id="55b67-103">No existe ningún formato literal para los tipos espaciales.</span><span class="sxs-lookup"><span data-stu-id="55b67-103">There is no literal format for spatial types.</span></span> <span data-ttu-id="55b67-104">Sin embargo, puede usar las funciones canónicas de Entity Framework a las que se llama mediante cadenas en formato Well-Known Text.</span><span class="sxs-lookup"><span data-stu-id="55b67-104">However, you can use canonical Entity Framework functions that you call using strings in Well-Known Text format.</span></span> <span data-ttu-id="55b67-105">Por ejemplo, la siguiente llamada de función crea un punto de geometría:</span><span class="sxs-lookup"><span data-stu-id="55b67-105">For example, the following function call creates a geometry point:</span></span>  
  
```  
GeometryFromText('POINT (43 -73)')  
```  
  
 <span data-ttu-id="55b67-106">El [métodos de SpatialEdmFunctions](https://msdn.microsoft.com/library/hh749531.aspx) página enumera todos los métodos espaciales canónicos de Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="55b67-106">The [SpatialEdmFunctions Methods](https://msdn.microsoft.com/library/hh749531.aspx) page lists all spatial canonical Entity Framework methods.</span></span> <span data-ttu-id="55b67-107">Haga clic en un método de interés para ver qué parámetros se deben pasar a una función.</span><span class="sxs-lookup"><span data-stu-id="55b67-107">Click on a method of interest to see what parameters should be passed to a function.</span></span>
