---
title: ICorDebugThread3::GetActiveInternalFrames (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugThread3.GetActiveInternalFrames Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread3::GetActiveInternalFrames
helpviewer_keywords:
- ICorDebugThread3::GetActiveInternalFrames method [.NET Framework debugging]
- GetActiveInternalFrames method [.NET Framework debugging]
ms.assetid: d69796b4-5b6d-457c-85f6-2cf42e8a8773
topic_type:
- apiref
ms.openlocfilehash: 680af5afa3ebef5bcaf9e34580e421dcc8093aaf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178467"
---
# <a name="icordebugthread3getactiveinternalframes-method"></a>ICorDebugThread3::GetActiveInternalFrames (Método)
Devuelve una matriz de marcos internos[(ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) objetos) en la pila.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp
HRESULT GetActiveInternalFrames  
      (  
      [in] ULONG32 cInternalFrames,  
      [out] ULONG32 *pcInternalFrames,  
      [in, out,size_is(cInternalFrames), length_is(*pcInternalFrames)]  
            ICorDebugInternalFrame2 * ppInternalFrames[]  
      );  
```  
  
## <a name="parameters"></a>Parámetros  
 `cInternalFrames`  
 [en] El número de fotogramas internos esperados en `ppInternalFrames`.  
  
 `pcInternalFrames`  
 [fuera] Puntero a `ULONG32` un que contiene el número de fotogramas internos de la pila.  
  
 `ppInternalFrames`  
 [adentro, fuera] Puntero a la dirección de una matriz de fotogramas internos en la pila.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El [ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) objeto se creó correctamente.|  
|E_INVALIDARG|`cInternalFrames`no es `ppInternalFrames` cero `null`y `pcInternalFrames` `null`es, o es .|  
|HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)|`ppInternalFrames`es menor que el recuento de fotogramas internos.|  
  
## <a name="exceptions"></a>Excepciones  
  
## <a name="remarks"></a>Observaciones  
 Los marcos internos son estructuras de datos insertadas en la pila por el tiempo de ejecución para almacenar datos temporales.  
  
 La primera `GetActiveInternalFrames`llamada, debe `cInternalFrames` establecer el parámetro en `ppInternalFrames` 0 (cero) y el parámetro en null. Cuando `GetActiveInternalFrames` se `pcInternalFrames` devuelve por primera vez, contiene el recuento de los fotogramas internos de la pila.  
  
 `GetActiveInternalFrames`entonces debe ser llamado una segunda vez. Debe pasar el recuento`pcInternalFrames`adecuado `cInternalFrames` ( ) en el parámetro y especificar `ppInternalFrames`un puntero a una matriz de tamaño adecuado en .  
  
 Utilice el [método ICorDebugStackWalk::GetFrame](icordebugthread3-getactiveinternalframes-method.md) para devolver marcos de pila reales.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaces de depuración](debugging-interfaces.md)
- [Depuración](index.md)
