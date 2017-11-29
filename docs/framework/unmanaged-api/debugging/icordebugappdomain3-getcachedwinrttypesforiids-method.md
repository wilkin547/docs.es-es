---
title: "ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAppDomain3.GetCachedWinRTTypesForIIDs
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs
helpviewer_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs method, [.NET Framework debugging]
- GetCachedWinRTTypesForIIDs method, ICorDebugAppDomain3 interface [.NET Framework debugging]
ms.assetid: 23682ca0-1bcf-48e6-996e-69f7ba337682
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 84b58e3a016431eba10710ea384338cb388404ff
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugappdomain3getcachedwinrttypesforiids-method"></a>ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs (Método)
Obtiene un enumerador para almacenado en memoria caché [!INCLUDE[wrt](../../../../includes/wrt-md.md)] tipos en un dominio de aplicación en función de sus identificadores de interfaz.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetCachedWinRTTypesForIIDs (   
    [in]  ULONG32            cReqTypes,  
    [in]  GUID                *iidsToResolve,  
    [out] ICorDebugTypeEnum   **ppTypesEnum  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `cReqTypes`  
 [in] El número de tipos necesarios.  
  
 `iidsToResolve`  
 [in] Un puntero a una matriz que contiene los identificadores de interfaz correspondientes a las representaciones administradas de la [!INCLUDE[wrt](../../../../includes/wrt-md.md)] tipos va a recuperar.  
  
 `ppTypesEnum`  
 [out] Un puntero a la dirección de un objeto de interfaz de "ICorDebugTypeEnum" que permite la enumeración de las almacenadas en caché administrada representaciones de la [!INCLUDE[wrt](../../../../includes/wrt-md.md)] tipos recuperar, en función de los identificadores de interfaz de `iidsToResolve`.  
  
## <a name="remarks"></a>Comentarios  
 Si el método no se puede recuperar la información de un identificador de interfaz específica, la entrada correspondiente en la colección "ICorDebugTypeEnum" tendrá un tipo de `ELEMENT_TYPE_END` para errores causados por problemas de recuperación de datos, o `ELEMENT_TYPE_VOID` para la interfaz desconocida identificadores.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:**[!INCLUDE[wrt](../../../../includes/wrt-md.md)]  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorDebugAppDomain3 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)
