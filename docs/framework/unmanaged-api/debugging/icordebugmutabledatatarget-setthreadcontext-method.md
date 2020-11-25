---
title: ICorDebugMutableDataTarget::SetThreadContext (método)
ms.date: 03/30/2017
ms.assetid: 8c0d01d5-67e5-4522-9ccf-c8f3a78cb4fd
ms.openlocfilehash: 558a1ee2eb0ac06213c2ebcebbd5595b69ecc43e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695715"
---
# <a name="icordebugmutabledatatargetsetthreadcontext-method"></a>ICorDebugMutableDataTarget::SetThreadContext (método)

Establece el contexto (valores de registro) para un subproceso.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
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

 El método `SetThreadContext` actualiza el contexto actual para el subproceso especificado por el argumento `dwThreadID` definido por el sistema operativo. El formato del registro de contexto viene determinado por la plataforma indicada por el método [ICorDebugDataTarget:: GetPlatform (](icordebugdatatarget-getplatform-method.md) . En Windows, se trata de una estructura de [contexto](/windows/win32/api/winnt/ns-winnt-arm64_nt_context) .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaz ICorDebugMutableDataTarget](icordebugmutabledatatarget-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
