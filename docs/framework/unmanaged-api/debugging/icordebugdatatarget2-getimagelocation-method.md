---
title: "Método ICorDebugDataTarget2::GetImageLocation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 696afe71-5852-478d-a33f-b2d2dbc4b91f
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d35e35ecf4dfc62575e42a45a861ad685f3f26b4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugdatatarget2getimagelocation-method"></a>Método ICorDebugDataTarget2::GetImageLocation
Devuelve la ruta de acceso de un módulo a partir de la dirección base del módulo.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetImageLocation(    [in] CORDB_ADDRESS baseAddress,  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `baseAddress`  
 [in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) valor que representa la dirección base del módulo.  
  
 `cchName`  
 [in] Número de caracteres en el búfer que va a recibir la ruta de acceso del módulo.  
  
 `pcchName`  
 [out] Puntero al número de caracteres escritos en el búfer `szName`.  
  
 `szName`  
 [out] Ruta de acceso del módulo.  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
>  Este método solo está disponible con .NET Native.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Interfaz ICorDebugDataTarget2](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)  
 [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
