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
ms.openlocfilehash: 40df1416e68c86efe6d404119cb37277fe21ac56
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677549"
---
# <a name="icordebugcomobjectvalue-interface"></a>Interfaz ICorDebugComObjectValue

Proporciona métodos para recuperar información asociada a un contenedor RCW (Runtime Callable wrapper).  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método GetCachedInterfacePointers](icordebugcomobjectvalue-getcachedinterfacepointers-method.md)|Obtiene los punteros de interfaz sin formato almacenados en memoria caché en el RCW actual.|  
|[Método GetCachedInterfaceTypes](icordebugcomobjectvalue-getcachedinterfacetypes-method.md)|Proporciona un enumerador para los tipos de interfaz en los que el objeto actual se ha usado como mayúsculas o minúsculas como.|  
  
## <a name="remarks"></a>Comentarios  

 Para comprobar si una instancia de una interfaz "ICorDebugValue" representa un RCW, un depurador llama a `QueryInterface` "ICorDebugValue" con `IID_ICorDebugComObjectValue` .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaces para depuración](debugging-interfaces.md)
- [Depuración](index.md)
