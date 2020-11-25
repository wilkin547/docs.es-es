---
title: ICorDebugMergedAssemblyRecord::GetSimpleNam (método)
ms.date: 03/30/2017
ms.assetid: bc3410f6-ebca-4bca-9b45-fc38c74fa9cb
ms.openlocfilehash: 11e43846f7b119933fb53bdf21423e28bbb792ac
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710550"
---
# <a name="icordebugmergedassemblyrecordgetsimplename-method"></a>ICorDebugMergedAssemblyRecord::GetSimpleNam (método)

Obtiene el nombre simple del ensamblado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetSimpleName(  
   [in] ULONG32 cchName,
   [out] ULONG32 *pcchName,
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `cchName`  
 [in] Número de caracteres del búfer `szName`.  
  
 `pcchName`  
 [out] Puntero al número de caracteres escritos realmente en el búfer `szName`.  
  
 `szName`  
 Puntero a una matriz de caracteres.  
  
## <a name="remarks"></a>Comentarios  

 Este método recupera el nombre sencillo de un ensamblado (por ejemplo, "System.Collections"), sin una extensión de archivo, versión, referencia cultural o el token de clave pública. Se corresponde con la propiedad <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> en código administrado.  
  
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
