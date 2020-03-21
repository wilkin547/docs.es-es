---
title: Método ICorDebugDataTarget2::GetSymbolProviderForImage
ms.date: 03/30/2017
ms.assetid: b7c0a2f0-e904-43b3-98e1-d669e8a589e8
ms.openlocfilehash: 500d36b414be686071990a6e1b40dd8759d02ae9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178936"
---
# <a name="icordebugdatatarget2getsymbolproviderforimage-method"></a>Método ICorDebugDataTarget2::GetSymbolProviderForImage
Devuelve el proveedor de símbolos de un módulo a partir de la dirección base de ese módulo.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetSymbolProviderForImage(  
    [in] CORDB_ADDRESS imageBaseAddress,
    [out] ICorDebugSymbolProvider **ppSymProvider  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `imageBaseAddress`  
 [en] Un [valor CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) que representa la dirección base de un módulo.  
  
 `ppSymProvider`  
 [fuera] Un puntero a la dirección de un [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) objeto.  
  
## <a name="remarks"></a>Observaciones  
  
> [!NOTE]
> Este método solo está disponible con .NET Native.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorDebugDataTarget2 (interfaz)](icordebugdatatarget2-interface.md)
- [Interfaces de depuración](debugging-interfaces.md)
