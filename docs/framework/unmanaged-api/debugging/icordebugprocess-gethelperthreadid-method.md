---
description: 'Más información acerca de: ICorDebugProcess:: GetHelperThreadID ((método)'
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
ms.openlocfilehash: ee7bd2106a37c5c67df48a54ff9ab7fa49a03f80
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801025"
---
# <a name="icordebugprocessgethelperthreadid-method"></a>ICorDebugProcess::GetHelperThreadID (Método)

Obtiene el identificador del subproceso del sistema operativo (SO) del subproceso auxiliar interno del depurador.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetHelperThreadID (  
    [out] DWORD *pThreadID  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pThreadID`  
 enuncia Puntero al identificador de subproceso del sistema operativo del subproceso auxiliar interno del depurador.  
  
## <a name="remarks"></a>Observaciones  

 Durante la depuración administrada y no administrada, es responsabilidad del depurador asegurarse de que el subproceso con el identificador especificado permanece en ejecución si llega a un punto de interrupción colocado por el depurador. Un depurador también puede querer ocultar este subproceso al usuario. Si aún no existe ningún subproceso auxiliar en el proceso, el `GetHelperThreadID` método devuelve cero en * `pThreadID` .  
  
 No se puede almacenar en caché el identificador del subproceso auxiliar, ya que puede cambiar con el tiempo. Debe volver a consultar el identificador del subproceso en cada evento de detención.  
  
 El identificador de subproceso del subproceso auxiliar del depurador será correcto en cada evento [ICorDebugManagedCallback:: CreateThread](icordebugmanagedcallback-createthread-method.md) no administrado, lo que permite que un depurador determine el identificador de subproceso de su subproceso auxiliar y lo oculte del usuario. Un subproceso que se identifica como un subproceso auxiliar durante un evento no administrado `ICorDebugManagedCallback::CreateThread` nunca ejecutará código de usuario administrado.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cordebug. idl. Cordebug. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
