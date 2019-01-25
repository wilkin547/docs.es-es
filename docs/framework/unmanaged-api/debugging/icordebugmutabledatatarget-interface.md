---
title: ICorDebugMutableDataTarget (Interfaz)
ms.date: 03/30/2017
ms.assetid: 14aad5b3-84ab-4bbc-94e3-1eb92e258d10
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f63343b43481d1d91d1db30cd2ace3214c5590a9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54492304"
---
# <a name="icordebugmutabledatatarget-interface"></a>ICorDebugMutableDataTarget (Interfaz)
Extiende la [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interfaz para admitir destinos de datos mutables.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[ContinueStatusChanged (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-continuestatuschanged-method.md)|Cambia el estado de continuación para el evento de depuración pendiente en el subproceso especificado.|  
|[SetThreadContext (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-setthreadcontext-method.md)|Establece el contexto (valores de registro) para un subproceso.|  
|[WriteVirtual (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-writevirtual-method.md)|Escribe la memoria en el espacio de direcciones de procesos de destino.|  
  
## <a name="remarks"></a>Comentarios  
 Esta extensión a la [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interfaz puede implementarse mediante herramientas de depuración que desea modificar el proceso de destino (por ejemplo, para realizar una depuración invasiva en directo).  
  
 Todos estos métodos son opcionales en el sentido de que, si no se implementa esta interfaz o en caso de error en las llamadas a estos métodos, no se pierde ninguna funcionalidad de depuración basada en una inspección principal.  Cualquier error `HRESULT` de estos métodos se propaga como el `HRESULT` de la llamada al método ICorDebug.  
  
 Tenga en cuenta que una sola llamada al método ICorDebug puede provocar diversas mutaciones y que no hay ningún mecanismo que garantice que las mutaciones relativas se aplican de forma transaccional (todas-o-ninguna).  Es decir, si una mutación produce un error después de que otras mutaciones (para la misma llamada ICorDebug) se hayan realizado correctamente, el proceso de destino podría quedarse en un estado incoherente y la depuración podría dejar de ser confiable.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
