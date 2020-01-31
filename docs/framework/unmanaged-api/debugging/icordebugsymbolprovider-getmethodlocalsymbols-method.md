---
title: ICorDebugSymbolProvider::GetMethodLocalSymbols (método)
ms.date: 03/30/2017
ms.assetid: 8b989e38-e779-49d1-9e90-f1f920484b08
ms.openlocfilehash: 41fc8e94ec8a5c8794674bebb32494bb3806e69d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791603"
---
# <a name="icordebugsymbolprovidergetmethodlocalsymbols-method"></a>ICorDebugSymbolProvider::GetMethodLocalSymbols (método)
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
  
## <a name="parameters"></a>Parameters  
 `nativeRVA`  
 [in] Dirección virtual relativa nativa del método.  
  
 `cRequestedSymbols`  
 [in] Número de símbolos locales solicitado.  
  
 `pcFetchedSymbols`  
 [out] Puntero al número de símbolos recuperados por el método.  
  
 `pcFetchedSymbols`  
 enuncia Puntero a una matriz [ICorDebugVariableSymbol](icordebugvariablesymbol-interface.md) que contiene los símbolos locales del método.  
  
## <a name="remarks"></a>Notas  
  
> [!NOTE]
> Este método solo está disponible con .NET Native.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también

- [GetMethodParameterSymbols (método)](icordebugsymbolprovider-getmethodparametersymbols-method.md)
- [ICorDebugSymbolProvider (interfaz)](icordebugsymbolprovider-interface.md)
- [Interfaces de depuración](debugging-interfaces.md)
