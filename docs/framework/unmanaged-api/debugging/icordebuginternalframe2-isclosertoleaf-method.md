---
title: ICorDebugInternalFrame2::IsCloserToLeaf (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame2.IsCloserToLeaf Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame2::IsCloserToLeaf
helpviewer_keywords:
- ICorDebugInternalFrame2::IsCloserToLeaf method [.NET Framework debugging]
- IsCloserToLeaf method [.NET Framework debugging]
ms.assetid: c1d3d1eb-8370-4f25-8297-3bd262b4740a
topic_type:
- apiref
ms.openlocfilehash: 83d3eda0f3c4619ec7a5df91d13ab9f3a58e5f01
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721353"
---
# <a name="icordebuginternalframe2isclosertoleaf-method"></a>ICorDebugInternalFrame2::IsCloserToLeaf (Método)

Comprueba si el `this` marco interno está más cerca de la hoja que el objeto ICorDebugFrame especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT IsCloserToLeaf([in] ICorDebugFrame * pFrameToCompare,  
                       [out] BOOL * pIsCloser);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pFrameToCompare`  
 de Puntero al objeto de comparación `ICorDebugFrame` .  
  
 `pIsCloser`  
 [out] `true` Si el `this` marco interno está más cerca de la hoja que el marco especificado por `pFrameToCompare` ; de lo contrario, `false` .  
  
## <a name="return-value"></a>Valor devuelto  

 Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|La comparación se realizó correctamente.|  
|E_FAIL|No se pudo realizar la comparación.|  
|E_INVALIDARG|`pFrameToCompare` o `pIsCloser` es null.|  
  
## <a name="remarks"></a>Comentarios  

 `IsCloserToLeaf` se puede usar para implementar una directiva para intercalar Marcos internos con otros marcos en la pila.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorDebugInternalFrame2 (Interfaz)](icordebuginternalframe2-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
- [Depuración](index.md)
