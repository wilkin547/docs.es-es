---
title: ICorDebugFunction3 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugFunction3
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: b22717b9-ead5-4eea-887e-789b52d613dc
topic_type:
- apiref
ms.openlocfilehash: 17eda7470e5f2e4b41d1f2ed164843eaeeedea93
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695875"
---
# <a name="icordebugfunction3-interface"></a>ICorDebugFunction3 (Interfaz)

[Compatible con .NET Framework 4.5.2 y versiones posteriores]  
  
 Extiende la interfaz ICorDebugFunction de manera lógica para proporcionar acceso al código desde una solicitud ReJIT.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetActiveReJitRequestILCode (método)](icordebugfunction3-getactiverejitrequestilcode-method.md)|Obtiene un puntero de interfaz a un [ICorDebugILCode](icordebugilcode-interface.md) que contiene el Il de una solicitud ReJIT activa.|  
  
## <a name="remarks"></a>Observaciones  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaces para depuración](debugging-interfaces.md)
- [Depuración](index.md)
- [ReJIT: Guía de How-To](/archive/blogs/davbr/rejit-a-how-to-guide)
