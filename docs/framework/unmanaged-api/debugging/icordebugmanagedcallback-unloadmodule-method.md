---
description: 'Más información acerca de: ICorDebugManagedCallback:: UnloadModule ((método)'
title: ICorDebugManagedCallback::UnloadModule (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UnloadModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UnloadModule
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadModule method [.NET Framework debugging]
- UnloadModule method [.NET Framework debugging]
ms.assetid: b12bfcd9-1e29-48bf-9a3d-44bfae5df5e8
topic_type:
- apiref
ms.openlocfilehash: d8d37b28d7a7d11000c259f1bcde3138634b2498
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754061"
---
# <a name="icordebugmanagedcallbackunloadmodule-method"></a>ICorDebugManagedCallback::UnloadModule (Método)

Notifica al depurador que se ha descargado un módulo de Common Language Runtime (DLL).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT UnloadModule (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugModule     *pModule  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pAppDomain`  
 de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contenía el módulo.  
  
 `pModule`  
 de Un puntero a un objeto ICorDebugModule que representa el módulo.  
  
## <a name="remarks"></a>Observaciones  

 El módulo no debe usarse después de esta llamada.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Método LoadModule](icordebugmanagedcallback-loadmodule-method.md)
- [ICorDebugManagedCallback (Interfaz)](icordebugmanagedcallback-interface.md)
