---
title: ICorDebugMergedAssemblyRecord::GetCulture (método)
ms.date: 03/30/2017
ms.assetid: 030b2f8c-8c21-40b7-855d-3afa78975a17
ms.openlocfilehash: 636d0fd25d345f513e00504b9eb5adb4f0c03b0f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710654"
---
# <a name="icordebugmergedassemblyrecordgetculture-method"></a>ICorDebugMergedAssemblyRecord::GetCulture (método)

Obtiene la cadena de nombre de referencia cultural del ensamblado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetCulture(  
   [in] ULONG32 cchCulture,
   [out] ULONG32 *pcchCulture,
   [out, size_is(cchCulture), length_is(*pcchCulture)] WCHAR szCulture[]  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `cchCulture`  
 [in] Número de caracteres del búfer `szCulture`.  
  
 `pcchCulture`  
 [out] Número de caracteres escritos realmente en el búfer `szCulture`.  
  
 `szCulture`  
 [out] Matriz de caracteres que contiene el nombre de referencia cultural.  
  
## <a name="remarks"></a>Comentarios  

 El nombre de referencia cultural es una cadena única que identifica una referencia cultural, como "en-US" [para la referencia cultural inglés (Estados Unidos)] o "neutral" (para una referencia cultural neutra).  
  
> [!NOTE]
> Este método solo está disponible con .NET Native.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaz ICorDebugMergedAssemblyRecord](icordebugmergedassemblyrecord-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
