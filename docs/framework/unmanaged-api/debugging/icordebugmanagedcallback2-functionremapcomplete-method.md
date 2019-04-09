---
title: ICorDebugManagedCallback2::FunctionRemapComplete (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.FunctionRemapComplete
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::FunctionRemapComplete
helpviewer_keywords:
- FunctionRemapComplete method [.NET Framework debugging]
- ICorDebugManagedCallback2::FunctionRemapComplete method [.NET Framework debugging]
ms.assetid: 5396c4c3-4ec3-4e3a-a38d-d65b21f0a2fc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 515d434e8d8f1c99cf5052ef9a2f1e098f6021b2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59140561"
---
# <a name="icordebugmanagedcallback2functionremapcomplete-method"></a>ICorDebugManagedCallback2::FunctionRemapComplete (Método)
Notifica al depurador que la ejecución de código ha cambiado a una nueva versión de una función modificada.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT FunctionRemapComplete (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFunction    *pFunction  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pAppDomain`  
 [in] Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene la función modificada.  
  
 `pThread`  
 [in] Un puntero a un objeto ICorDebugThread que representa el subproceso en el que se encontró el punto de interrupción de reasignación.  
  
 `pFunction`  
 [in] Un puntero a un objeto ICorDebugFunction que representa la versión de la función que se están ejecutando actualmente en el subproceso.  
  
## <a name="remarks"></a>Comentarios  
 Esta devolución de llamada da la oportunidad para volver a crear los steppers que existían previamente el depurador.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugManagedCallback2 (Interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [ICorDebugManagedCallback (Interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
