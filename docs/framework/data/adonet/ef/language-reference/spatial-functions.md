---
title: "Funciones espaciales | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 90cb177d-88a0-45be-97e8-3b306283c6e0
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Funciones espaciales
No existe ningún formato literal para los tipos espaciales.  Sin embargo, puede usar las funciones canónicas de Entity Framework a las que se llama mediante cadenas en formato Well\-Known Text.  Por ejemplo, la siguiente llamada de función crea un punto de geometría:  
  
```  
GeometryFromText('POINT (43 -73)')  
```  
  
 En la página [Métodos de SpatialEdmFunctions](http://msdn.microsoft.com/library/hh749531.aspx) se enumeran todos los métodos espaciales canónicos de Entity Framework.  Haga clic en un método de interés para ver qué parámetros se deben pasar a una función.