---
title: ICorDebugProcess::GetThreadContext (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetThreadContext
helpviewer_keywords:
- ICorDebugProcess::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: 5b132ef1-8d4b-4525-89b3-54123596c194
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ea977b1ccecf9de5a04e1f1127658ca6c15043a4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416545"
---
# <a name="icordebugprocessgetthreadcontext-method"></a>ICorDebugProcess::GetThreadContext (Método)
Obtiene el contexto para el subproceso determinado en este proceso.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetThreadContext(  
    [in] DWORD threadID,  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize), size_is(contextSize)]  
    BYTE context[]);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `threadID`  
 [in] El identificador del subproceso para el que se va a recuperar el contexto.  
  
 `contextSize`  
 [in] Tamaño de la matriz `context`.  
  
 `context`  
 [entrada, salida] Una matriz de bytes que describen el contexto del subproceso.  
  
 El contexto especifica la arquitectura del procesador en el que se está ejecutando el subproceso.  
  
## <a name="remarks"></a>Comentarios  
 El depurador debe llamar a este método en lugar de Win32 `GetThreadContext` método, porque el subproceso esté realmente en un estado de "secuestro", en el que se ha cambiado temporalmente su contexto. Este método debe utilizarse únicamente cuando un subproceso está en código nativo. Use [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) para subprocesos en código administrado.  
  
 Los datos devueltos están una estructura de contexto para la plataforma actual. Al igual que con Win32 `GetThreadContext` método, el llamador debe inicializar el `context` parámetro antes de llamar a este método.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
