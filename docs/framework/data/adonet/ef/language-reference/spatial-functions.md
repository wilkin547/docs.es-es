---
title: Funciones espaciales
ms.date: 03/30/2017
ms.assetid: 90cb177d-88a0-45be-97e8-3b306283c6e0
ms.openlocfilehash: 7d0979b5166c847244cbeec97acf4fa4f745a259
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91169588"
---
# <a name="spatial-functions"></a>Funciones espaciales

No existe ningún formato literal para los tipos espaciales. Sin embargo, puede usar las funciones canónicas de Entity Framework a las que se llama mediante cadenas en formato Well-Known Text. Por ejemplo, la siguiente llamada de función crea un punto de geometría:  
  
```sql  
GeometryFromText('POINT (43 -73)')  
```  
  
 Los <xref:System.Data.Common.CommandTrees.ExpressionBuilder.Spatial.SpatialEdmFunctions> métodos tienen todos los métodos Entity Framework canónicos espaciales. Haga clic en un método de interés para ver qué parámetros se deben pasar a una función.
