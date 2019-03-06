---
title: IEnumRAWINPUTDEVIC:Clone
ms.date: 03/30/2017
helpviewer_keywords:
- Clone method [WPF]
ms.assetid: 2a6a1900-aa55-45fa-9382-241d569a2dc4
ms.openlocfilehash: a4c5e7db813089d1dd138416ac54dd4be467b87b
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57355027"
---
# <a name="ienumrawinputdevicclone"></a>IEnumRAWINPUTDEVIC:Clone
Crea otro enumerador de dispositivo de entrada sin formato con el mismo estado que el enumerador actual para crear una iteración por la misma lista.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT Clone( [out] IEnumRAWINPUTDEVICE **ppenum);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `ppenum`  
  
 [out] Dirección de variable de salida que recibe el [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) puntero de interfaz. Si el método se realiza correctamente, el valor de esta variable de salida es indefinido.  
  
## <a name="property-valuereturn-value"></a>Valor de propiedad y valor devuelto  
 HRESULT: Este método admite los valores devueltos estándar E_INVALIDARG y E_OUTOFMEMORY, E_UNEXPECTED.  
  
## <a name="remarks"></a>Comentarios  
 Este método permite registrar un punto en la secuencia de enumeración con el fin de volver a ese punto en un momento posterior. El llamador debe liberar este nuevo enumerador por separado desde el primer enumerador.
