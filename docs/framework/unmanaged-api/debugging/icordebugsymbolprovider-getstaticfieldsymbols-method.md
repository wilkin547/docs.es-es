---
title: 'ICorDebugSymbolProvider:: Getstaticfieldsymbols ((método)'
ms.date: 03/30/2017
ms.assetid: b178367f-a6e4-413c-b06f-daf3804b456b
ms.openlocfilehash: 8c4211a60786016e25cc3e3419804817b57ab64e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138805"
---
# <a name="icordebugsymbolprovidergetstaticfieldsymbols-method"></a>ICorDebugSymbolProvider:: Getstaticfieldsymbols ((método)
Obtiene los símbolos de campo estáticos que corresponden a una firma Typespec.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetStaticFieldSymbols(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugStaticFieldSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `cbSignature`  
 [in] Número de bytes en la matriz `typeSig`.  
  
 `typeSig`  
 [in] Matriz de bytes que contiene la firma `typespec`.  
  
 `cRequestedSymbols`  
 [in] Número de símbolos solicitado.  
  
 `pcFetchedSymbols`  
 [out] Puntero al número de símbolos recuperados por el método.  
  
 `pSymbols`  
 enuncia Puntero a una matriz [ICorDebugStaticFieldSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md) que contiene los símbolos de campo estático solicitados.  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
> Este método solo está disponible con .NET Native.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también

- [GetInstanceFieldSymbols (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getinstancefieldsymbols-method.md)
- [ICorDebugSymbolProvider (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
