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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 30a9d26283d4f544bdd865e40cfc1c1c625ae462
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995506"
---
# <a name="icordebuginternalframe2isclosertoleaf-method"></a>ICorDebugInternalFrame2::IsCloserToLeaf (Método)
Comprueba si el `this` marco interno está más cerca de la hoja que el objeto ICorDebugFrame especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT IsCloserToLeaf([in] ICorDebugFrame * pFrameToCompare,  
                       [out] BOOL * pIsCloser);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pFrameToCompare`  
 [in] Un puntero a la comparación `ICorDebugFrame` objeto.  
  
 `pIsCloser`  
 [out] `true` si el `this` marco interno está más cerca de la hoja que el intervalo especificado por `pFrameToCompare`; en caso contrario, `false`.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|La comparación se realizó correctamente.|  
|E_FAIL|No se pudo realizar la comparación.|  
|E_INVALIDARG|`pFrameToCompare` o `pIsCloser` es null.|  
  
## <a name="remarks"></a>Comentarios  
 `IsCloserToLeaf` puede utilizarse para implementar una directiva para una intercalación de los marcos internos con otros marcos de la pila.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugInternalFrame2 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
