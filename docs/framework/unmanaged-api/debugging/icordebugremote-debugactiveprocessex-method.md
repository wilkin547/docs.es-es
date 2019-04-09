---
title: ICorDebugRemote::DebugActiveProcessEx (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugRemote.DebugActiveProcessEx
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget::DebugActiveProcessEx
helpviewer_keywords:
- ICorDebugRemote::DebugActiveProcessEx method [.NET Framework debugging]
- DebugActiveProcessEx method, ICorDebugRemote interface [.NET Framework debugging]
ms.assetid: b0df5c5d-9a2e-47bf-894c-6f8a9fe24a1f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 45b919d90454c9424cadb1d4dfc3b0dfb09e5053
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59209455"
---
# <a name="icordebugremotedebugactiveprocessex-method"></a>ICorDebugRemote::DebugActiveProcessEx (Método)
Inicia un proceso en un equipo remoto en el depurador.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT DebugActiveProcessEx (  
    [in]  ICorDebugRemoteTarget *   pRemoteTarget,  
    [in]  DWORD                     dwProcessId,  
    [in]  BOOL                      fWin32Attach,  
    [out] ICorDebugProcess **       ppProcess  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pRemoteTarget`  
 [in] Puntero a un [ICorDebugRemoteTarget (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md). Este parámetro se usa para determinar la máquina donde se ejecuta el proceso.  
  
 `id`  
 [in] El identificador del proceso al que va a adjuntar el depurador.  
  
 `win32Attach`  
 [in] `true` si el depurador debe comportarse como el depurador de Win32 para el proceso y enviar las devoluciones de llamada no administradas; en caso contrario, `false`.  
  
 `ppProcess`  
 [out] Un puntero a la dirección de un objeto "ICorDebugProcess" que representa el proceso al que se ha vinculado el depurador.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK  
 Se conectó correctamente al proceso en el equipo remoto.  
  
 E_FAIL (u otros códigos devueltos de E_)  
 No se puede asociar al proceso en el equipo remoto.  
  
## <a name="remarks"></a>Comentarios  
 No se admite la depuración en modo mixto en Silverlight.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** 4.5, 4, 3.5 SP1  
  
## <a name="see-also"></a>Vea también

- [ICorDebugRemote (Interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)
- [ICorDebug (Interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [Interfaces para depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
