---
title: Interfaz ICorDebugMutableDataTarget
ms.date: 03/30/2017
ms.assetid: 14aad5b3-84ab-4bbc-94e3-1eb92e258d10
ms.openlocfilehash: fcf7521f8261c8f8f84c7a9a9deb4b7a7d739c6e
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210012"
---
# <a name="icordebugmutabledatatarget-interface"></a>Interfaz ICorDebugMutableDataTarget
Extiende la interfaz [ICorDebugDataTarget](icordebugdatatarget-interface.md) para admitir destinos de datos mutables.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método ContinueStatusChanged](icordebugmutabledatatarget-continuestatuschanged-method.md)|Cambia el estado de continuación para el evento de depuración pendiente en el subproceso especificado.|  
|[Método SetThreadContext](icordebugmutabledatatarget-setthreadcontext-method.md)|Establece el contexto (valores de registro) para un subproceso.|  
|[Método WriteVirtual](icordebugmutabledatatarget-writevirtual-method.md)|Escribe la memoria en el espacio de direcciones de procesos de destino.|  
  
## <a name="remarks"></a>Observaciones  
 Esta extensión de la interfaz [ICorDebugDataTarget](icordebugdatatarget-interface.md) se puede implementar mediante herramientas de depuración que deseen modificar el proceso de destino (por ejemplo, para realizar una depuración invasiva en directo).  
  
 Todos estos métodos son opcionales en el sentido de que, si no se implementa esta interfaz o en caso de error en las llamadas a estos métodos, no se pierde ninguna funcionalidad de depuración basada en una inspección principal.  Cualquier error `HRESULT` de estos métodos se propaga como el `HRESULT` de la llamada al método ICorDebug.  
  
 Tenga en cuenta que una sola llamada al método ICorDebug puede provocar diversas mutaciones y que no hay ningún mecanismo que garantice que las mutaciones relativas se aplican de forma transaccional (todas-o-ninguna).  Es decir, si una mutación produce un error después de que otras mutaciones (para la misma llamada ICorDebug) se hayan realizado correctamente, el proceso de destino podría quedarse en un estado incoherente y la depuración podría dejar de ser confiable.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaces para depuración](debugging-interfaces.md)
- [Depuración](index.md)
