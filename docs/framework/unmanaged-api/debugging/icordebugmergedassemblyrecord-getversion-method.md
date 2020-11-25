---
title: ICorDebugMergedAssemblyRecord::GetVersion (método)
ms.date: 03/30/2017
ms.assetid: c6858b06-ae26-4312-b325-ea6025016675
ms.openlocfilehash: 7352a77fc8f41124d7e6c78a3dfc6ccd6d3a94aa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710511"
---
# <a name="icordebugmergedassemblyrecordgetversion-method"></a>ICorDebugMergedAssemblyRecord::GetVersion (método)

Obtiene información de la versión del ensamblado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetVersion(  
   [out] USHORT *pMajor,
   [out] USHORT *pMinor,
   [out] USHORT *pBuild,
   [out] USHORT *pRevision  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pMajor`  
 [out] Puntero al número de revisión principal.  
  
 `pMinor`  
 [out] Puntero al número de revisión secundaria.  
  
 `pBuild`  
 [out] Puntero al número de revisión de compilación.  
  
 `pRevision`  
 [out] Puntero al número de revisión.  
  
## <a name="remarks"></a>Comentarios  

 Para obtener información sobre los números de versión del ensamblado, consulte el tema de la clase <xref:System.Version>.  
  
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
