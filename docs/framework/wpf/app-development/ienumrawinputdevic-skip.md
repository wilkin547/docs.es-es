---
title: IEnumRAWINPUTDEVIC:Skip
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Skip method [WPF]
ms.assetid: c967b0f8-1c6a-459c-8c16-d4f08918ab65
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 216be1bc48a140bdd326010a87899cc342feb41d
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="ienumrawinputdevicskip"></a>IEnumRAWINPUTDEVIC:Skip
Indica al enumerador que omita el siguiente `celt` elementos de la enumeración para que la siguiente llamada a [IEnumRAWINPUTDEVIC:Next](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-next.md) no devolverá los elementos.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT Skip( [in] ULONG celt);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `celt`  
  
 [in] Número de elementos que se van a omitir.  
  
## <a name="property-valuereturn-value"></a>Valor de propiedad y valor devuelto  
 HRESULT: S_OK si el número de elementos proporcionado es `celt`. En caso contrario, S_FALSE.
