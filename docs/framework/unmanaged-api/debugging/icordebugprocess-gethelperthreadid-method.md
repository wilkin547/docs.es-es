---
title: ICorDebugProcess::GetHelperThreadID (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetHelperThreadID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetHelperThreadID
helpviewer_keywords:
- GetHelperThreadID method [.NET Framework debugging]
- ICorDebugProcess::GetHelperThreadID method [.NET Framework debugging]
ms.assetid: 84e1e605-37c1-49a5-8e12-35db85654622
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cd5e30d08e667dcd5a8be1f9502462f28290068e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61987745"
---
# <a name="icordebugprocessgethelperthreadid-method"></a>ICorDebugProcess::GetHelperThreadID (Método)
Obtiene el identificador de subproceso del sistema operativo (SO) del subproceso auxiliar interno del depurador.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetHelperThreadID (  
    [out] DWORD *pThreadID  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pThreadID`  
 [out] Id. de subproceso auxiliar interno del depurador de subproceso de un puntero al sistema operativo.  
  
## <a name="remarks"></a>Comentarios  
 Durante la depuración administrada y no administrados, es responsabilidad del depurador para asegurarse de que el subproceso con el identificador especificado sigue ejecutándose si se produce un punto de interrupción colocado por el depurador. Un depurador que también desee ocultar este subproceso del usuario. Si no hay ningún subproceso auxiliar existe en el proceso todavía, el `GetHelperThreadID` método devuelve cero en *`pThreadID`.  
  
 No se almacena en caché el identificador de subproceso del subproceso de aplicación auxiliar, ya que puede cambiar con el tiempo. Debe volver a consultar el identificador de subproceso en cada evento de detención.  
  
 El identificador de subproceso del subproceso auxiliar del depurador será correcto en cada no administrado [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) eventos, lo que permite a un depurador determinar el identificador de subproceso de su subproceso auxiliar y ocultarla del usuario. Un subproceso que se identifica como un subproceso auxiliar durante no administradas `ICorDebugManagedCallback::CreateThread` evento nunca ejecutará el código de usuario administrado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl. CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
