---
title: ICorDebugMutableDataTarget::SetThreadContext (método)
ms.date: 03/30/2017
ms.assetid: 8c0d01d5-67e5-4522-9ccf-c8f3a78cb4fd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cbbe4dcec29ba85c64b6e22a4348c56e80daf623
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479199"
---
# <a name="icordebugmutabledatatargetsetthreadcontext-method"></a>ICorDebugMutableDataTarget::SetThreadContext (método)
Establece el contexto (valores de registro) para un subproceso.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT SetThreadContext(  
   [in] DWORD dwThreadID,  
   [in] ULONG32 contextSize,   [in, size_is(contextSize)] const BYTE * pContext);  
```  
  
## <a name="parameters"></a>Parámetros  
 `dwThreadID`  
 [in] Identificador de subproceso definido por el sistema operativo.  
  
 `contextSize`  
 [in] Tamaño del búfer `pContext` que se va a escribir.  
  
 `pContext`  
 [in] Puntero a los bytes que se van a escribir.  
  
## <a name="remarks"></a>Comentarios  
 El método `SetThreadContext` actualiza el contexto actual para el subproceso especificado por el argumento `dwThreadID` definido por el sistema operativo. El formato del registro de contexto viene determinada por la plataforma que indica la [ICorDebugDataTarget:: GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) método. En Windows, se trata de un [contexto](/windows/desktop/api/winnt/ns-winnt-_arm64_nt_context) estructura.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [ICorDebugMutableDataTarget (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
