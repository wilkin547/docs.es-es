---
title: "ICorDebugThread::GetCurrentException (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread.GetCurrentException
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread::GetCurrentException
helpviewer_keywords:
- ICorDebugThread::GetCurrentException method [.NET Framework debugging]
- GetCurrentException method [.NET Framework debugging]
ms.assetid: 331ed465-a195-4359-8584-b82c6098b29b
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c18e2dfa68d425e5ec23d4573428018bc971f8b2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthreadgetcurrentexception-method"></a>ICorDebugThread::GetCurrentException (Método)
Obtiene un puntero de interfaz a un objeto ICorDebugValue que representa una excepción que se produce actualmente mediante código administrado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetCurrentException (  
    [out] ICorDebugValue **ppExceptionObject  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `ppExceptionObject`  
 [out] Un puntero a la dirección de un `ICorDebugValue` objeto que representa la excepción producida por el código administrado.  
  
## <a name="remarks"></a>Comentarios  
 El objeto de excepción existirá desde el momento en que se produce la excepción hasta el final de la `catch` bloque. Una evaluación de función, que se realiza mediante los métodos ICorDebugEval, borrará el objeto de excepción en el programa de instalación y restaurarla en la realización.  
  
 Las excepciones se pueden anidar (por ejemplo, si se produce una excepción en un filtro o en una evaluación de función), por lo que puede haber varias excepciones pendientes en un solo subproceso. `GetCurrentException`Devuelve la excepción más reciente.  
  
 El objeto de excepción y el tipo pueden cambiar a lo largo de la vida de la excepción. Por ejemplo, después de que se produce una excepción de tipo x, common language runtime (CLR) puede quedarse sin memoria y promoverla a una excepción de memoria insuficiente.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
