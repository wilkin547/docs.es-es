---
title: ICorDebugRegisterSet::GetThreadContext (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.GetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::GetThreadContext
helpviewer_keywords:
- GetThreadContext method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::GetThreadContext method [.NET Framework debugging]
ms.assetid: 0f63400b-dc1c-48d6-b51a-75c3f7f28e03
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 668b3849af9be24e019dc472a0b80067f0e1e0c1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54612741"
---
# <a name="icordebugregistersetgetthreadcontext-method"></a>ICorDebugRegisterSet::GetThreadContext (Método)
Obtiene el contexto del subproceso actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetThreadContext(  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize),  
        size_is(contextSize)] BYTE context[]  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `contextSize`  
 [in] El tamaño, en bytes, de la `context` matriz.  
  
 `context`  
 [in, out] Una matriz de bytes que componen el Win32 `CONTEXT` estructura para la plataforma actual.  
  
## <a name="remarks"></a>Comentarios  
 El depurador debe llamar a esta función en lugar de Win32 `GetThreadContext` funcione, porque el subproceso puede encontrarse en un estado de "secuestro" donde su contexto cambió temporalmente. Los datos devueltos son Win32 `CONTEXT` estructura para la plataforma actual.  
  
 Para los marcos no hoja, los clientes deberían comprobar qué registros son válidos mediante el uso de [GetRegistersAvailable](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [ICorDebugRegisterSet (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
- [ICorDebugRegisterSet2 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
