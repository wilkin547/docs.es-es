---
title: Funciones espaciales
ms.date: 03/30/2017
ms.assetid: 90cb177d-88a0-45be-97e8-3b306283c6e0
ms.openlocfilehash: 7b78cbf4dc53ba1bc4148fa0077615e43cc8f9f9
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="spatial-functions"></a>Funciones espaciales
No existe ningún formato literal para los tipos espaciales. Sin embargo, puede usar las funciones canónicas de Entity Framework a las que se llama mediante cadenas en formato Well-Known Text. Por ejemplo, la siguiente llamada de función crea un punto de geometría:  
  
```  
GeometryFromText('POINT (43 -73)')  
```  
  
 El [métodos de SpatialEdmFunctions](http://msdn.microsoft.com/library/hh749531.aspx) página enumera todos los métodos espaciales canónicos de Entity Framework. Haga clic en un método de interés para ver qué parámetros se deben pasar a una función.
