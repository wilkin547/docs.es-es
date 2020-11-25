---
title: Método ICorDebugDataTarget2::GetImageLocation
ms.date: 03/30/2017
ms.assetid: 696afe71-5852-478d-a33f-b2d2dbc4b91f
ms.openlocfilehash: c909b46a9bb70d23d1cd3a769ac24fcf58479308
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713800"
---
# <a name="icordebugdatatarget2getimagelocation-method"></a>Método ICorDebugDataTarget2::GetImageLocation

Devuelve la ruta de acceso de un módulo a partir de la dirección base del módulo.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetImageLocation(    [in] CORDB_ADDRESS baseAddress,  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `baseAddress`  
 de [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) valor que representa la dirección base del módulo.  
  
 `cchName`  
 [in] Número de caracteres en el búfer que va a recibir la ruta de acceso del módulo.  
  
 `pcchName`  
 [out] Puntero al número de caracteres escritos en el búfer `szName`.  
  
 `szName`  
 [out] Ruta de acceso del módulo.  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
> Este método solo está disponible con .NET Native.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaz ICorDebugDataTarget2](icordebugdatatarget2-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
