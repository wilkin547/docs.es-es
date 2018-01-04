---
title: "ICorDebugRemote::DebugActiveProcessEx (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugRemote.DebugActiveProcessEx
api_location: CorDebug.dll
api_type: COM
f1_keywords: ICorDebugRemoteTarget::DebugActiveProcessEx
helpviewer_keywords:
- ICorDebugRemote::DebugActiveProcessEx method [.NET Framework debugging]
- DebugActiveProcessEx method, ICorDebugRemote interface [.NET Framework debugging]
ms.assetid: b0df5c5d-9a2e-47bf-894c-6f8a9fe24a1f
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 09bc98b477231eb1466300451585f4569aff222c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
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
  
#### <a name="parameters"></a>Parámetros  
 `pRemoteTarget`  
 [in] Puntero a un [ICorDebugRemoteTarget (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md). Este parámetro se utiliza para determinar la máquina en que se ejecuta el proceso.  
  
 `id`  
 [in] El identificador del proceso al que va a adjuntar el depurador.  
  
 `win32Attach`  
 [in] `true` si el depurador debe comportarse como el depurador de Win32 para el proceso y envía las devoluciones de llamada no administradas; en caso contrario, `false`.  
  
 `ppProcess`  
 [out] Un puntero a la dirección de un objeto de "ICorDebugProcess" que representa el proceso al que se ha adjuntado el depurador.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK  
 Se conectó correctamente al proceso en el equipo remoto.  
  
 E_FAIL (u otros códigos devueltos de E_)  
 No se puede asociar al proceso en el equipo remoto.  
  
## <a name="remarks"></a>Comentarios  
 No se admite la depuración en modo mixto en Silverlight.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** 4.5, 4, 3.5 SP1  
  
## <a name="see-also"></a>Vea también  
 [ICorDebugRemote (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)  
 [ICorDebug (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
    
 [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
