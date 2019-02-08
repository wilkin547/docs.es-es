---
title: Funciones espaciales
ms.date: 03/30/2017
ms.assetid: 90cb177d-88a0-45be-97e8-3b306283c6e0
ms.openlocfilehash: 09402633c5e7f591a534992fc92655e6a2d1d88d
ms.sourcegitcommit: c6f69b0cf149f6b54483a6d5c2ece222913f43ce
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/08/2019
ms.locfileid: "55904475"
---
# <a name="spatial-functions"></a><span data-ttu-id="21111-102">Funciones espaciales</span><span class="sxs-lookup"><span data-stu-id="21111-102">Spatial Functions</span></span>
<span data-ttu-id="21111-103">No existe ningún formato literal para los tipos espaciales.</span><span class="sxs-lookup"><span data-stu-id="21111-103">There is no literal format for spatial types.</span></span> <span data-ttu-id="21111-104">Sin embargo, puede usar las funciones canónicas de Entity Framework a las que se llama mediante cadenas en formato Well-Known Text.</span><span class="sxs-lookup"><span data-stu-id="21111-104">However, you can use canonical Entity Framework functions that you call using strings in Well-Known Text format.</span></span> <span data-ttu-id="21111-105">Por ejemplo, la siguiente llamada de función crea un punto de geometría:</span><span class="sxs-lookup"><span data-stu-id="21111-105">For example, the following function call creates a geometry point:</span></span>  
  
```  
GeometryFromText('POINT (43 -73)')  
```  
  
 <span data-ttu-id="21111-106">El <xref:System.Data.Common.CommandTrees.ExpressionBuilder.Spatial.SpatialEdmFunctions> métodos tienen todos los métodos espaciales canónicos de Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="21111-106">The <xref:System.Data.Common.CommandTrees.ExpressionBuilder.Spatial.SpatialEdmFunctions> methods have all spatial canonical Entity Framework methods.</span></span> <span data-ttu-id="21111-107">Haga clic en un método de interés para ver qué parámetros se deben pasar a una función.</span><span class="sxs-lookup"><span data-stu-id="21111-107">Click on a method of interest to see what parameters should be passed to a function.</span></span>
