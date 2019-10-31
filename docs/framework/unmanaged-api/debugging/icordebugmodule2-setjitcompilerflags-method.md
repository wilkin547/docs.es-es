---
title: ICorDebugModule2::GetJITCompilerFlags (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.SetJITCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::SetJITCompilerFlags
helpviewer_keywords:
- ICorDebugModule2::SetJITCompilerFlags method [.NET Framework debugging]
- SetJITCompilerFlags method [.NET Framework debugging]
ms.assetid: ea574c84-c622-4589-9a14-b55771af5e06
topic_type:
- apiref
ms.openlocfilehash: 2358cee1b3a9aa50fb1f0e61d558f164a39aa86c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137363"
---
# <a name="icordebugmodule2setjitcompilerflags-method"></a>ICorDebugModule2::GetJITCompilerFlags (Método)
Establece las marcas que controlan la compilación Just-in-Time (JIT) de este ICorDebugModule2.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetJITCompilerFlags (  
    [in] DWORD dwFlags  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `dwFlags`  
 de Combinación bit a bit de los valores de la enumeración [cordebugjitcompilerflags (](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) .  
  
## <a name="remarks"></a>Comentarios  
 Si el valor de `dwFlags` no es válido, se producirá un error en el método `SetJITCompilerFlags`.  
  
 Solo se puede llamar al método `SetJITCompilerFlags` desde dentro de la devolución de llamada [ICorDebugManagedCallback:: LoadModule](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadmodule-method.md) para este módulo. Se producirá un error al intentar llamarlo después de que se haya entregado el `ICorDebugManagedCallback::LoadModule` devolución de llamada.  
  
 No se admite editar y continuar en plataformas de 64 bits o Win9x. Por lo tanto, si se llama al método `SetJITCompilerFlags` en cualquiera de estas dos plataformas con la marca CORDEBUG_JIT_ENABLE_ENC establecida en `dwFlags`, se producirá un error en el método `SetJITCompilerFlags` y en todos los métodos específicos para editar y continuar, como [ICorDebugModule2:: ApplyChanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
