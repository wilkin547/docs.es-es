---
title: 'ICorDebugInstanceFieldSymbol:: GetOffset (método)'
ms.date: 03/30/2017
ms.assetid: 7e470150-2b92-4425-989c-315f48964fd2
ms.openlocfilehash: 3886e29a1c2fd44fbe50d1eef722f99da7abdbe5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139016"
---
# <a name="icordebuginstancefieldsymbolgetoffset-method"></a>ICorDebugInstanceFieldSymbol:: GetOffset (método)
Obtiene el desplazamiento en bytes de este campo de instancia en su clase primaria.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetOffset(  
   [out] ULONG32 *pcbOffset  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pcbOffset`  
 Puntero al número de bytes que este campo de instancia compensa en su clase primaria.  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
> Este método solo está disponible con .NET Native.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugInstanceFieldSymbol (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
