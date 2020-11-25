---
title: ICorDebugThread::GetCurrentException (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetCurrentException
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetCurrentException
helpviewer_keywords:
- ICorDebugThread::GetCurrentException method [.NET Framework debugging]
- GetCurrentException method [.NET Framework debugging]
ms.assetid: 331ed465-a195-4359-8584-b82c6098b29b
topic_type:
- apiref
ms.openlocfilehash: c21be7b062b7e2d4129bafabae004351442ab853
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728061"
---
# <a name="icordebugthreadgetcurrentexception-method"></a>ICorDebugThread::GetCurrentException (Método)

Obtiene un puntero de interfaz a un objeto ICorDebugValue que representa una excepción que se está iniciando actualmente mediante código administrado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetCurrentException (  
    [out] ICorDebugValue **ppExceptionObject  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `ppExceptionObject`  
 enuncia Puntero a la dirección de un `ICorDebugValue` objeto que representa la excepción que el código administrado está produciendo actualmente.  
  
## <a name="remarks"></a>Comentarios  

 El objeto de excepción existirá desde el momento en que se produce la excepción hasta el final del `catch` bloque. Una evaluación de función, que se realiza mediante los métodos ICorDebugEval, borrará el objeto de excepción en el programa de instalación y lo restaurará cuando se complete.  
  
 Las excepciones se pueden anidar (por ejemplo, si se produce una excepción en un filtro o en una evaluación de función), por lo que puede haber varias excepciones pendientes en un único subproceso. `GetCurrentException` Devuelve la excepción más actual.  
  
 El objeto de excepción y el tipo pueden cambiar a lo largo de la duración de la excepción. Por ejemplo, después de que se produzca una excepción de tipo x, el Common Language Runtime (CLR) puede quedarse sin memoria y promoverlo a una excepción de memoria insuficiente.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
