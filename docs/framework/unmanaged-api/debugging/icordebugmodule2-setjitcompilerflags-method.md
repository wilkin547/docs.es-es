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
ms.openlocfilehash: b28e457ea0b51d320581c0fbe36574698081ea36
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792959"
---
# <a name="icordebugmodule2setjitcompilerflags-method"></a>ICorDebugModule2::GetJITCompilerFlags (Método)
Establece las marcas que controlan la compilación Just-in-Time (JIT) de este ICorDebugModule2.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetJITCompilerFlags (  
    [in] DWORD dwFlags  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `dwFlags`  
 de Combinación bit a bit de los valores de la enumeración [cordebugjitcompilerflags (](cordebugjitcompilerflags-enumeration.md) .  
  
## <a name="remarks"></a>Notas  
 Si el valor de `dwFlags` no es válido, se producirá un error en el método `SetJITCompilerFlags`.  
  
 Solo se puede llamar al método `SetJITCompilerFlags` desde dentro de la devolución de llamada [ICorDebugManagedCallback:: LoadModule](icordebugmanagedcallback-loadmodule-method.md) para este módulo. Se producirá un error al intentar llamarlo después de que se haya entregado el `ICorDebugManagedCallback::LoadModule` devolución de llamada.  
  
 No se admite editar y continuar en plataformas de 64 bits o Win9x. Por lo tanto, si se llama al método `SetJITCompilerFlags` en cualquiera de estas dos plataformas con la marca CORDEBUG_JIT_ENABLE_ENC establecida en `dwFlags`, se producirá un error en el método `SetJITCompilerFlags` y en todos los métodos específicos para editar y continuar, como [ICorDebugModule2:: ApplyChanges](icordebugmodule2-applychanges-method.md).  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
