---
title: ICorDebugManagedCallback::ControlCTrap (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.ControlCTrap
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::ControlCTrap
helpviewer_keywords:
- ICorDebugManagedCallback::ControlCTrap method [.NET Framework debugging]
- ControlCTrap method [.NET Framework debugging]
ms.assetid: 0500854e-2121-43d9-a028-64312da35258
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7f4794fb0383435f828626497036ad3458df2173
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59204996"
---
# <a name="icordebugmanagedcallbackcontrolctrap-method"></a>ICorDebugManagedCallback::ControlCTrap (Método)
Notifica al depurador que se captura CTRL+C en el proceso que se está depurando.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT ControlCTrap (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pProcess`  
 [in] Un puntero a un objeto ICorDebugProcess que representa el proceso en el que se captura la CTRL + C.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El depurador controlará la captura de CTRL+C.|  
|S_FALSE|El depurador no controlará la captura de CTRL+C.|  
  
## <a name="remarks"></a>Comentarios  
 Todos los dominios de aplicación dentro del proceso se detienen para esta devolución de llamada.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugManagedCallback (Interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
