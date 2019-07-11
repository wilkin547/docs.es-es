---
title: ICorDebugAppDomain3::GetCachedWinRTTypes (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain3.GetCachedWinRTTypes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypes
helpviewer_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypes method [.NET Framework debugging]
- GetCachedWinRTTypes method, ICorDebugAppDomain3 interface [.NET Framework debugging]
ms.assetid: 9afd0e04-a403-41e2-9528-a6dcbcdcbd4d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4ba981d86f90af449820ce13aa847169ca877429
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737772"
---
# <a name="icordebugappdomain3getcachedwinrttypes-method"></a>ICorDebugAppDomain3::GetCachedWinRTTypes (Método)
Obtiene un enumerador para todos los tipos en tiempo de ejecución de Windows almacenado en caché.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetCachedWinRTTypes (   
    [out] ICorDebugGuidToTypeEnum **ppGuidToTypeEnum)  
;  
```  
  
## <a name="parameters"></a>Parámetros  
 `ppGuidToTypeEnum`  
 [out] Un puntero a un [ICorDebugGuidToTypeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md) objeto de interfaz que puede enumerar las representaciones de tipos de Windows Runtime administradas actualmente cargado en el dominio de aplicación.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Windows en tiempo de ejecución  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugAppDomain3 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)
