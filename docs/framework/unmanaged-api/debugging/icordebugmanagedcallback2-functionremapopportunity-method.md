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
ms.openlocfilehash: bc6543b46200dd611e13bdf55aabfabd8302e70a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793335"
---
# <a name="icordebugmanagedcallback2functionremapopportunity-method"></a>ICorDebugManagedCallback2::FunctionRemapOpportunity (Método)
Notifica al depurador que la ejecución del código ha alcanzado un punto de secuencia en una versión anterior de una función editada.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT FunctionRemapOpportunity (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFunction    *pOldFunction,  
    [in] ICorDebugFunction    *pNewFunction,  
    [in] ULONG32              oldILOffset  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `pAppDomain`  
 de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene la función editada.  
  
 `pThread`  
 de Un puntero a un objeto ICorDebugThread que representa el subproceso en el que se encontró el punto de interrupción de reasignación.  
  
 `pOldFunction`  
 de Un puntero a un objeto ICorDebugFunction que representa la versión de la función que se está ejecutando actualmente en el subproceso.  
  
 `pNewFunction`  
 de Un puntero a un objeto ICorDebugFunction que representa la versión más reciente de la función.  
  
 `oldILOffset`  
 de Desplazamiento del lenguaje intermedio de Microsoft (MSIL) del puntero de instrucción en la versión anterior de la función.  
  
## <a name="remarks"></a>Notas  
 Esta devolución de llamada proporciona al depurador una oportunidad para reasignar el puntero de instrucción a su lugar adecuado en la nueva versión de la función especificada llamando al método [ICorDebugILFrame2:: remapfunction (](icordebugilframe2-remapfunction-method.md) . Si el depurador no llama a `RemapFunction` antes de llamar al método [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) , el motor en tiempo de ejecución seguirá ejecutando el código anterior y activará otra devolución de llamada `FunctionRemapOpportunity` en el siguiente punto de secuencia.  
  
 Esta devolución de llamada se invocará para cada fotograma que ejecute una versión anterior de la función especificada hasta que el depurador devuelva S_OK.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugManagedCallback2 (interfaz)](icordebugmanagedcallback2-interface.md)
- [ICorDebugManagedCallback (interfaz)](icordebugmanagedcallback-interface.md)
