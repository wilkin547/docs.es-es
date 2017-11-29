---
title: "ICorDebugProcess::GetHelperThreadID (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess.GetHelperThreadID
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess::GetHelperThreadID
helpviewer_keywords:
- GetHelperThreadID method [.NET Framework debugging]
- ICorDebugProcess::GetHelperThreadID method [.NET Framework debugging]
ms.assetid: 84e1e605-37c1-49a5-8e12-35db85654622
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 092e99cb1d5534cee56db08b5a2eedaaa2fc4724
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugprocessgethelperthreadid-method"></a>ICorDebugProcess::GetHelperThreadID (Método)
Obtiene el identificador de subproceso del sistema operativo (SO) del subproceso auxiliar interno del depurador.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetHelperThreadID (  
    [out] DWORD *pThreadID  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pThreadID`  
 [out] Id. de subproceso auxiliar interno del depurador de subproceso de un puntero para el sistema operativo.  
  
## <a name="remarks"></a>Comentarios  
 Durante la depuración administrada y no administrada, es responsabilidad del depurador para asegurarse de que el subproceso con el identificador especificado está en ejecución si se produce un punto de interrupción colocado por el depurador. Un depurador que también desee ocultar este subproceso del usuario. Si existe ningún subproceso auxiliar en el proceso, el `GetHelperThreadID` método devuelva cero en *`pThreadID`.  
  
 No se almacena en caché el identificador de subproceso del subproceso de aplicación auxiliar, ya que puede cambiar con el tiempo. Debe volver a consultar el identificador del subproceso en cada evento de detención.  
  
 El identificador de subproceso del subproceso de aplicación auxiliar del depurador será correcto en cada no administrado [ICorDebugManagedCallback:: CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) eventos, lo que permite a un depurador determinar el identificador del subproceso de un subproceso auxiliar y ocultar del usuario. Un subproceso que se identifica como un subproceso auxiliar durante no administrado `ICorDebugManagedCallback::CreateThread` evento nunca ejecutará el código de usuario administrado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl. CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
