---
title: Interfaz ICorDebugComObjectValue
ms.date: 03/30/2017
api_name:
- ICorDebugComObjectValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugComObjectValue
helpviewer_keywords:
- ICorDebugComObjectValue interface [.NET Framework debugging]
ms.assetid: 505a7f6c-d92b-42b4-b539-433f5102ea9b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4db005e1de043e60ffe958de732a5280fcccbea7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54529952"
---
# <a name="icordebugcomobjectvalue-interface"></a>Interfaz ICorDebugComObjectValue
Proporciona métodos para recuperar la información asociada a un contenedor invocable en tiempo de ejecución (RCW).  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetCachedInterfacePointers (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-getcachedinterfacepointers-method.md)|Obtiene los punteros de interfaz sin formato almacenados en caché en el RCW actual.|  
|[GetCachedInterfaceTypes (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-getcachedinterfacetypes-method.md)|Proporciona un enumerador para los tipos de interfaz que el objeto actual se ha convertido en grafía o usar como.|  
  
## <a name="remarks"></a>Comentarios  
 Para comprobar si una instancia de una interfaz "ICorDebugValue" representa un contenedor RCW, llama un depurador `QueryInterface` en "ICorDebugValue" con `IID_ICorDebugComObjectValue`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
