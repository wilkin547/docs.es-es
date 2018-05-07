---
title: ICorPublish::GetProcess (Método)
ms.date: 03/30/2017
api_name:
- ICorPublish.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish::GetProcess
helpviewer_keywords:
- ICorPublish::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorPublish interface [.NET Framework debugging]
ms.assetid: c5143805-2eb7-45b8-85ed-c8fb34df1084
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 414bc1bbd3578d0707e35fa70fe196b504af9942
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="icorpublishgetprocess-method"></a>ICorPublish::GetProcess (Método)
Obtiene un [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) instancia que representa el proceso con el identificador especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetProcess(  
    [in] unsigned              pid,   
    [out] ICorPublishProcess   **ppProcess  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pid`  
 [in] El identificador del proceso.  
  
 `ppProcess`  
 [out] Un puntero a la dirección de un `ICorPublishProcess` instancia que representa el proceso.  
  
## <a name="remarks"></a>Comentarios  
 `GetProcess` se produce un error si el proceso no existe o no es un proceso administrado que puede ser depurado por el usuario actual.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cordebug.idl, CorPub.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorPublish (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)
