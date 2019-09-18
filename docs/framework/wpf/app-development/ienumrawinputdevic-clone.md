---
title: IEnumRAWINPUTDEVIC:Clone
ms.date: 03/30/2017
helpviewer_keywords:
- Clone method [WPF]
ms.assetid: 2a6a1900-aa55-45fa-9382-241d569a2dc4
ms.openlocfilehash: cd634b4d4a88d83d425b787ed8493f9aa2504988
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053420"
---
# <a name="ienumrawinputdevicclone"></a>IEnumRAWINPUTDEVIC:Clone
Crea otro enumerador de dispositivo de entrada sin formato con el mismo estado que el enumerador actual para crear una iteración por la misma lista.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT Clone( [out] IEnumRAWINPUTDEVICE **ppenum);  
```  
  
## <a name="parameters"></a>Parámetros  
 `ppenum`  
  
 enuncia Dirección de la variable de salida que recibe el puntero de la interfaz [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) . Si el método no se realiza correctamente, el valor de esta variable de salida es indefinido.  
  
## <a name="property-valuereturn-value"></a>Valor de propiedad y valor devuelto  
 HRESULT: Este método admite los valores devueltos estándar E_INVALIDARG, E_OUTOFMEMORY y E_UNEXPECTED.  
  
## <a name="remarks"></a>Comentarios  
 Este método permite grabar un punto en la secuencia de enumeración para volver a ese punto en un momento posterior. El llamador debe liberar este nuevo enumerador por separado del primer enumerador.
