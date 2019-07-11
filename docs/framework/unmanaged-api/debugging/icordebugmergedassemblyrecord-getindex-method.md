---
title: ICorDebugMergedAssemblyRecord::GetIndex (método)
ms.date: 03/30/2017
ms.assetid: 98701444-b9bc-4978-9548-89ac3394147d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0c869c829acbfb9b0281537c7355229acbf2c5a7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67752724"
---
# <a name="icordebugmergedassemblyrecordgetindex-method"></a>ICorDebugMergedAssemblyRecord::GetIndex (método)
Obtiene el índice de prefijo del ensamblado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetIndex(  
   [out] ULONG32 *pIndex  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pIndex`  
 [out] Puntero al índice de prefijo.  
  
## <a name="remarks"></a>Comentarios  
 El índice de prefijo se utiliza para evitar colisiones de nombres en los nombres de tipos de metadatos combinados.  
  
> [!NOTE]
>  Este método solo está disponible con .NET Native.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugMergedAssemblyRecord (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
