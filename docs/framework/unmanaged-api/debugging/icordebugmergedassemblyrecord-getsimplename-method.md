---
title: ICorDebugMergedAssemblyRecord::GetSimpleNam (método)
ms.date: 03/30/2017
ms.assetid: bc3410f6-ebca-4bca-9b45-fc38c74fa9cb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b8c5499b63e5201fbf42ece07f4f3eff52129e09
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugmergedassemblyrecordgetsimplename-method"></a>ICorDebugMergedAssemblyRecord::GetSimpleNam (método)
Obtiene el nombre simple del ensamblado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetSimpleName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `cchName`  
 [in] Número de caracteres del búfer `szName`.  
  
 `pcchName`  
 [out] Puntero al número de caracteres escritos realmente en el búfer `szName`.  
  
 `szName`  
 Puntero a una matriz de caracteres.  
  
## <a name="remarks"></a>Comentarios  
 Este método recupera el nombre sencillo de un ensamblado (por ejemplo, "System.Collections"), sin una extensión de archivo, versión, referencia cultural o el token de clave pública. Se corresponde con la propiedad <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> en código administrado.  
  
> [!NOTE]
>  Este método solo está disponible con .NET Native.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorDebugMergedAssemblyRecord (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)  
 [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
