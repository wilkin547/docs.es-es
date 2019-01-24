---
title: ICorDebugManagedCallback2::FunctionRemapOpportunity (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.FunctionRemapOpportunity
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::FunctionRemapOpportunity
helpviewer_keywords:
- FunctionRemapOpportunity method [.NET Framework debugging]
- ICorDebugManagedCallback2::FunctionRemapOpportunity method [.NET Framework debugging]
ms.assetid: 0d6471bc-ad9b-4b1d-a307-c10443918863
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 86736f885e40e553195cf2a5f84575a5384e6b60
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54564713"
---
# <a name="icordebugmanagedcallback2functionremapopportunity-method"></a>ICorDebugManagedCallback2::FunctionRemapOpportunity (Método)
Notifica al depurador que la ejecución de código ha alcanzado un punto de secuencia en una versión anterior de una función modificada.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT FunctionRemapOpportunity (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFunction    *pOldFunction,  
    [in] ICorDebugFunction    *pNewFunction,  
    [in] ULONG32              oldILOffset  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pAppDomain`  
 [in] Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene la función modificada.  
  
 `pThread`  
 [in] Un puntero a un objeto ICorDebugThread que representa el subproceso en el que se encontró el punto de interrupción de reasignación.  
  
 `pOldFunction`  
 [in] Un puntero a un objeto ICorDebugFunction que representa la versión de la función que se está ejecutando actualmente en el subproceso.  
  
 `pNewFunction`  
 [in] Un puntero a un objeto ICorDebugFunction que representa la versión más reciente de la función.  
  
 `oldILOffset`  
 [in] El desplazamiento de lenguaje intermedio (MSIL) de Microsoft del puntero de instrucción en la versión anterior de la función.  
  
## <a name="remarks"></a>Comentarios  
 Esta devolución de llamada da la oportunidad de reasignar el puntero de instrucción al lugar adecuado en la nueva versión de la función especificada mediante una llamada al depurador el [Icordebugilframe2](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-remapfunction-method.md) método. Si el depurador no llama a `RemapFunction` antes de llamar a la [ICorDebugController](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) método, el tiempo de ejecución se seguirán ejecutando el código anterior y se activará otro `FunctionRemapOpportunity` devolución de llamada en el siguiente punto de secuencia.  
  
 Esta devolución de llamada se invocará para cada marco que se está ejecutando una versión anterior de la función especificada hasta que el depurador devuelve S_OK.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [ICorDebugManagedCallback2 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [ICorDebugManagedCallback (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
