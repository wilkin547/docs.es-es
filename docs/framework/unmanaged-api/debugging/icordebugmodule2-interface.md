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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 192f2476aff91d3a8302d070852ab2a3722d137c
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56970134"
---
# <a name="icordebugmodule2-interface"></a>ICorDebugModule2 (Interfaz)

Actúa como una extensión lógica ICorDebugModule (interfaz).  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[ApplyChanges (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md)|Aplica los cambios en los metadatos y los cambios en el código de lenguaje intermedio (MSIL) de Microsoft a los procesos en ejecución.|  
|[GetJITCompilerFlags (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-getjitcompilerflags-method.md)|Obtiene las marcas que controlan la compilación just-in-time (JIT) para esta `ICorDebugModule2`.|  
|[ResolveAssembly (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-resolveassembly-method.md)|Resuelve el ensamblado al que hace referencia el token de metadatos especificado.|  
|[SetJITCompilerFlags (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjitcompilerflags-method.md)|Establece las marcas que controlan la compilación JIT para esta `ICorDebugModule2`.|  
|[SetJMCStatus (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjmcstatus-method.md)|Establece el estado de "sólo mi código" (JMC) de todos los métodos de todas las clases en este `ICorDebugModule2` en el valor especificado, excepto aquellos en los `pTokens` matriz, que establece en el valor opuesto.|  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
>  Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
