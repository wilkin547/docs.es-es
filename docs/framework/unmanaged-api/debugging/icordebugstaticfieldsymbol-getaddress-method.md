---
title: ICorDebugStaticFieldSymbol::GetAddress (método)
ms.date: 03/30/2017
ms.assetid: 5a6c9a5a-ec72-4c40-a9c3-cee7baa63687
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8a45f233fdec23a504a71a68370e9da8e38ac0bd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760872"
---
# <a name="icordebugstaticfieldsymbolgetaddress-method"></a>ICorDebugStaticFieldSymbol::GetAddress (método)
Obtiene la dirección de un campo estático.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetAddress(  
   [out] CORDB_ADDRESS *pRVA  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 pRVA  
 [out] Puntero a la dirección virtual relativa (RVA) del campo estático.  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
>  Este método solo está disponible con .NET Native.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugStaticFieldSymbol (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
