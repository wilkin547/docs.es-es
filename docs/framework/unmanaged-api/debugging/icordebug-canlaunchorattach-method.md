---
title: ICorDebug::CanLaunchOrAttach (Método)
ms.date: 03/30/2017
api_name:
- ICorDebug.CanLaunchOrAttach
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::CanLaunchOrAttach
helpviewer_keywords:
- ICorDebug::CanLaunchOrAttach method [.NET Framework debugging]
- CanLaunchOrAttach method [.NET Framework debugging]
ms.assetid: ca7723db-7c07-4cdd-bd92-fba34928b623
topic_type:
- apiref
ms.openlocfilehash: 805f9a5d1f2590a06bfa929c152bdfd13900531a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134281"
---
# <a name="icordebugcanlaunchorattach-method"></a>ICorDebug::CanLaunchOrAttach (Método)
Devuelve un valor HRESULT que indica si el inicio de un nuevo proceso o la asociación al proceso existente especificado es posible en el contexto del equipo actual y de la configuración en tiempo de ejecución.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CanLaunchOrAttach (  
    [in] DWORD      dwProcessId,  
    [in] BOOL       win32DebuggingEnabled  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `dwProcessId`  
 de IDENTIFICADOR de un proceso existente.  
  
 `win32DebuggingEnabled`  
 de Pase `true` si tiene previsto iniciar con la depuración de Win32 habilitada o para asociarla con la depuración de Win32 habilitada; de lo contrario, pase `false`.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si los servicios de depuración determinan que es posible iniciar un nuevo proceso o asociarse al proceso dado, dada la información sobre la configuración del equipo y el tiempo de ejecución actual. Los valores HRESULT posibles son:  
  
- S_OK  
  
- CORDBG_E_DEBUGGING_NOT_POSSIBLE  
  
- CORDBG_E_KERNEL_DEBUGGER_PRESENT  
  
- CORDBG_E_KERNEL_DEBUGGER_ENABLED  
  
## <a name="remarks"></a>Comentarios  
 Este método es meramente informativo. La interfaz no impedirá que se inicie o se adjunte a un proceso, independientemente del valor devuelto por `CanLaunchOrAttach`.  
  
 Si planea iniciar con la depuración de Win32 habilitada o asociarla con la depuración de Win32 habilitada, pase `true` para `win32DebuggingEnabled`. El valor HRESULT devuelto por `CanLaunchOrAttach` podría diferir si se usa esta opción.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebug (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
