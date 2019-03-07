---
title: IEnumRAWINPUTDEVIC:Clone
ms.date: 03/30/2017
helpviewer_keywords:
- Clone method [WPF]
ms.assetid: 2a6a1900-aa55-45fa-9382-241d569a2dc4
ms.openlocfilehash: abc8a6e4780c8fe50afcf1b04f7e14aeb6452704
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485413"
---
# <a name="ienumrawinputdevicclone"></a>IEnumRAWINPUTDEVIC:Clone
Crea otro enumerador de dispositivo de entrada sin formato con el mismo estado que el enumerador actual para crear una iteración por la misma lista.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT Clone( [out] IEnumRAWINPUTDEVICE **ppenum);  
```  
  
## <a name="parameters"></a>Parámetros  
 `ppenum`  
  
 [out] Dirección de variable de salida que recibe el [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) puntero de interfaz. Si el método se realiza correctamente, el valor de esta variable de salida es indefinido.  
  
## <a name="property-valuereturn-value"></a>Valor de propiedad y valor devuelto  
 HRESULT: Este método admite los valores devueltos estándar E_INVALIDARG y E_OUTOFMEMORY, E_UNEXPECTED.  
  
## <a name="remarks"></a>Comentarios  
 Este método permite registrar un punto en la secuencia de enumeración con el fin de volver a ese punto en un momento posterior. El llamador debe liberar este nuevo enumerador por separado desde el primer enumerador.
