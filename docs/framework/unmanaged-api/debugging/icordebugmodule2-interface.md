---
title: ICorDebugModule2 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugModule2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2
helpviewer_keywords:
- ICorDebugModule2 interface [.NET Framework debugging]
ms.assetid: 0847e64f-fdbe-4c96-8168-da20fdc84d80
topic_type:
- apiref
ms.openlocfilehash: a3a1b658f4ab05c7029de907882fe5ab2513ccd8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127881"
---
# <a name="icordebugmodule2-interface"></a>ICorDebugModule2 (Interfaz)

Actúa como una extensión lógica de la interfaz ICorDebugModule.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[ApplyChanges (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md)|Aplica los cambios en los metadatos y los cambios en el código del lenguaje intermedio de Microsoft (MSIL) al proceso en ejecución.|  
|[GetJITCompilerFlags (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-getjitcompilerflags-method.md)|Obtiene las marcas que controlan la compilación Just-in-Time (JIT) para esta `ICorDebugModule2`.|  
|[ResolveAssembly (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-resolveassembly-method.md)|Resuelve el ensamblado al que hace referencia el token de metadatos especificado.|  
|[SetJITCompilerFlags (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjitcompilerflags-method.md)|Establece las marcas que controlan la compilación JIT para esta `ICorDebugModule2`.|  
|[SetJMCStatus (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjmcstatus-method.md)|Establece el Estado Solo mi código (JMC) de todos los métodos de todas las clases de este `ICorDebugModule2` en el valor especificado, excepto en los de la matriz `pTokens`, que establece en el valor opuesto.|  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
