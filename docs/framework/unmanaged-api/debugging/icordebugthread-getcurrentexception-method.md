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
ms.openlocfilehash: 8082b2a3654f1605f18f3b68f54464dc83c8e60a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133490"
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
 enuncia Puntero a la dirección de un objeto `ICorDebugValue` que representa la excepción que se está iniciando actualmente mediante código administrado.  
  
## <a name="remarks"></a>Comentarios  
 El objeto de excepción existirá desde el momento en que se produce la excepción hasta el final del bloque de `catch`. Una evaluación de función, que se realiza mediante los métodos ICorDebugEval, borrará el objeto de excepción en el programa de instalación y lo restaurará cuando se complete.  
  
 Las excepciones se pueden anidar (por ejemplo, si se produce una excepción en un filtro o en una evaluación de función), por lo que puede haber varias excepciones pendientes en un único subproceso. `GetCurrentException` devuelve la excepción más reciente.  
  
 El objeto de excepción y el tipo pueden cambiar a lo largo de la duración de la excepción. Por ejemplo, después de que se produzca una excepción de tipo x, el Common Language Runtime (CLR) puede quedarse sin memoria y promoverlo a una excepción de memoria insuficiente.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
