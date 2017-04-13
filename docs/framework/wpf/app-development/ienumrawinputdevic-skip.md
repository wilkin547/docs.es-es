---
title: "IEnumRAWINPUTDEVIC:Skip | Microsoft Docs"
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
  - "Skip (método)"
ms.assetid: c967b0f8-1c6a-459c-8c16-d4f08918ab65
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# IEnumRAWINPUTDEVIC:Skip
Indica al enumerador que omita los siguientes elementos `celt` en la enumeración para que la siguiente llamada a [IEnumRAWINPUTDEVIC:Next](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-next.md) no devuelva esos elementos.  
  
## Sintaxis  
  
```  
HRESULT Skip( [in] ULONG celt);  
```  
  
#### Parámetros  
 `celt`  
  
 \[in\] Número de elementos que se van a omitir.  
  
## Valor de propiedad y valor devuelto  
 HRESULT: S\_OK si el número de elementos proporcionados es `celt`; S\_FALSE en caso contrario.