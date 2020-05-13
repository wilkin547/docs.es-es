---
title: ICorDebugMutableDataTarget::ContinueStatusChanged (método)
ms.date: 03/30/2017
ms.assetid: 5a66d3f4-dd16-4d62-9dcc-0eab7041d894
ms.openlocfilehash: 49f517c0c09771ce86e43b801f6d7fce695d907a
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213314"
---
# <a name="icordebugmutabledatatargetcontinuestatuschanged-method"></a>ICorDebugMutableDataTarget::ContinueStatusChanged (método)
Cambia el estado de continuación para el evento de depuración pendiente en el subproceso especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ContinueStatusChanged(  
   [in] DWORD dwThreadId,  
   [in] CORDB_CONTINUE_STATUS continueStatus);  
```  
  
## <a name="parameters"></a>Parámetros  
 `dwThreadId`  
 Identificador de subproceso definido por el sistema operativo.  
  
 `continueStatus`  
 Valor [COREDB_CONTINUE_STATUS](../common-data-types-unmanaged-api-reference.md) que representa el nuevo estado de continuación solicitado.  
  
## <a name="remarks"></a>Observaciones  
 El depurador llama al método `ContinueStatusChanged` cuando llama a un método ICorDebug que requiere que el evento de depuración actual se trate de una manera potencialmente diferente al modo en que se suele tratar. Por ejemplo, si hay una excepción pendiente y el depurador solicita una operación que cancelará la excepción (como [ICorDebugILFrame::SetIP](icordebugilframe-setip-method.md) o `FuncEval`), esta API se usa para solicitar que se cancele la excepción.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaz ICorDebugMutableDataTarget](icordebugmutabledatatarget-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
