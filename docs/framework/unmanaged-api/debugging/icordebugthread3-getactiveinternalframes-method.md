---
title: "ICorDebugThread3::GetActiveInternalFrames (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread3.GetActiveInternalFrames Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread3::GetActiveInternalFrames
helpviewer_keywords:
- ICorDebugThread3::GetActiveInternalFrames method [.NET Framework debugging]
- GetActiveInternalFrames method [.NET Framework debugging]
ms.assetid: d69796b4-5b6d-457c-85f6-2cf42e8a8773
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b9b94827ac49c69c5e72c2e300a80914774cc498
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugthread3getactiveinternalframes-method"></a>ICorDebugThread3::GetActiveInternalFrames (Método)
Devuelve una matriz de marcos internos ([ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) objetos) en la pila.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetActiveInternalFrames  
      (  
      [in] ULONG32 cInternalFrames,  
      [out] ULONG32 *pcInternalFrames,  
      [in, out,size_is(cInternalFrames), length_is(*pcInternalFrames)]  
            ICorDebugInternalFrame2 * ppInternalFrames[]  
      );  
```  
  
#### <a name="parameters"></a>Parámetros  
 `cInternalFrames`  
 [in] El número de marcos internos esperados en `ppInternalFrames`.  
  
 `pcInternalFrames`  
 [out] Un puntero a un `ULONG32` que contiene el número de marcos internos en la pila.  
  
 `ppInternalFrames`  
 [entrada, salida] Un puntero a la dirección de una matriz de marcos internos de la pila.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve los siguientes HRESULT específicos así como los errores HRESULT que indican un error del método.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El [ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) objeto se creó correctamente.|  
|E_INVALIDARG|`cInternalFrames`no es cero y `ppInternalFrames` es `null`, o `pcInternalFrames` es `null`.|  
|HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)|`ppInternalFrames`es menor que el recuento de los marcos internos.|  
  
## <a name="exceptions"></a>Excepciones  
  
## <a name="remarks"></a>Comentarios  
 Los marcos internos son estructuras de datos que se inserta en la pila en tiempo de ejecución para almacenar datos temporales.  
  
 Cuando llama `GetActiveInternalFrames`, debe establecer el `cInternalFrames` parámetro en 0 (cero) y el `ppInternalFrames` parámetro en null. Cuando `GetActiveInternalFrames` en primer lugar se devuelve, `pcInternalFrames` contiene el número de marcos internos de la pila.  
  
 `GetActiveInternalFrames`a continuación, se debe llamar una segunda vez. Debe pasar el número apropiado (`pcInternalFrames`) en el `cInternalFrames` parámetro, y especificar un puntero a una matriz de tamaño adecuado en `ppInternalFrames`.  
  
 Use la [ICorDebugStackWalk:: GetFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-getactiveinternalframes-method.md) marcos de pila del método devuelva un valor real.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
