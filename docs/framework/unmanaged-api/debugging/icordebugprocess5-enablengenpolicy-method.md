---
title: "ICorDebugProcess5::EnableNGENPolicy (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess5::EnableNGenPolicy
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess5::EnableNGENPolicy
helpviewer_keywords:
- ICorDebugProcess5::EnableNGENPolicy method [.NET Framework debugging]
- EnableNGENPolicy method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 3b8e15ca-3c72-4685-a937-da4c739cb9e9
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cd259308494e1a86f0a6cdec8866bb66a1614b76
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess5enablengenpolicy-method"></a>ICorDebugProcess5::EnableNGENPolicy (Método)
Establece un valor que determina la forma en que una aplicación carga imágenes nativas mientras se ejecuta bajo un depurador administrado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT EnableNGENPolicy(  
    [in] CorDebugNGENPolicy ePolicy  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `ePolicy`  
 [in] A [CorDebugNGenPolicy](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md) constante que determina la forma en que una aplicación carga imágenes nativas mientras se ejecuta bajo un depurador administrado.  
  
## <a name="remarks"></a>Comentarios  
 Si la directiva está configurada correctamente, el método devuelve `S_OK`. Si `ePolicy` está fuera del intervalo de los valores enumerados definidos por [CorDebugNGenPolicy](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md), el método devuelve `E_INVALIDARG` y la llamada al método no tiene ningún efecto. Si no se puede actualizar la directiva de Native Image Generator (Ngen.exe), el método devuelve `E_FAIL`.  
  
 El `ICorDebugProcess5::EnableNGenPolicy` método puede llamarse en cualquier momento durante la duración del proceso. La directiva está en vigor para los módulos que se cargan después de establece la directiva.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorDebugProcess5 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
