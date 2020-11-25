---
title: Interfaz ICorDebugGenericValue
ms.date: 03/30/2017
api_name:
- ICorDebugGenericValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGenericValue
helpviewer_keywords:
- ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: bc14f408-b359-4c8c-ade2-888ccdf7261b
topic_type:
- apiref
ms.openlocfilehash: cfa0950ca2ef4e969258c147b762fa95e52a82e5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705827"
---
# <a name="icordebuggenericvalue-interface"></a>Interfaz ICorDebugGenericValue

Una subclase de "ICorDebugValue" que se aplica a todos los valores. Esta interfaz proporciona métodos Get y Set para el valor.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetValue (Método)](icordebuggenericvalue-getvalue-method.md)|Copia el valor en el búfer especificado.|  
|[Método SetValue](icordebuggenericvalue-setvalue-method.md)|Copia un nuevo valor del búfer especificado.|  
  
## <a name="remarks"></a>Comentarios  

 `ICorDebugGenericValue` es una subinterfaz porque no es remota.  
  
 En el caso de los tipos de referencia, el valor es la referencia en lugar del contenido de la referencia.  
  
 Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaces para depuración](debugging-interfaces.md)
