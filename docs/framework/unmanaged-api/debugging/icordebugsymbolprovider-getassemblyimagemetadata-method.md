---
title: 'ICorDebugSymbolProvider:: Getassemblyimagemetadata ((método)'
ms.date: 03/30/2017
ms.assetid: c3c9de67-b865-4ecf-b887-1f1d0719a0c0
ms.openlocfilehash: fb08df3b594e0c34dfe4ca791983b0c111239b23
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138913"
---
# <a name="icordebugsymbolprovidergetassemblyimagemetadata-method"></a>ICorDebugSymbolProvider:: Getassemblyimagemetadata ((método)
Devuelve los metadatos desde un ensamblado combinado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetAssemblyImageMetadata(  
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `ppMemoryBuffer`  
 enuncia Puntero a la dirección de un objeto [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) que contiene información sobre el tamaño y la dirección de los metadatos del ensamblado combinado.  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
> Este método solo está disponible con .NET Native.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugSymbolProvider (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
