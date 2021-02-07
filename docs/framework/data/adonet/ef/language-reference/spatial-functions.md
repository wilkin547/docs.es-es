---
description: 'Más información sobre: funciones espaciales'
title: Funciones espaciales
ms.date: 03/30/2017
ms.assetid: 90cb177d-88a0-45be-97e8-3b306283c6e0
ms.openlocfilehash: cde8f1b0fcf5904eb33fe061de69e566da2804dd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99767887"
---
# <a name="spatial-functions"></a><span data-ttu-id="b5b2b-103">Funciones espaciales</span><span class="sxs-lookup"><span data-stu-id="b5b2b-103">Spatial Functions</span></span>

<span data-ttu-id="b5b2b-104">No existe ningún formato literal para los tipos espaciales.</span><span class="sxs-lookup"><span data-stu-id="b5b2b-104">There is no literal format for spatial types.</span></span> <span data-ttu-id="b5b2b-105">Sin embargo, puede usar las funciones canónicas de Entity Framework a las que se llama mediante cadenas en formato Well-Known Text.</span><span class="sxs-lookup"><span data-stu-id="b5b2b-105">However, you can use canonical Entity Framework functions that you call using strings in Well-Known Text format.</span></span> <span data-ttu-id="b5b2b-106">Por ejemplo, la siguiente llamada de función crea un punto de geometría:</span><span class="sxs-lookup"><span data-stu-id="b5b2b-106">For example, the following function call creates a geometry point:</span></span>  
  
```sql  
GeometryFromText('POINT (43 -73)')  
```  
  
 <span data-ttu-id="b5b2b-107">Los <xref:System.Data.Common.CommandTrees.ExpressionBuilder.Spatial.SpatialEdmFunctions> métodos tienen todos los métodos Entity Framework canónicos espaciales.</span><span class="sxs-lookup"><span data-stu-id="b5b2b-107">The <xref:System.Data.Common.CommandTrees.ExpressionBuilder.Spatial.SpatialEdmFunctions> methods have all spatial canonical Entity Framework methods.</span></span> <span data-ttu-id="b5b2b-108">Haga clic en un método de interés para ver qué parámetros se deben pasar a una función.</span><span class="sxs-lookup"><span data-stu-id="b5b2b-108">Click on a method of interest to see what parameters should be passed to a function.</span></span>
