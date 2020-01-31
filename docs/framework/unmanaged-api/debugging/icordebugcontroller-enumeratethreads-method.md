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
ms.openlocfilehash: 815dc63a2dedecc613506b0f98702f58d6e7bd04
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783785"
---
# <a name="icordebugcontrollerenumeratethreads-method"></a>ICorDebugController::EnumerateThreads (Método)
Obtiene un enumerador para los subprocesos administrados activos en el proceso.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EnumerateThreads (  
    [out] ICorDebugThreadEnum **ppThreads  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `ppThreads`  
 enuncia Puntero a la dirección de un objeto "ICorDebugThreadEnum (" que representa un enumerador para todos los subprocesos administrados que están activos en el proceso.  
  
## <a name="remarks"></a>Notas  
 Un subproceso se considera activo después de que se haya enviado la devolución de llamada [ICorDebugManagedCallback:: CreateThread](icordebugmanagedcallback-createthread-method.md) y antes de que se haya enviado la devolución de llamada [ICorDebugManagedCallback:: ExitThread](icordebugmanagedcallback-exitthread-method.md) . Es posible que un subproceso administrado no tenga necesariamente ningún marco administrado en la pila. Los subprocesos se pueden enumerar incluso antes de la devolución de llamada [ICorDebugManagedCallback:: CreateProcess](icordebugmanagedcallback-createprocess-method.md) . La enumeración estará vacía naturalmente.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también
