---
description: 'Más información acerca de: ICorDebugProcess:: GetThreadContext (método)'
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
ms.openlocfilehash: 4cb926183522548e924013580f207d1d0677a0d3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746872"
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
  
## <a name="remarks"></a>Observaciones  

 El depurador debe llamar a este método en lugar de al `GetThreadContext` método Win32, ya que el subproceso puede estar realmente en un estado "secuestrado", en el que su contexto ha cambiado temporalmente. Este método solo se debe usar cuando un subproceso está en código nativo. Use [ICorDebugRegisterSet](icordebugregisterset-interface.md) para subprocesos en código administrado.  
  
 Los datos devueltos son una estructura de contexto para la plataforma actual. Al igual que con el `GetThreadContext` método de Win32, el llamador debe inicializar el `context` parámetro antes de llamar a este método.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
