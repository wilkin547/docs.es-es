---
title: ICorDebugThread3::CreateStackWalk (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugThread3.CreateStackWalk Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread3::CreateStackWalk
helpviewer_keywords:
- CreateStackWalk method [.NET Framework debugging]
- ICorDebugThread3::CreateStackWalk method [.NET Framework debugging]
ms.assetid: c55e35d9-f9aa-4268-94b5-dce44c61acf2
topic_type:
- apiref
ms.openlocfilehash: ca5db8c8570cedd9b0412b71058d453112a1831c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140131"
---
# <a name="icordebugthread3createstackwalk-method"></a>ICorDebugThread3::CreateStackWalk (Método)
Crea un objeto [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) para el subproceso cuya pila desea desenredar.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CreateStackWalk([out] ICorDebugStackWalk **ppStackWalk);  
```  
  
## <a name="parameters"></a>Parámetros  
 `ppStackWalk`  
 enuncia Puntero a la dirección del objeto [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) para el subproceso cuya pila desea desenredar.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El objeto de `ICorDebugStackWalk` se ha creado correctamente.|  
|E_FAIL|No se creó el objeto de `ICorDebugStackWalk`.|  
  
## <a name="exceptions"></a>Excepciones  
  
## <a name="remarks"></a>Comentarios  
 Si el método de `CreateStackWalk` se ejecuta correctamente, el contexto del objeto de `ICorDebugStackWalk` devuelto se establece en el contexto actual del subproceso.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
