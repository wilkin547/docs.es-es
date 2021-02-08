---
description: 'Más información sobre: ICorDebugThread3:: GetActiveInternalFrames ((método)'
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
ms.openlocfilehash: f228dd84708478bb364ac09407a68df3e8d971b6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800986"
---
# <a name="icordebugthread3getactiveinternalframes-method"></a>ICorDebugThread3::GetActiveInternalFrames (Método)

Devuelve una matriz de Marcos internos (objetos[ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) ) en la pila.  
  
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
 de Número de fotogramas internos esperados en `ppInternalFrames` .  
  
 `pcInternalFrames`  
 enuncia Un puntero a un `ULONG32` valor de que contiene el número de Marcos internos de la pila.  
  
 `ppInternalFrames`  
 [in, out] Puntero a la dirección de una matriz de Marcos internos de la pila.  
  
## <a name="return-value"></a>Valor devuelto  

 Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El objeto [ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) se ha creado correctamente.|  
|E_INVALIDARG|`cInternalFrames` no es cero y `ppInternalFrames` es `null` , o `pcInternalFrames` es `null` .|  
|HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)|`ppInternalFrames` es menor que el número de Marcos internos.|  
  
## <a name="exceptions"></a>Excepciones  
  
## <a name="remarks"></a>Notas  

 Los marcos internos son estructuras de datos insertadas en la pila por el motor en tiempo de ejecución para almacenar datos temporales.  
  
 Cuando se llama por primera vez `GetActiveInternalFrames` , se debe establecer el `cInternalFrames` parámetro en 0 (cero) y el `ppInternalFrames` parámetro en NULL. Cuando se `GetActiveInternalFrames` devuelve por primera vez, `pcInternalFrames` contiene el recuento de los marcos internos de la pila.  
  
 `GetActiveInternalFrames` a continuación, debe llamarse una segunda vez. Debe pasar el recuento adecuado ( `pcInternalFrames` ) en el `cInternalFrames` parámetro y especificar un puntero a una matriz de tamaño adecuado en `ppInternalFrames` .  
  
 Use el método [ICorDebugStackWalk:: GetFrame](icordebugthread3-getactiveinternalframes-method.md) para devolver los marcos de pila reales.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces para depuración](debugging-interfaces.md)
- [Depuración](index.md)
