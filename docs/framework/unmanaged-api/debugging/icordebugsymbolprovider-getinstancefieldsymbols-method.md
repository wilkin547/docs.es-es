---
description: 'Más información sobre: ICorDebugSymbolProvider:: Getinstancefieldsymbols ((método)'
title: ICorDebugSymbolProvider::GetInstanceFieldSymbols (método)
ms.date: 03/30/2017
ms.assetid: a29b9233-ee67-4b53-b8bc-c00b281e7edb
ms.openlocfilehash: 379d943743bb1fe21edbcca2265b4d8613d4f4b8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99659899"
---
# <a name="icordebugsymbolprovidergetinstancefieldsymbols-method"></a>ICorDebugSymbolProvider::GetInstanceFieldSymbols (método)

Obtiene los símbolos de campo de instancia que corresponden a una firma Typespec.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetInstanceFieldSymbols(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugInstanceFieldSymbol *pSymbols[]  
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
 enuncia Puntero a una matriz [ICorDebugStaticFieldSymbol](icordebugstaticfieldsymbol-interface.md) que contiene los símbolos de campo de instancia solicitados.  
  
## <a name="remarks"></a>Observaciones  
  
> [!NOTE]
> Este método solo está disponible con .NET Native.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Método GetStaticFieldSymbols](icordebugsymbolprovider-getstaticfieldsymbols-method.md)
- [Interfaz ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
