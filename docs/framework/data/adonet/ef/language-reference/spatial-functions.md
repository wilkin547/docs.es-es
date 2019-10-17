---
title: Funciones espaciales
ms.date: 03/30/2017
ms.assetid: 90cb177d-88a0-45be-97e8-3b306283c6e0
ms.openlocfilehash: eba384e77389f82006479f165178e80fcac244b1
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319300"
---
# <a name="spatial-functions"></a>Funciones espaciales
No existe ningún formato literal para los tipos espaciales. Sin embargo, puede usar las funciones canónicas de Entity Framework a las que se llama mediante cadenas en formato Well-Known Text. Por ejemplo, la siguiente llamada de función crea un punto de geometría:  
  
```sql  
GeometryFromText('POINT (43 -73)')  
```  
  
 Los métodos <xref:System.Data.Common.CommandTrees.ExpressionBuilder.Spatial.SpatialEdmFunctions> tienen todos los métodos de Entity Framework canónicos espaciales. Haga clic en un método de interés para ver qué parámetros se deben pasar a una función.
