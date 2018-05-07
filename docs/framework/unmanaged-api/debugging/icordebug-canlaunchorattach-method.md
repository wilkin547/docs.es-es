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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f86cc83936dd8150ca6b3f28c9b6a624278e2b36
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugcanlaunchorattach-method"></a>ICorDebug::CanLaunchOrAttach (Método)
Devuelve un valor HRESULT que indica si iniciar un nuevo proceso o asociarse al proceso especificado existente es posible en el contexto de la configuración de máquina y en tiempo de ejecución actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT CanLaunchOrAttach (  
    [in] DWORD      dwProcessId,  
    [in] BOOL       win32DebuggingEnabled  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `dwProcessId`  
 [in] El identificador de un proceso existente.  
  
 `win32DebuggingEnabled`  
 [in] Pasar `true` si va a iniciar con depuración de Win32 habilitada, o para asociar con la depuración de Win32 habilitada; en caso contrario, pase `false`.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si determinan los servicios de depuración que inicie un nuevo proceso o asociarse al proceso determinado es posible que, dada la información sobre la configuración de máquina y en tiempo de ejecución actual. Valores HRESULT posibles son:  
  
-   S_OK  
  
-   CORDBG_E_DEBUGGING_NOT_POSSIBLE  
  
-   CORDBG_E_KERNEL_DEBUGGER_PRESENT  
  
-   CORDBG_E_KERNEL_DEBUGGER_ENABLED  
  
## <a name="remarks"></a>Comentarios  
 Este método es meramente informativo. La interfaz no detendrá de iniciar o asociar a un proceso, independientemente del valor devuelto por `CanLaunchOrAttach`.  
  
 Si tiene previsto iniciar con depuración de Win32 habilitada o conectar con la depuración de Win32 habilitada, pasar `true` para `win32DebuggingEnabled`. El valor HRESULT devuelto por `CanLaunchOrAttach` pueden diferir si utiliza esta opción.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorDebug (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
