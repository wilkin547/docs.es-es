---
description: 'Más información acerca de: ICorDebug:: SetUnmanagedHandler ((método)'
title: ICorDebug::SetUnmanagedHandler (Método)
ms.date: 03/30/2017
api_name:
- ICorDebug.SetUnmanagedHandler
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::SetUnmanagerHandler
helpviewer_keywords:
- SetUnmanagedHandler method [.NET Framework debugging]
- ICorDebug::SetUnmanagedHandler method [.NET Framework debugging]
ms.assetid: 6b546be4-f86d-4536-8cfc-1d08e5066eb6
topic_type:
- apiref
ms.openlocfilehash: ffd4eb7ff0056a2468ec53eb3534434c2c8d556a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754334"
---
# <a name="icordebugsetunmanagedhandler-method"></a>ICorDebug::SetUnmanagedHandler (Método)

Especifica el objeto de controlador de eventos para los eventos no administrados.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetUnmanagedHandler (  
    [in] ICorDebugUnmanagedCallback  *pCallback  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pCallback`  
 de Un puntero a un objeto [ICorDebugUnmanagedCallback (](icordebugunmanagedcallback-interface.md) que representa el controlador de eventos para los eventos no administrados.  
  
## <a name="remarks"></a>Observaciones  

 El objeto de controlador de eventos para eventos no administrados debe establecerse después de una llamada a [ICorDebug:: Initialize](icordebug-initialize-method.md) y antes de cualquier llamada a [ICorDebug:: CreateProcess](icordebug-createprocess-method.md) o [ICorDebug::D ebugactiveprocess](icordebug-debugactiveprocess-method.md). Sin embargo, para los fines heredados, no es necesario establecer el objeto de controlador de eventos para los eventos no administrados hasta que se genere el primer evento de depuración nativo. En concreto, si `ICorDebug::CreateProcess` ha establecido la marca CREATE_SUSPENDED, los eventos de depuración nativos no se pueden enviar hasta que se reanude el subproceso principal.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebug (Interfaz)](icordebug-interface.md)
