---
title: "IEnumRAWINPUTDEVIC:Clone | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Clone (método)"
ms.assetid: 2a6a1900-aa55-45fa-9382-241d569a2dc4
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# IEnumRAWINPUTDEVIC:Clone
Crea otro enumerador de dispositivo de entrada sin formato con el mismo estado que el enumerador actual para iterar sobre la misma lista.  
  
## Sintaxis  
  
```  
HRESULT Clone( [out] IEnumRAWINPUTDEVICE **ppenum);  
```  
  
#### Parámetros  
 `ppenum`  
  
 \[out\] Dirección de variable de salida que recibe el puntero de interfaz [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md).  Si el método no se realiza correctamente, el valor de esta variable de salida es indefinido.  
  
## Valor de propiedad y valor devuelto  
 HRESULT: Este método admite los valores devueltos estándar E\_INVALIDARG, E\_OUTOFMEMORY, y E\_UNEXPECTED.  
  
## Comentarios  
 Este método permite grabar un punto en la secuencia de enumeración para volver a ese punto en un momento posterior.  El llamador debe liberar este nuevo enumerador de manera independiente con respecto al primer enumerador.