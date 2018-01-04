---
title: "ICorDebugProcess::SetThreadContext (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess.SetThreadContext
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess::SetThreadContext
helpviewer_keywords:
- ICorDebugProcess::SetThreadContext method [.NET Framework debugging]
- SetThreadContext method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: a7b50175-2bf1-40be-8f65-64aec7aa1247
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a7d40d455ea17b8df2acd77a1222ac6b080116c6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocesssetthreadcontext-method"></a>ICorDebugProcess::SetThreadContext (Método)
Establece el contexto para el subproceso especificado en este proceso.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT SetThreadContext(  
    [in] DWORD threadID,  
    [in] ULONG32 contextSize,  
    [in, length_is(contextSize), size_is(contextSize)]  
    BYTE context[]);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `threadID`  
 [in] El identificador del subproceso para el que se va a establecer el contexto.  
  
 `contextSize`  
 [in] Tamaño de la matriz `context`.  
  
 `context`  
 [in] Una matriz de bytes que describen el contexto del subproceso.  
  
 El contexto especifica la arquitectura del procesador en el que se está ejecutando el subproceso.  
  
## <a name="remarks"></a>Comentarios  
 El depurador debe llamar a este método en lugar de Win32 `SetThreadContext` funciona, ya que el subproceso esté realmente en un estado de "secuestro", en el que se ha cambiado temporalmente su contexto. Este método debe utilizarse únicamente cuando un subproceso está en código nativo. Use [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) para subprocesos en código administrado. Nunca es necesario modificar el contexto de un subproceso durante un evento de depuración fuera de banda (OOB).  
  
 Los datos pasados deben ser una estructura de contexto para la plataforma actual.  
  
 Este método puede dañar el tiempo de ejecución si se utiliza incorrectamente.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
