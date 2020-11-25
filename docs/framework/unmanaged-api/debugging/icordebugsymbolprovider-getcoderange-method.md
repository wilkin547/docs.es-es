---
title: ICorDebugSymbolProvider::GetCodeRange (método)
ms.date: 03/30/2017
ms.assetid: 49a2451f-d250-4e73-aa96-9ff49d9f11c6
ms.openlocfilehash: f61a98dbd5a65207a46e033d54f9d5f60adac201
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709133"
---
# <a name="icordebugsymbolprovidergetcoderange-method"></a>ICorDebugSymbolProvider::GetCodeRange (método)

Obtiene el tamaño y la dirección de inicio del método a partir de una dirección virtual relativa (RVA) en un método.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetCodeRange(  
   [in] ULONG32 codeRva,
   [out] ULONG32* pCodeStartAddress,
   [out] ULONG32* pCodeSize  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `codeRva`  
 [in] Dirección virtual relativa (RVA) en un método.  
  
 `pCodeStartAddress`  
 [out] Puntero a la dirección de inicio del método.  
  
 `pCodeSize`  
 Puntero al tamaño del código del método (número de bytes del código del método).  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
> Este método solo está disponible con .NET Native.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaz ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
