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
ms.openlocfilehash: 8b259636a8bd28abd3bba12c4a05dda3c13557e1
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784889"
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
  
## <a name="parameters"></a>Parameters  
 `cReqTypes`  
 de Número de tipos necesarios.  
  
 `iidsToResolve`  
 de Puntero a una matriz que contiene los identificadores de interfaz correspondientes a las representaciones administradas de los tipos de Windows Runtime que se van a recuperar.  
  
 `ppTypesEnum`  
 enuncia Puntero a la dirección de un objeto de interfaz "ICorDebugTypeEnum" que permite la enumeración de las representaciones administradas en caché de los tipos de Windows Runtime recuperados, en función de los identificadores de interfaz de `iidsToResolve`.  
  
## <a name="remarks"></a>Notas  
 Si el método no puede recuperar información de un identificador de interfaz concreto, la entrada correspondiente en la colección "ICorDebugTypeEnum" tendrá un tipo de `ELEMENT_TYPE_END` para los errores debido a problemas de recuperación de datos o `ELEMENT_TYPE_VOID` para los identificadores de interfaz desconocidos.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Windows Runtime  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugAppDomain3 (interfaz)](icordebugappdomain3-interface.md)
