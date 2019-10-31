---
title: 'ICorDebugSymbolProvider:: Getmethodlocalsymbols ((método)'
ms.date: 03/30/2017
ms.assetid: 8b989e38-e779-49d1-9e90-f1f920484b08
ms.openlocfilehash: 6cd04ea7f83fb7ae96d9ffd1beba39530511ec25
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138888"
---
# <a name="icordebugsymbolprovidergetmethodlocalsymbols-method"></a>ICorDebugSymbolProvider:: Getmethodlocalsymbols ((método)
Obtiene los símbolos locales del método a partir de la dirección virtual relativa (RVA) de ese método.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetMethodLocalSymbols(  
   [in] ULONG32 nativeRVA,  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugVariableSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `nativeRVA`  
 [in] Dirección virtual relativa nativa del método.  
  
 `cRequestedSymbols`  
 [in] Número de símbolos locales solicitado.  
  
 `pcFetchedSymbols`  
 [out] Puntero al número de símbolos recuperados por el método.  
  
 `pcFetchedSymbols`  
 enuncia Puntero a una matriz [ICorDebugVariableSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md) que contiene los símbolos locales del método.  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
> Este método solo está disponible con .NET Native.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también

- [GetMethodParameterSymbols (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodparametersymbols-method.md)
- [ICorDebugSymbolProvider (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
