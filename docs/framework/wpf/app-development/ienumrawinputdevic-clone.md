---
title: IEnumRAWINPUTDEVIC:Clone
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Clone method [WPF]
ms.assetid: 2a6a1900-aa55-45fa-9382-241d569a2dc4
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 35f3c00f3a0efd41c425ba29f8465a73e78d624c
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="ienumrawinputdevicclone"></a>IEnumRAWINPUTDEVIC:Clone
Crea otro enumerador de dispositivo de entrada sin formato con el mismo estado que el enumerador actual para crear una iteración por la misma lista.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT Clone( [out] IEnumRAWINPUTDEVICE **ppenum);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `ppenum`  
  
 [out] Dirección de la variable de salida que recibe la [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) puntero de interfaz. Si el método es incorrecto, el valor de esta variable de salida es indefinido.  
  
## <a name="property-valuereturn-value"></a>Valor de propiedad y valor devuelto  
 HRESULT: Este método es compatible con los valores devueltos estándares E_INVALIDARG y E_OUTOFMEMORY, E_UNEXPECTED.  
  
## <a name="remarks"></a>Comentarios  
 Este método permite grabar un punto en la secuencia de enumeración con el fin de volver a ese punto en un momento posterior. El llamador debe liberar este nuevo enumerador por separado desde el primer enumerador.
