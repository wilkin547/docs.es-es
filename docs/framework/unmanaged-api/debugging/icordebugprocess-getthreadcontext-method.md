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
ms.openlocfilehash: 41c5116d23655730f3586dc656aa69c8ae817b6c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792623"
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
  
## <a name="parameters"></a>Parameters  
 `threadID`  
 de IDENTIFICADOR del subproceso para el que se va a recuperar el contexto.  
  
 `contextSize`  
 [in] Tamaño de la matriz `context`.  
  
 `context`  
 [in, out] Matriz de bytes que describen el contexto del subproceso.  
  
 El contexto especifica la arquitectura del procesador en el que se ejecuta el subproceso.  
  
## <a name="remarks"></a>Notas  
 El depurador debe llamar a este método en lugar de al método `GetThreadContext` de Win32, porque el subproceso puede estar realmente en un estado "secuestrado", en el que su contexto ha cambiado temporalmente. Este método solo se debe usar cuando un subproceso está en código nativo. Use [ICorDebugRegisterSet](icordebugregisterset-interface.md) para subprocesos en código administrado.  
  
 Los datos devueltos son una estructura de contexto para la plataforma actual. Al igual que con el método de `GetThreadContext` de Win32, el llamador debe inicializar el parámetro `context` antes de llamar a este método.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
