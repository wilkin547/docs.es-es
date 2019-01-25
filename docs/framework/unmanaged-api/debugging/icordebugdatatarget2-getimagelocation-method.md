---
title: Método ICorDebugDataTarget2::GetImageLocation
ms.date: 03/30/2017
ms.assetid: 696afe71-5852-478d-a33f-b2d2dbc4b91f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3b2d6db83f78cb76181c0b54a8e6f4157e51130b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54648841"
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
 [in] Un [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) valor que representa la dirección base del módulo.  
  
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
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también
- [ICorDebugDataTarget2 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
