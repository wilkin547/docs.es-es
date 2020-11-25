---
title: ICorDebugSymbolProvider::GetAssemblyImageBytes (método)
ms.date: 03/30/2017
ms.assetid: 3db215aa-e180-4f70-8d23-6d5a0ffbc8e5
ms.openlocfilehash: b52614065d599edf8e556524c33e8bc50b4924ef
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709185"
---
# <a name="icordebugsymbolprovidergetassemblyimagebytes-method"></a>ICorDebugSymbolProvider::GetAssemblyImageBytes (método)

Lee datos de un ensamblado combinado a partir de una dirección virtual relativa (RVA) del ensamblado combinado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetAssemblyImageBytes(  
   [in] CORDB_ADDRESS rva,
   [in] ULONG32 length,
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `rva`  
 [in] Dirección virtual relativa (RVA) en un ensamblado combinado.  
  
 `length`  
 Número de bytes para leer desde el ensamblado combinado.  
  
 `ppMemoryBuffer`  
 Puntero a la dirección de un objeto [ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md) que contiene información sobre el búfer de memoria con metadatos de ensamblado combinados.  
  
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
