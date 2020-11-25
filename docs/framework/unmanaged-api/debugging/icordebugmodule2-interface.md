---
title: Interfaz ICorDebugModule2
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
ms.openlocfilehash: 2b8e6048dd6b8df71ac3dddcc4397f6d512127c7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695886"
---
# <a name="icordebugmodule2-interface"></a>Interfaz ICorDebugModule2

Actúa como una extensión lógica de la interfaz ICorDebugModule.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método ApplyChanges](icordebugmodule2-applychanges-method.md)|Aplica los cambios en los metadatos y los cambios en el código del lenguaje intermedio de Microsoft (MSIL) al proceso en ejecución.|  
|[Método GetJITCompilerFlags](icordebugmodule2-getjitcompilerflags-method.md)|Obtiene las marcas que controlan la compilación Just-in-Time (JIT) para este `ICorDebugModule2` .|  
|[Método ResolveAssembly](icordebugmodule2-resolveassembly-method.md)|Resuelve el ensamblado al que hace referencia el token de metadatos especificado.|  
|[Método SetJITCompilerFlags](icordebugmodule2-setjitcompilerflags-method.md)|Establece las marcas que controlan la compilación JIT para este `ICorDebugModule2` .|  
|[SetJMCStatus (Método)](icordebugmodule2-setjmcstatus-method.md)|Establece el Estado Solo mi código (JMC) de todos los métodos de todas las clases de este en `ICorDebugModule2` el valor especificado, excepto los de la `pTokens` matriz, que establece en el valor opuesto.|  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaces para depuración](debugging-interfaces.md)
