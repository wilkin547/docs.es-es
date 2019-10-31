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
ms.openlocfilehash: c6def272ecc7bd2b6e946e2c9623f0b60587d317
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128809"
---
# <a name="icordebugprocessgetthreadcontext-method"></a>ICorDebugProcess::GetThreadContext (Método)
Obtiene el contexto para el subproceso dado en este proceso.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetThreadContext(  
    [in] DWORD threadID,  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize), size_is(contextSize)]  
    BYTE context[]);  
```  
  
## <a name="parameters"></a>Parámetros  
 `threadID`  
 de IDENTIFICADOR del subproceso para el que se va a recuperar el contexto.  
  
 `contextSize`  
 [in] Tamaño de la matriz `context`.  
  
 `context`  
 [in, out] Matriz de bytes que describen el contexto del subproceso.  
  
 El contexto especifica la arquitectura del procesador en el que se ejecuta el subproceso.  
  
## <a name="remarks"></a>Comentarios  
 El depurador debe llamar a este método en lugar de al método `GetThreadContext` de Win32, porque el subproceso puede estar realmente en un estado "secuestrado", en el que su contexto ha cambiado temporalmente. Este método solo se debe usar cuando un subproceso está en código nativo. Use [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) para subprocesos en código administrado.  
  
 Los datos devueltos son una estructura de contexto para la plataforma actual. Al igual que con el método de `GetThreadContext` de Win32, el llamador debe inicializar el parámetro `context` antes de llamar a este método.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
