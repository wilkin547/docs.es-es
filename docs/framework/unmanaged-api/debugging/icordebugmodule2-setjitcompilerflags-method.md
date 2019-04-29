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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c71ccbc62ea026a55a7e84f6925a78850594a813
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61942524"
---
# <a name="icordebugmodule2setjitcompilerflags-method"></a>ICorDebugModule2::GetJITCompilerFlags (Método)
Establece las marcas que controlan la compilación just-in-time (JIT) de este ICorDebugModule2.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT SetJITCompilerFlags (  
    [in] DWORD dwFlags  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `dwFlags`  
 [in] Una combinación bit a bit de los [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) valores de enumeración.  
  
## <a name="remarks"></a>Comentarios  
 Si el `dwFlags` valor no es válido, el `SetJITCompilerFlags` método generará un error.  
  
 El `SetJITCompilerFlags` método se puede llamar solo desde el [ICorDebugManagedCallback:: LoadModule](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadmodule-method.md) devolución de llamada para este módulo. Intenta llamar después a la `ICorDebugManagedCallback::LoadModule` devolución de llamada se ha entregado will producirá un error.  
  
 Editar y continuar no se admite en plataformas Win9x o de 64 bits. Por lo tanto, si se llama a la `SetJITCompilerFlags` método en cualquiera de estas dos plataformas con la marca de CORDEBUG_JIT_ENABLE_ENC está establecida `dwFlags`, `SetJITCompilerFlags` método y todos los métodos específicos para editar y continuar, como [ICorDebugModule2:: ApplyChanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md), se producirá un error.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
