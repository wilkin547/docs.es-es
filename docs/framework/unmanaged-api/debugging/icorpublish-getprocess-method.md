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
ms.openlocfilehash: a9d28243e9907fcc6320b2e09a49312bf35a70b4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121786"
---
# <a name="icorpublishgetprocess-method"></a>ICorPublish::GetProcess (Método)
Obtiene una instancia de [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) que representa el proceso con el identificador especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetProcess(  
    [in] unsigned              pid,   
    [out] ICorPublishProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pid`  
 de Identificador del proceso.  
  
 `ppProcess`  
 enuncia Puntero a la dirección de una instancia de `ICorPublishProcess` que representa el proceso.  
  
## <a name="remarks"></a>Comentarios  
 `GetProcess` produce un error si el proceso no existe o no es un proceso administrado que el usuario actual puede depurar.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorPub. idl, CorPub. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorPublish (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)
