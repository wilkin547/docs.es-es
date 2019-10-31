---
title: ICorDebugNativeFrame2::GetStackParameterSize (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame2.GetStackParameterSize Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame2::GetStackParameterSize
helpviewer_keywords:
- ICorDebugNativeFrame2::GetStackParameterSize method [.NET Framework debugging]
- GetStackParameterSize method [.NET Framework debugging]
ms.assetid: f6a449c8-a941-43ba-9a90-c98b29ae3c36
topic_type:
- apiref
ms.openlocfilehash: 4dd9760c347bbc23f3e8225c1ff748c6b7b8bfe1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73096537"
---
# <a name="icordebugnativeframe2getstackparametersize-method"></a>ICorDebugNativeFrame2::GetStackParameterSize (Método)
Devuelve el tamaño acumulado de los parámetros de la pila en los sistemas operativos x86.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetStackParameterSize([out] ULONG32 * pSize)  
```  
  
## <a name="parameters"></a>Parámetros  
 `pSize`  
 enuncia Puntero al tamaño acumulado de los parámetros de la pila.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El tamaño de la pila se devolvió correctamente.|  
|S_FALSE|se llamó a `GetStackParameterSize` en una plataforma distinta de x86.|  
|E_FAIL|`The size of the parameters could not be returned`Operador|  
|E_INVALIDARG|`pSize` es `null`.|  
  
## <a name="exceptions"></a>Excepciones  
  
## <a name="remarks"></a>Comentarios  
 Los métodos [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) no ajustan el puntero de pila para los parámetros que se insertan en la pila. En su lugar, puede usar el valor devuelto por `GetStackParameterSize` para ajustar el puntero de la pila y, de este modo, inicializar un desenredado nativo, que se ajusta para los parámetros.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugNativeFrame2 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
