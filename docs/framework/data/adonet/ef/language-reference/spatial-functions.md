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
# <a name="spatial-functions"></a>Funciones espaciales

No existe ningún formato literal para los tipos espaciales. Sin embargo, puede usar las funciones canónicas de Entity Framework a las que se llama mediante cadenas en formato Well-Known Text. Por ejemplo, la siguiente llamada de función crea un punto de geometría:  
  
```sql  
GeometryFromText('POINT (43 -73)')  
```  
  
 Los <xref:System.Data.Common.CommandTrees.ExpressionBuilder.Spatial.SpatialEdmFunctions> métodos tienen todos los métodos Entity Framework canónicos espaciales. Haga clic en un método de interés para ver qué parámetros se deben pasar a una función.
