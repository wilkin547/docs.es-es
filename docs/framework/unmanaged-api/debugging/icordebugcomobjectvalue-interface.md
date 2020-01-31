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
ms.openlocfilehash: ed5b39ed4b2a14c071bf23fb04efbad6834e8a9d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783972"
---
# <a name="icordebugcomobjectvalue-interface"></a>Interfaz ICorDebugComObjectValue
Proporciona métodos para recuperar información asociada a un contenedor RCW (Runtime Callable wrapper).  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetCachedInterfacePointers (método)](icordebugcomobjectvalue-getcachedinterfacepointers-method.md)|Obtiene los punteros de interfaz sin formato almacenados en memoria caché en el RCW actual.|  
|[GetCachedInterfaceTypes (método)](icordebugcomobjectvalue-getcachedinterfacetypes-method.md)|Proporciona un enumerador para los tipos de interfaz en los que el objeto actual se ha usado como mayúsculas o minúsculas como.|  
  
## <a name="remarks"></a>Notas  
 Para comprobar si una instancia de una interfaz "ICorDebugValue" representa un RCW, un depurador llama a `QueryInterface` de "ICorDebugValue" con `IID_ICorDebugComObjectValue`.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](debugging-interfaces.md)
- [Depuración](index.md)
