---
title: ICorDebugMutableDataTarget::ContinueStatusChanged (método)
ms.date: 03/30/2017
ms.assetid: 5a66d3f4-dd16-4d62-9dcc-0eab7041d894
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3d2560aa484c6965047b2fdaf2c539b8ab675bc8
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36207708"
---
# <a name="icordebugmutabledatatargetcontinuestatuschanged-method"></a>ICorDebugMutableDataTarget::ContinueStatusChanged (método)
Cambia el estado de continuación para el evento de depuración pendiente en el subproceso especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT ContinueStatusChanged(  
   [in] DWORD dwThreadId,  
   [in] CORDB_CONTINUE_STATUS continueStatus);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `dwThreadId`  
 Identificador de subproceso definido por el sistema operativo.  
  
 `continueStatus`  
 Valor [COREDB_CONTINUE_STATUS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) que representa el nuevo estado de continuación solicitado.  
  
## <a name="remarks"></a>Comentarios  
 El depurador llama al método `ContinueStatusChanged` cuando llama a un método ICorDebug que requiere que el evento de depuración actual se trate de una manera potencialmente diferente al modo en que se suele tratar. Por ejemplo, si hay una excepción pendiente y el depurador solicita una operación que cancelará la excepción (como [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) o `FuncEval`), esta API se usa para solicitar que se cancele la excepción.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorDebugMutableDataTarget (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)  
 [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
