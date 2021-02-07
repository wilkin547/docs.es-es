---
description: 'Más información acerca de: ICorDebugProcess:: SetThreadContext (método)'
title: ICorDebugProcess::SetThreadContext (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.SetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::SetThreadContext
helpviewer_keywords:
- ICorDebugProcess::SetThreadContext method [.NET Framework debugging]
- SetThreadContext method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: a7b50175-2bf1-40be-8f65-64aec7aa1247
topic_type:
- apiref
ms.openlocfilehash: 3576c3bf3159e3960e7d2d4601ac2fb67d7218f7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753983"
---
# <a name="icordebugprocesssetthreadcontext-method"></a>ICorDebugProcess::SetThreadContext (Método)

Establece el contexto para el subproceso dado en este proceso.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetThreadContext(  
    [in] DWORD threadID,  
    [in] ULONG32 contextSize,  
    [in, length_is(contextSize), size_is(contextSize)]  
    BYTE context[]);  
```  
  
## <a name="parameters"></a>Parámetros  

 `threadID`  
 de IDENTIFICADOR del subproceso para el que se va a establecer el contexto.  
  
 `contextSize`  
 [in] Tamaño de la matriz `context`.  
  
 `context`  
 de Matriz de bytes que describen el contexto del subproceso.  
  
 El contexto especifica la arquitectura del procesador en el que se ejecuta el subproceso.  
  
## <a name="remarks"></a>Observaciones  

 El depurador debe llamar a este método en lugar de a la función de Win32 `SetThreadContext` , ya que el subproceso puede estar realmente en un estado "secuestrado", en el que su contexto ha cambiado temporalmente. Este método solo se debe usar cuando un subproceso está en código nativo. Use [ICorDebugRegisterSet](icordebugregisterset-interface.md) para subprocesos en código administrado. Nunca debe modificar el contexto de un subproceso durante un evento de depuración fuera de banda (OOB).  
  
 Los datos pasados deben ser una estructura de contexto para la plataforma actual.  
  
 Este método puede dañar el tiempo de ejecución si se usa de forma incorrecta.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
