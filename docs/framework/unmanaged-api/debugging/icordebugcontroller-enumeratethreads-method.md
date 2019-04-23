---
title: ICorDebugController::EnumerateThreads (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugController.EnumerateThreads
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::EnumerateThreads
helpviewer_keywords:
- ICorDebugController::EnumerateThreads method [.NET Framework debugging]
- EnumerateThreads method [.NET Framework debugging]
ms.assetid: 73f536f6-4668-4a4a-b3e4-ac7df862d5be
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 17ba15553d2e7dcd2090870eaab54b4c680631f1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59163090"
---
# <a name="icordebugcontrollerenumeratethreads-method"></a>ICorDebugController::EnumerateThreads (Método)
Obtiene un enumerador para los subprocesos administrados activos en el proceso.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT EnumerateThreads (  
    [out] ICorDebugThreadEnum **ppThreads  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `ppThreads`  
 [out] Un puntero a la dirección de un objeto "ICorDebugThreadEnum" que representa un enumerador para todos los subprocesos administrados que están activos en el proceso.  
  
## <a name="remarks"></a>Comentarios  
 Un subproceso se considera activo después de la [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) se ha enviado la devolución de llamada y antes de la [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitthread-method.md) se ha enviado la devolución de llamada . Un subproceso administrado no puede tener necesariamente ningún marco administrado en su pila. Los subprocesos se pueden enumerar incluso antes el [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) devolución de llamada. Naturalmente, la enumeración estará vacía.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también
