---
title: ICorDebugManagedCallback::UnloadClass (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UnloadClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UnloadClass
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadClass method [.NET Framework debugging]
- UnloadClass method [.NET Framework debugging]
ms.assetid: 66a59b18-ce9a-41f4-b23b-4dd6753d6d36
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 354de38e106ea16eef10bd9a9cebf2b27ca44d25
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54548133"
---
# <a name="icordebugmanagedcallbackunloadclass-method"></a>ICorDebugManagedCallback::UnloadClass (Método)
Notifica al depurador que se está descargando una clase.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT UnloadClass (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugClass      *c  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pAppDomain`  
 [in] Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene la clase.  
  
 `c`  
 [in] Un puntero a un objeto ICorDebugClass que representa la clase.  
  
## <a name="remarks"></a>Comentarios  
 No se debe hacer referencia a la clase después de esta llamada.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [LoadClass (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md)
- [ICorDebugManagedCallback (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
