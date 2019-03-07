---
title: ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain3.GetCachedWinRTTypesForIIDs
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs
helpviewer_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs method, [.NET Framework debugging]
- GetCachedWinRTTypesForIIDs method, ICorDebugAppDomain3 interface [.NET Framework debugging]
ms.assetid: 23682ca0-1bcf-48e6-996e-69f7ba337682
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 601110d37fabbff01aeb14d8ca69a27a2463353f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57491430"
---
# <a name="icordebugappdomain3getcachedwinrttypesforiids-method"></a>ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs (Método)
Obtiene un enumerador para almacenar en caché [!INCLUDE[wrt](../../../../includes/wrt-md.md)] tipos en un dominio de aplicación en función de sus identificadores de interfaz.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetCachedWinRTTypesForIIDs (   
    [in]  ULONG32            cReqTypes,  
    [in]  GUID                *iidsToResolve,  
    [out] ICorDebugTypeEnum   **ppTypesEnum  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `cReqTypes`  
 [in] El número de tipos necesarios.  
  
 `iidsToResolve`  
 [in] Un puntero a una matriz que contiene los identificadores de interfaz correspondientes a las representaciones administradas de la [!INCLUDE[wrt](../../../../includes/wrt-md.md)] tipos van a recuperar.  
  
 `ppTypesEnum`  
 [out] Un puntero a la dirección de un objeto de interfaz "ICorDebugTypeEnum" que permite la enumeración de la caché administrada representaciones de la [!INCLUDE[wrt](../../../../includes/wrt-md.md)] recuperar tipos, en función de los identificadores de interfaz en `iidsToResolve`.  
  
## <a name="remarks"></a>Comentarios  
 Si se produce un error en el método recuperar información para un identificador de interfaz específica, la entrada correspondiente en la colección "ICorDebugTypeEnum" tendrá un tipo de `ELEMENT_TYPE_END` errores debido a problemas de recuperación de datos, o `ELEMENT_TYPE_VOID` para la interfaz desconocida identificadores.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [ICorDebugAppDomain3 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)
