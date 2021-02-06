---
description: 'Más información sobre: ICorDebugSymbolProvider:: Getmethodlocalsymbols ((método)'
title: ICorDebugSymbolProvider::GetMethodLocalSymbols (método)
ms.date: 03/30/2017
ms.assetid: 8b989e38-e779-49d1-9e90-f1f920484b08
ms.openlocfilehash: f4eaac208d98b25ae4a53acfd977d354c6f6ac1b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99659821"
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
  
## <a name="parameters"></a>Parámetros  

 `nativeRVA`  
 [in] Dirección virtual relativa nativa del método.  
  
 `cRequestedSymbols`  
 [in] Número de símbolos locales solicitado.  
  
 `pcFetchedSymbols`  
 [out] Puntero al número de símbolos recuperados por el método.  
  
 `pcFetchedSymbols`  
 enuncia Puntero a una matriz [ICorDebugVariableSymbol](icordebugvariablesymbol-interface.md) que contiene los símbolos locales del método.  
  
## <a name="remarks"></a>Observaciones  
  
> [!NOTE]
> Este método solo está disponible con .NET Native.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Método GetMethodParameterSymbols](icordebugsymbolprovider-getmethodparametersymbols-method.md)
- [Interfaz ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
