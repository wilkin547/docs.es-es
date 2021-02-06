---
description: 'Más información sobre: ICorDebugSymbolProvider:: Getmergedassemblyrecords ((método)'
title: ICorDebugSymbolProvider::GetMergedAssemblyRecords (método)
ms.date: 03/30/2017
ms.assetid: cc4c510d-550d-4941-af34-81987caf3425
ms.openlocfilehash: f12bb3a49d7b49f9f8916c9d04417340502d44ba
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99659886"
---
# <a name="icordebugsymbolprovidergetmergedassemblyrecords-method"></a>ICorDebugSymbolProvider::GetMergedAssemblyRecords (método)

Obtiene los registros de símbolos para todos los ensamblados combinados.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetMergedAssemblyRecords(  
   [in] ULONG32 cRequestedRecords,  
   [out] ULONG32 *pcFetchedRecords,  
   [out, size_is(cRequestedRecords), length_is(*pcFetchedRecords)] ICorDebugMergedAssemblyRecord *pRecords[]  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `cRequestedRecords`  
 [in] Número de registros de símbolos solicitado.  
  
 `pcFetchedRecords`  
 [out] Puntero al número de registros de símbolos recuperados por el método.  
  
 `pRecords`  
 Puntero a una matriz de objetos [ICorDebugMergedAssemblyRecord](icordebugmergedassemblyrecord-interface.md) .  
  
## <a name="remarks"></a>Observaciones  
  
> [!NOTE]
> Este método solo está disponible con .NET Native.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaz ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
