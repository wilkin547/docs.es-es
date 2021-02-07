---
description: 'Más información sobre: ICorDebugAppDomain3:: Getcachedwinrttypesforiids ((método)'
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
ms.openlocfilehash: 76b93cdb8c465935a4aaf36090ee44f2b6253a3b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754178"
---
# <a name="icordebugappdomain3getcachedwinrttypesforiids-method"></a>ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs (Método)

Obtiene un enumerador para los tipos de Windows Runtime almacenados en memoria caché en un dominio de aplicación en función de sus identificadores de interfaz.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetCachedWinRTTypesForIIDs (
    [in]  ULONG32            cReqTypes,  
    [in]  GUID                *iidsToResolve,  
    [out] ICorDebugTypeEnum   **ppTypesEnum  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `cReqTypes`  
 de Número de tipos necesarios.  
  
 `iidsToResolve`  
 de Puntero a una matriz que contiene los identificadores de interfaz correspondientes a las representaciones administradas de los tipos de Windows Runtime que se van a recuperar.  
  
 `ppTypesEnum`  
 enuncia Puntero a la dirección de un objeto de interfaz "ICorDebugTypeEnum" que permite la enumeración de las representaciones administradas en caché de los tipos de Windows Runtime recuperados, en función de los identificadores de interfaz de `iidsToResolve` .  
  
## <a name="remarks"></a>Observaciones  

 Si el método no puede recuperar información de un identificador de interfaz concreto, la entrada correspondiente en la colección "ICorDebugTypeEnum" tendrá un tipo de `ELEMENT_TYPE_END` errores debido a problemas de recuperación de datos o `ELEMENT_TYPE_VOID` para los identificadores de interfaz desconocidos.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Windows Runtime  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugAppDomain3 (Interfaz)](icordebugappdomain3-interface.md)
