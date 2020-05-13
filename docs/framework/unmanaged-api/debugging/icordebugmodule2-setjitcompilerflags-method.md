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
ms.openlocfilehash: f73919634ba15dfd16694676d1389875fc2d79bc
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210194"
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
 de Combinación bit a bit de los valores de la enumeración [cordebugjitcompilerflags (](cordebugjitcompilerflags-enumeration.md) .  
  
## <a name="remarks"></a>Observaciones  
 Si el `dwFlags` valor no es válido, `SetJITCompilerFlags` se producirá un error en el método.  
  
 `SetJITCompilerFlags`Solo se puede llamar al método desde dentro de la devolución de llamada [ICorDebugManagedCallback:: LoadModule](icordebugmanagedcallback-loadmodule-method.md) para este módulo. Se producirá un error al intentar llamarlo después de que se haya `ICorDebugManagedCallback::LoadModule` entregado la devolución de llamada.  
  
 No se admite editar y continuar en plataformas de 64 bits o Win9x. Por consiguiente, si se llama al `SetJITCompilerFlags` método en cualquiera de estas dos plataformas con la marca CORDEBUG_JIT_ENABLE_ENC establecida en `dwFlags` , el `SetJITCompilerFlags` método y todos los métodos específicos para editar y continuar, como [ICorDebugModule2:: ApplyChanges](icordebugmodule2-applychanges-method.md), producirán un error.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
