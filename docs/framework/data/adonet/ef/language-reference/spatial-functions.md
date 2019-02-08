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
# <a name="spatial-functions"></a>Funciones espaciales
No existe ningún formato literal para los tipos espaciales. Sin embargo, puede usar las funciones canónicas de Entity Framework a las que se llama mediante cadenas en formato Well-Known Text. Por ejemplo, la siguiente llamada de función crea un punto de geometría:  
  
```  
GeometryFromText('POINT (43 -73)')  
```  
  
 El <xref:System.Data.Common.CommandTrees.ExpressionBuilder.Spatial.SpatialEdmFunctions> métodos tienen todos los métodos espaciales canónicos de Entity Framework. Haga clic en un método de interés para ver qué parámetros se deben pasar a una función.
